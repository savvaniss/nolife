# 07 · AI inhabitants and the living world (Keepers)

Design document 07 of 10. Author: Keeper and Landing design lead. Date: 2026-10-09. Status: draft for engineering review. Canonical names and numbers come from [the design spine](00-design-spine.md) (B.4 item 2, C.7, D.1, D.5); requirements R1-R30 come from the failure taxonomy. Values the spine does not set are marked "(this document)". No web search was used; external facts carry the research briefs' citations.

## Summary

This document specifies where AI appears in nolife and the rules that keep it from being mistaken for life. A **Keeper** is a disclosed artificial inhabitant with one of four jobs: **Greeter**, **Chronicler**, **Stand-in** or **Director**. The **Human Primacy Charter**, enforced in code, requires a badge naming whose behalf it acts on, exclusion from every metric, SLO and the Pool, and one-for-one withdrawal as humans arrive. Keepers hold no Coin, land, vote, Post or Standing, never moderate, never message offline humans and have no companion loops. Caps are 20% of visible occupants in public places and 0% in Holdings, Estates and quiet Wards unless enabled. The scripted Director arrives at L+6, Greeters and Chroniclers at L+12 as a randomised experiment, and Stand-ins at L+18. If human D30 trails control, the cap drops to 10%, then zero. Tiers cost US$0.003, 0.015 and 0.20 per agent-hour (blended ≤US$0.02), and spend is capped at 10% of infrastructure plus T&S.

---

## AI never counts as life

### The rule

The first reading of the name ("no life of its own") is that the platform manufactures no purpose. For AI this is a hard rule: **an artificial inhabitant is staff, never population.** A Keeper may keep a door, a ledger or a stall while humans are absent. It may never make a place look attended when it is not, or stand in for the reason people come.

Three findings drive this:

- **Agents have never made a place necessary.** Creatures, Black & White and Spore made one creature interesting, and none of them gave players a reason to stay ([source](https://www.howwegettonext.com/the-brain-in-the-machine/); [source](https://www.gamedeveloper.com/design/spore-my-view-of-the-elephant)). Animal Crossing's scripted villagers and real clock did more for "place" and "return" than any learning agent. Dwarf Fortress and RimWorld sell stories through cheap, legible systems paced by a director ([source](https://www.rimworldwiki.com/wiki/RimWorld)). The taxonomy's conclusion is that "AI changes what an empty room looks like, not whether people have a reason to be in it."
- **The emptiness is a density problem.** Second Life has about 27,769 regions and an average peak concurrency of about 49,649, roughly one or two humans per region at best ([source](https://danielvoyager.wordpress.com/2025/01/05/first-2025-main-grid-regions-goes-live-for-second-life/); [source](https://community.secondlife.com/forums/topic/523927-whats-secondlifes-real-population-summer-of-2025/)). nolife answers density with the Ward Plan, the Landing and the Civic Calendar (documents 02 and 03), not with bodies.
- **The audience is hostile, and "dead internet" fears can be measured.** 63% of 1,799 Quantic Foundry respondents chose the most negative option on generative AI in games ([source](https://quanticfoundry.com/2025/12/18/gen-ai/)). Bots were 51% of web traffic in 2024 ([source](https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/)). A world that fills its plazas with agents will be read as a world full of bots.

### What "living world" means here

In nolife the world is lived in by people. What changes when no one is looking is environment and civic machinery, not AI:

| Layer | Is it AI? | Document |
|---|---|---|
| Ward sky, time of day, weather | No: deterministic environment state | 05 |
| Civic Calendar and the Ephemeral Ward | No: owned by Charters and councils | 03 |
| The Chronicle | Drafting only; a human signs | 03 |
| Ambient happenings (bells, lamps, notices, weather fronts) | The Director: a scripted Keeper job with no body | 07 |
| Keepalive and Lineage creatures | No: scripted a-life under escrow | 04 |
| Greeters, Stand-ins | Yes: Keepers | 07 |

### What we took from ai-world-designer, and what we rejected

**Adopted:**
- the Human Primacy Charter;
- the T0/T1/T2 cost model, republished quarterly;
- Stand-ins that wear "the apron, not the face";
- quiet Wards;
- a decoupled Keeper runtime that degrades to scripted routines;
- Lineage without chance-for-cash (document 04);
- First Light (document 03).

**Rejected, with reasons (spine B.3):**

| Rejected | Why |
|---|---|
| Liveliness Floor: Keepers up to 50% of visible occupants at peak and six of eight off-peak | No evidence that agent density retains people; it is Horizon's emptiness behind a mask; 63% hostility |
| Keepers filling unfilled role slots in degraded form | "People stay where they are needed": if a Keeper holds the door, nobody needs the volunteer |
| Crew Apprentices, one Keeper per crew | A companion loop dressed as a group asset |
| Living ecology, desire lines, decay, districts that "go to seed" after 14 quiet days | No precedent; evicting quiet residents breaks the persistence covenant |
| Chance-based breeding of cash-out-able creatures | Gambling in at least one jurisdiction (R9) |
| Almanac planning on frontier models | The Director is scripted and non-LLM: cheap, auditable, legible |
| Houses buying Keeper slots | No Keeper capacity is sold during the experiment |
| An Assembly vote on adult companions in year three | No companion or romantic loops; reopening needs a World Charter amendment |

---

## Keepers and their four jobs

### The four jobs

| Job | Purpose | Where | Embodied | Max tier | Arrives | Withdraws when |
|---|---|---|---|---|---|---|
| **Greeter** | Holds a Landing when no human Host is on shift | Landing halls | Yes (or Counter mode, below) | T1 | L+12 | A human Host arrives: it hands over and leaves |
| **Chronicler** | Drafts Chronicle entries for a human to sign | Unembodied service; optionally a badged note-taker at a Ward event | Optional | T1 (nightly batch) | L+12 | Not applicable when unembodied; when embodied, it leaves first under the cap |
| **Stand-in** | Opt-in, interview-seeded tender of an absent resident's shop | That resident's Holding, Commons plot or Market stall | Yes (or Counter mode) | T2 | L+18 | Its resident comes online in the place, or after 60 days of the resident's inactivity |
| **Director** | Scripted, non-LLM pacer of ambient Ward happenings | Ward public cells (Stage, Market and Green) | No body | T0 only | L+6 | It never overrides human events; quiet Wards switch it off |

There are no other jobs. Doormen, barkeeps, townsfolk and crowd extras fail document 01's test (they fill time for the operator and show artificial occupancy as life). A new job needs a World Charter amendment.

### Identity: a Keeper is not a Passport

Keepers live in their own principal namespace, so the Charter's prohibitions are type errors rather than policy checks:

```text
KeeperRecord {
  id:            "kpr:<uuid>"            // never a Passport; cannot own an account
  job:           greeter | chronicler | stand_in | director
  principal:     platform | charter:<id> | passport:<id>     // "on whose behalf"
  badge_text:    e.g. "Greeter for nolife (artificial)",
                 "Stand-in for Mara Okonkwo (artificial)"
  place_binding: [place_id]              // cannot teleport or leave its binding
  tier_max:      T0 | T1 | T2
  voice_id:      catalogue id with provenance record, or null (text only)
  memory_policy: { per_human: opt_in, ttl_days: 90, cross_ward: false }
  limits:        { coin_per_sale, coin_per_day }   // Stand-in only
  log_ref:       append-only log readable by the principal and the Trust Desk
  spec_ref:      published job spec and prompt template (Chronicle)
}
```

The API gateway rejects any `kpr:` principal on these calls: `Ledger.*` account and balance operations, `Holding.lease`, `Post.assign`, `Standing.award`, `Ballot.cast`, `Assembly.stand`, `Safety.sanction` (kick, ban, lock, mute-other), `Calendar.create_event`, `Messaging.send` to an offline recipient, IM, friend request, group invite, `Census.count` and `Pool.weight`. A conformance job calls every one of these daily with a synthetic `kpr:` principal. Any call that does not return 403 pages the on-call engineer and is written to the Chronicle (this document).

### Disclosure in every form

- **Badge.** A persistent ring badge and "(artificial)" on the name tag, carried by the look descriptor into impostors at every tier (documents 05, 06).
- **First-contact notice.** The first time a Keeper addresses a person, a plain-language line says what it is, on whose behalf it acts and what it can do. Example: *"I'm a Greeter for nolife, an artificial guide. No human Host is on shift right now; one may arrive and take over. I can show you around and walk you to the 21:00 Open Stage."* Generic labels such as "assistant" or "NPC" are forbidden.
- **Reader** speaks "artificial, acting for X" before a Keeper's first line.
- **Machine-readable marking** on every chat line and synthesised audio frame (see Regulation and voices).

### Runtime

A separate **Keeper service**, outside the Cells, owns each Keeper's job state, memory and tier, and streams intents (go here, say this, run this vendor sale) to the Cell. The Cell applies them under the same physics, Luau and avatar budgets as any resident. If the service is unreachable, embodied Keepers fall back to T0 routines within 2 s and withdraw within 60 s (this document). Keepers sleep with their Cell and cost nothing while no human is in range.

### Example flow: a Greeter at 02:40 in São Paulo

1. Seven Portuguese-language newcomers arrive between 02:25 and 02:40, outside hosted hours (16:00-24:00); the experiment assigns the cohort to the Greeter arm.
2. One Greeter opens the hall: 1 of 8 visible occupants (12.5%, under the cap). It gives the first-contact notice and runs the script: dressed avatar and furnished Hearth within ten minutes, then First Light, which writes all seven names into the Chronicle.
3. It walks the cohort to a Civic Calendar event starting within 30 minutes; if none exists, it shows the Call Board's three invitations (one outside any Charter) and books the next human-hosted event.
4. At 02:58 a night-shift Landing Host comes online. The Greeter introduces the Host by name, hands over the roster and leaves within 60 s.

---

## The Human Primacy Charter

The Charter is published beside the World Charter and the Fee Page. Every clause names where it is enforced and how it is tested.

| # | Clause (spine C.7) | Enforced by | Test or publication |
|---|---|---|---|
| H1 | Wears a badge and says on whose behalf it acts | `principal` and `badge_text` required; the Presence layer refuses to replicate an unbadged Keeper; certified clients must render it (document 06) | Client conformance suite; audit of 100 encounters a quarter |
| H2 | Excluded from every metric, SLO and the Pool; share published beside the bot share | `Census.count` and `Pool.weight` reject `kpr:`; SLOs, ranking and "active" count humans only | Census, quarterly |
| H3 | Withdraws one-for-one as humans arrive | The cap controller (next section) | Cap breaches per 10,000 place-minutes, published monthly |
| H4 | Holds no Coin, land, vote, Post or Standing | Gateway type rule on `kpr:` | Daily conformance job |
| H5 | Never moderates; may act as a witness | `Safety.sanction` rejects `kpr:`; a Keeper's log may be attached to a report as evidence (document 08) | Daily conformance job |
| H6 | Never messages offline humans; never optimised for session length | Messaging rejects `kpr:` senders to offline recipients, IM, invites and notifications; evaluation metrics may not include session length, return frequency or spend | Evaluation specs published |
| H7 | No companion or romantic loops; scripted-only in Campus | No relationship state in job specs; an output classifier blocks affection or flirtation; Campus Keepers are T0 with no free text | Quarterly red-team report; no T1/T2 endpoints in Campus |
| H8 | Licensed or synthetic voices with provenance | The voice catalogue accepts only entries with a licence or synthesis record | Catalogue published |
| H9 | Memory rules (this document) | Per-human memory only after opt-in (see Regulation and voices) | Deletion latency, quarterly |
| H10 | Crisis routing (this document) | On a stated self-harm intent or emergency the Keeper stops its job, shows regional crisis resources and opens a priority Trust Desk ticket; it never counsels | Routing latency in the quarterly T&S report |

**Published job specs.** Every job's spec, prompt template, tools and evaluation metric is published in the Chronicle (safety filters summarised), and changes are recorded before they take effect: public change review (R19) applied to Keepers.

---

## Caps, withdrawal and quiet Wards

### The cap controller

For each place (a presence namespace, as defined in document 06), every 5 s:

```text
H        = visible humans (excludes Keepers, flagged bots and Nuisance-flagged accounts)
J_open   = Keeper job slots configured for the place that no human holds on shift right now
D_place  = the place's human density target (Ward hub cell ~130; Landing hall 20;
           Holding = its seat cap)
c        = current cap (0.20; 0.10 after a first failed parity read; 0 after a second)

K_max = min( J_open,
             floor( c/(1−c) × H ),      // keeps K/(H+K) ≤ c; at 20% this is floor(H/4)
             max(0, D_place − H) )      // one-for-one withdrawal as the place fills
```

- When K exceeds K_max, the most recently arrived Keeper withdraws first, walking to an exit or back room within 10 s; there is no pop-out. Stand-ins and Greeters that lose their slot drop to Counter mode.
- **Counter mode.** A Keeper that may not be embodied can still serve as a badged interface on its stall, desk or Landing board, with text, client-side voice and the same first-contact notice. It has no avatar and takes no space, so it is not a visible occupant. This is how a Stand-in serves a lone shopper and a Greeter serves a lone 03:00 arrival without breaking the 20% cap (see Open questions).
- **Empty places stay empty.** With H = 0, K_max = 0. No Keeper is ever rendered for nobody, and a Ward hub is never staged to look busy.

**Worked example (Market and Green cell, three Stand-ins enabled, D = 130):**

| Humans H | floor(H/4) | D − H | Embodied Keepers | Keeper share |
|---|---|---|---|---|
| 2 | 0 | 128 | 0 (all three in Counter mode) | 0% |
| 5 | 1 | 125 | 1 | 16.7% |
| 12 | 3 | 118 | 3 | 20.0% |
| 128 | 32 | 2 | 2 | 1.5% |
| 130 | 32 | 0 | 0 | 0% |

### Caps by place

| Place | Default | Maximum if enabled | Who enables |
|---|---|---|---|
| Ward public cells (Stage, Market and Green) | Director, note-taker, Market-stall Stand-ins | 20% | Platform; council may vote 0% |
| Landing halls | Greeter outside hosted hours | 20% | Platform |
| Commons plots | 0% | 20% (Stand-in only) | Plot holder |
| Holdings, Halls and Estates | 0% | 20% | Holder or Charter (`keepers_enabled`, document 02) |
| Hearths | 0% | 0% | Not available |
| Event instances, Event Mode, the Ephemeral Ward | 0% embodied | 0% (unembodied drafting only) | Not available |
| Night Wards and Adult-rated places | 0% | 0% during the experiment | Review after READ_1 |
| Campus | T0 scripted Greeter only | 20% | Institution |
| Quiet Wards | 0%, Director off | 0% | Ward council |

These are the spine's 20%/0% caps: 20% is the ceiling anywhere; 0% is the default wherever a human holds the land or the event is the point.

### Quiet Wards

- **Vote.** A Ward council (5 seats, from L+6) votes its Ward quiet by simple majority, effective within 24 h, recorded in the Chronicle and irreversible for 90 days (this document) so the experiment cannot be gamed.
- **Effect.** No Keeper of any job and the Director off; sky, time and weather keep running because they are environment. The directory shows a "Quiet" tag; Holdings are quiet by default.
- **Personal setting.** Any resident can choose "Hide Keepers" (default off): Keepers render as nothing, their chat is filtered, and a hidden Greeter becomes the self-guided flow. The share choosing it is published in the Census.

**Trade-off.** A strict 20% means no embodied Stand-in for a single visitor; Counter mode is the price. The rejected alternative, one service Keeper per place regardless of H, would show every lone visitor a room that is 50% artificial.

---

## Stand-ins

Stand-ins arrive at L+18, under whatever cap is in force then. They are the one Keeper that acts for an individual, so they carry the most rules.

### Eligibility and set-up

- **Who.** Merchants with a shop on a Holding, Commons plot or Market stall in a General or Moderate place; not Night Wards or Campus (this document).
- **The interview.** About 20 minutes in the Workshop covering catalogue, policies, hours, tone and things never to say. Agents seeded from two-hour interviews reproduced 1,052 people's survey answers at 85% of their own two-week consistency ([source](https://arxiv.org/abs/2411.10109v1)); we use the method for accurate shop knowledge, not to replicate a personality.
- **The Shop Brief.** At most 2,000 words, edited and approved by the resident. The Stand-in may state only what is in the brief, the live catalogue or the Fee Page; otherwise: *"I don't know; I'll leave Mara a message."*

### The apron, not the face

- Badge: "Stand-in for Mara Okonkwo (artificial)".
- It never speaks as the resident in the first person ("Mara usually restocks on Fridays", never "I restock"), and never claims the resident's experiences, opinions or promises beyond the brief.
- It never uses the resident's avatar, face or voice, even with consent; it wears a Common Body "apron" outfit and a catalogue voice.

### Transactions

The Stand-in holds no Coin. A sale is executed as the resident's own vendor sale: the Ledger moves the buyer's Coin to the resident under the normal fee stack. The Stand-in only invokes the sale.

| Limit | Default | Hard ceiling |
|---|---|---|
| Per sale | 2,500 Coin (US$25) | 10,000 Coin |
| Per day | 10,000 Coin (US$100) | 50,000 Coin |
| Discounts, refunds, custom deals | Not permitted | Not permitted |

Limits are design defaults (this document); the resident may set lower values.

- **Fees.** A Stand-in sale is never an in-person Market Day sale: it pays the standard 10% commission even on Saturday.
- **Pool.** The human buyer still counts as a purchaser, because the purchase is real; the Stand-in never counts as a purchaser, attendee or visitor.
- **Logs.** Every utterance and sale goes to an append-only log the resident can read and export and the Trust Desk can read for reports, kept 90 days. Messages wait until the resident next logs in (clause H6).

### State machine

```text
DRAFT ──interview done──▶ BRIEF_PENDING ──resident approves──▶ READY
READY ──resident offline AND shop open──▶ ON_DUTY
ON_DUTY ──resident online in the place──▶ READY            (one-for-one withdrawal)
ON_DUTY ──cap K_max reached──▶ COUNTER (Counter mode) ──slot frees──▶ ON_DUTY
ANY ──confirmed report or limit breach──▶ SUSPENDED ──Trust Desk review──▶ READY | RETIRED
ANY ──resident revokes──▶ RETIRED (log kept 90 days)
ANY ──60 days of resident inactivity──▶ RETIRED (spine rule; the resident may re-enable on return)
```

"Inactivity" means no session by the resident in any client, Reader included.

---

## The Director

The Director ships at L+6, before other Keepers, because it is scripted, has no body and occupies no space: RimWorld's paced, legible events without the AI ([source](https://www.rimworldwiki.com/wiki/RimWorld)).

### What it does

One Director per Ward reads human occupancy by cell, the Civic Calendar, the sky and weather schedule and the Chronicle's open threads, and schedules **happenings** from a library written by staff and by Charters (with Ward council approval). It mostly plays human-written scores.

```text
Happening {
  id, ward_id, author: staff | charter:<id>,
  kind: weather_front | bell | lamps | notice | stage_cue | ambient_fx | scenery_fauna,
  cells: [stage | market_green],          // Ward public cells only
  window: { earliest, latest }, duration_s,
  min_temperament: still | gentle | lively,
  supports_event: event_id | null          // a cue the event owner opted into
}
```

Examples: lamps at dusk; a bell 15 minutes before Market Day; a front that clears before Open Stage; a board line ("Open Stage in 20 minutes: 4 slots, 31 people here"); birds over the Green. Scenery fauna is never humanoid and never counted.

### Rules

1. **Never overrides human events.** No happening runs in a cell from 30 minutes before a Calendar event until it ends, unless the event's owner opted into it as a supporting cue (stage lights, a bell).
2. **Public fabric only.** No happening touches Holdings, Commons plots, Estates or anything a resident owns. It never damages or alters owned content and never moves Coin.
3. **No bodies, no summons.** It spawns no humanoid figures and sends no notifications. Notices appear only on in-world boards and in the Ward's calendar feed.
4. **Temperament** is set by the Ward council:
   - Still: sky and weather only.
   - Gentle (the default): at most 2 happenings per hour per hub cell.
   - Lively: at most 6 per hour per hub cell.

   Quiet Day forces Still, so Wednesdays belong to Charters.
5. **Empty Wards stay quiet.** With no humans in a cell, nothing runs except lamps and weather, which are environment clocks.

### Its own keep rule

From L+6, each Founding Ward alternates Director-on and Director-off weeks for 12 weeks (a switchback test under document 01's lifecycle). It is kept if returning humans in hub cells and Calendar attendance are no lower in on-weeks and complaints per 1,000 user-hours no higher; otherwise it goes to Still everywhere and is redesigned once. Having no body, it lives or dies by this test, not the Keeper kill rule (see Open questions).

---

## Cognition tiers and published costs

### Tiers

| Tier | What runs | Used when | Canonical cost per active agent-hour | Token assumptions (this document; prices are planning values) |
|---|---|---|---|---|
| **T0 scripted** | Behaviour trees, schedules, utility scoring, Director rules; CPU in the Cell | Always: every Keeper's floor; Campus; the Director | ≤ US$0.003 | None |
| **T1 small model** | Small hosted or edge model for short exchanges; Chronicler nightly batch drafts | A human is within talking range of a Greeter, Stand-in or embodied Chronicler | US$0.015 | About 1,500 cached input and 80 output tokens per turn, 30 turns an hour, at about US$0.10/US$0.50 per million tokens, about US$0.006 plus T0; voice synthesised on the client |
| **T2 memorable** | Mid-tier model with Shop Brief, Chronicle and opt-in memory context; hosted voice | A human engages a Stand-in in a sustained exchange (more than 3 turns) | US$0.20 | About 6,000 input and 250 output tokens per turn, 10 turns an hour, at about US$2/US$10 per million, about US$0.15; hosted TTS at about US$5 per million characters ([source](https://arcanumrpgs.com/blog/inworld-ai/)), about US$0.05 |

- **Blended:** at most US$0.02. With 30% of hours at T1, T2 may be at most ~6.8% of hours (0.003(0.70 − x) + 0.015 × 0.30 + 0.20x ≤ 0.02; our arithmetic).
- **Voice.** T1 speech ships as text plus a voice id and is synthesised on the client from the licensed catalogue, which is why T1 fits US$0.015.
- **Active agent-hour:** a Keeper instantiated with a human in range (embodied or Counter mode), or a Director-hour in a Ward with a human present. Tier costs are all-in: cognition, voice, memory store and Cell CPU share.
- **No lock-in.** No vendor publishes a cost per NPC-hour and prices turn over within a year ([source](https://arcanumrpgs.com/blog/inworld-ai/)), so model contracts are month-to-month and the runtime is model-agnostic.

### The 10% ceiling at the D.8 scales

Total Keeper spend is at most 10% of infrastructure plus trust and safety:

| Scale | Infra + T&S (US$M/yr) | Keeper ceiling (US$K/yr) | Agent-hours the ceiling buys at US$0.02 | Average concurrent Keepers | As a share of average human CCU | Binding constraint |
|---|---|---|---|---|---|---|
| Floor, 100K MAU (4,000 CCU) | 0.9 + 1.5 | 240 | 12.0M | ~1,370 | 34% | The 20% occupancy cap (at most 25% of human CCU) |
| Break-even, 350K (14,000 CCU) | 3.1 + 1.6 | 470 | 23.5M | ~2,680 | 19% | Roughly equal to the occupancy cap |
| Reference, 600K (24,000 CCU) | 5.3 + 2.7 | 800 | 40.0M | ~4,570 | 19% | Money, if Keepers ever saturated |

Our arithmetic. Realistic load is far lower: at an assumed 3% of human CCU the Floor spends about US$21K a year.

### Budget enforcement

A per-Ward token bucket and a world monthly budget are set at the ceiling divided by 12. When month-to-date spend projects above the budget, the service degrades in a fixed order:

1. T2 is restricted to Stand-ins with an open sale;
2. T2 turns off;
3. T1 is restricted to Greeters;
4. all Keepers drop to T0;
5. embodied Keepers withdraw.

Disclosure, logs and crisis routing never degrade. Every degrade step is recorded in the Chronicle.

**Publication.** Tier and blended costs, Keeper-hours by job and tier, spend against the ceiling, and the model vendor are republished quarterly from L+12 in the Census, beside the Keeper and bot shares.

---

## AI as tooling

AI that serves humans without inhabiting the world is unrestricted, budgeted in the T&S, Foundry or client lines rather than under the Keeper ceiling. It never appears as an occupant and never decides a sanction.

| Tool | Serves | Rule | Measured by |
|---|---|---|---|
| Report and chat triage | Wardens, moderators, Trust Desk | Ranks the queue; a human confirms every sanction. Roblox's Sentinel caught 35% of detected grooming cases before any report ([source](https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection)) | Time-to-action under 24 h; proactive share |
| Classification at upload | Foundry CSAM, likeness, script and CopyBot checks | Automatic block only for hash-matched illegal content; the rest goes to human review | False-positive and appeal rates |
| Measured translation | Mixed-language groups, the Bridge | Labelled "machine-translated", toggleable; Roblox reports only "stronger engagement", no D30 data ([source](https://about.roblox.com/newsroom/2024/02/roblox-introduces-ai-powered-real-time-chat-translations-in-16-languages)) | D7/D30 of mixed-language groups, on versus off (R29) |
| Foundry inference | LOD chains, impostors, atlasing | Never alters a creator's source asset | Foundry cost of US$0.01 per asset |
| Speech-to-text, text-to-speech, voiced GPS | Reader, deaf and blind residents | On-device where possible; never recorded without consent | XAG 119 checklist (R27) |
| Workshop generative assistants | Creators | Output carries provenance and an "AI-assisted" tag (Roblox Cube-class generators are asset tools, not worlds ([source](https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube))) | Share of AI-assisted listings, published |

The boundary: anything with an addressable name, a body or a presence in a place is a Keeper.

---

## The experiment, holdout and kill rule

### Why an experiment

Spine B.4 item 2 makes Keepers an L+12 experiment "killed if human D30 falls", and the spend sequence puts the Landing first. Keepers get no headcount at L; from L+6 a squad of three is drawn from the Landing and Grid teams within the 60-person cap (this document).

### Design

| Arm | Unit | Treatment | Control | Primary metric |
|---|---|---|---|---|
| **G (Greeter), L+12** | Newcomer cohorts arriving when no human Host is on shift, randomised 50/50 by cohort | Greeter-held Landing | Self-guided Landing (a human-only place) | Human D30, using the Census definition of "active" |
| **S (Stand-in), L+18** | Opted-in Merchants, randomised waitlist (half wait 90 days) | Stand-in on duty | Waitlisted shops | D30 of first-time shop visitors; Merchant D30 and sales |
| **Place exposure** (descriptive only) | Ward hub cells by hour | Keepers present | Matched Keeper-free hours | D30 of exposed humans |

**Sample size.** To detect a 2-point D30 difference around a 15% base, with 80% power at two-sided α = 0.05, requires about 4,700 newcomers per arm: n ≈ 7.84 × (0.15 × 0.85 + 0.13 × 0.87) / 0.02² (our arithmetic). Enrolment runs 90 days or until both arms reach 4,700, whichever is later.

### Keep rule and step-down

The spine's parity test: **human D30 in Keeper places must be at least that of comparable human-only places, or the cap drops to 10%, then to zero.**

```text
L+12  RUN_1 at c = 0.20 (Greeter, Chronicler)
L+16  READ_1: D30(treated) ≥ D30(control)?  (point estimate, pre-registered)
        yes ──▶ KEPT at 0.20; Stand-ins launch at L+18 at 0.20; re-read annually in Census
        no  ──▶ c = 0.10; RUN_2 for 90 days (a Greeter now needs ≥ 9 newcomers to embody)
L+20  READ_2: yes ──▶ KEPT at 0.10 | no ──▶ c = 0: embodied Keepers withdrawn,
        Stand-ins retired, Greeter replaced by the self-guided Landing; Chronicler
        drafts continue only as signed, unembodied tooling
ANY   HARM: at the day-45 interim, treated D7 is below control with the 95% CI
        excluding zero, OR reports per 1,000 Keeper-interaction-hours exceed the
        human baseline by 50% ──▶ SUSPENDED at once (document 01 lifecycle)
```

Every read, step and suspension is published in the Chronicle and Census with arm sizes, confidence intervals and cost. Stand-ins' own read follows the same steps independently. No result can raise the cap above 20%, add a job, extend Campus beyond T0 or count Keepers in any metric; each would need a World Charter amendment.

---

## Regulation and voices

### EU AI Act Article 50

Article 50 transparency duties apply from 2 August 2026. The Commission's final guidelines were published on 20 July 2026 ([source](https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content)). nolife applies them worldwide, not only in the EU:

| Duty | Mechanism |
|---|---|
| People must know they are interacting with an AI system: a plain-language notice or persistent badge, never a generic "assistant" label, saying on whose behalf the agent acts ([source](https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/)) | Badge, "(artificial)" name tag, first-contact notice naming the principal; badge carried in impostors; Reader's spoken notice |
| Providers mark AI output in machine-readable form, layered, with no single watermark deemed sufficient ([source](https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content); [source](https://www.techpolicy.press/the-eus-ai-transparency-code-of-practice-explained/)) | `synthetic: true` plus the KeeperRecord id on chat lines; provenance manifests on synthesised audio; C2PA-style provenance on Workshop assistant output (document 04) |
| Deepfakes must be labelled perceptibly; metadata or a T&C clause alone does not satisfy the duty ([source](https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content)) | No Keeper uses a real person's likeness or voice; the likeness consent registry blocks real-person avatars without verified consent (document 08) |

Signed Chronicle entries still carry "drafted by Chronicler (artificial)".

### Minors and companions

Character.AI banned open-ended chat for under-18s from November 2025 ([source](https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots)); Google and Character.AI settled the Setzer wrongful-death case in January 2026 ([source](https://www.jurist.org/news/2026/01/google-and-character-ai-agree-to-settle-lawsuit-linked-to-teen-suicide)); Italy's Garante fined Replika's maker EUR 5M ([source](https://en.wikipedia.org/wiki/Replika)). The open world is 18+, Campus Keepers are T0 with fixed lines, and no age gets a companion or romantic loop: job specs have no relationship state, and clause H7's classifier backs that up.

### Voices, likeness and labour

- **Precedent.** SAG-AFTRA's NLRB charge over Fortnite's AI Darth Vader (19 May 2025) has no reported outcome ([source](https://news.bloombergtax.com/esg/actors-union-files-labor-charge-over-ai-darth-vader-in-fortnite)). California AB 2602 requires explicit consent for performer digital replicas ([source](https://variety.com/2024/politics/news/sag-aftra-limit-ai-digital-replica-california-bill-1236120379/)). The NO FAKES Act of 2026 (S. 4591 / H.R. 8915) cleared Senate Judiciary in June 2026 but has passed neither chamber ([source](https://www.congress.gov/bill/119th-congress/house-bill/8915)).
- **The voice catalogue** holds only fully synthetic voices with a synthesis record, or voices built from recordings under a written licence naming AI synthesis and revocation terms. No replicas of real performers and no clones of residents, a Stand-in's own resident included.
- **Containment.** If Article 50 guidance or NO FAKES changes the badge or voice rules, only the Keeper service and the catalogue change.

### Data protection of Keeper memory

By default Keepers remember no individual; a Greeter forgets a cohort at handover, apart from the public Chronicle. "Remember me" is opt-in per Keeper, deletable at once, expires after 90 days, never crosses Wards, and is never used for targeting, pricing or training without a separate opt-in. Keepers do no biometric emotion recognition; crisis routing reads explicit text only.

---

## Requirements addressed

| Req | How this document addresses it |
|---|---|
| R25 | Four jobs; badge and principal notice; 20% cap with one-for-one withdrawal; no companion loops; licensed or synthetic voices; T0/T1/T2 costs published quarterly; spend ≤10% of infra plus T&S; D30 parity test (10%, then zero); deferred to L+12 |
| R11 | Greeter tested against the self-guided Landing by randomised cohort; it never replaces a human Host, and it hands over on arrival |
| R12 | Keepers excluded from the density SLO and the newcomer median; K_max = 0 when H = 0 |
| R13 | Keeper share beside bot share; costs, hours and reads in the Census; "active" counts humans only |
| R8 | Keepers excluded from Pool weighting; Stand-in sales are never Market Day in-person sales |
| R9 | Keepers hold no Coin; Stand-in sales run as the resident's own vendor sales under the Fee Page |
| R15 | Director never overrides Calendar events; Quiet Day forces Still; humans sign the Chronicle; no Keeper Posts |
| R19 | Keepers cannot vote or stand; job specs and changes are published in the Chronicle; quiet Wards by council vote |
| R21 | Campus Keepers are T0 only; no companion loops at any age |
| R22 | 0% Keepers in Night Wards and Adult places during the experiment |
| R23 | Keepers never moderate and may act as witnesses; AI triage with human confirmation; crisis routing to the Trust Desk |
| R27 | STT, TTS and voiced GPS as unrestricted tooling; Reader announces Keepers |
| R29 | Machine translation labelled, with its retention effect measured before it is claimed |
| R30 | No Keeper headcount at L; spend ceiling; first to be cut; the experiment gates any growth |

---

## Open questions

1. **Strict 20% and small rooms.** An embodied Keeper needs at least 4 humans present (9 at 10%). Counter mode covers lone visitors, but an unembodied Greeter may test worse, biasing the parity test. We keep the spine's 20%; "one service Keeper per place" is noted for review after READ_1.
2. **Parity on a point estimate.** At 4,700 per arm the 95% CI is about ±1.4 points, so a near-zero effect passes or fails on noise. A pre-registered non-inferiority margin (e.g. −1 point) would be more honest; we keep the spine rule and publish the CI.
3. **The Director and "zero".** The spine lists the Director as a Keeper job yet ships it at L+6. We give it its own test; if "zero" should include it, C.7 should say so.
4. **Is the Chronicler tooling?** Drafting for human signature is close to tooling; we keep the spine's L+12 date to avoid an early AI feature through a definitional gap.
5. **Greeters versus night Hosts.** Document 01 notes 03:00 arrivals have no human Host. Funding night-shift Landing Hosts from the Pool's 10% line may beat Greeters; the descriptive comparison with human-hosted cohorts should inform this.
6. **Pricing after the experiment.** Free Keepers on Holdings scale cost with Holdings; priced Keepers revive the rejected "houses buy slots" model.
7. **Stand-ins and replica law.** Whether NO FAKES or AB 2602 reach interview-seeded agents that use no likeness or voice is unsettled; legal review before L+18.
8. **Night Wards** are excluded from the experiment; review after READ_1.
9. **Price drift.** Tier ceilings are fixed in dollars while token prices fall; we propose fixed ceilings with T2 eligibility published quarterly.

---

## Sources

- Creatures and its player science: https://www.howwegettonext.com/the-brain-in-the-machine/
- Spore retrospective: https://www.gamedeveloper.com/design/spore-my-view-of-the-elephant
- RimWorld storyteller: https://www.rimworldwiki.com/wiki/RimWorld
- Second Life region count, 2025: https://danielvoyager.wordpress.com/2025/01/05/first-2025-main-grid-regions-goes-live-for-second-life/
- Second Life concurrency, 2025: https://community.secondlife.com/forums/topic/523927-whats-secondlifes-real-population-summer-of-2025/
- Quantic Foundry, generative AI sentiment: https://quanticfoundry.com/2025/12/18/gen-ai/
- Imperva 2025 Bad Bot Report: https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/
- Generative agent simulations of 1,000 people: https://arxiv.org/abs/2411.10109v1
- Inworld pricing and NPC-hour cost: https://arcanumrpgs.com/blog/inworld-ai/
- Roblox Sentinel: https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection
- Roblox chat translation: https://about.roblox.com/newsroom/2024/02/roblox-introduces-ai-powered-real-time-chat-translations-in-16-languages
- Roblox Cube: https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube
- EU AI Act Article 50 guidelines: https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/
- Article 50 final rules: https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content
- Code of Practice on marking and labelling: https://www.techpolicy.press/the-eus-ai-transparency-code-of-practice-explained/
- Character.AI under-18 ban: https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots
- Setzer settlement: https://www.jurist.org/news/2026/01/google-and-character-ai-agree-to-settle-lawsuit-linked-to-teen-suicide
- Replika and the Garante fine: https://en.wikipedia.org/wiki/Replika
- SAG-AFTRA charge over AI Darth Vader: https://news.bloombergtax.com/esg/actors-union-files-labor-charge-over-ai-darth-vader-in-fortnite
- California AB 2602: https://variety.com/2024/politics/news/sag-aftra-limit-ai-digital-replica-california-bill-1236120379/
- NO FAKES Act of 2026: https://www.congress.gov/bill/119th-congress/house-bill/8915
