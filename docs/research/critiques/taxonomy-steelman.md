# Steelman: the case against the failure taxonomy

Adversarial critique of `scratchpad/analysis/failure-taxonomy.md`, 2026-10-09.

**Method note.** I read the taxonomy and all 14 live research briefs (`*.prior.md` ignored). I ran 8 of 8 permitted WebSearch calls (standard mode) for counter-evidence; page fetching is blocked in this sandbox, so every "found" fact below rests on the search engine's quoted extracts, not on the cited page. Facts marked **(prior knowledge, unsearched)** were not searched and should be treated as hypotheses. The 8 searches covered: Linden Lab profitability/revenue; D90 retention benchmarks; OpenSim actives and Kitely region pricing; Project Zero's stated end reason; IMVU's current scale; any 2026 Oberwager MAU statement; the arXiv paper behind the demographics section; SLua status.

My brief is to attack, not to be fair. Where the taxonomy is right, I say so briefly and move on.

---

## 0. The one-paragraph version

The taxonomy reads a 23-year-old, profitable, owner-funded company with ~600K MAU, a US$650M/yr economy and a 24% MAU rise in its latest reported year as a failure, then explains the "failure" with eight root causes assigned after the outcome was known. Its strongest causal claims (land tax, purpose vacuum, strategic distraction, onboarding) are not tested against the obvious controls: OpenSim (same architecture, land 5-13x cheaper or free, 1/12 the users), IMVU (no land, no loop, ~7M MAU), industry retention base rates (SL's 10% D90 is average-to-good), and SL's own post-Sansar decade (full focus, same trajectory). The "winners" section is selected on outcome, half the winners are financially shakier than Linden Lab, and the requirement list (R1-R34) specifies a product that no survivor has ever had while every survivor is simpler than it. The hypothesis the taxonomy never entertains is the cheapest one: the global audience for an open-ended adult creation world is roughly 0.5-1M people, SL already has most of them, and nothing in R1-R34 changes that number.

---

## 1. Attack on "Why Second Life did not evolve" (taxonomy section 1)

### 1.0 "Did not evolve" is false on the taxonomy's own evidence

The taxonomy's own citations list, in order: mesh (2011), a licensed money transmitter (Tilia, 2019), EEP (2020), full cloud migration (2020), PBR with HDR/linear colour/reflection probes (2023), mirrors, PBR terrain and 2K textures grid-wide (June 2024), a Unity mobile app with 1M+ downloads (2024), glTF mesh import (2025), a pixel-streamed browser client (2025), and a Luau-based scripting runtime. On the last point the taxonomy is simply stale: R5 says "22 years of LSL-only" and section 1.1 implies nothing changed, but SLua (Linden's Luau fork, open-sourced on GitHub) went from alpha (March 2025) to **beta on parts of the main grid in December 2025**, with a 128 KB memory limit versus LSL's and breaking-change deployments scheduled through 2026 (search extracts: wiki.secondlife.com/wiki/Lua_Alpha; modemworld.me/2026/03/18/). That is the exact item R5 demands, shipping, and the taxonomy does not know it.

Migration speed is also better than implied: Firestorm telemetry (cited in `sl-history-stagnation.md` §4) shows ~80% of its users on a PBR-capable build within about 18 months of PBR launch. Moving a 20-year-old user base with 20 years of content onto a new renderer in under two years is not what stagnation looks like.

**Wrong benchmark.** Section 1.1 judges SL against game engines ("PBR a decade after game engines standardised it"). The relevant comparator is a persistent world that must keep rendering every asset uploaded since 2003. No such comparator exists among the "winners": Roblox's lighting is still the 2020-era "Future Is Bright" pipeline per the graphics brief; Minecraft Java is a 2009 renderer with mods; EVE and WoW are 2003-2004 engines. Among persistent worlds SL is, if anything, an unusually aggressive upgrader.

**"Additive, never a migration" is the moat, not the debt.** Section 1.1 treats eternal backward compatibility as the root defect; section 1.9 says inventories and 20-year-old content are "a switching cost no competitor has offered to carry". These are the same fact. The taxonomy cannot have R3 (a deprecation policy from day one) and keep the moat it praises in 1.9; the first deprecation is the day the moat drains. Horizon Worlds' Unity-to-Horizon-Engine switch stranding its VR content (`successors-wave2`) is the case study in what a deprecation policy does to a live world.

**Firestorm is an asset the taxonomy books as a liability.** "The client was ceded to volunteers" (1.1) and R4 treat a thriving open-source client ecosystem (15+ viewers, the most popular one maintained for free for 15 years, now on the official download page) as a failure of ownership. The alternative reading: Linden open-sourced the viewer in 2007 **(prior knowledge, unsearched)**, and the result is a client that survived every hardware transition at no cost to the company and that the hardcore prefer. No successor in the comparative table ever achieved a volunteer client community at all. The 542,967 unique Firestorm users in 30 days (2015) is evidence that most of the active base is served, not neglected.

### 1.1 The company is profitable and growing; "stalled" conflates hype with the business

The taxonomy opens with "Second Life is not dead" and then spends 240 lines on why it failed. The facts it cites: profitable since 2005 on US$25M raised; ~160 staff funded by a 10% take (Oberwager, Dec 2024, via blog.kowatek.com extract); a blog's reading that owners have taken US$0 out (unverified); MAU 500K (Oct 2024) to 620K (Dec 2025), +24%; economy ~US$650M/yr. No 2025-26 source on profitability surfaced in my search, so "profitable today" is inferred from the 2024 interview and the absence of any layoff or distress coverage; but every successor in table 2.1 that was VC- or corporate-funded is dead, and the privately owned, profit-funded one is the survivor. The taxonomy records this (2.2 #2, #5; alt-survivors "community-funded worlds outlast VC-funded ones") and then prescribes a VC-scale product (R1-R34).

"Stalled" is measured against 2006-2009 hype, which the taxonomy's own `sl-history-stagnation.md` §1 shows was a marketing-ROI bubble that burst before the user base peaked. The right null hypothesis for 2010-2026 is "a mature niche product at its natural size", and the taxonomy never tests it.

### 1.2 Land tax (section 1.2, R6, R21): the best-evidenced counter-case in the corpus is ignored

**The natural experiment.** OpenSimulator grids run the identical simulator architecture, region size, caps, content format and viewer. Region pricing there is US$15-40/month (Kitely 2015 tiers, per Hypergrid Business extracts) or free on self-hosted/OSgrid. Land is therefore 5-13x cheaper than SL's US$199-209, or free. The entire public hypergrid reached a **record 49,690 active users in July 2026** (Hypergrid Business, search extract): about one-twelfth of SL's MAU, after 17 years of trying. If tier were the binding constraint on an SL-shaped world, the cheap clone would be larger. It is not. The taxonomy cites the hypergrid figure (1.9) only to prove nobody replaced SL, never as a test of its own land-tax thesis.

**Price fell, demand fell anyway.** `sl-economy-creators.md` §3 computes that real tier fell roughly by half from 2008 to 2025 while private estates fell 34%. A quantity that falls while its price halves is a demand curve shifting inward. The taxonomy's reading (the tax suppressed growth) predicts the opposite.

**The 34% decline is mostly one event.** Private estates peaked at ~26,600 (Oct 2008, single ambiguous source), were below 19,000 by July 2014, and were 17,668 in April 2026. Roughly 80% of the decline happened in 2008-2014, and the 2008-09 part is the Openspace repricing, which converted or abandoned thousands of quarter-load sims in a few months. From mid-2014 to 2026 private estates fell ~7% in 12 years, i.e. flat. R6's evidence line "SL estates -34% from 2008 peak" is therefore mostly the Openspace episode the taxonomy files separately under governance (1.5), counted twice.

**"Taxed what should have compounded" is backwards.** A flat per-region fee charges an empty sim and a packed venue the same amount *to Linden*. That is a flat tax on space, not a tax on success; the packed venue also has tip and rental income the empty one lacks, so the fee is a smaller share of the venue's revenue. A flat space fee penalises *emptiness*, which is precisely what R21 (45-day use-it-or-lose-it) wants to do by other means. The taxonomy's own alt-survivors brief says the opposite of R6: "Charge for persistence from day one. Every platform that hosted open worlds for free either capped, charged, or shut down" (Spatial, Dreams, Sansar). R6 overrides a research finding without saying so.

**Wrong comparators.** R6 also cites "Sandbox/Decentraland land collapse". Those were speculative NFT assets with no hosting attached; SL tier is a hosting invoice. A hosting fee cannot "collapse"; it can only be paid or not.

### 1.3 Onboarding: "the funnel never moved" because it is at the industry base rate

The taxonomy's two anchors are 10% retained at 90 days (2007) and ~7% retained (2025) and it calls these a root cause. Base rates it never consults: Unity's glossary puts the gaming average at **about 10% at D90** (undated, search extract); GameAnalytics' 2025 benchmark over 11,600 mobile titles says **three-quarters of games fail to reach 3% at D28**, and a 2026 report covering 2025 puts median D7 just under 4%. On those figures a 2003-era desktop download with a 7-10% D90 is average to good. "The funnel never moved" is true and unremarkable; funnels in this industry do not move. R14's premise (first-hour redesign will change the number) is the premise of every orientation redesign Linden tried; the taxonomy records that none worked and concludes that the next one will.

**The 2025 data is read backwards.** "Mobile plus Project Zero reach ~10x the trial volume but only ~7% are retained" (1.3). 7% of 10x is 0.7; 10% of 1x is 0.1. If the Lab's numbers mean what they say, the new funnels produced roughly **seven times** as many retained newcomers as the old one, which is consistent with MAU rising 24% in the same year. The taxonomy quotes "only 7%" as failure and, in 1.7, says the on-ramps were shipped "after the budget to sustain them was spent". No source gives a reason for Project Zero's end; my search found the Lab reframed it in May 2026 as an "experiment" whose lessons feed desktop and mobile, and a 2025 cost of ~US$1.75 per streamed hour (modemworld extract), which is higher than the taxonomy's own $0.5-1 figure, not lower as the no-search checker suggested.

**"DAU has gone down" (Nov 2024) is cherry-picked** against MAU up 24% in 2025. One datum without a series is not a trend.

### 1.4 Purpose vacuum: unfalsifiable as stated

The rule in 2.2 #1 is: dead worlds lacked a loop; survivors had one. Test it on the cases the taxonomy omits or misfiles:

- **IMVU**: a 2004 3D avatar-chat world with no land, no quests, no scarcity, no events calendar, a creator economy (400K products/month) and **~7M MAU (2020, repeated as of Jan 2024 per a company profile extract)**, ten times SL. It appears in neither table. Its "loop" is "meet new people and dress up", which is the "purpose vacuum" by the taxonomy's definition.
- **Second Life itself**: 600K MAU for two decades with the "vacuum".
- **Habbo**: has the canonical loop (rares) and nearly died in 2012.
- **Rec Room**: full of games, 150M lifetime players, dead.
- **Entropia**: its "loop" is a net-extractive deposit economy (US$242M in, US$64M out); calling that purpose proves too much.
- **The bans**: 1.4 says gambling and banking were "the two activity loops with built-in stakes"; `sl-economy-creators.md` §6 says the economy grew 65% the year after both were banned. The loops were not load-bearing.

The variable is being assigned after the outcome. A cause that explains every outcome explains none.

### 1.5 Governance by decree: a constant, not a differentiator

Every behaviour in 1.5 is standard live-service practice, including among the taxonomy's winners: Blizzard's up-to-37% regional price rise (2026), Epic's 1 November 2025 pool rewrite (praised in section 4 as "best practice"), Roblox's repeated DevEx and age-gating changes, Meta's 48-hour reversal, VRChat's EAC. The taxonomy cannot list "continuous re-pricing" as a Roblox strength (section 4) and "decree, outcry, partial retreat" as an SL root cause. R23's model, EVE's CSM, belongs to a game whose subscriber base has also declined for a decade **(prior knowledge, unsearched)**; player councils are nice and do not change the demand curve.

### 1.6 Strategic distraction: the counterfactual fails on dates

- SL's concurrency decline began in mid-2009 and peak concurrency roughly halved by 2013, five years before Sansar's 2014 tease and under full SL focus.
- Sansar's cost was never found (the taxonomy says so). "Roughly six years of the engineering that could have rebuilt the simulator" is an assumption about allocation with no number behind it.
- 2020-2026 is the control: no sibling product, new owners, full focus, and the result is a mobile app still in beta, a streaming product killed at 14 months, concurrency flat at ~45-49K. If focus were the constraint, the post-Sansar decade should look different. It does not, which points at demand, not engineering bandwidth.
- EEP's three-year slip is attributed to Sansar by timing alone.

### 1.7 Hardware timing: the taxonomy blames SL for a bet SL did not make

"SL bet on VR while the market went mobile." The SL product pulled its Oculus viewer within a week in 2016 and never shipped VR again; Sansar was the VR bet, and 1.6 already charges it. Counting it twice is double-counting. Meanwhile, the stated reason mobile is hard for SL is the one the taxonomy itself gives in 1.1: 20 years of unbudgeted content. That is a content-budget problem, not a timing problem, and no successor with a 20-year content base exists to show it can be done.

### 1.8 Demographics: the evidence is a convenience sample, and the conclusion is inverted

The age figures (mean ~45 men, ~38.6 women) come from arXiv 2505.00287, which my search confirms is a paper on avatar versus text social support; its age data is Table 1 of a self-selected survey sample of 1,495 SL respondents, not an age study. Even taken at face value, an audience with a weighted mean age of ~43 and decade-long tenure is a **monetisation asset**: SL's gross economic flow is ~US$1,080 per MAU per year (US$650M / 600K) against Roblox's US$53-61 bookings per DAU per year. The taxonomy frames the cohort as a liability and Roblox's 18+ growth (18-24-year-old gamers, source: a secondary site) as a threat to a 45-year-old builder's world. The Teen Grid closure as "no younger cohort": the Teen Grid never had more than a few thousand users **(prior knowledge, unsearched)**; it was not a pipeline.

### 1.9 What it got right: the section that refutes the rest

1.9 lists cash-out, Tilia, a stable currency, profitability, latent demand (+50% in 2020, +24% in 2025) and the fact that nobody replaced it. Every exogenous shock (2006 hype, 2020 lockdown, 2025 access) produced a step up that then decayed to the same ~500-600K plateau. That is the signature of a fixed-size audience being reached faster, not of a product failing to retain a larger one.

---

## 2. Attack on "Why the successors failed" (section 2)

### 2.1 Survivorship bias in both directions

- **Omitted survivors** that break the patterns: IMVU (~7M MAU, no land, no loop), Avakin Life (1.6M MAU, bigger than SL, no UGC, 12 years), Active Worlds (31 years, skeleton crew), Entropia (24 years, withdrawable currency), OpenSim (17 years, cheap land, tiny). The comparative table lists 19 worlds, 17 dead or zombie, and treats this as evidence about design rather than about the category.
- **Categories are not stable over five years.** Rec Room in 2021 (US$3.5B, 150M lifetime players, UGC everywhere, cross-platform, creator payouts) satisfied every "winner" criterion in section 4 and every "transferable" principle, and is in the failure table. Roblox is in the winners table with DAU down from ~152M to 123M and a ~US$1B GAAP loss; VRChat with 30% layoffs, no published metrics and unknown finances; Zepeto with public numbers that stop in 2022 and EBITDA of about -US$42.5M; Habbo with a 2012 near-death and no broken-out financials; Discord pre-IPO. By the taxonomy's own financial standard, Linden Lab (profitable, owner-funded, growing MAU) is the healthiest company in either table.
- **Reality Labs' US$17.7B/US$19.2B losses are not Horizon Worlds' economics.** They are mostly hardware and R&D; attributing them to a social world's unit economics (2.1 Horizon row, business-models #5) is a category error that inflates the "subsidy" pattern.

### 2.2 The "transferable" principles do not discriminate

For each principle in section 4, a dead platform did the same thing:

| Principle | A winner cited | A failure that did it too |
|---|---|---|
| Engagement pool paid on retention | Epic 40% pool | Horizon US$50M creator fund paid on retention and purchases; Rec Room paid creators US$1M/quarter |
| Scarce, never-reissued items / scarce land | Habbo rares, FFXIV lottery | Habbo 2012 collapse; Decentraland/Sandbox had hard scarcity |
| Native social graph | Discord | Horizon had Facebook's |
| Seat-capped curated servers | NoPixel | thousands of dead FiveM servers, Pax Dei at a few hundred concurrent |
| Platform-owned moderation as a cost line | Roblox US$915M | Roblox also paid US$60M+ in settlements and is still sued; Habbo moderated and nearly died |
| Free, instant, mobile entry | Roblox | Horizon mobile pivot (no published MAU), Zepeto (collapsed when schools reopened) |

Principles that appear on both sides of the ledger are descriptions, not causes.

### 2.3 Pattern #10 "paywall at entry is fatal" contradicts the research

Hytale (buy-to-play US$19.99-69.99) is described in `alt-survivors.md` as "the largest 2026 new entrant in this category" with 1M+ players; FFXIV is a subscription MMO in the winners table. The pattern survives only by not counting them.

---

## 3. Where the taxonomy blames technology for a demand problem

1. **"An event of more than ~100 people cannot exist in one place" (1.1) and R1's 2,000-5,000 event mode.** No winner does this. Fortnite's 14M-concurrent concerts are instanced lobbies of ~100; VRChat instances cap around 80 **(prior knowledge, unsearched)**; Roblox servers run tens to a few hundred. SL's 100-avatar region is in line with the industry, and its venues work around it exactly as everyone else does, with adjacent instances. R1 then prescribes 2,000-5,000 simulated per place on the strength of Star Citizen's "quasi" meshing and Improbable's scripted demos; the taxonomy itself notes that Dual Universe's single shard "worked technically and died commercially". R1 is the same kind of unproven technology bet the taxonomy condemns in 1.7 and 2.2 #3.
2. **"Mirrors render everything twice" (1.1, R2).** Planar reflections render the scene twice in every engine ever shipped; it is the definition of a planar mirror, not technical debt. Using it as the evidence line for R2 is a tell that the technical-debt section was written to a conclusion.
3. **Density arithmetic (1.3, R15).** "1.2 avatars per region" divides concurrency by *all* regions, including ~17,600 private estates that owners pay to keep, most of them homes that are empty when the owner is not home, exactly as houses are. Paid-for emptiness is what ownership looks like. The number that matters, density in public hubs and venues at peak, was never measured; and the taxonomy's own 2.2 #6 shows Horizon, a world with no land at all, had the same emptiness (9% of worlds ever saw 50 visitors). Emptiness tracks audience size, not the land model.
4. **The AWS "uplift didn't change caps" complaint (1.1)** sits beside the Lab's finding that ~50% of users lack high-end machines. The binding constraint is the client and the audience's hardware; the Lab addressed it (Zero, mobile), got 10x trials and a 24% MAU rise, and still saw DAU soften. That is the clearest demand signal in the corpus: when access was removed as a barrier, the ceiling moved a little and stayed. The taxonomy reads it as a technology failure.
5. **R17/R18's three-tier fidelity contract** assumes fidelity gates demand. The research shows the opposite ordering: Avakin (phone, no UGC) at 1.6M MAU beats SL; Resonite (best in-world creation tools in the category) at ~190 concurrent; Blue Mars (best graphics of 2009) dead. The graphics brief's own first pattern is "fidelity is a budgeting problem before it is a rendering problem", which is about cost, not demand.

---

## 4. Numbers that are weak, double-counted or unsearched

- **"Peak concurrency roughly half the 88,220 of 2009" (1, 1.3).** Linden attributed the 2009 decline to its new bot restrictions (`community-purpose.md` §1; `sl-ux` §1), so an unknown share of the 88K was never human. The 2020 pandemic high of 60,068 is a plausible upper bound for the human peak; against that the 2025 peaks of 47-49K are a ~20% decline over 16 years, not a halving.
- **MAU series (1, 1.5, R16):** 1M (2013), 900K (2015), 800-900K (2017), 750K (2023), 500K (2024), 620K (2025) with no stated definition for any of them. The taxonomy admits they are irreconcilable and then uses them for the trend.
- **US$78M / 21,152 / 6,446 / 139 / 14:** one secondhand summary of one town hall, flagged by the taxonomy, still load-bearing for 1.2, 1.9 and R7.
- **"Estates -34% from 2008 peak" (R6):** ~80% of it is 2008-2014, dominated by the Openspace repricing; essentially flat since 2014 (see 1.2 above).
- **Pixel streaming cost (5, R17):** the taxonomy says ~$0.5-1/user-hour and the checker says that is high; a 2025 modemworld extract puts Linden's actual cost at ~US$1.75/hour per session. If so the taxonomy's number is low by 2x and R17's "capped funnel" economics are worse than stated.
- **Age sample (1.8):** convenience sample from a non-demographic paper; weighted mean ~42.8, not "~45".
- **Roblox 18+ DAU +32% (1.8):** secondary site (respawn.outlookindia.com), not the SEC exhibit the same section cites for other figures.
- **Avakin GBP 22M revenue / GBP -11M EBITDA (2.2 #5, 5):** Preqin profile, unverified, used twice as if audited.
- **Reality Labs losses as Horizon economics:** category error (see 2.1).
- **Sansar "six years of engineering" (1.6, R34):** no cost, no headcount, no allocation figure found; the taxonomy says so and keeps the conclusion.
- **Project Zero "after the budget to sustain them was spent" (1.7):** no source gives a reason; the Lab called it an experiment with lessons carried forward.
- **Quantic Foundry 63% (3, R30):** 1,799 self-selected respondents, acknowledged, still used to set a design requirement.
- **"Horizon 9% of worlds with 50+ visitors" (2.2 #6, R15):** a 2022 WSJ leak, used as a density benchmark without noting that SL, the survivor, scores similarly on the same metric.
- **No industry base rate anywhere:** retention (D7/D30/D90), MAU/registration ratio, estate churn, creator income distribution. Every SL number is presented as damning without a comparator; where I found comparators (D90), SL is at or above them.
- **Unsearched items doing load-bearing work:** mesh date, script starvation order, 2020 change of control, VRChat Plus price, Animal Crossing units, Roblox hours, server cost per sim, Teen Grid, Firestorm share, 45 fps frame. The taxonomy labels them; it does not discount them.

---

## 5. Internal contradictions in the requirements

- **R3 (deprecation policy) vs 1.9 (content as moat) vs R25 (full portability).** A world whose inventories export in glTF/VRM and whose assets can be deprecated has no switching cost. The taxonomy wants SL's moat without the thing that makes it a moat.
- **R6 (idle persistence nearly free) vs alt-survivors' "charge for persistence from day one" and the Spatial case (free hosting killed it).** The research says one thing; the requirement says the other; no reconciliation.
- **R7 (<10% all-in take) + R8 (35-45% of net revenue to a pool) + R9 (creators keep 50-70%) + R13 (US$1.5-3 per DAU per month on T&S and infra).** Roblox keeps ~75% of spend, spends ~US$0.9/DAU/month, and loses ~US$1B GAAP. Rec Room died keeping 30c. nolife proposes to keep less than either and spend more per DAU than Roblox. The arithmetic is not shown anywhere in section 5 or 6.
- **R1 (2,000-5,000 per place) vs 2.2 #3 (wrong hardware bet) and the Dual Universe row** ("worked technically and died commercially").
- **R23 (12-month notice, grandfathering) vs section 4's praise of Epic and Roblox for re-pricing continuously.**
- **2.2 #10 (paywall fatal) vs FFXIV (winner) and Hytale (largest 2026 entrant).**
- **R14/R15 (hosted cohorts, density SLOs) vs 1.3's own record** that every orientation redesign since 2007 left the funnel where it was, and vs the D90 base rate.
- **R34 (no sibling product) vs R17 (web + desktop + native mobile + optional VR + capped streaming, all at launch).** Four clients at launch is four sibling products for a company the taxonomy wants funded "from the core economy".

---

## 6. The hypothesis the taxonomy never tests: the audience is small

Put the corpus's own numbers side by side: SL ~600K MAU (23 years, every access channel now open); OpenSim ~50K actives (free land); IMVU ~7M MAU (no land, no creation beyond items); Avakin 1.6M MAU (no UGC); Resonite ~190 concurrent (best tools); VRChat ~150K peak concurrent (no persistence, no land); Horizon <200K MAU with Facebook's distribution; Rec Room dead at 150M lifetime players. Within this set, worlds that drop persistence, land, scripting and cash-out are the ones that get bigger, and the world with all four is the only one that has stayed up for two decades at a profit. The simplest model is that the market for "a persistent, self-owned, scriptable adult world with a real economy" is on the order of 0.5-1M people worldwide, SL already serves most of them, and each demand shock (2006, 2020, 2025) reached the same ceiling faster.

If that model is right, R1-R34 describe a product that costs Roblox money to build and serves a Linden-sized audience. The design implication is not "fix 34 errors"; it is either (a) build a capital-light world priced for a ~1M-MAU ceiling, which is what Linden Lab already runs, or (b) show, with evidence the taxonomy does not currently contain, why the ceiling is a design artefact rather than a demand fact. The taxonomy asserts (b) throughout and never argues it.

---

## 7. What the taxonomy gets right (briefly)

Operator risk and sunset covenants (2.2 #2, R25) are well evidenced across 12+ closures. The regulatory section (5) is the strongest in the document. The UGC-margin finding (Rec Room's 30c) is real and important, though the requirements then ignore it. Measurement opacity (2.2 #7, R16) is a fair criticism of Linden and of everyone else. The Firestorm/EAC/ToS cases do show that unilateral client-affecting changes are trust events. None of this rescues the causal story in sections 1-2.

---

## 8. Factual questions worth a search before the taxonomy is used

1. **Private-estate counts 2009-2014, year by year (Grid Survey archive).** Settles whether the "34% decline" is one Openspace event plus flatline or a continuing trend; R6 and 1.2 hang on it.
2. **Any 2024-2026 primary statement on Linden Lab profitability, revenue and cash distributions** (VentureBeat Dec 2024 original; Lab Gab transcripts; Oberwager interviews). Settles whether "stalled" describes a business in trouble or a profitable niche at its natural size, which decides whether the taxonomy's framing is right at all.
