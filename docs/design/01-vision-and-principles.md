# 01: Vision and principles

Design document 01 of 10; draft, 2026-10-09. Names and numbers come from [00-design-spine.md](00-design-spine.md) (sections C and D); evidence from [the failure taxonomy](../research/failure-taxonomy.md) (R1-R30) and the [panel proposals](panel/). No new research was done.

**Summary.** nolife is a persistent, adult-first virtual world. One self, one inventory and one social graph carry across every place. Residents build the world, communities run it, and money comes out through a licensed rail. The platform supplies institutions, roles, scarcity, a calendar and a constitution, but no quests, story or artificial civilization. The name sets three rules: the platform manufactures no life of its own; nobody pays for being alive here, only for the bytes they keep and a slice of what they sell; and nothing depends on one engine, vendor or investor staying alive. The audience, in priority order, is Second Life's ~600K residents and the OpenSim hypergrid, then the 2026 diaspora, then adults leaving youth platforms. This document sets the thesis, four promises, ten principles, the Never List and the success metrics. Launch (L) is October 2028; break-even is L+36 at 350K MAU.

---

## The thesis in one page

### What we are building

nolife is a **civilization engine, not a content product**: its job is to make community work cheap, legible and durable, not to be interesting by itself. It has three parts:

1. **A place that persists:** Hearths (free instanced homes), Holdings (Plot S, Plot M, Cell, Domain), Estates, language-tagged Wards and one Ephemeral Ward a year, on a Grid of headless Cells under a Presence layer (150 simulated avatars per Cell, 1,000 presence per place, 5,000 in Event Mode).
2. **Machinery for purpose:** the Civic Engine's Charters (institutions), Posts (roles with slots, shifts, badges and deputies), the Landing (a hosted first hour), the Civic Calendar, Trust, Standing and the Chronicle (an append-only public record).
3. **An economy that pays out:** the Ledger's Coin (display unit, 100 Coin = US$1.00, legally stored value), Fee Page, open Bazaar, Splits and royalties, a Commons Pool of 25% of net revenue, and cash-out on a licensed rail.

Around them sit the commitments that bind the operator: the Fidelity Contract, the Human Primacy Charter, the World Charter and Never List, Census, and Ferry (legacy import).

### The argument in five steps

1. **Second Life is not a failed business, and its audience is not obviously larger than it already serves.** SL has ~600-620K MAU, was profitable by 2005, keeps about 10% of a ~US$650M/yr economy, and its 7-10% D90 retention sits at the industry base rate ([Daniel Voyager](https://danielvoyager.wordpress.com/2025/12/19/second-life-now-at-620000-monthly-active-users/); [Kowatek](https://blog.kowatek.com/?p=88910); [Andrew Chen](https://andrewchen.com/interesting-graph-on-second-life-usage/)). The taxonomy's unrefuted cheapest hypothesis is a ~0.5-1M market mostly already in SL, so nolife breaks even at 350K MAU, survives at 100K and grows beyond only from surplus.
2. **What retains people is a group with a recurring time and place.** What lasted in SL was built and staffed by residents: the Confederation of Democratic Simulators since 2004, Virtual Ability with 1,000+ members, BURN2, and the Anglican Cathedral, which outlived its founder's exit ([SL wiki](https://wiki.secondlife.com/wiki/Confederation_of_Democratic_Simulators); [Virtual Ability](https://virtualability.org/about-us); [Episcopal Cafe](https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/)). Linden supplied places but never roles, schedules or scarcity. nolife treats this as a hypothesis to test with a holdout (R11), not a finding.
3. **The one SL root cause with no counter-example is content without budgets.** With no per-tier budgets, the hardware floor rose with the catalogue; Linden said in January 2025 that about half its users lack high-end machines ([Modemworld](https://modemworld.me/2025/01/02/)).
4. **Successors died of subsidy collapse, not of missing features.** Sansar, High Fidelity, AltspaceVR, Rec Room and Spatial ended when funding posture changed; survivors are cheap to keep alive (taxonomy 2.2). So rent is charged from day one, and the low creator take works only because rent and subscriptions carry the platform.
5. **A successor inherits a community only by carrying its continuity.** Sansar carried no inventory, identity or social graph and inherited no one; Club Penguin Rewritten and Habbo Origins inherited theirs by preserving them ([Vice](https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/)). nolife carries the moat (identity, inventory, the institution) and budgets the debt (content).

nolife is not VR-first, sells no land as tokens, is no sibling product and is not AI-populated; rejected ideas are listed under [How the document set fits together](#how-the-document-set-fits-together).

---

## What "nolife" means

Each reading is a binding rule with a test; a feature spec must name the reading it serves and pass its test.

| Reading | Rule | Test a feature must pass | Mechanisms that implement it |
|---|---|---|---|
| **1. No life of its own** | The platform manufactures no purpose. The life is the work of those insulted as "no-lifers"; the platform makes it cheap, legible and durable. | Does it give a community a tool, role, slot or record (pass), or fill time for the operator (reject)? | Charters, Posts, Civic Calendar, Commons lottery, Chronicle, Standing; Keepers capped at 20% and never counted as life |
| **2. Nobody is charged for being alive here** | Rent on bytes kept and a published slice of sales; never charges for visitors, growth or success. | Does any price rise with traffic or popularity? Reject. Sole exception: Event Mode above 1,000 presence, at cost, waived for Civic Calendar events. | Holding rent by Weight and GB; Fee Page; 0% resale and tips; Hibernation; nothing deleted for non-payment |
| **3. No life-support** | Nothing depends on one engine, vendor, headset, food server or investor staying alive. | If the dependency vanished tomorrow, what survives, and is the loss costed in writing? | Neutral formats (glTF, VRM, OpenUSD, NAR); two hosting providers from L; escrow; a written engine-exit cost (US$16M over 21 months); swappable voice; Keepalive; Floor Plan at 100K MAU |

Two panel readings are excluded: "a world where having no life is impossible because the place is alive" (ai-world-designer) implies an AI-filled world, and "no single company" (open-web) implies federation. The spine rejected both (B.3; B.4 items 1-2).

**Worked application.** "Ambient NPC crowds in empty Wards after midnight" fails reading 1: it fills time for the operator and shows artificial occupancy as life. A Greeter Keeper holding a Landing until a human Host arrives passes, because it hands over and is excluded from metrics (it still faces principle 5 and the L+12 experiment). "Charge Holdings per visitor-hour above an allowance" fails reading 2; it is the economist's metered compute, rejected in B.3. The alternative is Hibernation: a Cell sleeps after 10 minutes empty and wakes within 8 s (p95), which is what makes a US$69 Cell profitable.

---

## Who it is for and who it is not

### Audiences in priority order

| Priority | Who | Approximate size | How they arrive | What they need first |
|---|---|---|---|---|
| 1 | Second Life residents (~600K) and OpenSim hypergrid residents (45-50K) | SL ~600-620K MAU; hypergrid 48,376 actives in May 2026 ([Hypergrid Business](https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/)) | Through institutions (venues, roleplay Estates, disability and care communities, educators, festivals, adult and non-English groups) and earning creators | Charter Import, NAR, LSL Runtime, Re-delivery, Reader, Night Ward, Bridge |
| 2 | The 2026 diaspora from Spatial, Rec Room and Sansar, plus VRM avatar culture | Spatial deleted Free and Pro worlds on 27 July 2026 ([UploadVR](https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/)); Rec Room announced it "can't make the business work" ([GeekWire](https://www.geekwire.com/2026/rec-room-shutting-down-seattles-3-5b-social-gaming-platform-says-it-cant-make-the-business-work/)) | glTF/VRM import, `nolife-bento`, the Bazaar for outside stores such as BOOTH | A written persistence covenant; Founding Merchant terms |
| 3 | Adults ageing out of youth platforms | Roblox 18+ DAU grew 32% year on year in Q2 2026 (secondary source) ([Respawn](https://respawn.outlookindia.com/gaming/gaming-news/roblox-q2-2026-revenue-soars-36-to-15b-despite-bookings-miss)) | Ember (browser, zero install), the Landing | Being dressed and in a room with people within ten minutes |

Priority sets build order: where audiences compete for engineering time, priority 1 wins, which is why Charter Import precedes the Bazaar and Reader precedes VR (C.10). The wedge is institutions, not individuals: each durable SL community has one decision-maker who can bring hundreds to thousands. The Founding Programme recruits 50 Founding Charters, 25 of them by L; in private alpha they bring 5,000-10,000 residents (D.1).

### Who it is not for

| Not for | Why | What the design does instead |
|---|---|---|
| **Children outside Campus** | An adult cash-out economy under ECA Digital, PP Tunas and children's codes is unbounded regulatory risk ([Demarest](https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/); [AVPA](https://avpassociation.com/indonesia/)) | Open world 18+; ages 13-17 only in Campus via institutional SSO (General, no economy); none under 13 |
| **VR-first users** | ~1.77% of Steam users had a headset in January 2026 ([rec0ded88](https://rec0ded88.com/statistics/vr-gaming-headset-ownership/)); headset-gated worlds hit a ceiling (taxonomy 2.2 #2) | Optional VR view at L+30 (OpenXR desktop; Quest 3 at 72 Hz), never required; no native Quest port |
| **Brands buying land** | Unstaffed corporate builds were "a shop in the High Street filled with brochures but never having any staff" ([TechRadar](https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2)) | Staffed brand events sold on measured attendance, never land; no sponsored row |
| **Crypto** | Land sold before population: no survivor did it; tokens invite Howey analysis (taxonomy 2.2 #3) | Never List; Coin is fiat-pegged stored value |

"Not for" means the platform does not design, market or spend for that group; it does not ban them.

---

## Why now

Four conditions changed in 2025-2026.

**1. A 2026 look became affordable on mid-range hardware and in the browser.** Unreal Engine 5.8 shipped Lumen Lite and production-ready MegaLights ([Guru3D](https://www.guru3d.com/story/unreal-engine-58-debuts-lumen-lite-and-productionready-megalights/); [Epic](https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available)). WebGPU has shipped in Chrome, Safari 26 and desktop Firefox, though some devices still need WebGL2 ([gpuweb](https://github.com/gpuweb/gpuweb/wiki/Implementation-Status)). The modal Steam GPU in September 2026 is an RTX 5070 ([Digital Citizen](https://www.digitalcitizen.life/nvidia-rtx-5070-most-popular-gpu-steam-hardware-survey-september-2026/)). With budgets, one world can look current on an RTX 4060/5060 and still run in a browser. Consequence: the Fidelity Contract is a launch dependency, not polish.

**2. Regulation now requires what Second Life never built.**
- UK Ofcom "highly effective" age checks have applied since 25 July 2025 ([Inforrm](https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/)).
- Brazil's ECA Digital has been in force since 17 March 2026.
- EU AI Act Article 50 transparency duties apply from 2 August 2026 ([Stephenson Harwood](https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/)).
- The Digital Fairness Act is expected in November 2026 ([Heuking](https://www.heuking.de/en/news-events/newsletter-articles/detail/digital-fairness-act-implementation-obligations-companies-need-to-prepare-for.html)).

SL's Adult gate is still a self-declared birth date ([SL forums](https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/)); a successor that designs these in starts ahead of an incumbent that must retrofit. Consequence: five Age Module profiles at L, Coin as stored value, the Human Primacy Charter in code.

**3. The 2026 graveyard left communities homeless and proved the economics.** Rec Room, Spatial and Hathora's game customers (Hathora was acquired and wound down within two months) all lost their homes ([GamesBeat](https://gamesbeat.com/?p=318174)). Subsidy collapse kills; rent for persistence pays. Rec Room kept 30 cents of each UGC dollar after store fees ([Rec Room](https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue)). Consequence: own billing, rent on bytes, two hosting providers from L.

**4. Linden shows the model works, and its residents are receptive.** Linden is profitable on about a 10% take ([Kowatek](https://blog.kowatek.com/?p=88910)), but has repeatedly moved its fees:
- Marketplace commission went from 5% to 10% in December 2019 ([Ryan Schultz](https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/)).
- New region and Premium pricing took effect in June-July 2026 ([Modemworld](https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/)).
- Residents estimate the all-in take at 20-31% ([SL forums](https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/)).

Linden never shipped the Export permission bit proposed in 2012 ([Hypergrid Business](https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/)). Consequence: the Fee Page, notice and grandfathering, an Export bit every client honours.

**Not reasons.** VR adoption and AI-NPC maturity are not why now: nothing shows agent-filled density retaining humans (taxonomy section 3), and 63% of 1,799 Quantic Foundry respondents chose the most negative option on generative AI ([Quantic Foundry](https://quanticfoundry.com/2025/12/18/gen-ai/)).

---

## The four promises

Each promise is a product contract with its mechanisms, numbers and a measurable condition under which it is false. Its wording changes only with the spine.

### P-1. To the Second Life veteran

> "Bring your community, your builds, your scripts and, through Re-delivery, your look, and pay about a third of SL's land price under a charter that cannot reprice by blog post."

| Clause | Mechanism | Number | Breaks if |
|---|---|---|---|
| Community | Charter Import: roles, opt-in members, bans, rating, calendar, Holding in one transaction | ≥10 named SL institutions migrated by L+18 | Import splits or drops roles |
| Builds | NAR (superset of OAR/IAR); own-created SL content honouring the Export bit; exact prim, sculpt, llmesh rebuilds; Relight opt-in | `load oar` / `load iar` unchanged | Legacy content forcibly re-lit |
| Scripts | LSL Runtime: unchanged LSL compiled to Luau; unsupported calls fail loudly | 90% of Founding Charter scripts unmodified at L | Below 90% |
| Look | Re-delivery: proven SL purchase pays the creator 10 Coin per claim | ≤US$5,000 per merchant; US$1.5M fund, L-6 to L+24 | Body vendors stay out |
| Price | Cell US$69/month vs SL's US$349 setup + US$199/month (June 2026) | 69/199 = 35%; Founding Charters 30% off, frozen 36 months | Rise without 12 months' notice |
| No repricing | World Charter; Never List | Zero retroactive changes | Any decree-style change |

Not promised: no-transfer third-party content without an Export bit, L$ balances, or SL status (C.9).

### P-2. To the creator

> "Keep 87.5 cents of every dollar, all-in and audited, plus a share of a pool that grows with the world, with Splits, royalties and an Export bit every client honours."

The all-in figure comes from the Fee Page's worked example:

```
net(S) = S × (1 − commission) × (1 − cashout_fee) − rail_cost
       = 100.00 × 0.90 × 0.975 − 0.25        (US$100 of primary sales, ACH payout)
       = 87.50                                → all-in take 12.5%
```

Buying Coin on web or PC costs 0% (the platform absorbs ~3%), with no spread; resale, tips, in-person Market Day sales and off-platform-paid deliveries are 0%. The required margin (5% of gross) is printed beside the stack. The Commons Pool is 25% of net, monthly; 70% goes to creators by distinct returning purchasers wherever they sold. Splits allow up to 10 contributors; Component Royalties cap at 10%. **Breaks if:** the audited effective take is more than 2 points above the published figure (R7), or store-routed money-in exceeds 25% by L+12.

### P-3. To the newcomer

> "In your first hour a human host will say your name, walk you to a live event with at least ten other people and hand you three invitations to be needed."

```
t+0      account, private age band, language → Landing hall for that language
t≤10m    dressed Common Body avatar + furnished Hearth (R26)
         First Light: ten-minute shared job; every name written into the Chronicle
t≤30m    Host walks the cohort (target 12, range 6-20) to an event that starts within 30 minutes
end      Call Board: three invitations; at least one is outside any Charter
```

Cohorts start every 15 minutes per launch language, 16:00-24:00 local; outside those hours, and for a 10% holdout over 6 months, the Landing is self-guided. It is kept only if treated D30 ≥ holdout D30 + 3 points **and** ≥15%, published at L+6. **Breaks if:** the median people visible in a first session falls below 10, or first-session completion below 60%.

### P-4. To the community leader

> "Your Charter moves in one transaction (roles, members, bans, calendar and land), and the world gives you Posts, a treasury, succession and a stage in exchange for one weekly event and a named deputy."

A Charter has a permanent name, 2-20 roles, a ban list, a fixed rating, a calendar, a multi-signature Coin treasury and Holdings; owning land or a calendar requires a named deputy and succession rule. Standing-earning or stipended Posts are capped at one per eight active members (minimum three); event crews and unbadged roles are uncapped. The stage is the Ward Stage (168 hours a week, 40 prime hours by quarterly lottery) and Friday Open Stage. Founding Charters get a migration engineer and a first Cell (a Domain above 500 members) rent-free until L+6. **Breaks if:** fewer than 80% of venues survive a leader's 90-day absence, the test of the deputy rule.

---

## Design principles

Ten principles turn the three readings into working rules, each with its mechanisms, test and exclusions.

### 1. No manufactured life

- **Rule:** The operator ships tools for purpose (institutions, roles, scarcity, calendar, constitution), never purpose itself.
- **Carried by:** Charters, Posts, the Civic Calendar (Wednesday Quiet Day with no first-party events; Friday Open Stage; Saturday Market Day; Sunday Assembly Day), the Ephemeral Ward, the Chronicle.
- **Test:** at least 25% of MAU attend a scheduled event each month, and at least 40% of DAU-hours are spent in creator-run places by L+12.
- **Rules out:** quests, storylines, operator-run seasonal rituals beyond the single Ephemeral Ward (the four separately named rituals were replaced, B.3), and the ai-world-designer's ecology, decay and districts that "go to seed".

### 2. Carry the moat, budget the debt

- **Rule:** A trait is a moat where it keeps people present and a debt where it blocks people not yet present (taxonomy 1.9). Identity, inventory and social graph are carried in full; content is budgeted and converted.
- **Carried by:** Passport, Ferry (Charter Import, NAR, LSL Runtime, Re-delivery, Bridge), and the Foundry's Lite and Compat bakes.
- **Test:** at least 10 named SL institutions migrated with their membership by L+18; 90% LSL compatibility at L.
- **Rules out:** a "fresh start" world with no import (the Sansar mistake), and forced re-making of legacy content.

### 3. Budgets before fidelity

- **Rule:** Reference is a ceiling, not a floor. Every asset gets Lite and Compat versions automatically, Compat is never cut, and the hardware floor never rises.
- **Carried by:** the Fidelity Contract, the Foundry, Scene Weight, Fidelity Rank, and the published degrade order (distant avatars to impostors first; impostors from 30 m). Avatar budgets run from Reference (120,000 triangles) to Compat (20,000).
- **Test:** at least 60 fps on Lite at 100 presence, with p95 frame time per reference device published monthly.
- **Rules out:** a path-traced A+ tier, strand hair, fidelity minimums, and cutting Compat (B.3).
- **Trade-off accepted:** losing Unreal costs Reference, not the world. If the licence is not signed by 30 September 2027, Lantern ships Lite on the web stack and Reference waits.

### 4. Rent on bytes kept, never on people

- **Rule:** Persistence is rented, priced on Weight and GB with a printed cost basis. Traffic is free.
- **Carried by:** the rent list (Plot S US$19, Plot M US$35, Cell US$69 against a US$14 cost basis, Domain US$249), Hibernation, and the lapse rule (frozen for 90 days, then stored as a NAR in inventory and restorable indefinitely). Nothing is ever deleted for non-payment.
- **Test:** rent plus subscriptions are at least 50% of revenue by L+24 (modelled at 66%).
- **Rules out:** metered compute above a visitor allowance, free world hosting, and per-region flat tiers that charge empty and busy places the same.
- **Trade-off accepted:** a newcomer pays nothing to be present, but a builder who wants to keep a large place pays rent. The free Hearth (1 room, 8 guests, 1,000 Weight) is the floor.

### 5. Humans before agents

- **Rule:** AI never counts as life.
- **Carried by:** the Human Primacy Charter. Keepers are capped at 20% of visible occupants, withdraw one-for-one as humans arrive, never hold Posts, money, land, votes or Standing, never moderate, are excluded from every metric and from the Pool, and arrive only at L+12 as an experiment. Ward councils may vote their Ward quiet.
- **Test:** human D30 in Keeper places is at least that of comparable human-only places, or the cap drops to 10%, then to zero. Total Keeper spend is at most 10% of infrastructure plus T&S.
- **Rules out:** a 50-75% Liveliness Floor, Keepers filling role slots, and companion or romantic loops.
- **AI as tooling** (triage, classification, measured translation, Foundry inference, speech-to-text, text-to-speech) is unrestricted where it serves humans.

### 6. Optionality: belonging is offered, never required

- **Rule:** No feature requires Charter membership.
- **Carried by:** one of the three Call Board invitations is always outside any Charter; Standing heraldry is opt-in; Hearths and the Bazaar work for an individual; Quiet Day leaves space for people who do not join anything.
- **Test:** individual-only residents can reach every Trust right and every economic right (Maker, Merchant, Studio).
- **Rules out:** a "Citizen" subscription, civic standing that can be bought, and gating any economic action on group membership.
- **Trade-off accepted:** the Civic Engine's network effect is weaker when joining is optional. In return, the world does not shut out individualists.

### 7. Density is a requirement, not a hope

- **Rule:** An empty world is a defect with a service-level objective.
- **Carried by:** Wards open at 2,000 attached MAU and go fallow below 500 for 90 days (six Founding Wards at L); the density SLO of one avatar per 0.1 ha in Ward hub cells at weekly peak; synchronised instances of about 100; Reach blocks of 64 cells opened only at 80% rented; calendar-first discovery ranked by distinct returning humans, never payment.
- **Test:** a median of at least 10 people seen in a newcomer's first session; at least 70% Commons occupancy at peak.
- **Rules out:** selling acreage ahead of population, and sponsored ranking.

### 8. Adult-first, safe by construction

- **Rule:** The world is built for adults, adult commerce is a measured first-class purpose, and safety is always-on primitives, not a policy page.
- **Carried by:** the Age Module (UK, EU, Brazil, Indonesia, Texas at L; no ID image stored), Campus as the only place for minors, Night Wards (uploader verification, consent records, pre-publication review, deindex-but-sell), the Safety Kit (boundary on by default, 60-second evidence buffer), Tribunals.
- **Test:** median time-to-action under 24 h; Tribunal decisions in 72 h; Trust Desk decisions in 7 days; zero regulator findings.
- **Rules out:** six age bands, admitting 16-17s to General Wards, and a blanket adult exit. Tumblr's 2018 ban cost about 29% of page views ([TNW](https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/)).

### 9. A bound, legible operator

- **Rule:** The company publishes the numbers it would prefer to hide and binds itself in writing.
- **Carried by:** the World Charter (12 months' notice and grandfathering on persistence prices; sunset covenant of 12 months' notice plus escrow release), the Fee Page and its margin, Census, the Chronicle (including operator decisions), Assembly answers within 30 days, public deletion rates per Ward.
- **Test:** Census published quarterly with no gaps; third parties can reproduce concurrency within 5%; zero retroactive price changes.
- **Rules out:** a binding council (no world has shipped one) and repricing by blog post.

### 10. No life-support, including for the company

- **Rule:** No vendor, engine or funding round can end the world; the company is sized to survive a disappointing outcome.
- **Carried by:** two hosting providers from L; one container manifest; voice swappable (ODIN, Discord Social SDK, self-hosted SFU); nightly escrow; a written engine-exit cost; the Floor Plan (25 staff at 100K MAU) and US$6M Floor Reserve; the Tripwire; the US$45M envelope; a cap of 60 staff until recurring revenue covers payroll; zero paid acquisition.
- **Spend sequence:** rail and compliance before graphics; Reader before VR; Charter Import before the Bazaar; the Landing before Keepers; Compat before Reference polish.
- **Test:** a failover demo at L; recurring revenue covers operating costs at L+36.
- **Rules out:** a US$75-95M raise, a sibling product, and growth features funded before rent and subscriptions cover costs.

### Precedence when principles conflict

The spine resolves sixteen conflicts (B.4). For new ones this document proposes an order derived from those resolutions (not a spine decision; see Open questions).

1. Law and child safety (principle 8); cf. B.4 item 6, who is admitted.
2. World Charter and Never List (9); item 5, Coin vs "no coin".
3. Survival (10); item 13, lean vs honest funding.
4. Humans before agents (5); item 2.
5. Rent on bytes kept (4); item 3.
6. Budgets before fidelity (3); item 4.
7. Carry the moat (2); item 14, LSL as-is.
8. Density (7); item 12, Ward threshold vs launch day.
9. Optionality (6); item 9.
10. No manufactured life (1); item 11, resident aesthetics over platform look.

### The feature admission record

Every feature spec in documents 02-10 and later work carries this record; review rejects any empty field.

```text
FeatureAdmission {
  name:               string
  reading:            [NoLifeOfItsOwn | NobodyCharged | NoLifeSupport]   // at least one
  requirements:       [R1..R30]                                          // at least one
  principles_touched: [1..10], conflicts resolved by the precedence order
  never_list_check:   pass | fail                                        // a fail is final
  budget:             { frame_ms_per_tier, usd_per_ccu_hour, ts_usd_per_dau_month, headcount }
  spend_slot:         position in the C.10 spend sequence
  census_series:      the published metric this feature is expected to move
  test:               holdout | launch check | load test, with threshold and date
  kill_rule:          the measured condition under which it is removed
}
```

### Hypothesis lifecycle

Mechanisms resting on unproven hypotheses (the Landing, Keepers, chat translation, Director pacing) run through one state machine, so "keep only what works" is a process.

```text
PROPOSED ──spec admitted──▶ INSTRUMENTED ──holdout live──▶ MEASURING
MEASURING ──keep rule met at review date──▶ KEPT (re-reviewed annually in Census)
MEASURING ──keep rule missed──▶ RESCOPED (one retry, same holdout) ──missed again──▶ CUT
MEASURING ──harm signal (safety KPI, D30 below control)──▶ SUSPENDED ──▶ RESCOPED | CUT
Every transition is written to the Chronicle.
```

Spine instances: the Landing's keep rule (review at L+6); Keepers cut to a 10% cap, then zero, if human D30 falls (from L+12); translation's retention effect measured before it is claimed (R29).

---

## The Never List

The Never List is the operator's permanent refusals under the World Charter. Being permanent, it is read here as extend-only before sunset. Each refusal is enforced in a system, not only in policy.

| Never | Why (evidence) | Enforced where |
|---|---|---|
| **Crypto or NFTs** | Metaverse land volume fell 96% in 2022 ([The Block](https://www.theblock.co/post/197062/ncrooks@theblock.co)); NeosVR died of a founder split over crypto ([Wikipedia](https://en.wikipedia.org/wiki/NeosVR)) | Ledger: no external token or on-chain settlement; Coin leaves only via cash-out |
| **Loot boxes** | Chance plus cash-out value is gambling somewhere; SL banned gambling in 2007 ([TechCrunch](https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/)) | Ledger: no chance mechanic pays cash-out-able value; Lineage previewed, or random only if non-transferable |
| **Retroactive repricing** | Openspace (2008) and the education discount (2010): decree, outcry, retreat (taxonomy 1.5) | World Charter notice and grandfathering; versioned Fee Page |
| **Sale of Standing or Posts** | Bought status stops meaning someone is needed | Civic Engine: no price field, non-transferable |
| **Undisclosed AI** | AI Act Article 50; 63% hostility | Human Primacy Charter badge and notice |
| **Sale of biometrics** | Discord's vendor exposed 70,000 IDs ([The Record](https://therecord.media/discord-government-docs-exposed-breach)) | Passport: on-device or wallet credential; no ID images |
| **Sibling product** | Sansar had no continuity (taxonomy 1.6) | R30, Floor Plan, headcount cap |

---

## How we measure success

### Definitions

- **Active:** entered, moved, and interacted with another human for at least five minutes in the period. Keepers and bots are never active; their shares are published beside the figure.
- **Census** is quarterly; frame times monthly; revenue mix annually; the API reproduces concurrency within 5%.
- **Founding Charter members'** retention is reported separately from organic retention.

### North-star metrics (D.7)

| Area | Metric | Target | When |
|---|---|---|---|
| Arrival | First-session completion | ≥60% | From L |
| Arrival | Median people seen in a newcomer's first session | ≥10 | From L |
| Retention | Organic D7 / D30 / D90 | 25% / 15% / 10% | From L |
| Retention | Founding Charter members D90 | 25% | From L |
| Retention | Landing keep rule | Treated D30 ≥ holdout + 3 pts and ≥15% | Published L+6 |
| Scale | MAU | 100K / 200K / 350K; 600K is the reference ceiling | L+12 / L+24 / L+36 |
| Community | MAU at a scheduled event monthly | ≥25% | Ongoing |
| Community | Venues surviving a leader's 90-day absence | ≥80% | Ongoing |
| Creator economy | DAU-hours in creator-run places | ≥40% | By L+12 |
| Institutions | Whitelisted Estates with weekly events | ≥50 | By L+12 |
| Institutions | Named SL institutions migrated with membership | ≥10 (programme goal: 50 Founding Charters by L+12) | By L+18 |
| Institutions | Commons occupancy at peak | ≥70% | Ongoing |
| Institutions | Campus institutions | ≥20 | By L+18 |
| Reach | Mobile share of DAU / non-US share | ≥30% / ≥40% | By L+24 |
| Reach | Avatar items from off-platform stores | ≥30% | By L+24 |
| Business | Rent plus subscriptions as share of revenue | ≥50% (modelled 66%) | By L+24 |
| Business | Recurring revenue covers operating costs | At 350K MAU | L+36 (Oct 2031) |
| Payments | Payout failure | <1% | Ongoing |

### Guardrail metrics

None may worsen to hit a north-star target: median time-to-action under 24 h; reports per 1,000 user-hours, NCMEC reports and Ward deletion rates (quarterly); inventory loss ≤1 per 10M operations and p95 frame times (monthly); bot and Keeper shares; effective take within 2 points of the Fee Page; store-routed money-in ≤25% by L+12.

### Funding gates and the Tripwire

The Series A (US$33M, June 2028) requires all four:
- at least 15 Founding Charters with at least 50% of invited members active monthly;
- alpha Landing D30 at least 3 points above the holdout;
- at least 1,000 paid Holdings billing;
- a published plan with a headcount cap of 60.

The **Tripwire** triggers the Floor Plan (25 staff at 100K MAU; gap covered by the US$6M Floor Reserve) if either:
- the Series A has not closed by 30 September 2028;
- at L+12, fewer than 10 named SL institutions are active with at least 50% of their imported membership, or MAU is below 60K.

At the Floor the model loses US$0.9M a year (Reserve lasts ~7 years); at 350K MAU and 60 staff it earns +US$0.5M.

### What we do not optimise

The platform does not optimise session length, offline notifications or time-in-app, and discovery ranks by distinct returning humans, not minutes. Roblox's 2026 bookings miss after a recommender change shows how a single engagement metric distorts a platform ([SEC](https://www.sec.gov/Archives/edgar/data/0001315098/000162828026051059/ex991-robloxq22026earnin.htm)).

---

## How the document set fits together

### Hierarchy of authority

1. **[00-design-spine.md](00-design-spine.md)**: canonical names (C), numbers (D) and decisions (B). A contradicting document is wrong; disagreement goes in its Open questions and the spine value stays.
2. **This document**: canonical for the readings, promises, principles, Never List rationale and the admission record.
3. **Documents 02-10**: mechanism detail inside their systems.
4. **[The failure taxonomy](../research/failure-taxonomy.md)** defines R1-R30 and the evidence; **[the panel proposals](panel/)** are lineage only.

### The set

| Doc | Title | Owns | Principles |
|---|---|---|---|
| 02 | World structure and places | Ward Plan (C.2) | 4, 7 |
| 03 | Purpose, communities and roles | Civic Engine (C.1) | 1, 6 |
| 04 | Creation and creator economy | Workshop, Foundry, Ledger (C.3-C.4) | 2, 4 |
| 05 | Graphics and client tiers | Fidelity Contract, clients (C.5) | 3, 10 |
| 06 | Architecture, networking, persistence | Grid (C.6) | 3, 10 |
| 07 | AI inhabitants and the living world | Keepers (C.7) | 5 |
| 08 | Identity, safety, governance | Passport, Safety Kit, World Charter (C.8) | 8, 9 |
| 09 | Economy and business model | Ledger, Floor Plan (C.4, C.10, D.8) | 4, 10 |
| 10 | Legacy support and interoperability | Ferry (C.9) | 2 |

Dependencies: 03 depends on 02 (where Charters live) and 09 (stipends from the Pool's 10% line); 04 owns Foundry policy and 05 its pipeline; 07 waits on 03's L+6 Landing result; 10 depends on 03 (Charter Import) and 04 (the Export bit).

### Lineage: the base and the grafts

The base is **community-sociologist** (162 points): the only proposal that added social design (10/10 from every panel on "communities supply purpose") and the only one saying the operator must not manufacture life. Its two feasibility flaws were replaced:
- **Money** from **platform-economist**: the four money mechanisms, rent list, Splits and Component Royalties, the creator ladder, Re-delivery, Pool anti-farming, Campus-only minors, the DFA fallback; the Pool split corrected and Landing Hosts funded.
- **Roadmap** from **studio-exec**: sequencing, team plan, a Series A on measured numbers, the Tripwire, Hibernation, the "active" definition and Census, LSL as-is.

One part each came from **engine-architect** (Grid core, Fidelity Contract, Foundry, Common Body, Darkroom, CopyBot fingerprinting), **open-web-architect** (NAR, Vault, creator claim, `nolife-bento`, the live-occupancy directory, client names) and **ai-world-designer** (Human Primacy Charter, T0/T1/T2 costs, quiet Wards, Lineage without chance-for-cash, First Light).

### Alternatives rejected at the vision level

| Alternative | Source | Why rejected |
|---|---|---|
| Federated protocol, Open shards on one rail | open-web | Weakest shard sets everyone's card-scheme risk; rent leaks to cheap shards; unfunded. Partner-only Homestead Kit (L+12) instead |
| AI-filled living world (50-75% Liveliness Floor, ecology, decay) | ai-world | No evidence agent density retains people; breaks the persistence covenant |
| Fidelity-first (platform lighting, path tracing, consoles, US$75-95M raise) | engine | Alienates builders; platform-holder rules; recreates subsidy collapse |
| Creator economy as the base | economist | "An excellent shop with an empty plaza" |
| Paid Hearths for 25% of MAU, US$899 lifetime tier, "Citizen" subscription | sociologist | Payer share not credible; unbounded liability; civic standing never sold |
| Launch at month 12-15 with 45 people | economist, sociologist, studio | Not buildable; plan is US$45M, 60 people, launch 24 months after seed |

---

## Requirements addressed

Addressed here at the level of principle; mechanisms are specified in the listed document.

| R | How (this document) | Detail |
|---|---|---|
| R1 | Principle 7; Grid figures 150 / 1,000 / 5,000 | 06 |
| R2 | Principle 3: Reference a ceiling; degrade order; ≥60 fps on Lite | 05 |
| R3 | Reading 3: neutral formats, funded conversion | 04, 05 |
| R4 | P-3, principle 2: newcomer team; Lantern, Ember, Reader | 05 |
| R5 | Principle 3 for scripts: per-owner Luau budgets | 04, 06 |
| R6 | Reading 2, principle 4: rent on bytes; mix ≥50% by L+24 | 02, 09 |
| R7 | P-2: Fee Page formula, 12.5%, margin printed, audit | 04, 09 |
| R8 | P-2: Pool 25% of net, 70/20/10; ≥40% creator-run DAU-hours | 04, 09 |
| R9 | Never List; Coin as stored value | 04, 09 |
| R10 | Why now #2, P-2: licensed rail; payout failure <1% | 09 |
| R11 | P-3, hypothesis lifecycle: holdout and keep rule | 03 |
| R12 | Principle 7: density SLO; median ≥10 | 02 |
| R13 | Principle 9: "active", Census cadence, guardrails | 08 |
| R14 | Not-for list; VR optional at L+30; Compat never cut | 05 |
| R15 | Principle 1: Civic Calendar, Posts and deputies; 25% / 80% | 03 |
| R16 | Principle 7: Commons ≥70% occupancy; no demolition | 02 |
| R17 | Audiences (roleplay Estates); ≥50 by L+12 | 02 |
| R18 | P-1, principle 2: Charter Import; ≥10 institutions by L+18 | 10 |
| R19 | Principle 9, Never List: notice, grandfathering, Assembly | 08 |
| R20 | Reading 3, principle 10: escrow, two providers, exit cost | 05, 06 |
| R21 | Not-for list, principle 8: Age Module, Campus only | 08 |
| R22 | Principle 8: adult commerce measured; Night Ward controls | 08 |
| R23 | Principle 8: Safety Kit; time-to-action guardrail | 08 |
| R24 | Reading 3 ("no food server"): Keepalive | 04 |
| R25 | Principle 5, Human Primacy Charter, kill rule | 07 |
| R26 | P-3: dressed and housed in ten minutes; Workshop separate | 03, 04 |
| R27 | Audience priority 1; Reader before VR | 05 |
| R28 | Not-for list: Campus only for minors; ≥20 institutions | 08 |
| R29 | Non-English groups; PT and ES among the six Founding Wards | 02, 03 |
| R30 | Principle 10: US$45M, cap 60, Floor Plan, Tripwire, L+36 | 09 |

## Open questions

1. **P-3 says "at least ten other people"; the SLO is a median of at least 10**, so up to half of newcomers could see fewer. Cohorts run only 16:00-24:00 local, so before Greeter Keepers (L+12) a 03:00 arrival gets no human Host. Spine wording kept. Proposal: publish the share seeing fewer than 10 and the share arriving outside hosted hours, then reword to "in hosted hours" or add a p25 target.
2. **"About a third of SL's land price" compares US$69 with SL's US$199 monthly fee (35%)**, ignoring SL's US$349 setup fee and cheaper Homestead and mainland products. Document 09 should publish the full comparison.
3. **The "active" definition undercounts solo builders and shopkeepers**, the people the 40% creator-run target depends on. Proposal: a secondary "creator-active" Census series, canonical definition unchanged.
4. **The precedence order** is this document's derivation; the spine should ratify or replace it.
5. **Never List amendment.** The spine says "permanent" but gives no amendment rule; document 08 should write "extend-only" into the World Charter text.
6. **Founding Charter D90 is 25%**; studio-exec argued for ≥40% because members "arrive with a reason". 25% is kept; is it strict enough to test the institutional wedge beside the Tripwire's 50%-of-imported-membership test?
7. **The audience ceiling.** Break-even at 350K MAU is ~58% of SL's current MAU within three years. Census should publish the share of MAU with a prior SL or OpenSim account, separating substitution from expansion.
8. **Re-delivery depends on mesh-body vendors.** Without them P-1's "your look" fails for most migrants; document 10 should set a vendor-participation target.

---

## Sources

Cited inline above; all drawn from the project's failure taxonomy and research briefs.

- https://danielvoyager.wordpress.com/2025/12/19/second-life-now-at-620000-monthly-active-users/
- https://blog.kowatek.com/?p=88910
- https://andrewchen.com/interesting-graph-on-second-life-usage/
- https://wiki.secondlife.com/wiki/Confederation_of_Democratic_Simulators
- https://virtualability.org/about-us
- https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/
- https://modemworld.me/2025/01/02/
- https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/
- https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/
- https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/
- https://www.geekwire.com/2026/rec-room-shutting-down-seattles-3-5b-social-gaming-platform-says-it-cant-make-the-business-work/
- https://respawn.outlookindia.com/gaming/gaming-news/roblox-q2-2026-revenue-soars-36-to-15b-despite-bookings-miss
- https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/
- https://avpassociation.com/indonesia/
- https://rec0ded88.com/statistics/vr-gaming-headset-ownership/
- https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2
- https://www.guru3d.com/story/unreal-engine-58-debuts-lumen-lite-and-productionready-megalights/
- https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available
- https://github.com/gpuweb/gpuweb/wiki/Implementation-Status
- https://www.digitalcitizen.life/nvidia-rtx-5070-most-popular-gpu-steam-hardware-survey-september-2026/
- https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/
- https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/
- https://www.heuking.de/en/news-events/newsletter-articles/detail/digital-fairness-act-implementation-obligations-companies-need-to-prepare-for.html
- https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/
- https://gamesbeat.com/?p=318174
- https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue
- https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/
- https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/
- https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/
- https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/
- https://quanticfoundry.com/2025/12/18/gen-ai/
- https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/
- https://www.theblock.co/post/197062/ncrooks@theblock.co
- https://en.wikipedia.org/wiki/NeosVR
- https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/
- https://therecord.media/discord-government-docs-exposed-breach
- https://www.sec.gov/Archives/edgar/data/0001315098/000162828026051059/ex991-robloxq22026earnin.htm
