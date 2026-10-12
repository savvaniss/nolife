# 06. Architecture, networking and persistence (the Grid)

Design document 06 of 10. Owner: Grid team (10 engineers at L). Written 2026-10-09 against `00-design-spine.md`. Canonical names follow spine section C and numbers follow section D. Figures this document adds are marked as design defaults. Arithmetic that is ours and not a source's is marked "our arithmetic".

## Summary

This document specifies the Grid: how nolife simulates, replicates, stores and hosts the world. The world has two layers. **Cells** are headless C++/Rust processes, each simulating a 256 m square with Jolt physics at 30 Hz and a sandboxed Luau VM. The SLO is 150 simulated avatars per cell with voice. Above the cells, the **Presence layer** carries pose, look, chat and voice to 1,000 avatars per place through interest-managed relays: 10 Hz within 30 m, 5 Hz beyond, and at most 200 kbps per client. **Event Mode** reserves capacity for 5,000 per place in synchronised instances of about 100. An empty cell hibernates after 10 minutes and wakes within 8 s (p95), which is why a US$69 Cell costs US$14 a month to run. State lives in the authoritative **Entity Store** and the content-addressed **Vault**, with write budgets, hourly snapshots, 30-day rollback and nightly escrow. All-in infrastructure is US$0.025 per CCU-hour across two hosting providers from L.

---

## The two-layer world

### Why two layers

Second Life fixed one simulator process to each 256 m region, and that process sets the region's avatar cap (100 on a Full region), its price and its lag together ([source](https://wiki.secondlife.com/wiki/Land)). The 2020 move to AWS re-hosted the same model unchanged ([source](https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/)). Worlds that hold larger crowds pay in one of three ways:

- **Time.** EVE reached 6,739 pilots in one system by slowing simulation time ([source](https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe)). A world with live voice cannot slow time.
- **Money.** Star Citizen took a decade to reach shards of about 500 players, and its meshing is still "quasi-dynamic" in August 2026 ([source](https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27); [source](https://www.digitaltrends.com/gaming/star-citizen-500-player-server-update/)).
- **Simplification.** ScavLab peaked at 4,144 real players in a stripped-down arena ([source](https://www.mcvuk.com/business-news/tennis-for-two-thousand-the-story-behind-improbables-mass-event-in-scavlab/)).

The platforms that scaled used many instances of 100-200 players; Fortnite runs "up to 100 players per server instance" ([source](https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine)). nolife therefore separates **what you can touch** from **what you can see**:

| Layer | Carries | Unit | Capacity (canonical) | Authority |
|---|---|---|---|---|
| **Cells** (simulation) | Physics, scripts, object state, vehicles, damage parcels | One 256 m cell, one process | 150 simulated avatars with voice; Jolt at 30 Hz | Authoritative for its entities, under a lease from the Entity Store |
| **Presence layer** (replication) | Pose, look descriptor, chat, voice routing, Safety Kit signals | A place (a presence namespace over one or more cells) | 1,000 presence per place; 10 Hz within 30 m, 5 Hz beyond; ≤200 kbps per client, excluding voice | Relays only; no game logic |
| **Event Mode** (reserved) | Both layers, pre-allocated | A place in a reservation window | 5,000 per place in synchronised instances of ~100 | A stage cell plus instance cells |

### Places, cells and namespaces

- A **cell** is the 256 m simulation unit and also a rent product, the Cell. One cell process can host four Plot S, two Plot M or one Cell. A Domain is four contiguous cells.
- A **place** is a named presence namespace: a Holding of one or more cells, a Ward (four cells), or, on a Reach, the viewer's cell plus its eight neighbours. Presence tracks at most 1,000 avatars per place. At the 150 cap that takes at least seven cells, or overflow instances.
- **Hearths** are documents until entered, then run in a shared **Hearth host** process packing many instanced rooms (8 guests, or 25 for Hearth+).
- **Isolation.** Campus and every Night Ward have their own presence namespaces and cell pools. Session tokens carry the Passport's age band and maturity claims, and relays and cells check them on admission. A Campus token cannot reach an open-world relay. A token without the Night Ward check cannot enter an Adult-rated cell. Enforcement is in the network layer, not the client.

### Overflow rule (outside Event Mode)

1. A cell at 150 simulated avatars is **full**. Arrivals join an **overflow instance**: a second process loaded from the same Entity Store partition with a read-only copy of the owner's objects, chosen by friends-follow and Charter affinity. Estates instead apply their seat cap and published queue priority.
2. A place at 1,000 presence without a reservation opens a second presence namespace, and the owner is shown how to reserve Event Mode.
3. Two instances that are both below 20% of capacity for 5 minutes merge (design default; the policy is in doc 02).

---

## Cells: headless simulation, Jolt and Luau

### Process model

A cell is one container with a static C++/Rust binary and no Unreal code; Unreal renders only, in Lantern. This keeps Epic's server terms and Iris off the critical path; Iris is still opt-in and Experimental in the UE 5.7 docs ([source](https://www.strayspark.studio/blog/iris-replication-unreal-engine-opt-in-2026)).

- **Standard profile:** 2 vCPU and 4 GB, the basis of the Cell cost (D.3).
- **Hub profile:** 4 vCPU and 8 GB. The scheduler assigns it by calendar to Ward Stage and Market cells at weekly peak, Landing halls, Event Mode cells, and any cell that averaged more than 60 avatars in the previous hour.

Threads: simulation (Jolt, entity logic), scripts (Luau and LSL Runtime) and I/O.

**Tick (33.3 ms, 30 Hz), design defaults:**

| Stage | Simulation thread (ms) | Script thread (ms) |
|---|---|---|
| Ingest inputs and cross-cell messages | 2.0 | n/a |
| Jolt step (fixed Δt = 1/30 s) | 12.0 | n/a |
| Entity logic: sits, attachments, damage, parcels | 4.0 | n/a |
| Luau and LSL Runtime slices | n/a | 26.0 (pooled) |
| Persist events and emit deltas | 5.0 | 2.0 |
| Headroom | 10.3 | 5.3 |

The R1 SLO is p95 simulation-thread time ≤33.3 ms at monthly peak with 150 avatars and voice.

**Prediction.** Clients predict their own avatar, held objects and driven vehicles with the same Jolt build and timestep (a WebAssembly build in Ember), then reconcile against cell snapshots. The server corrects every misprediction, so cross-platform bit-exactness is not required.

### Boundaries and crashes

- Each cell keeps read-only **ghosts** of entities within 16 m of a shared border.
- Authority is a **lease** with an epoch number in the Entity Store. When an entity's centre crosses a border, the owning cell hands off its state, script VM image and epoch + 1; the receiver takes it only if the compare-and-swap succeeds, so no entity ever has two owners. A seated avatar and its vehicle cross as one handoff.
- **Crash equals reconnect.** A cell renews its lease every second. After three missed renewals the scheduler restarts it elsewhere from the last checkpoint plus the event-log tail, on the wake path. Clients stay on their presence relay, so avatars stay visible and chat and voice continue; only physics and scripts pause. Recovery target: **8 s p95**.

### Luau, the LSL Runtime and budgets (R5)

Scripts run in a Luau VM, the language Roblox runs at scale and Linden's SLua forks ([source](https://wiki.secondlife.com/wiki/Lua_Alpha)). LSL is uploaded unchanged and compiled transparently to Luau against the `ll` library, with OpenSim's BSD engine as the reference; unsupported calls fail loudly (B.4 item 14). Both share one scheduler and one set of budgets.

| Resource (per cell, design defaults) | Land scripts | Avatar attachments | Rule |
|---|---|---|---|
| CPU per tick | 18 ms, split by each Holding's Scene Weight share (minimum 0.5 ms) | 0.05 ms × avatars present | Work-conserving: idle share can be borrowed |
| Memory | 64 MB per Cell-equivalent, pro rata; 64 KB per LSL-origin script | 2 MB per avatar | Hard limit |
| Network (HTTP, email, cross-cell) | 30 requests/min per Holding + 1 per 1,000 Weight | 5 requests/min per avatar | Token bucket |

**Worst-offender throttle.** When CPU demand exceeds the pool, the scheduler ranks owners by usage ÷ share and cuts the highest back to its share first, until the pool fits. Owners within their share are never slowed, and Workshop shows the owner which script was throttled. This reverses Second Life's "scripts starve first". The R5 test: a runaway script in a 150-avatar cell degrades only its owner, and script-caused tick overruns stay under 1% of cell-hours.

---

## Presence, interest management and voice

### Relays and interest

Presence relays are stateless fan-out processes of up to 500 client connections each (design default). Cells publish authoritative poses to them at 30 Hz, and each relay ranks avatars per viewer:

```
priority(a, viewer) = w_dist · f(distance)        // 1.0 inside 30 m, falling to 0.1 at 256 m
                    + w_view · inFrustum(a)
                    + w_social · (friend | sameCharter | speaking | Post on duty)
                    // muted or blocked avatars are dropped entirely
rate(a) = 10 Hz if distance ≤ 30 m and rank < 40
        = 5 Hz  if in view, or rank < 400
        = 1 Hz  otherwise (keep-alive for impostor placement)
```

### Bandwidth budget at 1,000 presence (≤200 kbps, excluding voice)

| Stream | Encoding | Avatars | Rate | kbps |
|---|---|---|---|---|
| Near ring (≤30 m) | 24 B: quantised position, smallest-three rotation, velocity, animation blend, face deltas | 40 | 10 Hz | 76.8 |
| Far ring, in view | 5 B: 0.25 m position in a per-client slot table, heading, animation class | 360 | 5 Hz | 72.0 |
| Far ring, out of view | 5 B | 600 | 1 Hz | 24.0 |
| Object deltas, chat, look descriptors, Safety Kit events | Delta-coded | n/a | Event-driven | 19.2 |
| Transport overhead (~20 packets/s) | n/a | n/a | n/a | 8.0 |
| **Total** | | **1,000** | | **200.0** |

Our arithmetic. Spare budget lifts far-ring rates first. The 40-avatar near ring matches Lite; for Reference (100 full avatars) relays widen it to 100 and drop out-of-view avatars to 0.5 Hz, within the same cap. Impostors start at 30 m (D.4).

**Look descriptor (about 64 B, sent on change):** Bakes-on-Mesh atlas hash, silhouette class, four-colour palette, role badge and Keeper flag. The client fetches the impostor from the Vault CDN by hash. This is how impostors keep colour, silhouette and badge, and how a Keeper's badge survives at distance.

**Transport.** QUIC on Lantern, WebTransport on Ember, WebSocket where UDP is blocked. One connection carries three streams: presence (unreliable, sequenced), cell (reliable per entity) and control. Assets never use these streams.

### Voice

Voice sits behind one interface so the provider can be swapped (R20):

```
interface VoiceProvider {
  join(channel, token: ScopedToken): Session      // proximity, instance, stage or private
  setListenerPose(session, pos, facing)            // 10 Hz from the client
  setGate(session, speaker, allowed)               // Trust and Safety Kit gating, server-side
  premixFeed(channel): StreamUrl                   // Event Mode stage mix
  captions(channel): TextStream                    // speech-to-text in the same path (R27)
}
```

The implementations at L are 4Players ODIN, at €0.29 per peak concurrent user per month ([source](https://odin.4players.io/pricing)); the Discord Social SDK, open to all developers with voice since August 2025 ([source](https://alternativeto.net/news/2025/8/discord-social-sdk-launches-to-all-devs-with-in-game-voice-chat-and-cross-platform-play/)); and a self-hosted WebRTC SFU. Proximity channels are scoped to the cell, so voice scales with cells. Relays hold the Safety Kit's **60-second evidence buffer** in memory; it is written to storage only when a report is filed.

---

## Event Mode and instances

### What Event Mode is

Event Mode is a **capacity reservation**, not a different engine. An owner or Charter books a window for up to 5,000. The scheduler pre-allocates hub-profile cells and relays and warms them 5 minutes before the start.

**Pricing (canonical).** Reserved avatar-hours above the 1,000 presence every place already has cost US$0.004 each, waived for Civic Calendar events. Attendee traffic is never charged. *Example:* a non-Calendar concert reserving 3,000 for 2 hours pays (3,000 − 1,000) × 2 × US$0.004 = **US$16**; a Friday Open Stage slot of the same size pays nothing.

### Topology

```
        ┌──────────── Stage cell (hub profile, authoritative) ────────────┐
        │ performers and crew (≤20), stage objects, show-control scripts, │
        │ tips → Ledger API, pre-mixed audio → premixFeed                  │
        └───────────────┬──────── show stream (one-way, 30 Hz) ───────────┘
     ┌──────────────────┼──────────────────┬──────────── … ────────┐
 Instance 1 (~100)  Instance 2 (~100)  Instance 3 (~100)       Instance N
 full simulation of the audience floor; stage objects are read-only proxies
     └──────── presence: far-crowd field fed from all other instances ──────┘
```

- **Instances.** N = ⌈expected peak ÷ 100⌉ cell processes, each running a copy of the audience floor with full physics, dancing, sitting and proximity voice.
- **Synchronisation.** The stage broadcasts entity deltas, show cues and the audio clock. Instances never write stage state; tips and requests go to the stage as rate-limited messages, and money moves through the Ledger.
- **The far crowd.** The venue declares *crowd zones* (terraces, the bowl). Presence maps attendees from other instances into them by a deterministic seat map, as impostors, up to the 1,000-per-client limit; beyond that, generic impostors are scaled to the published attendance. A viewer sees their own 100 up close and up to 900 more as a real crowd.
- **Audio and placement.** The stage is mixed once for everyone. Proximity voice works only within an instance, within 10 m, gated by Trust. Friends-follow, Charter affinity and language tag decide placement. Cross-instance chat is one slow-mode channel moderated by Hosts and Wardens on duty.

**Validation.** Alpha events run to 1,000; 2,000 is validated by Sep 2029, before the first Ephemeral Ward; 5,000 arrives at L+23. Nothing above 5,000 is promised: Improbable's "over 10,000" is a 2022 capability claim ([source](https://improbable.io/blog/an-improbable-story-accelerating-into-the-metaverse-and-what-comes-next)).

---

## Hibernation and elastic capacity

### The rule

**A cell with no avatars sleeps after 10 minutes and wakes within 8 s (p95).** The economics depend on this rule. A 2 vCPU cell awake all month costs 730 × 2 × US$0.069 = **US$100.74** at Edgegap's rate ([source](https://edgegap.com/pricing)); the Cell's US$10 compute basis assumes about 70 awake hours (70 × 2 × US$0.069 = US$9.66, our arithmetic). Kitely is the precedent: it suspends idle regions and reloads them on teleport, trading a few seconds of load for cost ([source](https://www.hypergridbusiness.com/2015/06/kitely-cuts-prices-60-for-large-regions)).

### State machine

```
            teleport intent / neighbour approach / alarm / owner edit / reservation
   ┌────────┐ ───────────────────────────────────────────────▶ ┌─────────┐
   │ ASLEEP │  (no process; state in Entity Store, assets in Vault)│ WAKING  │ ≤8 s p95
   └────────┘ ◀──── FLUSHING ◀──── IDLE (10:00 countdown) ◀──── │  AWAKE  │◀┘
                  checkpoint +       any arrival cancels the countdown
                  snapshot, ≤5 s
   PINNED: reservations, Ward hubs and Landing halls in scheduled hours, and Civic
   Calendar events from 5 minutes before the start stay AWAKE regardless of occupancy
```

**What wakes a cell:**
1. **Teleport intent.** Opening a place card, accepting an offer or following a Call Board link starts the wake, overlapping the client's transition.
2. **Neighbour approach.** An avatar comes within 64 m of the border.
3. **Script alarms.** Up to 24 a day per Holding, each up to 30 s of simulation (design default). At most 6 awake hours a month, inside the 70-hour basis.
4. **Owner edits** from Workshop, and **inbound HTTP** to a script URL still pending after 2 s.

**What does not:** vendor purchases (an in-world vendor is a Bazaar listing; delivery goes Bazaar → Ledger → inventory), and Keepalive life-support, which runs as a platform service outside cells (R24).

**Script semantics.** Timers freeze while asleep. On wake every script receives `on_wake(elapsed_seconds)` (mapped to `changed(CHANGED_REGION_START)` plus timer catch-up in the LSL Runtime), so meters compute elapsed time rather than loop through it.

### Wake budget (p95 ≤ 8.0 s)

| Step | s |
|---|---|
| Take a warm process on the nearest provider | 0.5 |
| Fetch checkpoint and event-log tail | 2.0 |
| Resolve asset manifests (collision and scripts only) | 1.5 |
| Build the Jolt world | 1.5 |
| Restore Luau VM images, fire `on_wake` | 1.5 |
| Register with presence, hand the client over | 1.0 |
| **Total** | **8.0** |

### Elastic capacity

The **Grid Scheduler** is our own provider-neutral control plane.
- **Warm pools:** idle generic processes equal to 5% of awake cells, minimum 20 per region (design default), so no wake waits for a container start.
- **Packing:** asleep cells cost nothing; awake cells are packed by profile. Edgegap's fractional vCPUs ([source](https://edgegap.com/pricing)) are an upside this document does not count.
- **Calendar-driven provisioning:** Civic Calendar and Event Mode bookings are known in advance, so base load is bought as committed capacity, at 20-30% discounts on Edgegap ([source](https://edgegap.com/blog/announcement-offering-changes-for-2025)).

### Example flow: visiting a sleeping Charter Hall

1. 21:04: Ana clicks "Visit" on a Hall card from the Call Board. Ember shows the arrival transition, and cell `hall-7f3a` goes to WAKING.
2. +0.4 s: a warm process on provider B takes lease epoch 412. +2.3 s: the 21:00 snapshot plus 212 log events are loaded. +5.6 s: Jolt and the VMs are restored, and the rental meter gets `on_wake(3,912)`.
3. +6.4 s: the cell registers with its relay and Ana appears. She leaves at 21:31; the cell goes IDLE and sleeps at 21:41. The visit cost the Hall nothing: rent covers bytes kept, never traffic.

---

## Entity Store, Vault and snapshots

### Entity Store

The Entity Store holds **documents plus an append-only event log**, partitioned by Holding, Ward, Hearth and Campus site. It uses open-source, self-hostable components only, so the escrowed copy can actually be run.

```
interface EntityStore {
  acquireLease(partition, cellId): Epoch                  // compare-and-swap
  append(partition, epoch, events[], durability): Offset  // DURABLE: acked after quorum
  checkpoint(partition, epoch, docDiff, vmImages): SnapshotId
  read(partition, atSnapshot?): Documents + logTail
  rollback(partition, toSnapshot, requester): RollbackPlan
}
```

| Persistence class | Examples | Write path | Loss bound |
|---|---|---|---|
| Durable | Rez, derez, owner edits, parcel settings, script key-value writes, Charter role changes | Synchronous append, acked after quorum across three zones | 0 after the ack |
| Checkpointed | Dynamic-object positions, Luau VM state | Every 60 s and on FLUSHING | ≤60 s |
| Ephemeral | Poses, particles, local chat, voice | Never persisted (evidence buffer only on report) | n/a |

Coin is not in the Entity Store. It lives in the Ledger, a strongly consistent double-entry system that cells reach only through an idempotent API, so a cell crash cannot create or destroy money. Inventory has its own service (below).

### Write budgets (canonical: 60 + 10 × avatars writes per minute per cell)

The precedent is Roblox's DataStore budget of 60 + 10 × players requests per minute per server, with a 30-request queue per key ([source](https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits)). Budgets cover script-initiated durable writes:
- the base 60 is split among the cell's Holdings by Scene Weight share, minimum 5 each;
- of each avatar's 10, 5 go to the Holding where it stands and 5 to its own attachment store;
- each allocation is a token bucket one minute deep, so bursts pass.

Over-budget writes to the same key coalesce within 1 s, then queue (30 per key), then return an error event to the script; nothing is dropped silently. A 150-avatar cell may make 1,560 writes a minute. Workshop edits and inventory operations are exempt.

### Inventory and the loss target

Inventory is a versioned document per Passport. Every mutation (give, buy, rez, derez, delete to a 30-day Trash, NAR import) is a single-transaction **move between containers** with an idempotency key, so retries cannot duplicate or lose an item. A nightly reconciler checks that every item sits in exactly one container and every in-world object points to a live item.

**Target (canonical): at most 1 loss per 10 million operations, published monthly.** A loss is any item gone without a logged cause, any acknowledged mutation that was not made durable, or any referenced asset that cannot be fetched. Losses count even if restored later; restorations are published beside them. At Reference scale that allows about 20 a month on ~200M operations (our arithmetic).

### Vault

- Content-addressed, S3-compatible storage behind a CDN; every blob is named by its SHA-256 hash.
- An asset is a signed **manifest** listing the source and every Foundry derivative by hash (tier bakes, the four-level LOD chain, impostor, BC7/ASTC/ETC2/KTX2 textures, collision), plus the provenance envelope, permission bits including Export, Fidelity Rank and maturity tag.
- Blobs are reference-counted and never deleted while any manifest, item, snapshot or escrow copy refers to them; unreferenced blobs are kept 30 days.
- **NAR restore by hash anywhere.** A thin NAR carries documents and manifests; a full NAR also embeds the blobs. Either restores on any host by resolving the same hashes. OSgrid's 2025 wipe and 2026 asset-metadata outage show what a non-addressable store costs a community ([source](https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff); [source](https://www.hypergridbusiness.com/?p=79686)).

### Snapshots and rollback (canonical: hourly, 30 days)

- Every awake partition snapshots hourly (document diff plus log offset) and on FLUSHING; asleep partitions need none. Retention is 30 days.
- A Holding owner, or the Charter role with land rights, can restore to any snapshot in that window: terrain, parcel settings and the owner's objects. Rollback **never** deletes others' property; their later-rezzed objects return to their inventories with a notice. It never touches inventory or the Ledger, so purchases cannot be undone through land.
- A lapsed Holding is frozen 90 days, then stored as a NAR in the owner's inventory, restorable indefinitely (D.6).

| Failure | RPO | RTO |
|---|---|---|
| Cell, host or zone loss | Durable 0; checkpointed ≤60 s | ≤8 s p95 per cell |
| One provider's compute | Same | Presence and all Holdings within 4 h on the other provider, Ward hubs first (design default) |
| Primary data provider | ≤5 min via log shipping; ≤24 h worst case via nightly escrow | 24 h, rehearsed annually |

---

## Multi-vendor deployment, escrow and the Homestead Kit

### One manifest, two providers live from L

Vendor survival now outranks price as a risk: Hathora's 2026 acquisition moved its game customers off within weeks ([source](https://gamesbeat.com/?p=318174)), leaving Stormgate without online play ([source](https://www.techspot.com/news/111969-stormgate-servers-go-dark-following-ai-focused-hosting.html)), and Firestorm Zero closed when its streaming provider forced a migration ([source](https://modemworld.me/2025/06/27/)).

Every Grid component therefore ships under **one deployment manifest** that runs unchanged on Edgegap (US$0.069 per vCPU-hour), Amazon GameLift Servers (c6i.large at US$0.109 an hour) ([source](https://aws.amazon.com/gamelift/servers/pricing/)), Nitrado GameFabric, or bare metal.

| Rule | Value |
|---|---|
| Providers live at L | 2 (canonical) |
| Steady-state split | ~70/30 (design default), so the secondary is never cold |
| Survivability | Either provider carries 60% of weekly peak, hubs and Landing halls first |
| Failover demo at L | A live Ward with residents present moves between providers, in public |
| Annual drill | 25% of awake cells move between providers; results published |
| Data | Primary Vault and Entity Store at one provider; log shipping and nightly escrow to the other |

### Escrow

- **Code.** An independent agent holds source, build pipeline, images, manifests and runbooks for cells, relays, the Scheduler, Entity Store tooling, the Vault, the Foundry, the LSL Runtime, the protocol reference and Ledger export tools, refreshed every release. It is released under Apache-2.0 **only** when the 12-month shutdown notice fires (B.4 item 1); an open server before then leaks rent (B.3).
- **Data.** Nightly, the Entity Store's logical dump and the day's Vault blobs replicate to the second provider, and the agent signs an updated escrow index.
- **Annual restore test (R20).** A random 1% of Holdings are restored from escrow alone on the secondary provider, every hash is verified, and the result is published. A failed restore counts as an inventory-loss incident.

### The Homestead Kit (L+12, partners only, US$29 per cell-month)

The only self-hosting: the same cell container plus a **Kit agent**, on partner hardware (OpenSim grid operators, institutions, long-running estates).

| Constraint (canonical) | Enforcement |
|---|---|
| General or Moderate only | Certificates carry a maturity ceiling; Adult tokens refused; Campus never hosted on a Kit |
| Assets only through the Foundry | No direct blob ingest; uploads return as Vault manifests |
| Central Passport and Ledger | Sessions issued centrally; Coin only through the Ledger API |
| Platform takedown | Signed commands executed within 1 hour, or the certificate is revoked and the Vault, Passport and relays refuse the cell |

A Kit partition's primary store may run on partner hardware, but its event log streams continuously to the central store, so escrow, NAR export and takedown work as on platform cells. Kit cells use central relays, so the Safety Kit and Census counting are unchanged. The partner supplies compute, so of a Cell's US$14 basis only the US$4 of storage, escrow and operations applies; the US$29 covers that plus presence, CDN and Foundry. Federation, Open shards and Crossing stay rejected (B.3).

---

## Protocol and third-party clients

The protocol is published in full at L as a versioned specification with a test harness. Third-party clients are blessed from L; certification follows at L+24.

| Surface | Transport | Contents |
|---|---|---|
| Session | HTTPS (OAuth-style) | Passport login; **scoped tokens** with age band, Night Ward check, Campus flag and Trust rank, which decide reachable relays, cells and Ledger operations |
| Presence | QUIC/WebTransport, unreliable | Poses, look descriptors, chat, Safety Kit events |
| Cell | QUIC/WebTransport, reliable per entity | Object state, physics snapshots, script UI, sit and attach |
| Assets | HTTPS from the Vault CDN, by hash | Tier derivatives only |
| Ledger | HTTPS hosted payment sheet | Purchases, tips, transfers |
| Voice | `VoiceProvider` | Provider media; tokens from the session |
| Text profile | Presence subset at 1 Hz plus object list | Reader: chat, IM, inventory, teleport, object list, voiced GPS (R27) |

**Rules:**
- **Derivatives only.** Clients never receive source uploads; source export follows the Export bit. Any client can replay what it receives, as CopyBot showed in 2006, so the defence is Foundry fingerprinting against the catalogue, not DRM.
- **Required behaviour.** Clients must honour Keeper badges, maturity gating, the default-on personal boundary and mute, block and vanish. Uncertified clients reach the Ledger only through the hosted payment sheet.
- **Versions.** Each protocol version is supported at least 24 months after its successor ships (design default, mirroring C.3). Breaking changes go through the World Charter's public change review, which the Assembly can demand.
- **Certification at L+24** (conformance suite, security review, directory listing) unlocks direct Ledger calls and building tools. The first-party client must still match third-party clients on first-session completion, annually (R4); Firestorm, not Linden's viewer, carried Second Life's users ([source](https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/)).

---

## Cost per CCU-hour

### The canonical breakdown: US$0.025, at about 10 avatars per awake cell

| Line | US$/CCU-hour | Derivation (our arithmetic on cited rates) |
|---|---|---|
| Compute | 0.012 | A 2 vCPU cell is US$0.11-0.14 an hour at US$0.055-0.069 per vCPU-hour ([source](https://aws.amazon.com/gamelift/servers/pricing/); [source](https://edgegap.com/pricing)), ~US$0.10 committed: US$0.010 per avatar. Relays, warm pools, Scheduler and Hearth hosts add US$0.002 |
| Egress and CDN | 0.007 | ~120 kbps real-time average (54 MB an hour) plus ~30 MB of asset streaming, at US$0.10 per GB list less committed CDN pricing |
| Voice | 0.002 | ODIN's €0.29 per peak user-month is ~€0.0004 per CCU-hour times the peak-to-average ratio (~€0.001 at 2.5×); the line also carries captions and the SFU fallback |
| Storage, escrow and backup | 0.004 | Vault and Entity Store at ~US$0.023 per GB-month, doubled for the second provider, plus snapshots and restore tests |
| **All-in** | **0.025** | |

Outside this line: trust and safety (US$1.50 per DAU-month, floor US$1.5M a year); the Foundry (US$0.01 per asset); Keeper cognition (≤10% of infrastructure plus T&S); and Stream (US$1.75 an hour, capped at 5% of infrastructure, about 25,700 hours a year at the Floor, our arithmetic).

### Annual infrastructure at the D.8 scales

Average CCU is 4% of MAU, so cost = CCU × 8,760 × US$0.025:

| Scale | MAU | Average CCU | US$M a year |
|---|---|---|---|
| Floor | 100K | 4,000 | 0.9 |
| Break-even | 350K | 14,000 | 3.1 |
| Reference | 600K | 24,000 | 5.3 |

This reproduces D.8. Roblox's infrastructure plus T&S line was US$1,153.5M in 2025 ([source](https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm)): servers are not what kills a social world.

### The per-Cell cost basis (printed on the Fee Page)

**Cell, US$69 a month; basis US$14:** compute US$10 (~70 awake hours on 2 vCPU), storage and escrow US$2 (30 GB at two providers), operations US$2. It holds only because of hibernation. Plot S and Plot M share a cell process, so their compute is a Weight share of the cell's awake hours. Ward hubs, Landing halls and Hearth hosts are platform costs inside the per-CCU line.

### Sensitivity

| Change | Per CCU-hour | At Reference scale |
|---|---|---|
| 5 avatars per awake cell instead of 10 | 0.037 | +US$2.5M a year |
| Average egress at the 200 kbps cap | 0.029 | +US$0.8M |
| Holdings average 140 awake hours | Cell compute basis US$19.3 | Margin −US$9 per Cell-month; price unchanged, basis reprinted |

The first row matters most, so Census publishes avatars per awake cell monthly from alpha.

---

## Scaling plan and SLOs

### Published SLOs

| SLO | Target | Measured as | Published |
|---|---|---|---|
| Cell capacity (R1) | 150 avatars with voice; Jolt at 30 Hz | p95 simulation tick ≤33.3 ms at monthly peak | Quarterly |
| Place presence | 1,000 | Tracked avatars per client in the largest places | Quarterly |
| Presence rates | 10 Hz within 30 m, 5 Hz beyond (in view) | p95 delivered rate | Quarterly |
| Downstream | ≤200 kbps per client, excluding voice | p99 per-client bitrate | Quarterly |
| Event Mode | 2,000 by Sep 2029; 5,000 at L+23 | Validated event and report | At each gate |
| Hibernation | Sleep after 10 min empty; wake ≤8 s p95 | Teleport-to-simulation time | Monthly |
| Crash recovery | ≤8 s p95 | Lease loss to cell live | Monthly |
| Script isolation (R5) | Overruns <1% of cell-hours | Scheduler attribution | Quarterly |
| Inventory loss | ≤1 per 10M operations | As defined above | Monthly |
| Concurrency (R13) | Third parties within 5% | Census API against relay counts, excluding bots and Keepers | Quarterly |

Keepers use capacity but are excluded from every SLO and human count; their share is published beside the bot share (C.7).

### Capacity schedule

| Date | Peak CCU capacity | Providers | Gate to pass first |
|---|---|---|---|
| Sep 2027 | Load test | 1 + staging on a second | 150-avatar cell with voice (D.1) |
| Jan-Sep 2028 (alpha) | 2,000 (design default) | 2 | Founding Charter events; first restore test |
| **L, Oct 2028** | **5,000** | **2** | Escrow and the public failover demo |
| L+12 (design step) | 12,000 | 2 | Homestead Kit live; first annual drill |
| **L+24** | **25,000** | ≥2 | Third-party certification; Event Mode at 5,000 done (L+23) |
| **2032** | **60,000** | ≥2 | Above SL's 2026 peak of 48,802 ([source](https://danielvoyager.wordpress.com/2026/05/11/second-life-daily-user-concurrency-update-10th-may-2026/)) |

Each step requires p95 cell tick within SLO at the previous monthly peak. Nothing takes a global lock; the store scales by partition, presence by relay. The Grid team of 10 at L splits as cells, Jolt and scripts 3; presence and voice 2; Entity Store, inventory and Vault 2; Scheduler, SRE and escrow 2; protocol 1. Hosting, voice and CDN are vendors.

### Alternatives rejected

| Alternative | Why rejected |
|---|---|
| Unreal dedicated servers with Iris | Iris is Experimental ([source](https://www.strayspark.studio/blog/iris-replication-unreal-engine-opt-in-2026)); simulation would sit under Epic's terms, and an engine exit would cost the world, not just Reference |
| Seamless single shard with dynamic meshing | Star Citizen is still "quasi-dynamic" after a decade; Dual Universe's single shard ran and was switched off in August 2025 ([source](https://en.wikipedia.org/wiki/Dual_Universe)) |
| In-memory world state (SpatialOS-style) | The model that died; persistence that survives is a budgeted key-value store |
| Always-on cells | US$101-202 a month per cell against a US$69 price |
| Metered compute above a visitor allowance | Charges places for success (B.3) |
| Federation, Open shards, open server before sunset | Safety, rail and rent leakage (B.3) |
| Sole-source managed backend or per-CCU middleware | The Hathora lesson; per-CCU pricing such as Photon's ([source](https://doc.photonengine.com/photon/v1/pricing)) scales against rent |
| Luau compiled to WASM (open-web) | A second toolchain at L for isolation the Luau VM already gives; may revisit for the Kit |
| Client-authoritative or peer-to-peer simulation | Cheating, asset leakage, unenforceable Safety Kit gating |

---

## Requirements addressed

| R | How |
|---|---|
| R1 | 150-avatar cells with voice, Jolt at 30 Hz, 1,000 presence, Event Mode 2,000 (Sep 2029) and 5,000 (L+23), Sep 2027 gate, quarterly p95 tick |
| R2 | Look descriptors feed impostors; clients get only tier derivatives |
| R4 | Protocol documented at L, third-party clients blessed, certification at L+24, Reader text profile |
| R5 | Per-owner CPU, memory and network pools; worst-offender throttle; LSL Runtime under the same scheduler; <1% overrun test |
| R6 | Hibernation makes rent on bytes viable (US$14 basis); traffic free; Event Mode only above 1,000, at cost, waived for Civic Calendar |
| R12 | Instance overflow and merge; Ward hub pre-warming |
| R13 | Concurrency from relay counts via Census, reproducible within 5%; bot and Keeper shares separated; inventory loss and avatars per awake cell monthly |
| R14 | Ember on WebTransport/WebSocket; Stream capped at 5% of infrastructure |
| R15 | Synchronised ~100 instances, stage authority, pre-mixed audio |
| R18 | Content-addressed Vault; thin and full NAR restore by hash; lapsed Holdings become NARs |
| R20 | One manifest, two providers from L, voice abstraction, code and data escrow, annual restore and drill, failover demo at L, Homestead Kit at L+12 |
| R21 | Scoped tokens; Campus and Night Ward namespaces isolated in the network layer |
| R23 | Server-side Trust gating in `setGate`; evidence buffer in the relay |
| R24 | Keepalive outside cells, so hibernation cannot brick value-bearing objects |
| R25 | Keepers excluded from SLOs and counts; badge in look descriptor |
| R27 | Reader text profile; captions in the voice path |
| R28 | Campus cells platform-hosted and isolated; NAR export for Campus sites |
| R29 | Language tag is a placement and discovery key, never an identity shard |
| R30 | Infrastructure US$0.9M at the Floor; Grid team of 10 |

---

## Open questions

1. **Voice may be over-budgeted.** ODIN implies ~€0.0004-0.001 per CCU-hour against the spine's US$0.002. We keep US$0.002 (captions and the SFU share the line) and review after alpha.
2. **The Event Mode fee recovers reserved compute, not egress.** At ~100 per instance, compute is ~US$0.002-0.003 per avatar-hour, inside the canonical US$0.004; egress (~US$0.007) stays in the general budget, consistent with free traffic. We keep US$0.004 and re-measure at the 2,000 validation.
3. **The 70-awake-hour basis is unmeasured;** nightly venues may run 100-150 hours. Census should publish awake hours by Holding type.
4. **Capacity at L may be tight.** 100K MAU at L+12 means 4,000 average CCU and perhaps 8,000 at peak, so this document adds a 12,000 step at L+12. The peak-to-average ratio is assumed until alpha data exists.
5. **150 with voice on 2 vCPU is unproven;** the Sep 2027 gate may require hub profiles above ~100.
6. **Ember on mid-range phones.** Whether WebGPU can draw a 1,000-presence crowd at the Lite budget is open; some devices still need WebGL2 ([source](https://github.com/gpuweb/gpuweb/wiki/Implementation-Status)).
7. **Rate cards.** Nitrado GameFabric's post-Hathora pricing and Edgegap's 2027 rate are unknown; a rise above 30% breaks the US$0.012 compute line.
8. **Campus on the Homestead Kit** would put minors on partner hardware. This document says no until L+24 at the earliest.
9. **Takedown on partner hardware.** Certificate revocation works technically; counsel must confirm it satisfies the DSA and Online Safety Act before L+12.

---

## Sources

- Second Life regions and caps: https://wiki.secondlife.com/wiki/Land
- Second Life on AWS: https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/
- Second Life peak concurrency 48,802: https://danielvoyager.wordpress.com/2026/05/11/second-life-daily-user-concurrency-update-10th-may-2026/
- Linden SLua (Luau fork): https://wiki.secondlife.com/wiki/Lua_Alpha
- Firestorm Zero closure: https://modemworld.me/2025/06/27/
- Firestorm's share of users: https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/
- EVE M2-XFE record: https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe
- Star Citizen meshing, Aug 2026: https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27
- Star Citizen 500-player shards: https://www.digitaltrends.com/gaming/star-citizen-500-player-server-update/
- ScavLab 4,144 players: https://www.mcvuk.com/business-news/tennis-for-two-thousand-the-story-behind-improbables-mass-event-in-scavlab/
- Improbable 10,000 claim: https://improbable.io/blog/an-improbable-story-accelerating-into-the-metaverse-and-what-comes-next
- Dual Universe shutdown: https://en.wikipedia.org/wiki/Dual_Universe
- Unreal Iris, 100 players per instance: https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine
- Iris still Experimental: https://www.strayspark.studio/blog/iris-replication-unreal-engine-opt-in-2026
- Roblox DataStore budgets: https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits
- Roblox 2025 infrastructure and T&S: https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm
- Edgegap pricing: https://edgegap.com/pricing
- Edgegap 2025 changes and discounts: https://edgegap.com/blog/announcement-offering-changes-for-2025
- GameLift Servers pricing: https://aws.amazon.com/gamelift/servers/pricing/
- Photon pricing: https://doc.photonengine.com/photon/v1/pricing
- ODIN pricing: https://odin.4players.io/pricing
- Discord Social SDK open to all: https://alternativeto.net/news/2025/8/discord-social-sdk-launches-to-all-devs-with-in-game-voice-chat-and-cross-platform-play/
- Hathora acquisition: https://gamesbeat.com/?p=318174
- Stormgate after Hathora: https://www.techspot.com/news/111969-stormgate-servers-go-dark-following-ai-focused-hosting.html
- Kitely idle-region suspension: https://www.hypergridbusiness.com/2015/06/kitely-cuts-prices-60-for-large-regions
- OSgrid wipe and outage: https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff ; https://www.hypergridbusiness.com/?p=79686
- WebGPU implementation status: https://github.com/gpuweb/gpuweb/wiki/Implementation-Status
