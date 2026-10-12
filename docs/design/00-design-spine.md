# nolife: the design spine

Canonical design for the nolife document set, written 2026-10-09 by the lead designer. Its sources are the failure taxonomy in `docs/research/failure-taxonomy.md` (requirements R1-R30), the six proposals in `docs/design/panel/`, and the three judge reports in `docs/design/panel/judges/`. No web search was used here. Any external fact cites the taxonomy or the proposals.

**Rules for writers.** The names in section C and the numbers in section D are canonical. A document may add detail but may not contradict either; if you disagree, keep the value and raise it under Open questions. "L" is public launch (October 2028) and "L+n" means n months after it. All money is in US$.

---

## A. Thesis

**What it is.** nolife is a persistent, adult-first virtual world. One self, one inventory and one social graph persist across every place. Residents build everything in-world or import it; communities run the places, the calendar and the roles; and the economy pays out real money through a licensed rail. It is a civilization engine, not a content product. It ships institutions, roles, scarcity, a calendar and a constitution, and no quests, story or artificial civilization.

**For whom.** In order of priority:
1. The roughly 600K residents of Second Life and the 45-50K of the OpenSim hypergrid. They arrive through their institutions (venues, roleplay estates, disability and care communities, educators, festivals, adult communities, non-English groups) and their earning creators.
2. The 2026 diaspora from Spatial, Rec Room and Sansar, and VRM avatar culture.
3. Adults ageing out of youth platforms.

It is not for children outside Campus, VR-first users, brands buying land, or crypto.

**Why now.**
- UE 5.8's Lumen Lite and production MegaLights bring a 2026 look to mid-range hardware, and WebGPU ships in every major browser. With budgets, one world can look current on an RTX 5060 and still run in a browser.
- Regulation now demands what Second Life never built: Ofcom-grade age checks (July 2025), Brazil's ECA Digital (March 2026), EU AI Act Article 50 (August 2026), and the Digital Fairness Act expected in November 2026. A successor that designs these in starts ahead of an incumbent still using a self-declared birthday.
- The 2026 graveyard (Rec Room, Spatial, Hathora) left communities homeless and proved the point: subsidy collapse kills, rent for persistence pays.
- Linden shows the model works, profitable on about a 10% take, while its fee creep, opaque metrics and missing export make its residents receptive.

**What "nolife" means.** The name has three readings, and each one is a design rule.
1. **No life of its own.** The platform manufactures no purpose. The life is the people insulted as "no-lifers": those who ran SL9B on donated regions, carried the Anglican Cathedral past its founder's exit, and have run the Confederation of Democratic Simulators since 2004. The platform makes their work cheap, legible and durable.
2. **Nobody is charged for being alive here.** Residents pay rent on the bytes they keep and a published slice of what they sell, never for visitors, growth or success.
3. **No life-support.** Nothing depends on one engine, vendor, headset, food server or investor staying alive. That means neutral formats, two hosting providers, escrow, a written engine-exit cost, and a company sized to survive at 100K MAU.

**The promises.**
- **Second Life veteran:** "Bring your community, your builds, your scripts and, through Re-delivery, your look, and pay about a third of SL's land price under a charter that cannot reprice by blog post."
- **Creator:** "Keep 87.5 cents of every dollar, all-in and audited, plus a share of a pool that grows with the world, with Splits, royalties and an Export bit every client honours."
- **Newcomer:** "In your first hour a human host will say your name, walk you to a live event with at least ten other people and hand you three invitations to be needed."
- **Community leader:** "Your Charter moves in one transaction (roles, members, bans, calendar and land), and the world gives you Posts, a treasury, succession and a stage in exchange for one weekly event and a named deputy."

---

## B. Decision log

### B.1 The base and why

The base is **community-sociologist** (162 points), chosen on the judges' reasoning rather than the score:
- Its purpose engine is the only one that adds social design instead of restating R11 and R15-R19. All three panels scored it 10/10 on "communities supply purpose"; no other proposal scored above 8.
- It tells the strongest "why nolife" story, and it is the only thesis that says the operator must not manufacture life, which is the lesson of Sansar, Rec Room and Horizon.
- It reads the root causes most honestly: the funnel is not the cause, the group effect is a hypothesis to measure, and Keepers are a stopgap that gets cut first.

The feasibility panel ranked it fourth (49) for two flaws, and the synthesis removes both:
1. **Money.** Its P&L needed 25% of MAU paying for Hearths, and its Landing Hosts were unfunded. Its money design is replaced wholesale by **platform-economist's** (feasibility rank 1; economics 9-10 on every panel), with the Pool split corrected and Landing Hosts funded.
2. **Roadmap.** Its nine-month Phase 0 had no team plan, engine-licence step or reuse. It is replaced by **studio-exec's** sequencing, team plan, a Series A raised on measured numbers and a kill criterion, with a larger team and a later launch.

Platform-economist (161) was considered as the base and declined. Every panel judged its purpose engine "a payroll" that risks "an excellent shop with an empty plaza". The other proposals each contribute one part:
- **Engine-architect** supplies graphics and the server core (best graphics score with every panel), without its minors policy, consoles, imposed aesthetics or US$75-95M raise.
- **Open-web-architect** supplies import tooling, without federation.
- **AI-world-designer** supplies the AI rulebook, without an AI-filled world.

This is the desirability panel's composite verdict, adopted as the plan.

**Kept from the base:** Charters, Posts and deputies, the Landing and Call Board, the Civic Calendar, the Ephemeral Ward, Standing, the Chronicle, the Ward open/fallow rule, the Commons lottery, Estates, Night Wards, the World Charter and Never List, tribunals by lot, the 20% Keeper cap, the 70/20/10 split, 18+ by default, and the place names.

### B.2 Grafted ideas, by source

- **platform-economist:**
  - The four money mechanisms: rent on bytes kept, never visitors; one Fee Page with a worked example and the required margin printed; the Pool as a share of net revenue; a fiat-pegged closed unit on a licensed rail.
  - A granular rent list with a printed cost basis.
  - Splits (up to 10 contributors) and Component Royalties (up to 10%).
  - The Maker, Merchant and Studio ladder.
  - The Re-delivery Programme and Founding Merchant terms.
  - The Starter Catalogue, which earns Pool weight.
  - The open Bazaar protocol.
  - Minors only in an isolated Campus.
  - A Digital Fairness Act fallback.
  - A P&L at several scales with sensitivity tests.
  - A segregated, capped prepay.
  - Pool anti-farming rules: purchasers only; unverified accounts weighted 0.5; a 75% bonus for referred new or lapsed residents.
- **studio-exec:**
  - Cell hibernation as a stated rule.
  - Spend sequencing.
  - A Series A raised on four measured numbers.
  - A kill criterion (the Tripwire).
  - A team plan by function, with vendors for first-line moderation, age assurance, the rail and voice.
  - Frozen founding rent traded for a weekly event and deputies.
  - The engine-terms fallback.
  - An Adult ward at private alpha.
  - LSL running as-is on OpenSim's BSD engine.
  - The "active" definition and the Census.
  - Public deletion rates per Ward.
  - Portuguese and Spanish community managers at launch.
  - The currency's legal form as stored value.
- **engine-architect:**
  - Headless C++/Rust cells with Jolt and Luau, and Unreal as renderer only.
  - A written exit cost and a licence budget line.
  - The costed Foundry with per-view caps and a degrade order.
  - Line-item frame budgets and avatar budgets.
  - CopyBot fingerprinting.
  - Server-side Bakes-on-Mesh, and badge-carrying impostors.
  - The Common Body, a kit library and Blocks.
  - World-owned photo mode (Darkroom).
  - Exact prim, sculpt and llmesh rebuilds, offered as opt-in Relight.
  - Inventory-loss as a published metric.
  - C2PA-style provenance and a likeness consent registry.
- **open-web-architect:**
  - The Ferry creator claim (a one-time code placed in the creator's SL profile).
  - NAR as a strict superset of OAR/IAR.
  - The content-addressed Vault.
  - Hypergate, deferred and first to be cut.
  - `nolife-bento` for VRM.
  - EEP skies exported as USD.
  - Calendar feeds over ActivityPub and iCal.
  - A directory that shows live human occupancy and bot share.
  - The names Lantern, Ember, Reader and Passport.
- **ai-world-designer:**
  - The Human Primacy Charter.
  - The T0/T1/T2 cost model, republished quarterly.
  - Stand-ins that wear "the apron, not the face".
  - Quiet Wards.
  - Lineage, without chance-for-cash.
  - The shared first job (First Light).
  - Retention published by ladder rung.

### B.3 Rejected ideas

- A Foundation-owned eight-spec protocol, conformance suite, Crossing federation, Open shards and one rail settling on third-party shards (open-web): the weakest shard would set everyone's card-scheme and regulatory risk, one adult-shard breach would expose the rail, rent would leak to cheap shards (OpenSim economics), and the scope is unfunded.
- An open-source server for anyone before sunset (open-web; economist): It leaks rent. The server goes to escrow, the Homestead Kit is limited to partners, and the code becomes Apache-2.0 only at sunset.
- Admitting 16-17s; six age bands; a Scholar band in General Wards (open-web, engine, sociologist): It brings ECA Digital, PP Tunas and the children's code into an adult cash-out economy.
- A 50-75% Liveliness Floor of Keepers; Keepers filling role slots; crew Apprentices (ai-world): No evidence that agent density retains people; 63% of players are hostile to generative AI; it undermines "people stay where they are needed".
- Ecology, desire lines, decay, and districts that "go to seed" after 14 quiet days (ai-world): No precedent; evicting quiet residents breaks the persistence covenant.
- Chance-based breeding for cash-out-able value (ai-world): It is gambling in at least one jurisdiction (R9).
- A ban or cap on sub-let markups (ai-world, open-web): It ends the estate-manager livelihood; disclosure is used instead.
- Metered compute above a visitor allowance (economist): It charges places for being successful.
- 150K paid Hearths; US$199 Halls; a US$899 lifetime tier; a "Citizen" subscription (sociologist): The payer share is not credible; parity gives no reason to switch; the lifetime tier is an unbounded liability; civic standing must never be sold.
- Console and native Quest ports; a path-traced A+ tier; strand hair (engine): Platform-holder rules for an adult cash-out world, and a scope sink.
- Platform-owned lighting, a full-bright ban, fidelity minimums, forced legacy re-make (engine): Alienates photographers, clubs and builders (B.4, item 11).
- A US$75-95M raise with a 120-person cap (engine): Recreates subsidy collapse; its survival configuration does not add up.
- Cutting Compat; mobile at month 18 (studio cut list): Reopens root cause 1.1 and breaches R14.
- Launch at month 12-15; a nine-month Phase 0; 45 people at launch (economist, sociologist, studio): Not buildable (feasibility panel).
- Selling streamed hours (engine); `rbx-compat`; a binding council (open-web); a sponsored discovery row (studio): R14 allows streaming only as a funnel; wrong audience; no world has shipped a binding council; paid rank breaks "rank by returning humans".
- Four separately named annual rituals: Replaced by one: the Ephemeral Ward.
- 1.5% cash-out plus a 4% spread; a 3% top-up fee (engine, open-web): One 2.5% cash-out fee, no spread, and 0% to buy.

### B.4 Contradictions resolved

1. **Federation vs. central safety.**
   - One operator runs one world, one Ledger and one safety system.
   - The protocol is documented and third-party clients are blessed.
   - The partner-only Homestead Kit is the only self-hosting. Its cells are General or Moderate only, take assets only through the Foundry, use central Passport and Ledger, and remain under platform takedown.
   - Server source goes to escrow and is released under Apache-2.0 only once the 12-month shutdown notice fires.
2. **AI inhabitants vs. human primacy.**
   - Keepers are capped at 20% of visible occupants and withdraw as humans arrive.
   - They never hold Posts, money, land or votes, and never moderate.
   - They arrive at L+12 as an experiment that is killed if human D30 falls.
3. **Rent vs. "no land tax".**
   - Rent is load-bearing and priced on budget and bytes, never traffic.
   - The only metered activity is an Event Mode reservation above 1,000 presence, charged at cost and waived for Civic Calendar events.
   - Hibernation makes a US$69 Cell profitable.
   - Nothing is ever demolished.
4. **UE5 fidelity vs. mobile and browser reach.**
   - Reference is a ceiling, not a floor, and every asset gets Lite and Compat versions automatically.
   - Ember is first-class at L and Compat is never cut.
   - Mobile ships at L+9 on the Lite tier.
   - There are no console or Quest ports. Losing Unreal would cost Reference, not the world.
5. **Coin vs. "no coin".**
   - Coin is a display unit: 100 Coin = US$1.00, local fiat shown first, no spread.
   - Legally it is stored value held by the licensed partner.
   - If the Digital Fairness Act restricts paid currencies, the display switches to fiat and the ledger is unchanged.
6. **Who is admitted.** The open world is 18+. Ages 13-17 are admitted only in Campus via institutional SSO. Nobody under 13 is admitted.
7. **Pool to places vs. to creators.** So that marketplace-only creators are not starved:
   - 70% goes to creators, weighted by distinct returning purchasers of their goods wherever sold;
   - 20% to Charters and venues, by returning members attending events;
   - 10% to public Post stipends.
8. **Scarce Posts vs. staff-heavy institutions.**
   - Only Posts that earn Standing or public stipends are capped: one per eight active members, minimum three.
   - Event crews are uncapped for the duration of the event.
   - Unbadged internal roles are unlimited.
9. **Civic machinery vs. individualists.** No feature requires Charter membership. One of the three Call Board invitations is always outside any Charter, and Standing heraldry is opt-in.
10. **Paid roles vs. volunteer motivation.** Standing is the main reward. Public stipends go only to Landing Hosts, Ward Wardens and Jurors.
11. **Platform look vs. resident aesthetics.**
    - Wards own sky, time and weather; Holding owners set their own sky.
    - A personal photo sky is visible only to the person who sets it.
    - Full-bright survives as a capped Unlit/Emissive material.
    - Legacy content displays as imported, with Relight opt-in.
    - Building codes come from Charters or councils, never the platform.
12. **The Ward threshold vs. launch day.**
    - Six Founding Wards open at L, with Founding Charter members counted as attached.
    - After L, a Ward opens at 2,000 attached MAU and goes fallow below 500 for 90 days.
    - Going fallow affects only Commons plots, which are refunded and packed into a NAR.
13. **Lean vs. honest funding.** US$45M, 60 people at L, and a launch 24 months after the seed: more than any lean proposal, half of engine-architect's raise. The Floor Plan keeps R30 true.
14. **LSL transpiler vs. LSL as-is.**
    - Residents upload LSL unchanged.
    - Ferry compiles it transparently to Luau against an `ll` library, using OpenSim's BSD engine and tests as the reference.
    - Unsupported calls fail loudly.
    - 90% of Founding Charter scripts run unmodified at L.
15. **Self-hosting timing.** Escrow, NAR export and a two-provider failover demo ship at L (R20's test). The Homestead Kit follows at L+12.
16. **Sub-letting.** Sub-letting is allowed without a cap. Every listing prints the platform base rent next to the landlord's fee, so the landlord's margin is visibly a service margin.

---

## C. The named systems (canonical)

**C.1 Civic Engine (purpose engine).** The product. Its parts:
- **Charters** are institutions: a permanent name, 2-20 roles, a ban list, a fixed rating, a calendar, a Coin treasury and Holdings. A Charter owning land or a calendar must name a deputy and a succession rule.
- **Posts** are roles with slots, a shift calendar, a badge, an optional stipend and a deputy. The base vocabulary is Host, Mentor, DJ, Warden, Builder, Chronicler, Teacher, Healer, Quartermaster and Juror.
- **The Landing** is the first hour:
  1. The newcomer joins a hosted cohort and gets a dressed avatar and a furnished Hearth within ten minutes.
  2. **First Light**, a ten-minute shared job, writes every name into the Chronicle.
  3. The Host walks the cohort to an event starting within 30 minutes.
  4. The **Call Board** lists Charters recruiting this week and gives three invitations.

  A 10% holdout gets a self-guided Landing.
- **The Civic Calendar**:
  - A weekly rhythm in each Ward's local time: Wednesday Quiet Day (no first-party events), Friday Open Stage (slots by lottery weighted by audience retention), Saturday Market Day, Sunday Assembly Day.
  - A seasonal layer owned by Charters.
  - The annual Ephemeral Ward.
- **Trust** (Visitor, New, Member, Known, Trusted, plus a Nuisance flag) gates rights.
- **Standing** (Neighbour, Regular, Pillar, Elder) is civic. It is earned through Posts, shifts, events, members retained, Commons use and jury duty, and it decays with absence.
- **The Chronicle** is an append-only public record that includes operator decisions and Assembly answers.

**C.2 Ward Plan (place and space).**
- **Hearths** are free instanced homes; Residents get Hearth+.
- **Holdings** are rented land: Plot S, Plot M, Cell and Domain. A Charter's principal Holding is its **Hall**. A Holding sits on an island or on a **Reach**, a contiguous mainland with roads and water that grows only when nearly full.
- **Estates** are Holdings with a whitelist, seat caps, ranks, a meter API, damage parcels and published queue priority. Cosmetics and priority may be sold; pay-to-win and loot boxes may not.
- **Wards** are public, language-tagged four-cell districts:
  - the **Commons**: 64 lottery plots across two cells;
  - the **Stage**;
  - the **Market** and **Green**.

  **Night Wards** are Adult-rated Wards.
- The **Ephemeral Ward** is built by Charters each August and runs in the second full week of September from 2029. It mints never-reissued relics at 0% resale fee and is erased on camera.
- **Event instances** are synchronised and hold about 100 each.
- There are **Landing halls** per language, and **Campus**.

Discovery is calendar-first and ranked by distinct returning humans, never by payment. Nothing is deleted for non-payment.

**C.3 Workshop and Foundry (creation).**
- **Workshop** is the creator interface, separate from the consumer UI (R26). It includes:
  - **Blocks**, parametric building compiled to meshes;
  - a PBR material and light editor with a live Fidelity Rank meter;
  - a Luau editor;
  - a free kit library;
  - import of glTF 2.0/VRM 1.0 (runtime), OpenUSD (scenes) and MetaHuman output.

  Generative assistants tag their output with provenance. Luau runs sandboxed, with per-owner CPU, memory and network budgets that throttle the worst offender. Format conversion is platform-funded, and retiring a format requires a converter and 24 months' notice.
- **The Foundry** is the server-side build farm every upload passes through. Its stages: normalise (1 unit = 1 m, PBR), catalogue fingerprinting (CopyBot defence), CSAM, likeness and script checks, a four-level LOD chain and octahedral impostor, collision, BC7/ASTC/ETC2/KTX2 transcoding, Bakes-on-Mesh atlasing, Lite/Compat bakes, Scene Weight, and a Fidelity Rank (Excellent, Good, Fair, Heavy). A licensed engine stage then cooks Nanite data; without the licence, Reference falls back to LOD chains.

**C.4 Ledger (economy and money flows).**
- **Coin** (B.4 item 5) is bought in exact amounts. There are no bundles and no chance mechanics that pay anything cash-out-able.
- **The Fee Page** shows the single fee stack, with a worked example and the required margin.
- **The Bazaar** is the open-protocol marketplace. In-world vendors and outside stores (BOOTH, Gumroad, Kitely Market) use the same API.
- **Primitives:** Splits, Component Royalties, an optional resale royalty of up to 10%, and multi-signature Charter treasuries with legal-entity attachment.
- **The creator ladder:**
  - **Makers** (any adult) sell and spend in-world.
  - **Merchants** (verified, with tax data on file) cash out.
  - **Studios** add team seats and an SLA.
- **The Commons Pool** is 25% of net revenue (gross less processing, refunds and taxes), paid monthly and split 70/20/10:
  - Weighting is by returning purchasing users: a purchase in the last 90 days and visits on at least 2 days that month.
  - Unverified accounts count 0.5. A 75% bonus applies for six months to referred new or lapsed residents.
  - Each equipped Starter Catalogue item counts as a purchaser for 90 days.
  - The formula and the median payout are published quarterly.
- **Cash-out** runs on a licensed partner rail. W-9/W-8 and DAC7 data are collected before the first payout, an adult-specialist acquirer is pre-qualified, and purchases are coded as stored value, never under an adult merchant category code.
- **Keepalive** is escrowed life-support for value-bearing scripts, with a food-independent end state. Its **Lineage** registry hosts breedable genetics with habitat caps. Breeding outcomes are either previewed before commit, or random only for non-transferable offspring.

**C.5 Fidelity Contract and clients (graphics).** The server-enforced contract gives every asset a budget per tier and automatic fallbacks, so the hardware floor never rises.

Tiers: **Reference** (RTX 4060/5060 class); **Lite** (Steam Deck and Switch 2-class GPUs, M1 Macs, Snapdragon 8 Gen 2/A16 phones, desktop WebGPU; performance classes only, no console port); **Compat** (WebGL2, low Android, integrated GPUs); and **Stream**, a capped funnel rather than a tier.

Over-budget content degrades in a published order, and a buyer always sees their own item in its tier version. Impostors keep outfit colour, silhouette and role badge. The open-licensed **Common Body** uses a VRM 1.0 skeleton, a MetaHuman-compatible face rig and a published Bento table. **Darkroom** farm-renders any public place.

The clients:
- **Lantern** is the native UE 5.8 client: Reference and Lite on Windows and macOS at L, Lite on iOS and Android at L+9.
- **Ember** is the browser client (Babylon.js, WebGPU with WebGL2 fallback): Lite and Compat, the full economy, no building at L.
- **Reader** is the text client (Radegast successor): chat, IM, inventory, teleport, object list, voiced GPS, speech-to-text, text-to-speech and keyboard-only use, with a funded maintainer.

A named newcomer team owns first-session completion. Unreal renders only. If the custom licence is not signed by 30 September 2027, Lantern ships Lite on the web stack and Reference waits.

**C.6 Grid (architecture).** The world has two layers.
- **Cells** are headless C++/Rust processes running Jolt and a Luau VM. They simulate physics, scripts and object state behind the authoritative **Entity Store** (documents plus an event log), so a crash is a reconnect. Clients predict locally with the same Jolt build.
- **The Presence layer** carries pose, look, chat and voice through interest-managed relays.

Around those layers:
- **Event Mode** reserves capacity for crowds.
- **Vault** is content-addressed, S3-compatible asset storage, so a NAR restores by hash anywhere.
- Idle cells **hibernate**.
- Persistence has write budgets, snapshots, owner rollback, and nightly escrow to a second provider.
- One container manifest runs on Edgegap, GameLift Servers, Nitrado GameFabric or bare metal, with two providers live from L.
- Voice is swappable between ODIN, the Discord Social SDK and a self-hosted SFU.
- The protocol is documented at L, and third-party certification follows at L+24.
- The **Homestead Kit** is the partner-only self-hosted cell.

**C.7 Keepers (AI inhabitants).** AI never counts as life. A **Keeper** is a disclosed artificial inhabitant with one of four jobs:
- **Greeter**: holds a Landing when no human Host is on shift, and hands over when one arrives.
- **Chronicler**: drafts Chronicle entries for a human to sign.
- **Stand-in**: an opt-in, interview-seeded tender of an absent resident's shop. It is badged "Stand-in for X (artificial)", never speaks as the resident in the first person, has a transaction limit, keeps logs, and is withdrawn after 60 days of the resident's inactivity.
- **Director**: a scripted, non-LLM pacer of ambient Ward happenings that never overrides human events.

The **Human Primacy Charter** is enforced in code. Keepers:
- wear a badge and say on whose behalf they act;
- are excluded from every metric, SLO and the Pool, with their share of occupants published beside the bot share;
- withdraw one-for-one as humans arrive;
- hold no Coin, land, vote, Post or Standing;
- never moderate (they may act as witnesses);
- never message offline humans and are never optimised for session length;
- have no companion or romantic loops, and are scripted-only in Campus;
- use licensed or synthetic voices with provenance.

Ward councils may vote their Ward quiet. AI as tooling (triage, classification, measured translation, Foundry inference, speech-to-text, text-to-speech) is unrestricted where it serves humans.

**C.8 Passport, Safety Kit and World Charter (identity, safety, governance).**
- **Passport** is one persistent self: pseudonymous username, changeable display name, private age band (on-device estimation or wallet credential; no ID image stored; appeals avoid document upload), Trust, Standing, licences readable off-platform, and inventory.
- **The Age Module** has profiles at L for the UK (Ofcom "highly effective"), the EU (DSA Art. 28, wallet credential), Brazil (ECA Digital), Indonesia (PP Tunas) and Texas; California OS signals follow in 2027.
- **Campus** is the only place for ages 13-17: General-rated and isolated, with no economy and no cash-out.
- **The Night Ward** check also unlocks Adult-tagged commerce, which requires uploader verification, consent records and human pre-publication review. Spend is maturity-tagged from day one. A deindex-but-sell switch acts within hours. Exclusion from cash-out is held as a contingency that only a processor can trigger.
- **The Safety Kit** is always on: personal boundary on by default; one-gesture mute, block and vanish; Warden kick and lock; a 60-second evidence buffer; consent prompts for avatar-to-avatar actions; upload, voice and proximity gated by Trust.
- **Appeals** go from a Charter Warden to a **Tribunal** (three jurors drawn by lot from Pillar Standing and above) to the Trust Desk. Legal and child-safety cases are platform-only and immediate.
- **Governance.** **Ward councils** write ordinances. The advisory **Assembly** can demand public review of any change that affects clients. The **World Charter** guarantees notice and grandfathering on persistence prices and a sunset covenant (12 months' notice plus escrow release).
- **The Never List:** no crypto or NFTs, no loot boxes, no retroactive repricing, no sale of Standing or Posts, no undisclosed AI, no sale of biometrics, no sibling product.
- **Census** publishes the metrics. "Active" means a person entered, moved, and interacted with another human for at least five minutes in the period.

**C.9 Ferry (legacy import).** Ferry carries identity, inventory and social graph (the moat), and budgets and converts content (the debt). Its parts:
- **Charter Import** moves roles, opt-in members, ban list, rating, calendar and Holding in one transaction.
- **NAR** is a strict superset of OAR/IAR (`load oar` and `load iar` work unchanged) and also serves as the export format.
- **SL import** brings in own-created content via creator-only viewer export, honouring the Export bit. Prims, sculpts and llmesh are rebuilt exactly but display as-is, with **Relight** opt-in.
- **Creator claim:** a one-time SL profile code signs the imported catalogue to the creator's Passport.
- **The LSL Runtime** is described in B.4 item 14.
- **Avatars:** the Common Body and Bento table, `nolife-bento`, VRM 1.0, and EEP skies as USD.
- **Re-delivery** pays creators when a migrating resident proves an SL purchase and claims the nolife edition.
- **The Bridge** relays chat and calendar through residents' own accounts, with Discord as fallback.
- **Hypergate** speaks Firestorm's protocol.

Not imported: no-transfer third-party content without an Export bit, L$ balances, and SL status.

**C.10 Founding Programme and Floor Plan (business model).**

Revenue, by weight: Holding rent; Resident subscriptions; the 10% commission; the 2.5% cash-out fee; and services (Campus, a 10% share of Estate tickets and priority, Event Mode reservations, Darkroom renders, staffed brand events sold on measured attendance, never land). Paid acquisition is zero.

The **Founding Programme**:
- **Founding Charters**: 50 communities, 25 of them by L. Each gets a migration engineer, a first Cell (or a Domain above 500 members) rent-free until L+6, and then 30% off list, frozen for 36 months. In return, each runs a weekly public event and names deputies.
- **Founding Merchants**: the first 1,000 verified creators, with reduced commission, funded conversion, the creator claim and Re-delivery.
- **Founders' Pass**: a capped, segregated three-year prepay.

The **Floor Plan** runs 25 staff at 100K MAU, with the gap covered by the **Floor Reserve**. The **Tripwire** triggers the Floor Plan if either:
- the Series A has not closed by 30 September 2028; or
- at L+12, fewer than 10 named SL institutions are active with at least 50% of their imported membership, or MAU is below 60K.

Spend sequence is fixed: rail and compliance before graphics; Reader before VR; Charter Import before the Bazaar; the Landing before Keepers; Compat before Reference polish. Growth features are funded only once rent and subscriptions cover costs.

---

## D. Canonical numbers

### D.1 Timeline

- **Nov 2026:** seed closes; Phase 0 Foundations begins.
- **Mar 2027:** draft World Charter, Fee Page and Fidelity Contract published.
- **Sep 2027 gates:** 150-avatar cell load test with voice passed; Unreal licence signed by 30 September or the fallback is triggered.
- **Dec 2027:** rail and age-assurance contracts signed, with the adult policy on file.
- **Jan-Sep 2028, Phase 1 Founding (private alpha):**
  - 25 Founding Charters and 5,000-10,000 residents;
  - Night Ward;
  - Coin and cash-out in the US, UK and EU;
  - Re-delivery open.

  The Series A closes in June 2028.
- **Oct 2028 (L), public launch:**
  - Lantern (Windows and macOS), Ember and Reader;
  - English, Portuguese and Spanish;
  - Pix, the Bazaar and Census;
  - escrow and the failover demo.

  The first Pool payout is at L+1.
- **L+6 (Apr 2029):** Landing holdout result; Campus with SSO; Ward councils and Tribunals; Director.
- **L+9 (Jul 2029):** Lantern Lite on iOS and Android.
- **L+11 (Sep 2029):** first Ephemeral Ward, with Event Mode validated at 2,000 beforehand.
- **L+12 (Oct 2029):** Japanese and German Wards with konbini; first Assembly election; Keeper experiment; Homestead Kit; UE6 decision documented; Tripwire review.
- **L+18 (Apr 2030):** Stand-ins; Hypergate; R18 test.
- **L+23 (Sep 2030):** Event Mode at 5,000.
- **L+24 (Oct 2030):** R6, R14 and R29 tests; third-party client certification.
- **L+30 (Apr 2031):** optional VR view (OpenXR desktop; Quest 3 at 72 Hz).
- **L+36 (Oct 2031):** recurring revenue covers operating costs at 350K MAU.
- **2032:** capacity for 60,000 CCU.

### D.2 Team and money

- **Envelope: US$45M.**
  - Seed: US$12M (Nov 2026).
  - Series A: US$33M (Jun 2028), including the US$6M Floor Reserve.
  - This funds 24 months to launch and 36 months to break-even.
- **Series A gates** (all four required):
  - at least 15 Founding Charters with at least 50% of invited members active monthly;
  - alpha Landing D30 at least 3 points above the holdout;
  - at least 1,000 paid Holdings billing;
  - a published plan with a headcount cap of 60.
- **Founders' Pass:** US$249 for 36 months of Resident. Capped at 20,000 passes (no more than US$5M), held in a segregated account, refundable pro rata, and not counted as runway.
- **Headcount:** 20 at seed, 40 by Dec 2027 and 60 at L; capped at 60 until recurring revenue covers payroll; 100 at Linden scale; 25 in the Floor Plan.
- **Launch team of 60:** Lantern 12; Grid 10; trust and safety, policy, community and localisation 10 (including 4 Portuguese/Spanish community managers); Foundry, Workshop and tools 7; Ember 5; product, design, research and Landing 5; executive, finance, legal and people 5; Ledger, payments and compliance 4; Reader and accessibility 2. Vendors cover first-line moderation, age assurance, the rail, voice and hosting.
- **Costs:** US$150K loaded per head; engine licence 3% of gross; engine exit US$16M over 21 months (planning value; Ember carries the world meanwhile).
- **Paid acquisition: US$0** (CPI of US$75-300 per payer never pays back).

### D.3 Prices and the Fee Page

- **Coin:** 100 Coin = US$1.00; local fiat shown first at a daily-fixed rate; no spread
- **Free account:** Hearth (1 room, 8 guests, 1,000 Weight); 2,000 items / 1 GB; Maker selling
- **Resident:** US$9.99/month or US$99/year: Hearth+ (4 rooms, 25 guests, 4,000 Weight), 20 GB, 300 Coin monthly allowance shown in fiat
- **Extra storage:** US$1 per 10 GB-month
- **Plot S (¼ cell, 4,000 Weight, 4 GB):** US$19/month
- **Plot M (½ cell, 10,000 Weight, 10 GB):** US$35/month
- **Cell (256 m, 30,000 Weight, 30 GB):** US$69/month. Printed cost basis US$14: compute US$10 (~70 awake hours on 2 vCPU), storage and escrow US$2, operations US$2
- **Domain (4 contiguous cells, 120,000 Weight):** US$249/month
- **Non-profit and education:** 50% off; Class Cell US$34.50
- **Commons plot (2,048 m², 900 Weight):** US$8/month; lottery ticket US$24 (3 months prepaid), refunded in full to losers within 24 h
- **Homestead Kit (partners only):** US$29 per cell-month
- **Event Mode above 1,000 presence:** US$0.004 per reserved avatar-hour; waived for Civic Calendar events
- **Darkroom:** 10 free renders a month, then 10 Coin each
- **Stream:** 2 free hours per new account on a Compat device; cost US$1.75/h published; capped at 5% of infrastructure
- **Buying Coin on web or PC:** 0% (the platform absorbs ~3%)
- **App-store top-ups:** Store fee shown as a separate line; store-routed money-in ≤25% by L+12
- **Primary commission:** 10%; Founding Merchants 5% for 12 months from L; body and head vendors' Re-delivery editions 0% for 12 months
- **Resale, tips, in-person Market Day sales, off-platform-paid deliveries:** 0% (optional resale royalty up to 10%)
- **Estate tickets and priority:** 10%
- **Cash-out:** 2.5% plus pass-through rail cost (US$0.25 ACH, EUR 0.50 SEPA, ~US$2 international); minimum 2,500 Coin domestic, 10,000 Coin international; weekly
- **Worked example:** A US$10 sale leaves 900 Coin; cashed out within a US$100 payout, the all-in take is 12.5%
- **Required margin (printed):** 5% of gross
- **Commons Pool:** 25% of net: 70 creators / 20 Charters and venues / 10 public Posts
- **Re-delivery:** 10 Coin per claim; ≤US$5,000 per merchant; US$1.5M fund running from L-6 to L+24

Every sub-let listing shows the base rent. Any price rise needs 12 months' notice and grandfathering.

### D.4 Fidelity targets and frame budgets

| Tier | Output | Frame budget | Full avatars | Lighting |
|---|---|---|---|---|
| Reference | 1440p from 960p internal (DLSS/FSR/XeSS Quality), 8 GB RTX 4060/5060 | 16.7 ms (60 fps) | 100 | Lumen GI and reflections, MegaLights, virtual shadow maps, Substrate |
| Lite | 1080p | 16.7 ms (60 fps) | 40 + 60 impostors | Lumen Lite or lightmaps + probes; SSR |
| Compat | 720p, 256 m draw distance | 33.3 ms (30 fps) | 20 + 2D impostors | Baked; one cascaded shadow |
| VR view (L+30) | Quest 3 / OpenXR | 13.9 ms (72 Hz) | 40 | Lite settings |

**Frame budget breakdowns (ms):**
- **Reference:** Nanite visibility and base 3.5, Lumen GI 3.0, Lumen reflections 1.2, VSM 2.0, MegaLights (≤32 shadowed lights) 1.5, 100 avatars 3.0, translucency and Niagara 1.0, post and upscale 1.3, UI 0.2.
- **Reference VRAM (8 GB):** textures 2.5 GB, Nanite 1 GB, avatars 1.5 GB, caches and targets 1.5 GB, headroom 1.5 GB.
- **Lite:** base 5.0, lighting 3.0, shadows 1.5, avatars 4.0, translucency 1.0, post and UI 1.2, headroom 1.0.
- **Compat:** forward 12, shadow 4, avatars 8, post 3, headroom 6.

**Avatar budgets:**

| Tier | Triangles | Materials | Bones | Texture memory | Attachments |
|---|---|---|---|---|---|
| Reference | 120,000 | 12 | 300 | 80 MB | 24 |
| Lite | 35,000 | 6 | 120 | 24 MB | 12 |
| Compat | 20,000 | 2 (atlased) | 75 | 8 MB | 6 |

**Reference per-view caps:** 20M visible source triangles, a 2.5 GB streaming pool, 32 shadowed lights and 300 skinned meshes.

**Degrade order:** distant avatars to impostors, then fewer shadowed lights, then lower off-focus LODs, then fewer translucency effects, then over-budget attachments to their tier version. The owner is shown the cause. Impostors start at 30 m, and p95 frame time per reference device is published monthly.

### D.5 Concurrency, infrastructure and cost

- **Cells:** 150 simulated avatars with voice (the SLO); Jolt at 30 Hz.
- **Places:** 1,000 presence; 10 Hz within 30 m, 5 Hz beyond.
- **Event Mode:** 5,000 per place (validated at 2,000 by Sep 2029); synchronised instances of 100.
- **Per-client downstream:** at most 200 kbps, excluding voice.
- **Hibernation:** a cell sleeps after 10 minutes empty and wakes within 8 s (p95).
- **Persistence:** 60 + 10 × avatars writes per minute per cell; hourly snapshots; 30-day owner rollback; nightly escrow; inventory loss of at most 1 per 10 million operations, published monthly.
- **All-in infrastructure: US$0.025 per CCU-hour.** Compute 0.012, egress and CDN 0.007, voice 0.002, storage, escrow and backup 0.004, assuming about 10 avatars per awake cell.
- **Trust and safety** (vendors and tooling; staff counted separately): US$1.50 per DAU-month, with a floor of US$1.5M a year.
- **Capacity:** 5,000 CCU at L, 25,000 by L+24 and 60,000 by 2032; 2 hosting providers from L.
- **Keeper cognition** per active agent-hour: T0 scripted up to US$0.003; T1 small model US$0.015; T2 memorable US$0.20; blended at most US$0.02. Total Keeper spend is capped at 10% of infrastructure plus T&S.
- **Foundry:** US$0.01 per asset.

### D.6 Places and civic numbers

- **Wards:** four cells each (Commons 2 with 64 plots, Stage 1, Market and Green 1). A Ward opens at 2,000 attached MAU and goes fallow below 500 for 90 days. Six Founding Wards at L: English ×3 by time zone, Portuguese, Spanish, and an English Night Ward. One home Ward per resident, changeable every 30 days.
- **Density SLO:** one avatar per 0.1 ha in Ward hub cells at weekly peak (~130). A newcomer's first session shows a median of at least 10 people.
- **Commons:** a plot unused for 45 days returns to the lottery, with objects moved to inventory and 80% of unused prepaid rent refunded; a pause policy is published. The Reach opens in 64-cell blocks once it is at least 80% rented; there are 2 Reaches at L.
- **Landing:** a cohort every 15 minutes per launch language, 16:00-24:00 local; target size 12 (range 6-20); self-guided otherwise; a 10% holdout for 6 months.
- **Posts:** Standing-earning Posts capped at 1 per 8 active members (minimum 3); each Ward has 8 Warden and 12 Host Posts, paid from the Pool's 10% line.
- **Stage:** 168 hours a week, 40 of them prime hours allocated by quarterly lottery.
- **Standing:** decays one rank per 12 months of absence.
- **Elections:** to vote, Trust Member, 90 days' tenure and verified 18+; to stand for council, Standing Regular; for the Assembly, Pillar plus 12 months. Ward council of 5 from L+6 and Assembly of 9 from L+12, both annual; written answers within 30 days.
- **Service levels:** Tribunal 72 h; Trust Desk 7 days; median time-to-action under 24 h.
- **Lapsed Holding:** frozen for 90 days, then stored as a NAR in inventory, restorable indefinitely.
- **Bridge and scripts:** the Bridge runs for 18 months, and 90% of Founding Charter scripts must run unmodified at L.

### D.7 Retention and outcome targets (published via Census)

- **First session:** completion at least 60%.
- **Organic retention:** D7 25%, D30 15%, D90 10%. Founding Charter members: D90 25%.
- **The Landing is kept if** treated D30 is at least holdout D30 + 3 points and at least 15% (published at L+6).
- **MAU:** 100K at L+12, 200K at L+24, 350K at L+36; 600K is the reference ceiling.
- **Community activity:** at least 25% of MAU at a scheduled event each month; at least 80% of venues survive a leader's 90-day absence; at least 40% of DAU-hours in creator-run places by L+12.
- **Migration and institutions:** at least 50 whitelisted Estates with weekly events by L+12; at least 10 named SL institutions migrated with their membership by L+18 (programme goal: 50 Founding Charters by L+12); at least 70% Commons occupancy at peak; at least 20 Campus institutions by L+18.
- **By L+24:** mobile at least 30% of DAU and non-US at least 40%; at least 30% of avatar items from off-platform stores; rent plus subscriptions at least 50% of revenue (modelled at 66%).
- **Payments and cadence:** payout failure under 1%. Census is quarterly, frame times monthly and the revenue mix annual.

### D.8 Unit economics (canonical model)

Assumptions:
- DAU = 25% of MAU; average CCU = 4% of MAU.
- Paid Holdings = 5% of MAU (8% at the Floor) at an average of US$58/month.
- Residents = 12% of MAU at US$105 net per year.
- Primary sales = US$200 per MAU-year at an effective 9% commission.
- Cash-out = US$75 per MAU-year; Coin purchases = US$100 per MAU-year; other revenue = US$4 per MAU-year.

| US$M/yr | Floor: 100K MAU, 25 staff | Break-even: 350K, 60 staff | Reference: 600K, 100 staff |
|---|---|---|---|
| Holding rent | 5.6 | 12.2 | 20.9 |
| Resident subscriptions | 1.3 | 4.4 | 7.6 |
| Commission | 1.8 | 6.3 | 10.8 |
| Cash-out fees | 0.2 | 0.7 | 1.1 |
| Other services | 0.4 | 1.4 | 2.4 |
| **Gross revenue** | **9.2** | **24.9** | **42.8** |
| Processing (3% of money-in) | 0.5 | 1.5 | 2.7 |
| Commons Pool | 2.2 | 5.9 | 10.0 |
| Infrastructure | 0.9 | 3.1 | 5.3 |
| Trust and safety | 1.5 | 1.6 | 2.7 |
| Engine licence | 0.3 | 0.7 | 1.3 |
| Staff | 3.8 | 9.0 | 15.0 |
| Compliance, legal, localisation, payout ops | 0.8 | 2.2 | 3.0 |
| Acquisition (Re-delivery, Founding programmes, Ephemeral Ward) | 0.2 | 0.5 | 0.5 |
| **Operating result** | **-0.9** (Reserve lasts ~7 years) | **+0.5** | **+2.3** |

**Sensitivity:** halving primary sales and subscriptions at Reference scale gives about -US$4.2M. Holding headcount at 75 brings it to about -US$0.4M.

**Coin conservation check (Reference scale):**
- Coin in: purchases 60.0 + allowances 2.6 + Pool 10.0 = 72.6.
- Coin out: commission 10.8 + cash-out 45.0 + fees 1.1 + rent and subscriptions paid from balances 13.5 + services 2.2 = 72.6.

Document 09 must reproduce both the sensitivity and the conservation check.

---

## E. Requirement traceability

- **R1:** Grid: 150-avatar Cells, 1,000 presence, Event Mode 5,000; voice load test is the Sep 2027 gate
- **R2:** Fidelity Contract + Foundry: budgets, fallbacks, degrade order; ≥60 fps on Lite at 100 presence, monthly
- **R3:** Workshop format policy (glTF 2.0 + VRM 1.0, OpenUSD); funded conversion; converter + 24 months' notice
- **R4:** Lantern, Ember and Reader shipped continuously by the newcomer team; protocol at L; third-party clients blessed (certified L+24); first-session completion compared annually
- **R5:** Per-owner Luau budgets that throttle the worst offender; LSL Runtime under the same budgets
- **R6:** Rent for Holdings, Hearth+ and storage; traffic free; Event Mode at cost; no free hosting; mix published annually
- **R7:** Fee Page: own billing; 12.5% round trip; 0% resale; margin printed; store-routed money-in ≤25% by L+12; annual audit
- **R8:** Commons Pool: 25% of net, 20% to venues, returning-purchaser weighting with anti-farming; ≥40% of DAU-hours in creator-run places
- **R9:** Coin as stored value, fiat shown, exact amounts, no bundles; Lineage rule; DFA reviewed within 90 days
- **R10:** Licensed rail; tax data at onboarding; adult-specialist acquirer pre-qualified
- **R11:** Landing with First Light, Call Board and 10% holdout; D.7 keep rule
- **R12:** Ward Plan density SLO, merging, fallow, routing; median ≥10
- **R13:** Census: quarterly, documented "active", API reproducible within 5%, bot and Keeper shares
- **R14:** Lantern and Ember at L; mobile L+9; VR L+30 optional; Stream capped at 2 h with published cost
- **R15:** Civic Calendar, Ephemeral Ward, 100-avatar instances, Posts with deputies
- **R16:** Commons lottery: refundable ticket, 45-day rule, 80% refund, pause policy; no demolition
- **R17:** Estates; ≥50 by L+12
- **R18:** Ferry: Charter Import, NAR, SL import, 18-month Bridge, export
- **R19:** World Charter; Assembly answered within 30 days; public change review; Chronicle
- **R20:** Escrow, NAR export, two providers, voice abstraction, documented exit, 12 months' notice, failover demo at L; Homestead Kit deferred to L+12
- **R21:** Age Module (five profiles at L), no stored IDs, minors only in Campus, OS signals, Night Ward gate
- **R22:** Night Ward controls: pre-publication review, uploader verification, consent records, stored-value coding, deindex-but-sell, adult share published
- **R23:** Safety Kit, Trust ranks, quarterly KPIs (reports per 1,000 user-hours, time-to-action, NCMEC, Ward deletion rates), audit logs
- **R24:** Keepalive and Lineage from L
- **R25:** Keepers under the Human Primacy Charter; deferred to L+12; 20% cap; published costs; D30 parity test
- **R26:** Landing (dressed Common Body, furnished Hearth within ten minutes); Workshop separate from the consumer UI
- **R27:** Reader at L with an XAG 119/GAG checklist and a funded maintainer; Virtual Ability as a Founding Charter
- **R28:** Campus: SSO at L+6, bulk accounts, Class Cell US$34.50, NAR export, persistence covenant; ≥20 institutions by L+18
- **R29:** Language-tagged Wards (PT/ES at L, JA/DE L+12); Pix, then konbini at L+12; translation measured; VRM; Bazaar for outside stores
- **R30:** Floor Plan, Floor Reserve, Tripwire; US$45M; cap of 60; no sibling product; growth gated; break-even at L+36

Deferred to L+12 by design: R20 self-hosting and R25 Keepers. Nothing is unaddressed.

---

## F. Outlines for the ten design documents

Each document uses these H2 headings in order and contains every listed item, using section D values.

1. **docs/design/01-vision-and-principles.md**
   - **H2 headings:** The thesis in one page; What "nolife" means; Who it is for and who it is not; Why now; The four promises; Design principles; The Never List; How we measure success; How the document set fits together.
   - **Must contain:** the three readings as rules; the not-for list; ten principles (including optionality, rent on bytes kept, budgets before fidelity, humans before agents); the D.7 north-star metrics; L = Oct 2028 and break-even at L+36; the base-and-grafts lineage.

2. **02-world-structure-and-places.md**
   - **H2 headings:** The Ward Plan at a glance; Hearths; Holdings, Halls and Reaches; Estates; Wards and the Commons; Night Wards and ratings; The Ephemeral Ward and event instances; Landing halls and Campus; Density, discovery and the empty-world rule; Persistence and lapse handling.
   - **Must contain:** Holding sizes, Weights and prices; Ward composition, open/fallow rules and the six Founding Wards; the Commons ticket, 45-day rule and 80% refund; the density SLO and the median of 10; the Reach 80% rule; sub-let disclosure; the lapse rule; ranking by returning humans.

3. **03-purpose-communities-and-roles.md**
   - **H2 headings:** Purpose comes from communities; Charters; Posts and the deputy rule; The Landing and First Light; The Call Board; The Civic Calendar; Scarcity, relics and status; Standing and Trust; The Chronicle; The first year and optionality.
   - **Must contain:** the Post cap; Landing cadence, size, holdout and keep rule; the weekly rhythm by day; Ephemeral Ward dates and relic rules; Standing ranks and decay; Landing Host pay from the 10% line; the 25% event and 80% venue-survival targets.

4. **04-creation-and-creator-economy.md**
   - **H2 headings:** Two interfaces; Blocks, import and the Foundry; Luau, budgets and the LSL Runtime; Ownership, licence, provenance and the Export bit; Coin and the Fee Page; The Bazaar and vendors; Splits, royalties and the creator ladder; The Commons Pool; Keepalive and Lineage; UGC moderation and fingerprinting.
   - **Must contain:** the full Fee Page and the worked example; the Pool formula and 70/20/10 split; Maker, Merchant and Studio; Split and royalty caps; Starter Catalogue weighting; Market Day as in-person only; the Lineage rule; Foundry stages and cost.

5. **05-graphics-and-client-tiers.md**
   - **H2 headings:** The Fidelity Contract; Tiers and reference devices; Frame budgets; Asset budgets, Scene Weight and Fidelity Rank; The Foundry pipeline; Lighting, skies and keeping UGC beautiful; Avatars: Common Body, atlasing, impostors; Clients: Lantern, Ember, Reader, mobile, VR, Stream; Engine, licence and exit; Darkroom.
   - **Must contain:** every table in D.4; the degrade order; impostors at 30 m; the lighting decision (B.4 item 11); the 30 Sep 2027 licence gate and fallback; the US$16M / 21-month exit; mobile at L+9 and VR at L+30; Compat never cut.

6. **06-architecture-networking-persistence.md**
   - **H2 headings:** The two-layer world; Cells: headless simulation, Jolt and Luau; Presence, interest management and voice; Event Mode and instances; Hibernation and elastic capacity; Entity Store, Vault and snapshots; Multi-vendor deployment, escrow and the Homestead Kit; Protocol and third-party clients; Cost per CCU-hour; Scaling plan and SLOs.
   - **Must contain:** 150 / 1,000 / 5,000; 30 Hz and 10/5 Hz; 200 kbps; sleep after 10 minutes and wake within 8 s; write budgets; the inventory-loss target; the US$0.025 breakdown and the per-Cell cost basis; the capacity schedule and two providers.

7. **07-ai-inhabitants-and-living-world.md**
   - **H2 headings:** AI never counts as life; Keepers and their four jobs; The Human Primacy Charter; Caps, withdrawal and quiet Wards; Stand-ins; The Director; Cognition tiers and published costs; AI as tooling; The experiment, holdout and kill rule; Regulation and voices.
   - **Must contain:** the 20%/0% caps; start at L+12 (Stand-ins L+18); no Posts, money, land, votes or moderation; T0/T1/T2 costs and the 10% ceiling; the D30 parity test (cap to 10%, then zero); quiet Wards; Article 50 disclosure; what was rejected from ai-world-designer.

8. **08-identity-safety-governance.md**
   - **H2 headings:** Passport; The Age Module and regional profiles; Campus and minors; Night Wards and adult commerce; The Safety Kit; Trust ranks and moderation operations; Appeals and Tribunals; Charters, Ward councils and the Assembly; The World Charter and Never List; Census.
   - **Must contain:** 18+ with Campus only for minors; no stored ID images; the five profiles at L; the T&S budget and floor; time-to-action under 24 h; the 72 h and 7-day SLAs; council and Assembly sizes and dates; 12-month notices; the "active" definition.

9. **09-economy-and-business-model.md**
   - **H2 headings:** Money flows end to end; Revenue lines and price list; The Fee Page and required margin; Commons Pool economics; Unit economics at three scales; Sensitivity and Coin conservation; Funding, the Floor Plan and the Tripwire; Team plan and spend sequencing; The Founding Programme; Payments, tax and consumer law.
   - **Must contain:** D.8 reproduced exactly; the US$45M envelope and Series A gates; headcount of 60/100/25; Founders' Pass terms; the Re-delivery Fund; zero paid acquisition; the DFA fallback and DAC7/1099-K handling.

10. **10-legacy-support-and-interoperability.md**
    - **H2 headings:** The moat-and-debt rule; Ferry from Second Life; Charter Import; NAR and OpenSimulator; The LSL Runtime and Luau; Common Body, Bento mapping and Re-delivery; The Bridge and Hypergate; VRM, BOOTH and other worlds; Export, portability and the sunset covenant; What is not imported.
    - **Must contain:** the 18-month Bridge; 90% LSL compatibility; Re-delivery terms; the creator claim; Hypergate at L+18 as the first cut; opt-in Relight; the not-imported list; at least 10 institutions by L+18 and 50 Founding Charters by L+12.

---

## G. Glossary of canonical terms

- **Assembly**: 9-seat elected advisory body.
- **Bazaar**: open-protocol marketplace.
- **Bridge**: 18-month chat and calendar relay with Second Life.
- **Call Board**: the Landing's board of recruiting Charters.
- **Campus**: isolated education tier; the only place for ages 13-17.
- **Cell**: 256 m simulation unit; also a rent product.
- **Census**: public metrics page and API.
- **Charter / Charter Import**: an institution / its one-transaction migration.
- **Chronicle**: append-only public record.
- **Civic Calendar / Civic Engine**: the calendar / the purpose engine.
- **Coin**: display unit; 100 = US$1.00; legally stored value.
- **Commons / Commons Pool**: lottery plots / 25% of net revenue.
- **Common Body**: open-licensed first-party avatar.
- **Component Royalty**: a royalty of up to 10% on derived works.
- **Darkroom**: world-owned photo mode.
- **Domain**: four-cell Holding.
- **Ember / Lantern / Reader**: browser, native and text clients.
- **Entity Store**: authoritative cell state.
- **Ephemeral Ward**: annual ritual Ward, erased on camera.
- **Estate**: Holding with whitelist, seat cap and ranks.
- **Event Mode**: reserved capacity for 5,000 presence.
- **Fee Page**: the published fee stack.
- **Ferry**: legacy import.
- **Fidelity Contract / Rank**: tier budgets / Excellent to Heavy.
- **First Light**: the Landing's shared job.
- **Floor Plan / Reserve / Tripwire**: survival configuration, its US$6M reserve, its trigger.
- **Founders' Pass**: capped three-year prepay.
- **Founding Charter / Merchant / Ward**: launch-programme participants.
- **Foundry**: asset build farm.
- **Grid**: the Cells and Presence architecture.
- **Hall**: a Charter's principal Holding.
- **Hearth / Hearth+**: free / Resident home.
- **Holding**: rented land (Plot S, Plot M, Cell, Domain).
- **Homestead Kit**: partner-only self-hosted cell.
- **Human Primacy Charter**: binding rules for Keepers.
- **Hypergate**: bridge for Firestorm users.
- **Keepalive / Lineage**: escrowed life-support / breedables registry.
- **Keeper**: disclosed AI inhabitant.
- **L**: public launch, October 2028.
- **Landing**: hosted first hour.
- **LSL Runtime**: transparent LSL-to-Luau layer.
- **Market Day / Quiet Day**: Saturday 0% in-person commission / Wednesday without first-party events.
- **NAR**: superset of OAR/IAR.
- **Never List**: permanent refusals.
- **Night Ward**: Adult-rated Ward.
- **Passport**: persistent identity.
- **Post**: role with slots, shifts, badge, stipend and deputy.
- **Presence layer**: crowd replication.
- **Reach**: contiguous mainland.
- **Re-delivery Programme**: paid claims on SL purchases.
- **Reference / Lite / Compat / Stream**: tiers and the streaming funnel.
- **Relight**: opt-in rebuild of legacy content.
- **Resident**: the subscription.
- **Safety Kit**: always-on safety tools.
- **Scene Weight**: content budget that replaces Land Impact.
- **Splits**: up to 10-way revenue division.
- **Stand-in**: opt-in shop-tending Keeper.
- **Standing / Trust**: civic / safety ladders.
- **Starter Catalogue**: creator goods given to newcomers.
- **Tribunal**: three jurors drawn by lot.
- **Vault**: content-addressed asset store.
- **Ward / Ward council**: public district / its 5-seat council.
- **Workshop**: creator interface.
- **World Charter**: the operator's constitution.
