# nolife: a living world first — design proposal from the artificial-life and agent-systems angle

Author role: designer of a-life and AI-agent systems (Sims/Dwarf Fortress lineage). Date: 2026-10-09. Evidence base: `analysis/failure-taxonomy.md` (R1-R30) and nine research briefs (a-life and AI NPCs, community purpose, SL community census, networking and scale, graphics, safety and regulation, business models, legacy interop, SL economy). Numbers not in those files are design targets and are marked as such.

---

## 1. Thesis and premise

**The name is the failure we are designing against.** Second Life's residents have a phrase for the grid in 2026: "So beautiful. So empty." Roughly 1,820 km² of land against a ~49,000 peak concurrency is about one or two avatars per region at the busiest hour (Source: https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/ ; https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/). That is *no life*: a place that does not move when you are not looking and does not notice when you arrive. "nolife" is also the old insult for people who spend their evenings in virtual worlds. We take the name the way Burners took "burner": the world where having no life is impossible, because the place is alive and keeps a record of you.

**Premise.** nolife is a persistent, adult, self-owned, scriptable world with a real economy and cash-out, the four pillars nobody except SL, OpenSim and Resonite currently combine (taxonomy 1.9). It differs from every predecessor in one design commitment: **every open place runs on its own clock whether or not a human is present, and the world remembers.** A district has weather, seasons, a daily rhythm, resources that regrow at a limited rate, inhabitants with jobs and memories, and a Chronicle of what happened there. When you walk in at 03:00 on a Tuesday the baker is opening, the lamps are lit, someone (disclosed as artificial) knows you were here last week and that your crew finished the pier. When six humans arrive, the artificial inhabitants step back into the back rooms and the humans run the place.

**What the evidence says this can and cannot do.** The taxonomy is blunt: nothing in the corpus shows agent-filled density retaining humans; agents change "what an empty room looks like, not whether people have a reason to be in it" (taxonomy section 3, R25). I build around that finding. nolife's purpose engine is human: crews, roles, scarce land, a calendar, assemblies (R11, R15, R16, R19). The living layer has three narrower, measurable jobs: (1) the *off-peak* problem, so a venue with a Tuesday-morning audience of two is not dead; (2) legible, story-generating places in the Dwarf Fortress and RimWorld sense of cheap visible systems plus a pacing director (Source: https://www.rimworldwiki.com/wiki/RimWorld); (3) the "return" loop that Animal Crossing's real clock and dumb villagers delivered better than any learning AI (alife brief, pattern 1). It never substitutes for people in metrics, governance or the economy.

**Why a-life failed before.** Creatures, Black & White and Spore made one creature interesting and never made a place necessary; The Sims Online put humans in the Sim slots and removed the control loop its audience was buying; SL's breedables died with one vendor's food server (alife brief, patterns 1-4; Source: https://boingboing.net/2017/05/20/breedables-vs-drm.html). Section 8.7 states how nolife inverts each.

**Guardrails are part of the thesis, not an appendix.** Hostility to generative AI is concentrated in exactly the social players nolife targets (63% of 1,799 Quantic Foundry respondents chose the most negative option) and EU AI Act Article 50 applies from 2 August 2026 (Source: https://quanticfoundry.com/2025/12/18/gen-ai/ ; https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/). So: every artificial inhabitant is badged, has a job, is capped, withdraws as humans arrive, costs a published amount, and is never counted as a person, never holds money or land, never votes, never moderates, never forms a companion loop with a minor, and never exists to maximise your session (section 8).

---

## 2. Who comes first and why

The wedge is the communities the SL census identifies as institution-shaped (group, roles, ban list, land, calendar), because whole communities move on institutional continuity and a credible persistence guarantee, and individuals do not (census brief, section 5). Each is recruited through its named leader with a charter import (R18) and a dual-presence window.

**Wave 1 (closed alpha, five named institutions).** 1) **OpenSim refugees and educators.** OSgrid wiped its database in 2025 and was offline for weeks in 2026; its users already know how to pack an OAR (Source: https://www.hypergridbusiness.com/?p=79686). Day one: OAR/IAR import, a class region at US$39/month, institutional SSO, a written persistence covenant (R28, R20). 2) **Virtual Ability** (1,000-1,300 members; Cape Able text-first). Day one: the first-party text client with voiced GPS and chat captions (R27), because they cannot come otherwise. 3) **Live-music venues** of the Cafe Musique type (60+ shows a week). Day one: parcel stream URL, host/DJ roles, tip rails with charity splits, and a *Keeper* door host who keeps the schedule, queue and greetings while the human host sleeps (the "staffed venue" finding, Source: https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2). 4) **Roleplay estates** (1920s Berlin, Crack Den, Gor-style): whitelisting, access and ban lists, ranks, HUD meters, damage parcels, paid queue priority (R17), plus a living town: disclosed artificial townsfolk with memory, so a Berlin street is populated at 06:00 CET. 5) **Event institutions** (BURN2, Fantasy Faire, Second Pride, VWBPE): temporary multi-region estates, performer scheduling, and the annual scarce ritual region (R15, R16).

**Why they come.** Each gets what SL never supplied: schedule and roles as objects, a venue that is never unstaffed, a persistence guarantee in writing, and institutional continuity in one transaction, without abandoning SL during a 12-24-month bridge (R18).

**Wave 2 (public launch).** Furry and avatar-identity communities (Luskwood's 40,000+ customers) via VRM/glTF import and a first-party open-licensed body; the broader SL adult-roleplay economy once the Adult district and gated commerce are live (R21, R22); OpenSim grid operators as self-hosted cell operators (R20).

**Wave 3 (months 12-24).** Language shards: Portuguese, Spanish, Japanese and German districts with paid localisation and local rails (R29), recruited through the volunteer gateways SL abandoned in 2010 and Japan's VRoid/BOOTH pipeline (taxonomy 1.8).

**Migration mechanics.** A leader applies; a paid migration engineer runs the charter import and OAR conversion at platform cost; the community gets a 90-day rent holiday and a first event on the civic calendar with a Keeper holding the door. Target: ten named SL institutions migrated with membership by month 18 (R18 test).

---

## 3. The purpose engine

Purpose is supplied by other people attached to a time and a place (community-purpose brief, pattern 1; taxonomy 1.4). nolife's engine has six parts; the living world supports each but owns none.

**Institutions.** A **crew** is 3-12 people with a shared hall, a crew log in the Chronicle, 2-10 roles and one Apprentice (section 8). A **house** is a chartered institution (venue, estate, congregation, school) with land, a calendar, a treasury and a named deputy for every role that owns land or a calendar (R15). A **district** is a public place with an elected assembly. The substrate is SL's group model, on which every durable community was built (Source: https://wiki.secondlife.com/wiki/Group), plus what it lacked: a schedule, a deputy and a treasury.

**Roles.** Host, mentor, DJ, moderator, builder, judge, chronicler, migration engineer and tide-warden are objects with slots, badges, a stipend (in marks with fiat shown, R9) and succession rules; ≥80% of venues must survive a leader's 90-day absence (R15 test). A Keeper may fill an unfilled slot in degraded form (hold a door, keep a queue, read notices) but never mentor, moderate or judge.

**Scarcity.** Public land in prime districts goes by lottery with full-price tickets and a 45-day use-it-or-lose-it rule with refunds and a published pause policy (FFXIV's model, R16; Source: https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1). Private homes are rented and never auto-demolished. Some items are never reissued (Habbo rares; Source: https://www.habbo.com/community/article/22292/update-state-habbo-economy). The ecology adds a third scarcity: species populations are capped by tended habitat (section 8), so a breeder needs land and a crew.

**Events and calendar.** Day one: a weekly rhythm (Market Day Saturday, Open Stage Friday, Assembly Sunday, Tides daily) and one annual ritual, **Emberfall**, a region that exists for one week a year and is burned at the end (BURN2's lesson; Source: https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/). First-party events run as synchronised ~100-avatar instances (R15); the Almanac (section 8) fills gaps between human events.

**Governance.** A published charter with 12 months' notice and grandfathering, public change-review, and an elected Grid Assembly answered in writing (R19); EVE's CSM turnout of 12-17% is the benchmark (Source: https://www.eveonline.com/news/view/heres-your-csm-20). Districts set their own rules within the charter.

**Status.** Status is written, not bought: Chronicle entries, titles earned through roles, a house's calendar longevity. The Chronicle is public; a newcomer reads a district's last week before arriving.

**The first hour.** Every account lands on a **Tide**: every 20 minutes a boat reaches the Harbour with 6-12 newcomers, a paid human tide-warden and a badged Keeper guide (R11). Before any scripting panel the newcomer has a dressed avatar on the open-licensed body and a furnished room in a crew hall (R26). The Tide's first task is a shared ten-minute job (relight the pier lanterns) that puts every name in the Harbour Chronicle; the warden then walks the cohort to the next Assembly or Open Stage. Success is "met a person or joined a crew", measured by randomised holdout against the industry D30 base; if the lift is absent the Tide is redesigned, not defended (R11 test). The Keeper guide ensures nobody stands alone and withdraws when a human mentor takes over.

**The first year.** Visitor (free, a room in a shared hall) → resident (subscription, a home) → crew member (a shared hall and an Apprentice) → role holder (host, DJ, mentor, with stipend) → steward of a house (land, calendar, deputy) → district assembly candidate. Each step is a badge and a Chronicle entry; D7/D30/D90 by rung is published from month six, since the group-retention effect has never been measured (taxonomy 1.4, R13).

---

## 4. World structure

**The Archipelago.** nolife is islands, not a continent: each a *district* (public) or an *estate* (private), made of cells of 50-150 simulated avatars under a presence layer showing 500-1,000 (R1), connected through harbours where Tides arrive. No contiguous mainland means no 27,000-region map to feel empty in.

**Land model.** Land is rented, never sold, priced by area and content budget, with no setup fee (R6): Garden plot (a home, 512 m²-equivalent, 2,000 budget units) is included in a Resident subscription; Homestead (1 ha, 20 avatars, 15,000 units) US$25/month; Estate (one full 150-avatar cell, 60,000 units) US$99/month; Estate+ (two cells, event mode) US$149/month; Campus region (education, General-rated, OAR export) US$39/month. SL's full region is US$199-209/month plus US$349 setup (Source: https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/), OpenSim's US$8-40 (Source: https://www.hypergridbusiness.com/2015/04/digiworldz/); nolife sits between, because persistence rent is load-bearing (taxonomy section 5 arithmetic). Sub-letting at a markup is not permitted; houses may allocate space to members at cost. Public parcels go by lottery (R16).

**Persistence.** Every object is a document plus an event log with per-cell and per-creator write budgets, nightly snapshots, and owner rollback to any of the last 30 days (networking brief, implication 5). Nothing a resident made is deleted for non-payment: lapsed land is packed into inventory as an OAR-like bundle and re-rezzed when rent resumes.

**Density management and the Liveliness Floor (R12, R25).** Public hubs target one avatar per 0.1 ha at peak. Each open public cell publishes a floor of eight visible inhabitants. Humans fill it first; Keepers fill the remainder up to 50% of visible occupants at peak and six of eight at the quietest hour, withdrawing one-for-one as humans arrive, with narrative cover (the florist goes to the back). Thin instances merge; a district under the floor for 14 days **goes to seed**: it closes, its plots are bundled to their owners and the ecology reclaims it. Reopening is a civic event the Almanac schedules and a crew must sponsor. Newcomers are routed to live events, never a quiet cell (R12).

**Places that change.** Seasons on the real calendar, weather per district, paths worn where people actually walk (desire lines from presence data), gardens that overgrow untended, buildings that need a crew's upkeep or decay to picturesque ruin. Change is slow (weeks), reversible, never destroys owned content, and affects only public fabric and the look of neglected plots.

**Discovery.** Three channels, none algorithmic feeds: the Chronicle (what happened where, last 7 days), the civic calendar, and "where my people are" (crew and house presence). Language is a shard key: districts declare a language and newcomers see theirs first (R29).

---

## 5. Creation and creator economy

**Tools.** Two interfaces: a consumer client and a separate Workshop (R26). In-world building keeps the SL virtue of making things where you stand (parametric blocks, snapping, group build rights) and adds glTF 2.0 import, VRM 1.0 avatars and OpenUSD scene import as the canonical formats (R3; legacy brief, implication 2). Scripting is Luau in a sandbox with per-owner CPU, memory and network budgets that throttle the worst offender rather than starving every script (R5), plus WASM for heavier systems and an LSL layer (section 10). Generative tooling (text-to-mesh, texture synthesis) is a Workshop assistant whose output carries a provenance manifest and an in-world "AI-assisted" tag; it feeds the simulation, never replaces it (alife brief, implication 11).

**Ownership.** Creators own what they make. The licence is one page: the platform may display, cache, transcode and back up content to run the service; any other use needs a defined affirmative opt-in (the 2013 ToS lesson; Source: https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/). A creator-set Export bit, honoured by every client, ships their own work out as glTF/VRM/USD. No platform model trains on creator content without opt-in.

**Monetisation and take rates (R7, R8, R9).** One closed currency, the **mark**, at a fixed 100 marks = US$1 with the fiat price shown beside every mark price, exact-amount purchase, no bundles, no chance mechanics paying anything transferable, stipends displayed in fiat (CPC Key Principles; Source: https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr). Fee stack, published on one page with the platform's required margin beside it: 10% commission on primary sales, 0% on resale, a 2.5% spread on buying marks, a 2.5% cash-out fee; all-in ≤15% round trip against SL's user-estimated 20-31% (Source: https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/). Billing is first-party on web and PC; app stores are top-up channels only. A **creator and venue pool** of 25% of platform net revenue is paid monthly, weighted by returning purchasing users per creator and house, 15% reserved for houses that keep a calendar, with Epic's November 2025 anti-farming rules (purchasers only, per-place retention; Source: https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items). Keeper traffic can never earn a payout.

**Cash-out (R10).** Payout runs on a licensed, partnered money-transmission rail (the Tilia lesson; Source: https://modemworld.me/2024/04/26/summary-of-tilia-acquisition-lab-gab-sl-round-table-news/), with KYC, W-9/W-8 and DAC7 data collected before the first payout, and an adult-specialist acquirer pre-qualified in reserve.

**Portability.** Own-created inventory exports as glTF/VRM/USD with signed licence metadata; the marketplace is an open protocol that third-party stores (a BOOTH-style off-platform market) can list into, reversing SL's 2009 Xstreet lock-in (economy brief, implication 7).

**UGC moderation.** Every uploaded asset and script is machine-reviewed before it is served; upload, scripting, voice and proximity rights are earned through behaviour-based trust ranks that idling and mass-friending cannot raise (R23; Source: https://docs.vrchat.com/docs/vrchat-safety-and-trust-system). Adult-tagged goods need uploader verification, consent records and pre-publication review, with a deindex-but-sell switch for processor pressure (R22); real-person likenesses need verified consent (NO FAKES-ready).

---

## 6. Graphics and client strategy

**Fidelity target.** "Best feasible in 2026" means the Unreal 5.8 look running on the hardware the audience owns: the modal Steam GPU is an RTX 5070 with a far weaker long tail (Source: https://www.digitalcitizen.life/nvidia-rtx-5070-most-popular-gpu-steam-hardware-survey-september-2026/), ~50% of SL users lack high-end machines (Source: https://modemworld.me/2025/01/02/), and Epic's 2026 investment went into Lumen Lite and MegaLights for Switch 2-class devices (Source: https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available). Fidelity is a budgeting problem before it is a rendering problem (graphics brief, pattern 1).

**Three tiers, enforced server-side (R2).** *Reference* (RTX 4060/5060-class, 1080p-1440p with DLSS/FSR/XeSS, 60 fps): Nanite, Lumen, MegaLights, Substrate, optional path tracing. *Lite* (Switch 2, Quest 3, M-series Mac, mid Android, 60 fps): Lumen Lite-class GI, probe lighting, SSR. *Compat* (WebGL2, low Android, 30 fps): baked lighting, a 200-500 stud-equivalent draw distance. Avatar ranks per tier: Reference ≤70,000 triangles and 8 materials, Lite ≤20,000 (VRChat's Quest cap; Source: https://docs.vrchat.com/docs/vrchat-202115), Compat ≤7,500. Every asset carries all three budgets; the pipeline auto-generates LODs, impostors and transcoded textures on upload; over-budget content is impostored or hidden, never rendered twice.

**Frame budgets (Reference, 16.6 ms).** World 6.0 ms, avatars 5.0 ms (up to 100 visible; impostors beyond 30 m), lighting 3.0 ms, Keepers and crowds 1.0 ms (MetaHuman Collections-style crowds, which Epic claims reach hundreds on mobile), UI and post 1.6 ms. Lite 16.6 ms with avatars capped at 40 visible; Compat 33 ms.

**Engine and clients (R4, R14, R20).** First-party desktop client on UE 5.8 for Reference and Lite; a WebGPU browser client (Babylon.js, WebGL2 fallback) for Compat and zero-install visiting; native mobile within 12 months; VR as an optional view that never gates identity or inventory (~1.77% of Steam users have a headset; Source: https://rec0ded88.com/statistics/vr-gaming-headset-ownership/). Content is engine-neutral (glTF/VRM/USD), the protocol is documented, third-party clients are blessed, and the engine exit cost is written down: the simulation server has no engine dependency. Pixel streaming is a time-capped funnel at a published ~US$1.75/streamed hour (taxonomy section 5).

**Living-world rendering.** Seasons, weather and time of day are first-class environment state, not per-parcel settings, so the world looks different on return. Gaussian-splat captures serve as backdrops with proxy collision (≤500K splats on Lite) for scanned real venues and memorials. Keepers use player budgets; an over-budget Keeper is hidden exactly as an avatar would be.

---

## 7. Architecture

**Two-layer world model (R1).** A presence layer (position, pose, voice, chat at 5-10 Hz, interest-managed through relays) shows 500-1,000 avatars per place, and a simulation layer (physics, scripts, vehicles, Keepers) is sharded into elastic cells of 50-150 avatars. Published SLOs: 100-150 per cell with voice; 500-1,000 per contiguous place; 2,000-5,000 only in a declared event mode with impostors and pre-mixed audio. We do not promise 10,000; the observed ceilings are 4,144-4,500 at scripted events and ~500 per Star Citizen shard after a decade (Source: https://www.mcvuk.com/business-news/tennis-for-two-thousand-the-story-behind-improbables-mass-event-in-scavlab/ ; https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27).

**Cells and the entity store.** Cells are containerised, stateless simulation servers behind an authoritative entity store with a replication layer (Star Citizen's pattern), so a cell crash is a reconnect, not a lost place. Cells deploy from one manifest to two providers from day one (Edgegap at ~US$0.069/vCPU-hour and GameLift Servers at ~US$0.055), because vendor disappearance, not price, is the top infrastructure risk (Hathora, 2026; Source: https://edgegap.com/blog/announcement-offering-changes-for-2025 ; https://aws.amazon.com/gamelift/servers/pricing/ ; https://gamesbeat.com/?p=318174). Voice sits behind an abstraction that can swap ODIN (EUR 0.29 per peak user per month), the Discord Social SDK or a self-hosted SFU (Source: https://odin.4players.io/pricing).

**Persistence.** Documents plus an event log, per-cell write budgets on the Roblox pattern (60 + 10 × players requests per minute; Source: https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits), snapshots, owner rollback, escrowed server images and self-hostable cells with an annual restore test (R20).

**The Keeper runtime.** Agents do not live in cells. A separate Keeper service owns each agent's memory and cognition tier and streams intents (go here, say this, do this job) to the cell, which applies them under the same physics and script budgets as a player; a cell that loses the service degrades to scripted routines. The Almanac (one process per district) reads only aggregate state. Closed districts are not simulated; they advance by a coarse ledger tick every ten minutes, the Dwarf Fortress off-screen abstraction.

**Cost per CCU.** Compute US$0.002-0.005 per avatar-hour before voice and persistence, voice ~EUR 0.01 per hour for a 30-hour user, Keepers per section 8. A 10,000-CCU world runs at roughly US$50-100 per hour of server cost (networking brief, section 8). Infrastructure plus trust and safety is budgeted at US$1.5-3 per DAU per month, against Roblox's automated floor of ~US$0.9 (Source: https://app.edgar.tools/companies/RBLX).

**Scaling plan.** Launch at 5,000 CCU (50 open cells), 150-avatar cell load test with voice before launch (R1 test), 20,000 CCU by month 12, 60,000 by month 36 (SL's 2020 human peak was 60,068). Scaling is horizontal; the only shared services (entity store, Chronicle index, Keeper memory store) are sharded by district.

---

## 8. AI and the living world

This section is the angle: what the living layer is, what it must never do, what it costs, and why it succeeds where Spore, The Sims Online and the breedables failed.

### 8.1 Inhabitants: Keepers with jobs

A **Keeper** is a disclosed artificial inhabitant with a job, a home, a schedule and a memory. Jobs are what a staffed venue and an inhabited town need: door host, stage manager, shopkeeper, groundskeeper, ferry pilot, archivist, watchman, apprentice. A house buys Keeper slots the way it rents land; public districts get a platform-funded allowance up to the Liveliness Floor. A Keeper's loop is Animal Crossing's made explicit: a routine on the real clock, needs tied to the ecology (the baker needs the mill's flour), and relationships stored on a public "who I know" page.

**Memory and the Chronicle.** Each Keeper has an episodic memory (summarised nightly) and reads the district Chronicle, the public event log humans and Keepers both write to: the mechanism Smallville demonstrated and Proxi bet on (Source: https://the-decoder.com/sims-running-on-chatgpt-are-a-glimpse-into-the-social-future-of-ai/ ; https://gamesbeat.com/will-wrights-gallium-studios-raises-6m-to-build-memory-game-proxi/). Memory about a specific human is deletable by that human, never used for targeting, and never shared across districts without their consent.

### 8.2 The Almanac: a director, not an agent

Emergence needs legibility and pacing (alife brief, pattern 3). Each district runs an **Almanac**, a RimWorld-style storyteller that reads aggregate state (occupancy, ecology stocks, calendar gaps, open threads in the Chronicle) and schedules low-stakes happenings that need humans: the mill is short of grain, so Market Day pays double for wheat; a storm downed the pier lanterns before Friday's Open Stage; a herd crosses the north meadow on the 14th. It cannot destroy owned content, move money or override human events on the calendar; it fills gaps by published amounts, and the district assembly can vote its temperament (quiet, lively, dramatic).

### 8.3 Ecology and the economy of living things

**Living Ecology.** Districts have flora, fauna, weather and resources with a limited daily yield (Animal Crossing's hook), regrowth curves and habitat that must be tended; untended land goes wild. It is the a-life layer humans touch most, and it is cheap: cellular and statistical simulation, no language models.

**Lineage: breedables done right (R24).** Creator-designed species register with the platform's Lineage service, which hosts genetics, "food" and life-support for every value-bearing creature. A vendor's exit bricks no animal: the service converts the species to a food-independent "perma" state on a published schedule, the fate KittyCatS owners could buy and Ozimals owners could not (Source: https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/). Designed sinks stop trait inflation: a district's live population is capped by tended habitat, new traits emerge only through registry slots the Almanac opens seasonally, and over-bred lineages collapse as a legible Chronicle event. Breeding chance is permitted because no random outcome pays marks; creatures sell under the normal fee stack (R9).

### 8.4 Companions, crews and Stand-ins

**Apprentices are crew property, not personal companions.** Each crew may have one Apprentice: a Keeper that lives in the hall, keeps the log, greets visitors and remembers the crew; it belongs to the group so the bond is social, not solitary. Open-ended personal companions are not offered in v1: Character.AI's under-18 ban, the Setzer settlement and Italy's EUR 5M Replika fine make the solitary companion loop a liability we decline (Source: https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots ; https://www.jurist.org/news/2026/01/google-and-character-ai-agree-to-settle-lawsuit-linked-to-teen-suicide). Romantic or sexual Keeper behaviour is disabled everywhere; the Grid Assembly may revisit adult-only companions in year three, once safety KPIs have two years of history.

**Stand-ins (year two).** A resident may leave an opt-in Stand-in to tend their shop or hold their venue's door while offline: a Keeper seeded from an interview with the resident, the method of the 1,052-person generative-agent study (85% of participants' own two-week consistency; Source: https://arxiv.org/abs/2411.10109v1). A Stand-in wears the resident's apron, not their face: badged "Stand-in for X (artificial)", it cannot speak as the resident in the first person, cannot transact above a resident-set limit, keeps a full log, and is withdrawn after 60 days of inactivity.

### 8.5 The Human Primacy Charter: what AI must never do

Published on the fee page and enforced in code:

1. **Disclosed, always.** A persistent ring badge, "(artificial)" on the name tag, a plain-language first-contact notice naming on whose behalf it acts (house or platform), per AI Act Article 50; never a generic "assistant" label (R25).
2. **Never counted as a person.** Keepers are excluded from every published metric; concurrency, density SLOs and the pool count humans only; the Keeper share of occupants is published beside bot share (R13, R25).
3. **Capped and withdrawing.** ≤50% of visible occupants in any public cell at peak, zero in Adult districts' private rooms, and one-for-one withdrawal as humans arrive.
4. **No money, no land, no vote.** Keepers hold no marks, own nothing, list nothing and earn pool payouts for nobody; Lineage creatures are the only artificial things with value, and humans own them.
5. **No moderation.** A Keeper may flag and may be a witness (its log is evidence under R23) but never adjudicates, kicks or bans.
6. **No hollow engagement.** No Keeper messages an offline human, sends notifications, flatters or is optimised for session length; its objective is its job and the place's state. The R25 holdout is the audit: if human D30 in Keeper-filled places falls below human-only places, the cap is lowered.
7. **No minors.** The main world is 18+ (section 9); the Campus tier gets scripted Keepers only, with no open-ended dialogue.
8. **Licensed voices and faces.** Keeper voices are synthetic with provenance or licensed under bargained terms; no replica of a real performer or resident without verified consent (the Darth Vader charge and NO FAKES; Source: https://news.bloomberglaw.com/tech-and-telecom-law/actors-union-files-labor-charge-over-ai-darth-vader-in-fortnite).
9. **Opt-out districts.** Any district may vote to run with zero Keepers ("quiet districts"); 63% hostility deserves a door marked exit.
10. **Published cost.** Every tier's cost per agent-hour is public and the total Keeper spend stays ≤10% of the safety-plus-infrastructure budget (R25).

### 8.6 Tiered cognition and the cost per agent-hour

No vendor publishes a cost per NPC-hour (alife brief, open questions), so nolife publishes its own from first-party API list prices as of October 2026 (small hosted model ~US$0.10 input / US$0.50 output per million tokens; mid-tier US$2 / US$10; frontier US$4-10 / US$20-50; batch at half price), re-published quarterly:

| Tier | What runs | When | Published cost per active agent-hour |
|---|---|---|---|
| T0 Routine | Behaviour trees, utility AI, schedules, ecology; CPU in the cell | Always, for every Keeper | ≤US$0.003 (a fraction of an avatar-hour's compute) |
| T1 Ambient | Small hosted or on-device model for short talk; ~1,500 cached input + 80 output tokens per turn, 30 turns/hour, one nightly reflection | When a human is within talking distance | ~US$0.01-0.02 |
| T2 Memorable | Mid-tier model with Chronicle and memory context, ~6,000 input + 250 output tokens per turn, ~10 turns/hour | Only when a human engages a named Keeper, Apprentice or Stand-in | ~US$0.15-0.25; frontier models reserved for Almanac planning in nightly batch |

Budget check at reference scale (150K DAU, ~8,000 average concurrent humans, 160 open cells, ten Keepers each): ~1.15M Keeper-hours a month, 30% T1-active and 2% T2-active, ≈ US$3.5K + US$5.2K + US$5.8K ≈ US$15K a month, 3-6% of a US$225-450K infrastructure-plus-safety budget. Closed districts cost nothing. If prices double, T2 eligibility narrows; disclosure never does.

### 8.7 Why this succeeds where the precedents failed

Spore's creatures were decoration; Keepers have jobs whose neglect shows in the Chronicle. The Sims Online took the god-view away; nolife returns it as stewardship: humans run crews, houses and the Almanac's temperament, Keepers do the chores. Black & White's creature was illegible; every Keeper's memory and schedule are inspectable pages. Creatures' community lived on forums; nolife's ecology and Lineage registries live where the community meets. Breedables died of one vendor's server; Lineage is escrowed with a designed end-of-life. And unlike Horizon's empty rooms, nolife never pretends: an empty room is a room with badged staff, which is what a real shop at 06:00 looks like.

---

## 9. Identity, safety, governance, regulation

**Age and audience.** The main world is 18+ with a private age band bound to a pseudonymous public identity: on-device facial estimation or a wallet credential (the EU age-verification app), never a stored ID image, since Discord's 70,000-ID breach came through the human appeals vendor (Source: https://cyberinsider.com/discord-confirms-70000-government-ids-exposed-in-third-party-breach/). Age assurance is a configurable regional module with per-region thresholds and profiles for the UK, EU, Brazil, Indonesia and Texas (R21). A 13+ **Campus** tier exists only on isolated, institution-hosted regions (SSO, bulk accounts, General rating, no open-ended Keeper chat, parental surfaces). Adult districts are gated by an Ofcom-grade check that also unlocks Adult-tagged commerce; adult spend and cash-out are instrumented from day one and the rail contract names its adult policy (R22; Source: https://www.theregister.com/2025/11/21/ofcom_osa_fine_undress/). nolife's stated primary purpose is creation and play, with Australia's "primary purpose" test in view (Source: https://www.esafety.gov.au/node/2109).

**Embodied safety (R23).** Personal boundary default-on, one-gesture mute/block/vanish, instance kick and lock, a rolling evidence buffer attached to any report, behaviour-earned trust ranks gating upload, voice, scripting and proximity, and consent prompts for any avatar-to-avatar action (Bloodlines' bite consent as the pattern). KPIs (reports per 1,000 user-hours, median time-to-action under 24 hours) are published quarterly with audit logs ready for information requests, because Ofcom fines un-evidenced compliance as readily as non-compliance (Source: https://xident.io/blog/age-assurance-evidence-ofcom-information-request-second-fine-2026/). Proactive detection is budgeted before capacity; Keepers are witnesses with logs, never judges.

**Pseudonymity.** Display names are free and changeable; verification is private and banded; no real-name requirement ever (Meta's 2020-2022 reversal is the precedent).

**Community self-rule and appeals.** Houses hold access and ban lists; districts hold assemblies with published turnout; the Grid Assembly is elected annually and answered in writing (R19). Platform sanctions carry a human-reviewed appeal with published median time and reversal rate. Change control: 12 months' notice and grandfathering on persistence prices, public change-review for client-affecting updates, zero retroactive repricing (the Openspace lesson; Source: https://forums-archive.secondlife.com/356/24/291220/1.html).

**Economy law.** No chance mechanics paying anything transferable, no tokens or NFTs (Steam distribution and Howey exposure), fiat shown everywhere, DAC7 and 1099-K data at payout onboarding (R9, R10). Headset biometrics are processed on-device, only abstracted animation data leaves, consent-only, never sold.

---

## 10. Legacy support

**Principle: preserve, don't replace.** Habbo Origins and Club Penguin Rewritten inherited communities by keeping what the community was; Sansar inherited nothing because it carried no inventory, identity or social graph (taxonomy 2.1). nolife carries the institution and the creator's own work, and is honest about what it cannot carry.

**Imported.** 1) **Charter import** (R18): group name, roles and abilities, opt-in member list, ban list, maturity rating, calendar and land allocation in one transaction, the leader as owner. 2) **OAR/IAR import** on day one: terrain, parcels, prims, sculpts and llmesh geometry converted to glTF, textures, and LSL script text (legacy brief, implication 1). 3) **LSL compatibility layer**: LSL runs under the Luau sandbox through a transpiler with budgets, covering the common 80% (chat, touch, timers, animations, permissions, HTTP) with a published unsupported list, so vendor HUDs and meters are re-registered, not rewritten. 4) **Avatars**: VRM 1.0 and glTF import for VRoid, VRChat-exported and Resonite avatars; a first-party open-licensed Bento/BOM-class body so SL migrants are not naked; a vendor programme inviting SL mesh-body makers to license Export-enabled versions, because rights, not formats, are the barrier (legacy brief, pattern 2). 5) **Content export from SL** is limited by SL's own rule (creator of every part), and nolife says so plainly: you bring what you made.

**Re-made.** VRChat worlds (Unity scenes) and Sansar content are rebuilt, with a port bounty from the creator pool for the first 200 community venues. SL's Linden Homes and mainland have no equivalent; the Harbour and Garden plots replace them.

**Bridged.** A 12-24-month SL bridge: a registered scripted agent in an SL region relays group chat and event notices both ways, the civic calendar syncs with SL listings, and a house can run the same show in both worlds (R18). OpenSim grids may run nolife cells on their own hardware as self-hosted estates with hypergrid teleport to their old grid (R20).

**Guarantees.** Persistence in writing, 12 months' notice before any shutdown with escrowed images and annually tested export tools, platform-funded conversion for any retired format with 24 months' notice (R3, R20); breedables and vendor-dependent HUDs migrate onto Lineage and the escrow API (R24).

---

## 11. Business model and go-to-market

**Money in.** Six lines, published annually (R6): Resident subscription US$9.99/month or US$99/year (a Garden plot, 10 GB inventory, a stipend shown in fiat); Resident+ US$19.99/month (a Homestead, 50 GB, an Apprentice slot); land rent per section 4; activity metered near cost (visitor-hours beyond a house's allowance at US$0.01, event mode at US$0.02, Keeper-hours per section 8); a 10% primary-sales commission and 2.5% spreads each way; the Campus tier. **Reference-scale arithmetic (600K MAU, 150K DAU, US$100M/year of new money in, the taxonomy's reference).** Subscriptions: 12% of MAU at ~US$110 = US$7.9M. Rent: 12,000 Homesteads/gardens at ~US$20 and 6,000 estates at ~US$110 = US$10.8M. Activity and Keeper metering: US$2M. Commission on ~US$50M of primary sales: US$5M; spreads on US$100M in and US$40M out: US$3.5M. Campus: US$0.7M. Total ≈ US$30M. Costs: 110 staff at US$150K loaded = US$16.5M; infrastructure plus trust and safety at US$1.5-3 per DAU-month = US$2.7-5.4M; payments ~3% = US$3M; creator and venue pool at 25% of net revenue ≈ US$6.7M. Total ≈ US$29-32M. Rent plus subscriptions are ~62% of revenue, meeting R6's ≥50% test, and the creator-facing take stays near 15% only because rent carries the platform (taxonomy section 5). The margin is thin by design: Linden's model with a published fee page and an activity line that grows with crowds, not acreage.

**Funding posture (R30).** US$45M over 36 months to self-funding at ≤600K MAU; a headcount cap of 110; a written survival configuration of 40 staff and US$7M a year that 100K MAU (~US$5.5M of recurring revenue plus rent) nearly covers; no sibling product; growth features (Stand-ins, event mode at 5,000, further language shards) funded only once rent and subscriptions cover costs. Subsidy collapse is the strongest death pattern in the corpus (taxonomy 2.2 #1), so the plan assumes the money stops at month 36.

**Go-to-market.** Zero paid acquisition: at ~1-2% payer rates mobile CPIs imply US$75-300 per payer (Source: https://liftoff.ai/?p=34267). Growth comes from migrated institutions, invites that land the invitee on the inviter's crew Tide, postable rituals (Emberfall is designed to be clipped), and the OpenSim and SL bridges. Sequencing: five institutions in alpha, fifty whitelisted estates and twenty institutions by month 12-18, four language shards by month 24.

**Unit economics.** Blended ARPU target US$50 per MAU-year; infrastructure plus safety ~US$0.9-1.8 per DAU-month; Keeper spend ≤10% of that; payout failure <1%; store-routed money-in ≤25% by month 12 (R7, R10).

---

## 12. Roadmap sketch

**Phase 0, Foundations (Q4 2026 - Q2 2027).** Cells and presence layer with the 150-avatar voice load test; entity store and event-log persistence on two providers; UE 5.8 client on Reference and Lite; text client; OAR/IAR import and the LSL layer; the charter, fee page and Human Primacy Charter published; T0 Keepers and the ecology; closed alpha with the five Wave 1 institutions.

**Phase 1, Harbour (Q3 2027 - Q2 2028, public launch).** Desktop and WebGPU browser clients; the Tide with its randomised holdout; crews, roles, deputies, civic calendar; lottery land and the 45-day rule; marks, first-party billing, the licensed payout rail with tax onboarding; T1 Keepers under the Liveliness Floor; Lineage v1; the first Emberfall; metrics page and API; SL bridge opens. Milestones: first-session completion ≥60%, 50 whitelisted estates, median ≥10 people visible in a newcomer's first session.

**Phase 2, Districts (Q3 2028 - Q2 2029).** Native mobile; Adult district with Ofcom-grade gating and gated commerce; Almanac per district with assembly-set temperament; T2 named Keepers and crew Apprentices; first Grid Assembly election; Campus tier at 20 institutions; Portuguese and Spanish shards; mobile ≥30% of DAU by month 24.

**Phase 3, Stand-ins and federation (Q3 2029 - Q4 2030).** Opt-in Stand-ins; self-hosted cells for OpenSim operators; Japanese and German shards with VRoid/BOOTH pipelines; event mode to 2,000-5,000; neural texture compression once SM 6.10 leaves preview (graphics brief, implication 5); operating costs covered by recurring revenue by month 36.

**Phase 4, Successor-proofing (2031).** UE6 migration under the documented exit plan; assembly vote on adult companions; annual restore and failover drills; the survival configuration is exercised if growth has stalled.

---

## 13. Requirement coverage table

| Req | Mechanism in this proposal |
|---|---|
| R1 | Cells of 50-150 under a 500-1,000 presence layer; event mode 2,000-5,000 with impostors; SLOs published; 150-avatar voice load test in Phase 0 (s.7). |
| R2 | Reference/Lite/Compat budgets on every asset, enforced server-side; auto LODs and impostors; avatar ranks 70K/20K/7.5K; Keepers under the same budgets (s.6). |
| R3 | glTF 2.0 + VRM 1.0 runtime, OpenUSD interchange, platform-funded conversion, 24 months' notice (s.5, 10). |
| R4 | First-party consumer, browser and text clients shipped continuously; documented protocol; third-party clients blessed (s.6, 9). |
| R5 | Luau/WASM sandbox, per-owner budgets throttling the worst offender; LSL layer under the same budgets (s.5, 10). |
| R6 | Rent from day one (Garden/Homestead/Estate/Campus), no free hosting tier, activity near cost, revenue mix published annually (s.4, 11). |
| R7 | One fee page: 10% primary, 0% resale, 2.5% spreads, ≤15% round trip, first-party billing, stores as top-ups, margin stated (s.5). |
| R8 | Pool of 25% of net revenue, purchaser-weighted, 15% for houses with calendars, Epic-style anti-farming, Keeper traffic excluded (s.5). |
| R9 | The mark fixed at 100 = US$1, fiat shown, exact amounts, no bundles, no chance paying anything transferable, stipends in fiat (s.5). |
| R10 | Licensed partnered rail, KYC and W-9/W-8/DAC7 at payout onboarding, adult-specialist acquirer in reserve (s.5). |
| R11 | The Tide: hosted cohort every 20 minutes with a paid warden and a badged Keeper guide; "met a person or joined a crew"; randomised holdout (s.3). |
| R12 | Liveliness Floor of 8, one avatar per 0.1 ha at peak, thin instances merge, districts go to seed after 14 days, newcomers routed to live events (s.4). |
| R13 | Metrics page and API; Keeper share and bot share published; retention by ladder rung from month six (s.3, 8.5). |
| R14 | Desktop plus WebGPU browser at launch, native mobile within 12 months, VR optional, streaming a capped funnel at published cost (s.6). |
| R15 | Weekly rhythm, Emberfall, roles as objects with slots, badges, stipends and deputies; the Almanac fills gaps only (s.3). |
| R16 | Public parcels by lottery, full-price tickets, 45-day rule with refunds and pause policy; private homes rented, never demolished (s.3, 4). |
| R17 | Whitelisted estates with access and ban lists, ranks, damage parcels, HUD meters, paid queue priority; living towns of disclosed Keepers (s.2). |
| R18 | Charter import, OAR/IAR import, 12-24-month SL chat and event bridge, glTF/VRM export of own work (s.10). |
| R19 | Charter, 12 months' notice and grandfathering, public change-review, elected Grid Assembly answered in writing; Keepers cannot vote (s.3, 9). |
| R20 | Self-hostable cells, escrowed images, export tools, two providers, swappable voice, engine exit cost documented, annual drills (s.7, 10). |
| R21 | Regional age-assurance module, on-device estimation or wallet credential, no stored IDs, 18+ main world, isolated 13+ Campus, Ofcom-gated Adult districts (s.9). |
| R22 | Adult spend instrumented, uploader verification and pre-publication review, platform-currency coding, deindex-but-sell switch (s.5, 9). |
| R23 | Boundary default-on, one-gesture controls, instance lock, evidence buffer, trust ranks, quarterly KPIs; Keepers as witnesses only (s.9). |
| R24 | Lineage: platform-hosted, escrowed life support with designed perma conversion; escrow API for vendor HUDs (s.8.3). |
| R25 | Human Primacy Charter: badge and on-whose-behalf notice, jobs, ≤50% cap and withdrawal, no minors, licensed voices, three cognition tiers with published cost, ≤10% of safety-plus-infra, holdout audit (s.8). |
| R26 | Dressed avatar on an open-licensed body and a furnished room before any scripting panel; consumer client separate from the Workshop (s.3, 5). |
| R27 | First-party text client with voiced GPS, chat STT/TTS, keyboard navigation, funded maintenance; Virtual Ability in Wave 1 (s.2, 6). |
| R28 | Campus tier: SSO, bulk accounts, private regions with OAR export, General rating, US$39/month, written persistence commitment (s.2, 4). |
| R29 | Language as a shard key, four paid localisations, local rails, VRM import and off-platform markets; chat translation measured (s.2, 4). |
| R30 | US$45M to self-funding at ≤600K MAU, 110-head cap, 40-head survival configuration, no sibling product, growth gated on recurring revenue (s.11). |

None is "not addressed". Two are weaker than asked: R11's causal test needs a post-launch holdout, and R29's chat-translation retention effect has no precedent to size against (taxonomy 1.8).

---

## 14. Biggest risks and what I would cut first

**Risk 1: the living layer does not move retention.** If the R25 holdout shows human D30 no better in Keeper-filled places, the cap drops and T2 cognition goes first. The ecology, Chronicle and Almanac are cheap enough (T0, no language models) to keep, and they are the parts with precedent (Animal Crossing, RimWorld).

**Risk 2: the audience is ~0.5-1M and SL already serves most of it.** The taxonomy's cheapest hypothesis. The answer is the funding posture: fixed costs that survive at 100K MAU and a wedge of institutions, not a mass launch. If month-18 migration misses ten institutions, mobile and language shards are deferred, not the covenant.

**Risk 3: the payment rail and adult content.** Card-scheme pressure took Steam, itch.io and DLsite adult content down in July 2025 (Source: https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story). Mitigations: the deindex-but-sell switch, platform-currency coding and the reserve acquirer; the contingency, excluding Adult-tagged cash-out, is processor-triggered only.

**Risk 4: AI backlash and regulatory drift.** Disclosure, quiet districts and the no-minors rule are the mitigations; if Article 50 guidance or a NO FAKES safe harbour changes the badge or voice rules, the Keeper runtime is the only component affected.

**Risk 5: engine and vendor dependency.** A UE6 break stranding content, as Horizon's engine switch did; a voice or hosting vendor vanishing inside 18 months (Hathora). Engine-neutral formats, two providers and swappable voice are built in; the exit cost is written down.

**Cut order, cheapest regret first.** 1) Stand-ins. 2) T2 cognition (keep T0/T1). 3) Event mode above 1,000. 4) VR client and Gaussian-splat capture. 5) Pixel-streaming funnel. 6) Language shards beyond Portuguese and Spanish. 7) Apprentices. Never cut: disclosure, the text client, charter import, the fee page, the persistence covenant, or the Tide. The Tide is the one pure hypothesis here, and the only piece that tests whether a successor can supply what Linden never measured: the first group.
