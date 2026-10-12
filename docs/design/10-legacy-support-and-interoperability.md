# 10. Legacy support and interoperability (Ferry)

Design document 10 of 10. Owner: Foundry, Workshop and tools team (7 at L); LSL Runtime scheduling in Grid (doc 06); Re-delivery Fund in Ledger (doc 09). Written 2026-10-09 against `00-design-spine.md` (names: section C; numbers: section D). Added figures are marked design defaults; facts not confirmed by a search extract are marked "(prior knowledge)".

## Summary

Ferry is how a Second Life or OpenSim community moves to nolife without dying on the way. It carries identity, inventory and social graph without loss (the moat) and budgets and converts content (the debt). Six mechanisms do the work. **Charter Import** moves a group's roles, opt-in members, ban list, rating, calendar and Holding in one transaction. **NAR**, a strict superset of OAR/IAR, carries builds in and out. Prims, sculpts and llmesh are rebuilt exactly and displayed as imported, with **Relight** opt-in. The **LSL Runtime** compiles unchanged LSL to Luau, and 90% of Founding Charter scripts must run unmodified at L. A one-time **creator claim** code signs a creator's catalogue to their Passport, and **Re-delivery** pays creators 10 Coin per proven SL purchase. The **Bridge** relays chat and calendar for 18 months. **Hypergate** arrives at L+18 and is the first thing cut. Targets: 50 Founding Charters by L+12, and at least 10 named SL institutions migrated with their membership by L+18.

---

## The moat-and-debt rule

### The rule

The failure taxonomy's rule decides every Ferry choice. A trait is a **moat** where it keeps the people already present, and a **debt** where it blocks the people not yet present (taxonomy 1.9). Second Life's inventories and relationships are a switching cost that no competitor has offered to carry. Those same unbudgeted inventories raised its hardware floor: Linden said in January 2025 that about half its users lack high-end machines ([source](https://modemworld.me/2025/01/02/)). Ferry therefore follows three rules:

1. **Carry the moat losslessly.** Identity, inventory, group structure and relationships arrive intact or not at all. A partial Charter is worse than none.
2. **Budget the debt, but never force it.** Legacy content always passes through the Foundry and gets Lite and Compat versions. It is never re-lit, re-made or demolished without the owner's consent (spine B.4 item 11).
3. **Rights, not formats, are the barrier.** Every SL export path comes down to "creator of every part". SL never adopted the Export bit, and avatar looks are third-party bodies sold no-mod, no-transfer ([source](https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/); [source](https://modemworld.me/2013/08/24/)). The format work is cheap. The rights programmes (creator claim, Re-delivery and the Export bit) are the hard part.

### What a migrant brings, and what Ferry does with it

| Trait | Moat or debt | Ferry treatment |
|---|---|---|
| Group: name, roles, members, ban list, rating, calendar | Moat | Charter Import, one transaction |
| Land and builds the resident made | Moat (place) + debt (budget) | NAR, exact rebuild, Scene Weight, Relight opt-in |
| Scripts (vendors, HUD meters, tip jars, doors) | Moat | LSL Runtime, unchanged |
| Look (third-party mesh body and head) | Moat, blocked by rights | Common Body now; Re-delivery when the vendor joins |
| Creator reputation and catalogue | Moat | Creator claim |
| Friends | Moat | Mutual reconnection, never silent import |
| Audience still in SL | Moat (temporary) | Bridge for 18 months |
| Legacy materials, full-bright, unbudgeted mesh | Debt | Preserved, capped, fallbacks generated |
| L$ balances, SL status | Liabilities of another operator | Not imported |

Sansar inherited nothing because it carried no inventory, identity or social graph (taxonomy 1.6). OpenSim carried everything but an economy and an audience, and has about 45-48K monthly actives ([source](https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/)). Ferry carries the institution, the creator and the economy together.

---

## Ferry from Second Life

### What can lawfully leave Second Life

Linden's viewer exports no objects. Kokua and Firestorm export Collada only for objects the logged-in avatar created, every part, with that avatar's own textures ([source](https://modemworld.me/2013/08/24/); Firestorm per prior knowledge). There is no official export of compiled scripts (prior knowledge). Ferry accepts creator-only Collada exports; the creator's original glTF or Collada sources (preferred over llmesh); LSL source text; textures, sounds and animations (.anim, BVH) from the viewer's "Save As"; OAR/IAR from OpenSim grids; and EEP or Windlight settings, converted to OpenUSD skies.

### Rebuild, display as imported, Relight opt-in

Every imported asset passes the Foundry at US$0.01 per asset. Conversion is platform-funded (C.3). Ferry adds three import stages ahead of the Foundry's normal ones:

1. **Exact rebuild.** Prims are re-tessellated from their parameters (profile, path, cut, hollow, twist, taper, shear) using OpenSimulator's BSD-licensed PrimMesher lineage. Sculpts are reconstructed from their RGB displacement maps. For llmesh, the highest LOD is read as the source and the Foundry regenerates its own four-level LOD chain. The result matches SL's highest-LOD geometry within float tolerance.
2. **Legacy material profile.** Diffuse, normal and specular maps, alpha modes and glow are kept as a **Legacy** material that reproduces the SL look on every tier. Full-bright survives as the capped Unlit/Emissive material (B.4 item 11).
3. **Weight report.** The Foundry computes Scene Weight before anything is placed, for example: "This archive is 42,600 Weight. Your Cell holds 30,000. Choose a Domain, place a subset, or keep the rest in inventory." Nothing is dropped silently.

**Relight** is an owner-initiated rebuild into the native pipeline: PBR metallic-roughness conversion, a Nanite cook where the engine licence allows it, and per-Holding probe and lightmap bakes. It is opt-in per object, linkset or Holding (the default is always as imported), previewed side by side in Darkroom, free, and revertible for 30 days, matching owner rollback (D.5). It covers content the owner created or may modify; for no-mod purchases only the creator can publish a Relit edition, as a new version buyers may adopt.

### The creator claim

The creator claim binds an SL creator identity to a Passport, so reputation, attribution and Re-delivery eligibility move with the person.

```
1. Creator (Passport, Trust ≥ New) requests a claim for SL account "Name Resident".
2. Ferry issues a one-time code NOLIFE-XXXX-XXXX (valid 14 days).
3. Creator places the code in that SL account's public profile text.
4. Ferry reads the public profile, matches the code and records the binding
   (SL account ↔ Passport) in the signed provenance log. The code can then be removed.
5. Every import whose SL creator field matches the bound account is signed to the
   Passport. The Foundry fingerprints claimed catalogues first.
```

Design defaults: one SL account binds to one Passport, and a Passport may bind up to 5 SL accounts (store alts are common). Disputes go to the Trust Desk (7 days, D.6). A claimant's SL legacy name is reserved as their nolife username until L+12, which blocks squatting on known brands. "Verified SL creator" shows on the Passport only on opt-in.

Residents use the same code mechanism ("account link") to prove control of an SL account for Re-delivery, Charter membership and friend reconnection.

**The CopyBot defence.** Any client can replay the asset stream it receives (doc 06), so Ferry attempts no DRM. Instead, Foundry fingerprinting checks every upload against claimed catalogues first. A non-creator upload that matches a claimed asset is rejected and attributed to the original. Repeat matches cost Merchant status.

**Friends** are carried as suggestions only. When two Passports have each linked an SL account, and one of them uploads an SL friend list, Ferry proposes a reconnection that both must accept. Unaccepted suggestions are deleted after 180 days (design default).

**Adult content.** Imported Adult-tagged goods face the Night Ward controls with no grandfathering: uploader verification, consent records and human pre-publication review (C.8, R22). Review of Founding Merchants' Adult catalogues starts in January 2028 so capacity is not the bottleneck at L.

---

## Charter Import

### Why the group is the unit

Second Life's durable communities rest on the group: 2-10 roles with abilities, a ban list of up to 500, a rating fixed at creation, a permanent name, and land ([source](https://wiki.secondlife.com/wiki/Group); [source](https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.7.14.292630)). Communities move when the institution moves intact, as one object rather than 1,300 sign-ups, under a credible persistence guarantee; educators named cost and persistence as decisive ([source](https://www.scitepress.org/Papers/2014/49578/)).

### The transaction

Charter Import is one Entity Store transaction that commits everything or nothing.

```
CharterImport {
  source:     { kind: sl_group | opensim_group | manual,
                external_group_id?, attested_by: PassportId }   // account-linked leader
  name:       string            // permanent; collision-checked
  rating:     General | Moderate | Adult    // fixed; Adult requires the Night Ward check
  roles:      [ { name, abilities[], external_role_id?, post?: PostType } ]   // 2..20
  members:    [ { external_account_id, display_name, role_refs[] } ]  // become invitations
  bans:       [ { external_account_id | PassportId, note? } ]
  calendar:   ICalFeed | [EventSpec]        // ≥1 weekly public event for Founding Charters
  holding:    { product: PlotS|PlotM|Cell|Domain, site: island|Reach,
                terms: Founding|List|NonProfit, hall: true }
  deputy:     PassportId        // required: the Charter owns land and a calendar
  succession: Rule              // required
  content:    [ NAR | OAR | IAR ref ]       // restored into the Hall after commit
}
```

**Validation, in order. Any failure rejects the whole transaction with a reason code.**

1. **Authority.** The attesting Passport is linked to an SL account that owns the group, or that holds abilities to manage roles and bans. A migration engineer checks manual imports.
2. **Name.** The name is free, or reserved for this institution. The Founding outreach list is pre-reserved.
3. **Roles.** There are 2-20 roles. SL abilities map by table, and anything unmappable becomes an unbadged internal role (unlimited, B.4 item 8).
4. **Posts.** Roles marked as Posts fit the Post cap of one per eight active members, minimum three. Until people join, the cap is computed on invited members, and it is re-checked at L+6 (design default).
5. **Deputy and succession rule** are present (C.1).
6. **Holding and terms.** For Founding Charters: a first Cell, or a Domain above 500 members, rent-free until L+6, then 30% off list, frozen for 36 months (C.10).
7. **Weight.** The Foundry's dry run fits the content to the Holding's Weight, or the leader chooses a subset.

**Members are invitations, not accounts.** The roster becomes pending memberships keyed to SL account identifiers, each with its reserved role. A member joins by linking their SL account or via an invite link the leader posts as an SL group notice through the Bridge. Pending invitations and their SL names are purged after 180 days (design default), because nobody on a roster has consented to anything.

**Bans survive identity changes.** A ban keyed to an SL account applies the moment that account links to any Passport, and then becomes a Passport ban.

**The calendar** arrives as iCal or a form, in the Civic Calendar's seasonal layer, with one weekly public event flagged as the Founding commitment (cure rule in doc 09).

### State machine

```
Draft ──validate──► Validated ──commit──► Committed ──restore──► Restoring ──► Live
  └──reject◄──────────┘                                  partial ─┘ (over Weight or
                                                                  rights-blocked items
                                                                  listed in Import Report)
Invitation:  Invited ──link/accept──► Joined     Invited ──180 days──► Expired (purged)
Rollback:    the owner may roll the Hall back to any snapshot for 30 days (D.5).
```

The **Import Report** is the contract with the leader. It lists:
- every asset, as imported, rebuilt, over budget (placed in inventory) or blocked by rights, with the reason;
- every script, as running, approximate or failed, with the call that failed;
- Weight before and after.

### Example: a live-music venue

A Cafe Musique-class venue (60+ shows a week ([source](https://secondlife.aditi.lindenlab.com/destination/aism))): a group of 2,400, 6 roles, 180 bans, a stream URL and DJ tip jars.

| Day | Step |
|---|---|
| T-30 | Migration engineer assigned; the leader links an SL account; the builder runs the creator claim |
| T-21 | Dry run: 51,000 Weight, so the venue takes a Domain (above 500 members: rent-free until L+6) |
| T-14 | LSL dry run on 312 scripts: 296 unmodified, 11 approximate, 5 fail on an SL-hosted lookup and are rewritten |
| T-0 | Commit: Charter, Hall, 2,400 invitations, 180 bans, calendar; DJ and Host become Posts; the Bridge starts |
| T+7 | NAR restored; stream and tip jars live; first weekly show on the Civic Calendar |
| T+90 | Census: *invited* members active (Series A measure) and *imported* members active (Tripwire measure) |

### Targets and counting

- **Founding Charters:** 25 by L and 50 by L+12 (C.10, D.7).
- **Migrated institutions:** at least 10 named SL institutions migrated with their membership by L+18 (D.7; this is the R18 test).
- **Series A gate:** at least 15 Founding Charters with at least 50% of *invited* members active monthly (D.2).
- **Tripwire:** at L+12, if fewer than 10 named SL institutions are active with at least 50% of their *imported* membership, the Floor Plan triggers (C.10).
- **Definitions.** "Invited" means the roster at commit. "Imported" means the members who joined. "Active" uses the Census definition (C.8).

**Outreach list** (census brief): Virtual Ability, the VWBPE committee, Second Pride, Fantasy Faire/RFL, the 1920s Berlin Project, the Crack Den, Luskwood, Cafe Musique, First UCC SL and UUCSL, each a single decision-maker who can bring hundreds to thousands ([source](https://virtualability.org/about-us); [source](https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/)).

---

## NAR and OpenSimulator

### Why OpenSim first

The hypergrid's roughly 45-48K monthly actives ([source](https://www.hypergridbusiness.com/2026/01/opensim-land-grows-as-traffic-slows-slightly/)) already pack archives and have lost content: OSgrid gave five weeks' warning of a database wipe in 2025 and was offline for weeks in 2026 ([source](https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff); [source](https://www.hypergridbusiness.com/?p=79686)). OAR and IAR are the only mass-migration path that exists.

### The NAR format

An OAR packages a region as a gzipped tar with an XML manifest: terrain, parcels, objects with their inventories and scripts, and the assets they reference. An IAR does the same for an inventory subtree. Neither carries cryptographic provenance (prior knowledge, legacy brief). NAR is a strict superset:

```
archive.xml                                     OAR/IAR control file (unchanged)
terrains/ landdata/ objects/ assets/ inventory/ OAR/IAR trees (unchanged)
nolife/manifest.json      NAR version; every blob by content hash (Vault)
nolife/provenance/        signed envelope per asset: creator Passport, licence,
                          Copy/Modify/Transfer, Export bit, maturity tag
nolife/derivatives/       optional tier bakes, LOD chains, impostors
nolife/scripts/           Luau output beside original LSL source
nolife/charter/           Charter document, roles, calendar.ics (Charter exports)
nolife/sky/               OpenUSD sky and environment assets
```

The rules:
- **`load oar` and `load iar` work unchanged.** The Workshop console and the Homestead Kit accept OpenSim archives and OpenSim's command syntax as they are.
- **Exports stay readable by OpenSim.** An export lays out a valid OAR/IAR tree, with nolife-only data under `nolife/`. As a design default, CI loads every export into a pinned OpenSimulator release on every build.
- **Thin and full.** A *thin* NAR references blobs by hash; a *full* NAR embeds them. Either restores by hash on any host (doc 06).

### Rights in archive import

OpenSim implements the Export bit, and Firestorm honours it there (prior knowledge, legacy brief).

| Creator vs importer | Permissions | Export bit | Result |
|---|---|---|---|
| Importer is the creator (or bound by creator claim) | Any | Any | Imported, signed to the importer |
| Third party | No-transfer | Not set | **Not imported**; listed in the report |
| Third party | Any | Set | Imported, attributed to the original creator |
| Third party | Transfer | Not set | **Held**: rezzable only on the importer's own Holdings, never listed for sale, attributed; released if the creator claims and approves |

Held is a containment rule that this document adds. The spine's not-imported list names only no-transfer content (see Open questions).

### OpenSim operators

Federation and Crossing were rejected (B.3). An OpenSim grid operator has three routes instead:

1. Move estates as NARs into ordinary Holdings.
2. Become a **Homestead Kit** partner from L+12 at US$29 per cell-month. Kit cells are General or Moderate only, take assets only through the Foundry, use the central Passport and Ledger, and stay under platform takedown (doc 06).
3. Plug its market into the Bazaar Delivery API. Kitely Market is the intended first external store.

A single-language grid's community can become a Ward once it reaches 2,000 attached MAU (D.6).

---

## The LSL Runtime and Luau

### Decision

Residents upload LSL unchanged. Ferry compiles it transparently to Luau against an `ll` library, with OpenSim's BSD engine and tests as the reference. Unsupported calls fail loudly. 90% of Founding Charter scripts must run unmodified at L (B.4 item 14).

Luau is the native language. Roblox runs it at scale, and Linden's SLua is a Luau fork that reached main-grid beta in December 2025 ([source](https://wiki.secondlife.com/wiki/Lua_Alpha)), so one VM serves migrants from both worlds.

```
LSL source ──parse (LSL grammar; OpenSim dialect + common OSSL)──► typed AST
  ──lower──► Luau module: coroutine per script, state/event tables, ll.* calls, int32/float32 helpers
  ──static check──► unsupported calls, money calls, external HTTP hosts
  ──run──► same Luau VM, scheduler and per-owner budgets as native Luau (doc 06)
```

### Semantics preserved exactly

| LSL behaviour | Implementation |
|---|---|
| 32-bit wrapping integers | `bit32`-based helpers (Luau numbers are doubles) |
| Single-precision floats, vectors, rotations | Float32 rounding at assignment and at `ll` boundaries |
| `state`, entry and exit, the event queue | Coroutine per script. A state change clears the queue; the queue bound matches the reference engine |
| `llSleep` and built-in function delays | Yields of the same length, so a vendor's pacing is unchanged |
| Listens, link messages, timers, sensors | Native cell events; sensors and raycasts via Jolt |
| Script memory | 64 KB per LSL-origin script, inside the owner's budget (doc 06) |
| Sleeping cells | `changed(CHANGED_REGION_START)` plus one coalesced timer catch-up on wake (docs 02 and 06) |

### Compatibility classes

| Class | Examples | Behaviour |
|---|---|---|
| **A: exact** | Chat, touch, sit, timers, lists, strings, link messages, permissions, animations, inventory give, dialogs, HTTP in and out, parcel media and stream URL; particles mapped to Niagara templates | Runs unmodified |
| **B: approximate** | Vehicle parameters, physics material constants, pathfinding | Runs. Flagged "feel may differ", because Jolt replaces Havok |
| **C: unsupported** | Calls that depend on SL-hosted services; estate-god functions with no equivalent; Linden experience-key ties; viewer-side restraint commands (`@` messages) | Statically flagged. At runtime the handler stops and raises `LSL_UNSUPPORTED(<call>)` to the owner. Never a silent no-op |

**Money.** `llGiveMoney`, `money()` events and `PERMISSION_DEBIT` map to the Ledger in Coin.
- L$ amounts are not converted, because L$ is not imported and has no fixed rate to Coin.
- The static check lists every money-handling script with its fiat effect, for example "this vendor charges 250 Coin = US$2.50", and the owner confirms before the script activates.
- Debit permission is re-granted in nolife, with a per-script spend cap.

**Vendor servers.** Scripts that call an external host for value-bearing behaviour (breedables, rental meters, vendor HUDs) are offered **Keepalive**: escrowed life-support with a food-independent end state (C.4, R24). Breedables migrate to **Lineage**.

### Measuring the 90%

- **Corpus:** every distinct LSL source (by hash) imported by Founding Charters before 1 September 2028; also reported weighted by instance count.
- **"Unmodified":** compiles with no edit and raises no `LSL_UNSUPPORTED` in a 7-day soak in its Hall; Class B also needs owner sign-off.
- **Oracle:** a differential harness feeds one recorded event trace to OpenSim's engine and to the LSL Runtime and compares chat, link messages, object state and Ledger calls. Known OpenSim-versus-SL divergences are listed and SL behaviour is targeted.
- **Gate:** published in Census at L by class, with the ten most-hit unsupported calls. Below 90% at L-3, those calls outrank every other Ferry feature.

**Toward native Luau.** The Workshop shows the generated Luau, which the owner can fork into native Luau. Retiring the LSL Runtime needs a converter and 24 months' notice (C.3), and not before L+60 (design default).

---

## Common Body, Bento mapping and Re-delivery

### The Common Body

A 2026 SL avatar is a third-party mesh body and head, sold no-mod and no-transfer, and the resident who wears it cannot legally import it (legacy brief, pattern 2). The answer is the open-licensed **Common Body** (C.5). It uses a VRM 1.0 skeleton, a MetaHuman-compatible face rig and server-side Bakes-on-Mesh atlasing at the Foundry, and the Landing dresses every newcomer in it within ten minutes (R26). Avatar budgets are canonical (D.4):

| Tier | Triangles | Materials | Bones | Texture memory | Attachments |
|---|---|---|---|---|---|
| Reference | 120,000 | 12 | 300 | 80 MB | 24 |
| Lite | 35,000 | 6 | 120 | 24 MB | 12 |
| Compat | 20,000 | 2 (atlased) | 75 | 8 MB | 6 |

### The published Bento table

Bento (2016) is a 133-bone skeleton that adds face, hand, wing, tail and hind-limb bones (legacy brief, prior knowledge). VRM 1.0's humanoid covers the body. **`nolife-bento`**, a glTF extension, carries the bones VRM lacks. An excerpt (bone names from prior knowledge):

| SL bone | Target |
|---|---|
| mPelvis, mTorso, mChest, mNeck, mHead | VRM `hips`, `spine`, `chest`, `neck`, `head` |
| mSpine1-4 | `nolife-bento` (extra spine segments) |
| mCollarLeft, mShoulderLeft, mElbowLeft, mWristLeft, mHand* | `leftShoulder`, `leftUpperArm`, `leftLowerArm`, `leftHand`, VRM finger chains (mirrored for right) |
| mHipLeft, mKneeLeft, mAnkleLeft, mFootLeft, mToeLeft | `leftUpperLeg`, `leftLowerLeg`, `leftFoot`, `leftToes` |
| mEyeLeft, mFaceJaw; other mFace* | `leftEye`, `jaw`; the extension, driving the face rig |
| mWing*, mTail1-6, mHindLimb*, mGroin | `nolife-bento` |

**Tier reduction:** Reference keeps every bone (133 < 300); Lite (120) turns face bones into blend shapes and halves wing and tail chains; Compat (75) keeps the VRM humanoid plus one tail and one wing bone. `.anim` and BVH retarget through the table into glTF animations, and animation overriders run as Class A scripts. Vendors get fitting tools for their SL sources, and Component Royalties of up to 10% let a body maker become a platform for clothing makers (C.4).

### The Re-delivery Programme

Re-delivery pays creators when a migrating resident proves an SL purchase and claims the nolife edition (C.9). The terms are canonical (D.3, and doc 09):

| Term | Value |
|---|---|
| Payment to creator | **10 Coin per claim** |
| Cap per merchant | **US$5,000** (50,000 claims) |
| Fund | **US$1.5M**, from **L-6 to L+24** (April 2028 to October 2030) |
| Body and head vendors' Re-delivery editions | **0% commission for 12 months** |
| Founding Merchants (first 1,000 verified creators) | 5% commission for 12 months from L; funded conversion; creator claim; Re-delivery |

```
1. Merchant (verified, creator claim done) marks items re-deliverable and uploads
   or links its own SL sales records (buyer account, item, date).
2. Resident links their SL account (account link).
3. Resident claims item X; Ferry matches the linked SL account to the merchant's records.
     match    → nolife edition delivered free to the resident; 10 Coin to the merchant from the Fund
     no match → resident uploads their SL transaction record; merchant approves or rejects
                within 14 days (design default)
4. The nolife edition's licence mirrors the SL purchase (no-transfer stays no-transfer).
```

**Anti-fraud and accounting (design defaults):**
- One claim per item per SL account. An SL account links to only one Passport, which bounds claims by alts.
- A claim is not a purchase, so it carries no Commons Pool purchaser weight. This closes the self-dealing loop between a merchant and their own alts.
- 1% of claims are audited each month.
- At the cap, or once the Fund is exhausted, claims continue unpaid at the merchant's option. Unspent money returns to the operator at L+24 and is reported in Census (doc 09).

**Why pay the creator.** The look belongs to a few hundred vendors; a per-claim fee turns the most important supply-side deal into a per-customer one. Kitely's re-delivery to stranded OSgrid buyers is the precedent ([source](https://www.hypergridbusiness.com/?p=79686)).

---

## The Bridge and Hypergate

### The Bridge (18 months)

The Bridge relays chat and calendar between a Charter and its SL group through residents' own accounts, with Discord as the fallback (C.9). The service runs **18 months from L**, from October 2028 to April 2030 (D.6). Founding Charters can use it from the day of their alpha import.

**Architecture.**
- **No SL credentials leave the resident's device.** The Bridge agent runs inside Lantern or Reader, or as a small headless companion app, on a **Bridge holder's** machine, logged into SL as that resident.
- **Failover.** A Charter names up to three holders, normally the leader and deputies.
- **Disclosure.** Holders set their SL account's scripted-agent status where SL policy requires it (prior knowledge).

| Relayed | Not relayed |
|---|---|
| Group chat both ways, prefixed `[nolife] Name:` or `[SL] Name:` | Private IMs, unless both parties opt in |
| Group notices ↔ Charter notices | Voice and media |
| Charter calendar → SL notices; iCal and ActivityPub feeds (B.2) | Inventory, money, teleports |
| A "visit from SL" link to the Hall, opening in Ember with no install | Senders blocked on either side |

**Safety.** Bridged messages are tagged *external*, pass native chat moderation and can be muted as a class. Wardens can suspend a Charter's Bridge, and relay rates stay inside SL's group-chat throttles.

**If Linden blocks it**, the channel relays to Discord via the Discord Social SDK, open to all developers since August 2025 ([source](https://alternativeto.net/news/2025/8/discord-social-sdk-launches-to-all-devs-with-in-game-voice-chat-and-cross-platform-play/)). The iCal and ActivityPub feeds need no SL cooperation. Bridge traffic and each Charter's audience split are published at the L+18 R18 test.

### Hypergate (L+18, first to cut)

Hypergate speaks Firestorm's protocol, so residents who keep Firestorm can visit nolife places (C.9). Firestorm, not Linden's viewer, carried most of SL's users ([source](https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/)).

**Scope (all design defaults):**
- **Login** via Firestorm's grid manager with Passport credentials; visitors arrive at Trust Visitor with a "Hypergate" badge.
- **Places:** General and Moderate only. No Night Ward, because a third-party viewer cannot attest the Safety Kit.
- **Rendering:** Compat derivatives as viewer-protocol mesh and textures; nolife avatars as impostors with role badges.
- **Actions:** chat, teleport between Hypergate-enabled places, sit. No building, Ledger or avatar-to-avatar actions; Wardens can kick and lock.

**Cost.** About two engineers for 12 months (≈US$0.3M at US$150K loaded, D.2), plus gateway compute inside the US$0.025 per CCU-hour envelope.

**Cut rule.** Hypergate is first in the cut order (doc 09). It is cut without further review if, at L+12, the Floor Plan has triggered, the Bridge or Charter Import targets are behind, or the LSL Runtime is below 90%. It is a second protocol implementation, and nothing a community needs in order to move depends on it.

---

## VRM, BOOTH and other worlds

**VRM.** VRM 1.0 is a glTF 2.0 profile with humanoid, MToon, spring-bone, node-constraint and animation extensions ([source](https://vrm.dev/vrm1/); [source](https://github.com/vrm-c/univrm)). It is the only widely adopted open humanoid format, and neither VRChat nor Resonite imports it natively ([source](https://wiki.resonite.com/Avatar_Creation)). In nolife VRM 1.0 is the runtime format (C.3): 0.x files migrate on import, MToon maps to the toon shader, spring bones run as client-side secondary motion, and every avatar gets a Fidelity Rank plus generated Lite and Compat bakes.

**BOOTH and off-platform stores.** VRChat-Japan grew on BOOTH's roughly 10.4bn-yen 3D-model trade, not on VRChat's own store ([source](https://realsound.jp/tech/2026/02/post-2303955.html)). The Bazaar's open delivery API serves BOOTH, Gumroad and Kitely Market exactly as it serves in-world vendors (C.4):

```
POST /bazaar/v1/deliveries
  { store_id, order_ref, buyer_passport_claim_token, asset_bundle (glTF/VRM),
    licence: { transfer: false, modify: bool, export: bool }, signature }
→ Foundry ingest → buyer inventory, with provenance (store, creator, order_ref)
```

Off-platform-paid deliveries carry 0% commission and are non-transferable unless the creator registers them (D.3). The target is at least 30% of avatar items from off-platform stores by L+24 (D.7), helped by Japanese Wards with konbini at L+12. Pool weight for such deliveries is open in doc 09.

**Other worlds:**

| Source | Path |
|---|---|
| Ready Player Me GLBs (service shut 31 January 2026) ([source](https://genies.com/blog/ready-player-me-shutdown)) | glTF import, auto-rigged to the Common Body |
| Resonite | glTF/GLB import; logic re-made in Luau |
| Spatial (worlds deleted 27 July 2026) ([source](https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/)), Unity scenes, VRChat worlds | glTF/OpenUSD exporters → Workshop; shaders approximated as PBR; Udon and scripts re-made in Luau |
| Sansar, Rec Room | Re-made; creators get Founding Merchant terms where eligible |

OpenUSD is the scene format because the industry is converging on it. AOUSD began ISO certification of Core Spec 1.1 in July 2026 ([source](https://www.linuxfoundation.org/press/aousd-drives-global-3d-data-interoperability-ai-workflows-with-core-spec-milestones-and-members)), and SL creators asked Linden for USD support the same month ([source](https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/)).

---

## Export, portability and the sunset covenant

**The Export bit.** Every asset's provenance envelope carries a creator-set Export bit (C.4).
- A creator can always export their own work.
- A buyer can export a purchase only if the bit is set.
- Certified clients honour the bit. Uncertified clients receive only cooked derivatives (doc 06).

The content licence is one plain-language page defining the affirmative action required before any platform re-use, because creators remember SL's 2013 ToS Section 2.3 episode ([source](https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/)).

**What anyone can take out, at any time, free:**

| Data | Format |
|---|---|
| A Holding | Full or thin NAR, loadable by OpenSim's `load oar` |
| Inventory subtree | NAR (IAR-compatible) |
| Own-created assets | glTF 2.0; VRM 1.0 for avatars; OpenUSD for scenes and skies |
| Own scripts | Luau and the original LSL |
| Licences held | Signed licence records, readable off-platform via Passport |
| A Charter (owner) | Charter document, roles, calendar (iCal), members who consented |

Campus sites export as NARs too (R28). Lapsed Holdings are frozen for 90 days, then stored as a NAR in inventory, restorable indefinitely (D.6). Protocol versions are supported for 24 months after their successor ships (doc 06).

**The sunset covenant.** The World Charter guarantees 12 months' notice before any shutdown, followed by escrow release (C.8). During the notice period:

1. Full NAR export is unrestricted.
2. Signed licence records are published, so other operators can honour them.
3. The escrowed server source, including the LSL Runtime, the Foundry and the protocol reference, is released under Apache-2.0, and the data escrow becomes restorable by any host (B.4 item 1; doc 06).
4. Founders' Pass holders are refunded pro rata (doc 09).

Escrow, NAR export and a two-provider failover demo ship at L (B.4 item 15). This is the answer to OSgrid's wipe, and to Sansar's unexplained outage in December 2021 ([source](https://uploadvr.com/sansar-offline-without-explanation/)).

---

## What is not imported

The canonical list (C.9):

1. **No-transfer third-party content without an Export bit.** This covers most SL avatar looks until their vendors join Re-delivery.
2. **L$ balances.** There is no currency bridge. nolife will not take on a liability priced by another company's exchange.
3. **SL status.** Account age, payment status, Premium and the self-declared Adult flag. Every Passport passes the Age Module, and Trust and Standing are earned in nolife.

Also excluded: region builds whose builder is not the importer (named institutions get migration-engineer time instead); script dependencies on SL-hosted services (Class C); payment data and SL credentials; and roster entries of people who never opted in, which expire after 180 days.

---

## Trade-offs and alternatives rejected

| Alternative | Source | Why rejected |
|---|---|---|
| Forced re-make of legacy content in the native pipeline | engine-architect | Alienates the photographers, clubs and builders whose look is the community (B.4 item 11). Relight is opt-in |
| Transpile the common 80% of LSL and flag the rest for rewrite | sociologist, open-web, ai-world | Rewriting tip jars and meters is the cost that stops venues moving. LSL runs as-is, with a 90% gate |
| Crossing federation; OpenSim grids as sovereign shards | open-web | The weakest shard would set everyone's card-scheme and safety risk (B.3). The Homestead Kit is the only self-hosting |
| A platform-run Bridge holding residents' SL passwords | — | Credential custody and SL-ToS exposure. A device-side agent costs uptime, mitigated by up to three holders |
| L$ → Coin exchange | — | An unbounded liability at a rate nolife does not control (R9) |
| Re-delivery paid from the Commons Pool | economist | Would starve the creators the Pool weights. A separate, bounded Fund closes at L+24 |
| Hypergate at L; `rbx-compat` | open-web | A second protocol before the first is stable; the wrong audience (B.3) |

**Main trade-off accepted.** Some Founding Charter places will look like 2015 SL inside a 2026-looking world. The Fidelity Contract keeps them inside budget, Relight makes the upgrade one click, and the community, not the platform, decides when.

---

## Requirements addressed

| R | How |
|---|---|
| R2 | Every import passes the Foundry: Weight report, Lite and Compat bakes, per-tier Bento reduction |
| R3 | glTF/VRM runtime, OpenUSD scenes; funded conversion (US$0.01 per asset); converter plus 24 months' notice, LSL Runtime included |
| R4 | Hypergate for Firestorm users at L+18; Bridge agent inside the first-party clients; NAR documented |
| R5 | LSL Runtime under the Luau scheduler and per-owner budgets; 64 KB per LSL-origin script |
| R13 | Census publishes LSL compatibility, import outcomes, Re-delivery claims and Fund balance, Bridge traffic |
| R18 | Charter Import; NAR/OAR/IAR; SL import with creator claim; 18-month Bridge; export; ≥10 institutions by L+18; 50 Founding Charters by L+12 |
| R20 | Free NAR export, restore by hash anywhere, sunset covenant with escrow release, Homestead Kit at L+12 |
| R22 | Imported Adult goods get full Night Ward review, no grandfathering |
| R24 | Vendor-server scripts offered Keepalive; breedables moved to Lineage |
| R26 | Common Body and Bento table; Re-delivery for the look |
| R27 | Bridge agent runs in Reader; Virtual Ability is on the Founding outreach list |
| R28 | Campus NAR export; educators' OAR archives load unchanged |
| R29 | VRM 1.0; BOOTH, Gumroad, Kitely Market at 0% via the Bazaar; ≥30% off-platform avatar items by L+24 |
| R30 | Hypergate costed (about US$0.3M) and first to be cut; Re-delivery Fund bounded at US$1.5M |

---

## Open questions

1. **Transferable third-party content without an Export bit.** The spine's list names only no-transfer content; this document adds the Held state. Should the spine adopt it, or exclude such content entirely?
2. **Is NAR loadable by OpenSim?** "Strict superset" assumes OpenSim's reader ignores `nolife/`. Verify in Phase 0; if not, export emits a pure OAR/IAR beside the NAR.
3. **The Bridge window for late migrants.** The Bridge runs from L to L+18, so a community that moves at L+15 gets three months. Should the window run per Charter (18 months from import), at the cost of operating the Bridge until about L+36?
4. **If Linden blocks profile codes or Bridge agents,** Discord and iCal survive, but the creator claim needs a fallback proof (a Marketplace store-description code or a signed in-world object).
5. **Viewer-side restraint commands** are Class C at L. Should a consent-gated Restraint API, built on the Safety Kit's consent prompts, ship for the Night Ward? Without it some Estates cannot move.
6. **Migration-engineer capacity.** With one engineer to at most five Charters (design default), 25 Charters by L takes about five engineers from a 7-person team during Phase 1. Should the Series A fund contractors for this?
7. **Class B and the 90%.** Counting approximate scripts that the owner has approved may flatter the figure. Should Class B be reported separately and excluded from the gate, alongside a vehicle-emulation test set built in Phase 0?

---

## Sources

- SL groups: https://wiki.secondlife.com/wiki/Group
- SL ban-list limit: https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.7.14.292630
- Export bit and the origin of stolen content: https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/
- Creator-only Collada export: https://modemworld.me/2013/08/24/
- SL ToS 2.3 revision: https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/
- SL CCUG, July 2026 (glTF and USD requests): https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/
- Linden hardware statement: https://modemworld.me/2025/01/02/
- SLua: https://wiki.secondlife.com/wiki/Lua_Alpha
- Firestorm usage: https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/
- OpenSim statistics, January 2026: https://www.hypergridbusiness.com/2026/01/opensim-land-grows-as-traffic-slows-slightly/
- OpenSim statistics, May 2026: https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/
- OSgrid wipe: https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff
- OSgrid outage and Kitely re-delivery: https://www.hypergridbusiness.com/?p=79686
- Educators on cost and persistence: https://www.scitepress.org/Papers/2014/49578/
- Virtual Ability: https://virtualability.org/about-us
- 1920s Berlin Project: https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/
- Live-music venues (AISM, Cafe Musique): https://secondlife.aditi.lindenlab.com/destination/aism
- Sansar outage: https://uploadvr.com/sansar-offline-without-explanation/
- Club Penguin Rewritten: https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/
- VRM 1.0: https://vrm.dev/vrm1/
- UniVRM: https://github.com/vrm-c/univrm
- Resonite avatar import: https://wiki.resonite.com/Avatar_Creation
- BOOTH 3D-model trade: https://realsound.jp/tech/2026/02/post-2303955.html
- Ready Player Me shutdown: https://genies.com/blog/ready-player-me-shutdown
- Spatial creator worlds deleted: https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/
- AOUSD Core Spec 1.1 and ISO: https://www.linuxfoundation.org/press/aousd-drives-global-3d-data-interoperability-ai-workflows-with-core-spec-milestones-and-members
- Discord Social SDK: https://alternativeto.net/news/2025/8/discord-social-sdk-launches-to-all-devs-with-in-game-voice-chat-and-cross-platform-play/
