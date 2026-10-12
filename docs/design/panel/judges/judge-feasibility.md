# Judge report: technical and economic feasibility, 2026-2030

Judge lens: can a realistic team and budget build and run this between late 2026 and 2030? Sections 5 (creator economy), 6 (graphics), 7 (architecture), 11 (business) and 12 (roadmap) were weighted hardest. Numbers were checked against `analysis/failure-taxonomy.md` (section 5 unit economics and reconciliation, R1-R30) and the research briefs. No web search was used.

Scale: 1-10 per criterion, 7 criteria, max 70.
(1) solves root causes; (2) communities supply purpose; (3) graphics ambition appropriate and reachable; (4) economics aligned and viable; (5) technical feasibility and architecture; (6) safety and regulatory soundness; (7) legacy support and originality.

## Summary table

| Proposal | C1 | C2 | C3 | C4 | C5 | C6 | C7 | Total |
|---|---|---|---|---|---|---|---|---|
| platform-economist | 8 | 7 | 6 | 9 | 6 | 8 | 8 | **52** |
| studio-exec | 8 | 8 | 6 | 8 | 7 | 8 | 6 | **51** |
| engine-architect | 8 | 6 | 8 | 5 | 8 | 7 | 8 | **50** |
| community-sociologist | 8 | 10 | 6 | 5 | 4 | 8 | 8 | **49** |
| open-web-architect | 8 | 7 | 6 | 4 | 5 | 5 | 9 | **44** |
| ai-world-designer | 6 | 7 | 6 | 4 | 5 | 6 | 7 | **41** |

Ranking: platform-economist > studio-exec > engine-architect > community-sociologist > open-web-architect > ai-world-designer.

## Cross-cutting feasibility findings

These apply to every proposal and set the bar for the per-proposal scores.

1. **Build cost is unresearched, and most proposals under-fund it.** The taxonomy says outright that "build cost and funding climate" and "engines" were not researched. Five of the six proposals raise US$30-45M. That money has to pay for a UE5.8 native client, a second renderer (WebGPU/WebGL2), a text client, a custom cell and presence server, a content pipeline, a licensed payments rail, age-assurance profiles for five jurisdictions and moderation. Corpus anchors are High Fidelity (~US$73M raised, unsearched), Blue Mars (>US$13M, dead on one client) and Rec Room (US$294M). Linden's US$25M to profitability in 2005 is not a fair comparator for a two-renderer, regulated 2026 build. Only engine-architect (US$75-95M) prices the build plainly, and its business section then contradicts that figure (below).
2. **Cell hosting only works if cells sleep.** At US$0.14-0.28 an hour, a 2-4 vCPU cell running all month costs US$101-202. The US$39-99 cell prices in every proposal are viable only because elastic cells hibernate when empty and bill by occupied cell-hours, the Kitely pattern. Studio-exec says so outright (US$10-35 a month per cell). Economist prints a US$18 compute basis, which implies the same thing without stating it. The rest are silent. Any proposal that does not make hibernation a stated architecture rule has a hidden cost line.
3. **Trust and safety at US$1.5-3 per DAU per month is probably low for an adult-capable world.** Every proposal copies the taxonomy's figure. At 150K DAU it buys US$2.7-5.4M a year for infrastructure and safety combined. Infrastructure alone is US$2-3M at Linden scale (engine-architect). That leaves only ~10-30 moderator-equivalents to deliver human pre-publication review of Adult goods, 72-hour appeals, under-24-hour time-to-action and Ofcom-grade evidence. Only studio-exec names it as the line most likely to break the floor budget.
4. **Engine licensing is a business line, not a footnote.** Unreal's standard terms are royalty-on-gross, and a UGC platform that ships an editor and competes with UEFN is a negotiation risk. Engine-architect budgets 2-4% of revenue and an US$12-20M, 18-24-month exit. Economist and studio-exec name a custom licence as the first commercial act and give a fallback (Godot, or Babylon for Lite/Compat). Sociologist, ai-world-designer and open-web-architect wave at it.
5. **Payer-rate assumptions are where proposals diverge most.** The taxonomy's reconciliation uses 60K subscribers (10% of MAU) and 20K paid estates. Proposals that go well past that (sociologist's 150K paid Hearths, open-web's 15K estates at 300K MAU) carry most of their viability on that one number.

---

## platform-economist: 52/70 (rank 1)

| C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|
| 8 | 7 | 6 | 9 | 6 | 8 | 8 |

**C1 (8).** Squarely targets the alignment failure (rent scales with regions, not trade), the hidden 20-31% take, budgets (R2) and governance (R19). It is weaker on the funnel and purpose causes.
**C2 (7).** Roles are paid objects: venue-share stipends split by roster, the Starter Catalogue earning pool points, a lottery, the Week. It works, but the purpose is mostly financial plumbing.
**C3 (6).** A competent copy of the three-tier contract (150K/32K/10K triangles, 16.6/16.6/33 ms) with VRChat-style rank blocking. The Godot replacement path for Lite (12-18 months) is specified. It has no frame-budget breakdown and no pipeline costing.
**C4 (9).** The strongest economics in the set:
- The credit flow is conserved and checks out: US$83 enters per MAU, plus US$17 of pool, against US$24 of commission and US$75 of cash-out.
- Rent is priced on bytes kept, never on visitors, with a printed cost basis per cell (US$18 compute, US$4 storage, US$6 ops against a US$59 price).
- A four-scale P&L is profitable at 300K MAU (+US$1.2M) and at 600K (+US$7.9M), and an explicit sensitivity test (halve subscriptions and sales, and 600K breaks even) is published.
- The survival loss at 100K (~US$1M a year on 30 staff) is covered by a stated US$5M reserve.
- The Founders' Charter prepay sits in a segregated account, and a DFA fallback to stored value is engineered in advance.

Weak inputs: 20% subscription conversion is above the taxonomy's 10%, and US$240 of primary sales per MAU is untested.
**C5 (6).** The architecture is the standard, correct two-layer cell and presence design, with a multi-vendor manifest and named escrow. The roadmap is not credible on time: public launch at month 12-15 on a US$12M seed would need the UE desktop, WebGPU and text clients, the cell server, the ledger, a rail in four jurisdictions and five age profiles all done.
**C6 (8).** The cleanest minors posture. Minors exist only in an isolated, SSO-provisioned Campus with no open economy or cash-out, which takes ECA Digital, PP Tunas and Texas commerce rules out of the economy. Also present: backup withholding budgeted, a stored-value fallback, and adult controls built before anyone asks.
**C7 (8).** The Re-delivery Programme (proof of SL purchase, creator paid 10 NC per claim from an acquisition line) is the only proposal that attacks the rights barrier economically rather than technically. Component Royalties and split ledgers turn a body maker into a platform. Originality is moderate.

**Fatal flaws**
- The month 12-15 launch on a US$12M seed is not buildable. The scope (two renderers plus a text client, cell and presence servers, a ledger, a rail in US/EU/UK/Brazil, five age profiles, charter import, escrow and failover) needs roughly twice the time or money. A slip of 9-12 months pushes the month-36 self-funding target past the US$40M runway.
- Viability rests on 20% of MAU subscribing and US$240 of primary sales per MAU. The proposal's own sensitivity test shows halving both erases the margin at Linden scale, which leaves no buffer for the T&S overrun in finding 3.

---

## studio-exec: 51/70 (rank 2)

| C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|
| 8 | 8 | 6 | 8 | 7 | 8 | 6 |

**C1 (8).** Budgets, rent, governance by charter, published metrics and funding posture are all targeted. It names the incumbent's ability to match prices as risk 1.
**C2 (8).** Arrivals cohorts with a holdout, roles with mandatory deputies, the Almanac, Fairground, curated estates on Rockstar's rules, ward bylaws, and public per-ward deletion rates (the Reddit signal). Institutions trade a weekly event and a deputy for founding rent frozen 36 months. A tight, testable bargain.
**C3 (6).** The ambition is appropriate: Reference at 1440p/60 with 6 ms for avatars, Lite with 5 ms. It states a realistic trade-off: if Epic will not sign a custom licence, Lite and Compat ship on Babylon and Reference waits. Two problems:
- Ten client engineers at launch for a UE client, a Babylon client and Reader is thin.
- It lists cutting the Compat tier as an option, which would re-open the hardware-floor root cause (taxonomy 1.1).

**C4 (8).** The most honest P&L:
- Three states, with the floor shown as a loss: 100K MAU loses ~US$3M a year on 35 staff.
- 400K MAU makes +US$4.6M on 60 staff, and Linden scale reaches ~US$38M revenue against ~US$26M costs.
- Benchmarked against Avakin (GBP 22M revenue, GBP -11M EBITDA, no rent line) and Linden (profitable on ~160-200 staff).
- The pre-sale is capped at US$1.5M for migrating institutions only.
- Hibernating cells make the US$99 cell price arithmetically sound (US$10-35 hosting).

It loses a point because self-funding needs 400K MAU, two-thirds of SL's base, within ~18 months of launch, against the taxonomy's 0.5-1M ceiling. The "D90 ≥40% for institution members" target is also unsupported.
**C5 (7).** The best sequencing in the set:
- Spend order is fixed: rail and compliance before graphics, Reader before VR, charter import before marketplace, Arrivals before AI.
- The 45-person launch team is broken down by function.
- The Series A is raised on four measured numbers.
- A kill criterion is written in: shrink to a 25-person OpenSim-plus-economy business if fewer than 10 institutions migrate.
- Pragmatic reuse: the LSL runtime is built on OpenSim's BSD engine, and first-line moderation, age assurance and the rail are vendors.

It loses points because the seed (20 people, 14 months, cell server at 150 with voice, Reference and web clients, imports, LSL runtime) is very aggressive.
**C6 (8).** The world is 18+ in practice. Night Ward commerce is coded as stored value. KPIs and the active definition are published, and T&S is named as the line most likely to break the floor budget. Moving to an e-money stored-value balance brings payment-institution rules into play, but the partner carries the licence.
**C7 (6).** Legacy support is solid (OAR/IAR, LSL running as-is, charter import, a bridge with a Discord fallback, a vendor programme), but it is the least original proposal; it is mostly a disciplined assembly of the requirements.

**Fatal flaws**
- Engineering is under-resourced for the launch scope. Twenty people in 14 months cannot deliver a 150-avatar voice cell server, a UE Reference client, a Babylon web client, charter and OAR import and an LSL runtime, and 10 client engineers at launch cannot carry two renderers plus Reader. The likely failure is a late or low-quality first-party client, which is exactly the "nobody owned the newcomer interface" debt.
- Self-funding is tied to 400K MAU by month 36. Under the taxonomy's unrefuted ceiling hypothesis that is a market-share bet against an incumbent that can cut prices, and the ~US$3M-a-year floor loss draws on reserves the US$33M plan does not size.

---

## engine-architect: 50/70 (rank 3)

| C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|
| 8 | 6 | 8 | 5 | 8 | 7 | 8 |

**C1 (8).** The deepest treatment of the one root cause with no counter-example (content without budgets), and the "no life-support" engineering rule addresses vendor and engine dependency (R20, R24). Purpose and governance causes are covered at compliance level only.
**C2 (6).** Requirement-complete but thin: roles, charters, a lottery, Event Grounds and an assembly. Role badges carried into impostors is a nice touch. Little that is new.
**C3 (8).** The best graphics plan in the set:
- Tier A has a line-item 16.7 ms budget (Nanite 3.5, Lumen GI 3.0, VSM 2.0, 100 avatars 3.0, and so on), plus a VRAM plan for an 8 GB card.
- There is a Quest 72 Hz budget and per-plot and per-view scene caps with a published degrade order.
- The Foundry is costed: US$0.005-0.02 per asset, US$100-250K a year for weekly rebakes, ~450 TB a month of CDN at 100K DAU.
- Twelve concrete rules keep UGC beautiful.
- It states the trade-off: a triple QA surface and a 25-person, ~US$5M-a-year graphics team.

It is held at 8 for three reasons:
- Building Nanite meshes server-side from user uploads needs Unreal tooling in the cloud, a licensing dependency.
- The WebGPU Tier C renderer must look consistent with UE.
- Console, Quest and A+ path-tracing tiers stretch "reachable".

**C5 (8).** The most feasible core:
- Cells are headless C++/Rust with Jolt and Luau, outside Unreal. Unreal only renders, client prediction uses the same Jolt build, and replication is in-house.
- The engine exit is written down: 18-24 months and US$12-20M, with the web client carrying the world in the meantime.
- The engine licence is budgeted at 2-4% of revenue.
- Inventory-loss rate is a published metric.

The risk is breadth, not design.
**C4 (5).** The reference-scale P&L is reasonable: ~US$46M revenue, ~US$37M costs including the engine licence, rent plus subscriptions at 67%. But the survival configuration is internally contradictory: "At 100K MAU the fixed base must fit ~US$8M of revenue, so headcount is capped at 120", when 120 staff cost US$19.2M a year. The US$75-95M raise is the most honest build estimate in the set, yet it breaks R30's lean posture and has no stated path to the 100K floor.
**C6 (7).** Strong on CopyBot-style fingerprinting at upload, a likeness consent registry ready for NO FAKES, on-device biometrics and C2PA provenance as the AI Act mark. It loses points for admitting minors (six bands, parental surfaces for 10-15) into an adult-capable world headed for consoles, a larger regulatory surface than 18+-plus-Campus.
**C7 (8).** The most technically complete legacy path:
- Prims are regenerated exactly, sculpts rebuilt from displacement maps, and llmesh imported at its top LOD as Nanite source.
- Bento maps to the Common Body by a published table, and particles map to Niagara by parameter.
- An LSL runtime ships alongside a vendor opt-in programme.

Original contributions: the Foundry, a farm-rendered photo mode, and a "your Second Life, lit" claim that can be checked.

**Fatal flaws**
- The survival configuration cannot work: a 120-person cap (~US$19M) against ~US$8M of revenue at 100K MAU. As written this is the subsidy-collapse pattern (taxonomy 2.2 #1), a company that dies the first time growth stalls.
- PS5, Switch 2 and Quest native clients in Phase 2 are not reachable for an adult-capable UGC world with its own billing, cash-out and Adult Districts. Platform-holder content and payment rules make this a scope sink that competes with the Tier C and mobile work the audience actually needs.

---

## community-sociologist: 49/70 (rank 4)

| C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|
| 8 | 10 | 6 | 5 | 4 | 8 | 8 |

**C1 (8).** Targets purpose (1.4), budgets (1.1), rent (1.2), governance (1.5) and funding posture (1.7). Each mechanism maps to a taxonomy cause.
**C2 (10).** The best purpose engine in the set:
- Posts are scarce by rule (one slot per eight active members).
- Standing has two ladders and decays with absence.
- The Landing has a Call Board that ends in three concrete invitations.
- The Civic Calendar includes a Quiet Day that cedes the slot to Charters.
- The Ephemeral Ward mints relics.
- The Chronicle records the operator's own decisions.
- Ward tribunals use jurors drawn by lot.
- Wards open only at 2,000 attached MAU and go fallow below 500.

Every piece is something communities run, not content the operator supplies.
**C3 (6).** Appropriate and conventional: three tiers, a 16.7 ms Reference budget split four ways, Compat avatars at the VRChat Quest cap, Reference deferred to Phase 1. Less detail than engine-architect, and no engine-licence analysis.
**C4 (5).** The structure is right (rent load-bearing, a 12.5% round trip, a 25% pool split 70/20/10), but the numbers stretch. The reference-scale P&L needs 150,000 paid Hearths (25% of MAU) on top of 60,000 Citizens and 15,000 Halls to reach ~US$36.8M and break even. Paid human Landing Hosts, Wardens and Jurors come out of the pool, and Risk 6 admits this labour line is unsized. The funding does not fit: US$35-45M to month 36 against 120 staff, whose payroll alone is ~US$54M over three years even with a ramp.
**C5 (4).** The architecture text is the standard, correct design. The roadmap is the least credible in the set: Phase 0 (9 months, 2,000 CCU closed beta) ships the whole civic core, the text client, desktop and browser clients, OAR/IAR and charter import and the SL bridge, with no team plan, no engine-licence step and no vendor-reuse plan.
**C6 (8).** 18+ by default, with a 13-17 Scholar band confined to Education Halls and General Wards. The regional module is thorough, AI Keepers are capped at 20% and excluded from all metrics, and the World Charter's Never List is explicit. Admitting a Scholar band at all adds some surface compared with economist's Campus.
**C7 (8).** Strong migration (charter import, an LSL transpiler plus a compatibility subset, a vendor licensing programme, OpenSim grids joining as Wards) and the most original civic design (Ephemeral Ward, Standing, Chronicle).

**Fatal flaws**
- The P&L only breaks even if a quarter of MAU pays for a Hearth on top of 10% Citizens. At a taxonomy-consistent payer share, Linden scale runs at a ~US$5-10M annual loss, and the paid-human Landing Host programme (the mechanism the thesis depends on) has no funded line.
- Phase 0 (9 months) and the US$35-45M raise cannot deliver the stated scope with 120 staff. The civic core would launch on unfinished clients, re-running the failure where the newcomer interface was the weakest link.

---

## open-web-architect: 44/70 (rank 5)

| C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|
| 8 | 7 | 6 | 4 | 5 | 5 | 9 |

**C1 (8).** The only proposal that removes the operator as a single point of failure structurally: a Foundation, Apache-2.0 code and forkable data. Budgets live in the asset envelope.
**C2 (7).** Standard machinery (roles with deputies, a lottery, Founding Week, an Assembly electing three board seats), plus calendars federated over ActivityPub and Charters that travel across shards.
**C3 (6).** Reasonable: Lantern on UE (Tier B first), Ember on Babylon, Godot named as the open fallback ("losing Unreal costs Tier A, not the world"). The budgets are looser than the others: Tier A shows everything, with a user-set minimum, up to Poor and Very Poor ranks.
**C4 (4).** Thin and structurally leaky:
- Break-even arrives only near 300K MAU on 15,000 estates at US$39. That is 5% of MAU renting, against SL's ~17,600 estates at ~600K (~3%).
- The open reference server plus a US$15-a-month charter fee lets chartered third-party shards undercut Commons' rent, the line the taxonomy calls load-bearing. OpenSim already showed where that ends: cheap land, no platform economy.
- The Foundation grant and a 2% cash-out fee squeeze the margin further. The proposal's own Risk 6 concedes the thinness.

**C5 (5).** Good choices: Luau on WASM in a component sandbox, QUIC/WebTransport, content-addressed Vault, an S3-compatible asset store. But eight versioned specifications, a conformance suite, three clients, a federation (Crossing, Warden), Hypergate (a second protocol implementation) and rbx-compat on US$30M with 70-80 staff is overreach. Standards work slows product iteration in exactly the years the client must improve fastest.
**C6 (5).** The proposal is candid that federation weakens safety:
- Rogue Open shards speak the identity protocol.
- Defederation is blunt.
- The press will call any bad shard "nolife".
- Commons shards admit 16+ beside Adult-chartered districts.
- One Till rail spans every chartered shard, so a single adult shard's breach exposes the whole network to card-scheme action and OSA/DSA scrutiny of the directory and Crossing.

**C7 (9).** The best legacy and the most original proposal:
- NAR as a superset of OAR/IAR, with `load oar` and `load iar` unchanged.
- The Ferry creator claim via a one-time code in an SL profile.
- Hypergate, a Firestorm-speaking bridge shard.
- rbx-compat for Roblox scripters.
- Bento-to-VRM with a `nolife-bento` extension.
- Sub-letting capped at published rent.
- Standards submission through Khronos and AOUSD.

**Fatal flaws**
- Rent leaks out of the operator. With the server open-source and charter fees at US$15 a month plus 1% of Till volume, low-cost chartered shards will host the estates and Commons keeps the safety and support costs. This rebuilds the OpenSim economics (cheap land, no viable operator) the proposal set out to beat.
- Federated safety plus one shared currency rail means the weakest chartered shard sets the network's regulatory and processor risk. With 16-17-year-olds admitted on Commons, one adult-shard incident can cost the rail for everyone.
- Scope (8 specs, conformance, federation, 3 clients, Hypergate) against US$30M and an 80-person cap.

---

## ai-world-designer: 41/70 (rank 6)

| C1 | C2 | C3 | C4 | C5 | C6 | C7 |
|---|---|---|---|---|---|---|
| 6 | 7 | 6 | 4 | 5 | 6 | 7 |

**C1 (6).** It frames emptiness as the central failure, but the taxonomy classes density as a shared trait of survivors, not a cause. Much of the engineering budget goes to the living layer rather than to the budgets, rent and governance causes, which it covers at compliance level.
**C2 (7).** The human mechanisms are good: crews of 3-12, houses, the Tide's shared ten-minute job that writes every name into the Chronicle, publishing D30 by ladder rung. But Keepers fill unfilled role slots in degraded form, which blurs "people stay where they are needed".
**C3 (6).** Conventional tiers. Reference gives avatars 5 ms and Keepers/crowds 1 ms. Seasons, weather and desire lines are environment state. Reachable, unremarkable.
**C4 (4).** At Linden scale the P&L only breaks even (~US$30M revenue against US$29-32M costs). The survival configuration runs a deficit (40 staff and US$7M a year against ~US$5.5M revenue). US$45M over 36 months has to fund the largest bespoke scope in the set. In its favour, the Keeper cost model is the most rigorous AI costing anywhere in the corpus: token-level per tier, ~US$15K a month at reference scale, 3-6% of infrastructure plus safety.
**C5 (5).** A sound decoupling: the Keeper runtime lives outside cells and degrades to scripted routines, and closed districts advance by a coarse ledger tick. But the ecology, Almanac, Lineage, Keeper memory store, Stand-ins, decay and desire lines are all novel systems with no shipped precedent at this scale, on 110 staff.
**C6 (6).** The Human Primacy Charter is excellent: Keepers are excluded from metrics, hold no money, land or vote, never moderate, and districts can opt out. But the Liveliness Floor lets Keepers reach 50% of visible occupants at peak and six of eight (75%) at the quietest hour. That is the opposite of what the evidence supports, it collides with the 63% generative-AI hostility in the target audience, and it builds AI Act and companion-liability exposure into the core.
**C7 (7).** Lineage (platform-hosted genetics with habitat caps, seasonal trait slots and legible collapse against trait inflation) is the most original fix for breedables. Legacy otherwise matches the field (charter, OAR/IAR, LSL layer, bridge).

**Fatal flaws**
- The thesis is built on the one mechanism the corpus says has no evidence of retaining humans, at a 50-75% occupancy cap, for an audience openly hostile to generative AI. If the R25 holdout fails, the differentiator is gone and what remains is a break-even SL clone.
- The economics are zero-margin at Linden scale and in deficit at the survival floor, while the scope is the largest of any proposal. There is no cushion for the T&S overrun or build slip that finding 1 predicts.

---

## Best ideas to graft into the final design

1. **Rent on bytes kept, not visitors, with compute metered at published cost and a printed per-cell cost basis** (platform-economist). It aligns platform income with persistence without taxing success, and printing the cost basis makes the margin auditable (R6, R7).
2. **Make cell hibernation an explicit architecture rule** (studio-exec; implicit in economist and open-web). It is the arithmetic condition under which US$39-99 cells cover hosting, so it should be a stated SLO, not an assumption.
3. **Re-delivery Programme: verified former customers claim nolife copies against SL purchase records, with creators paid per claim from an acquisition line** (platform-economist). It is the only economic answer to the rights barrier, the real blocker to migrating an avatar's look.
4. **Headless, non-Unreal cell servers (C++/Rust, Jolt, Luau) with Unreal as renderer only, a written US$12-20M / 18-24-month exit cost and a 2-4% engine-licence budget line** (engine-architect). It bounds the largest vendor dependency and keeps server costs off Epic's terms.
5. **The Foundry: a costed server-side pipeline (normalise, fingerprint, LOD chain, impostor, transcode, bake, fidelity rank) with per-view caps and a published degrade order** (engine-architect). It is the concrete mechanism that discharges the one uncontested root cause, at US$10-20K per million assets.
6. **Server-side Bakes-on-Mesh atlas compositing and impostors that carry outfit colour and role badges** (engine-architect). It keeps 100 avatars inside the frame budget without losing social legibility at distance.
7. **Upload fingerprinting against the catalogue as a CopyBot defence** (engine-architect). It is a cheap attribution control on a stream that cannot be DRM-protected.
8. **Spend sequencing plus a kill criterion: rail and compliance before graphics, Reader before VR, Arrivals before AI; the Series A raised on four measured numbers; shrink to a 25-person floor if fewer than 10 institutions migrate** (studio-exec). It converts R30 from a promise into an operating rule.
9. **Engine-terms fallback: if Epic will not sign a custom licence, ship Lite/Compat on the WebGPU stack and let Reference wait** (studio-exec). It is an explicit, low-regret trade-off that keeps launch off the engine negotiation's critical path.
10. **Minors only in an isolated, SSO-provisioned Campus with no open economy or cash-out** (platform-economist). It takes ECA Digital, PP Tunas and Texas commerce rules out of the economy and shrinks the regulatory surface.
11. **Posts scarce by rule (one slot per eight active members), Wards opened only at 2,000 attached MAU and fallowed below 500** (community-sociologist). These are cheap, legible rules that make roles meaningful and stop empty public land before it exists.
12. **An append-only Chronicle that records the operator's own decisions and Assembly answers, plus ward tribunals of jurors drawn by lot who earn Standing** (community-sociologist). Low-cost institutional memory and distributed appeals that make governance visible.
13. **NAR as a strict superset of OAR/IAR over a content-addressed Vault, plus the Ferry creator claim via a one-time code in an SL profile** (open-web-architect). Restores resolve by hash anywhere, and creator reputation migrates with provenance.
14. **Sub-letting capped at the published rent** (open-web-architect). It removes the tier-arbitrage spread that made SL's first fortune a landlord's, at zero engineering cost.
15. **The Keeper cost model (token-level per tier, re-published quarterly) and the Human Primacy Charter clauses (excluded from metrics, no money, land or vote, no moderation, opt-out districts), but with the 20% cap rather than 50%** (ai-world-designer). It is the only rigorous AI costing in the corpus, and its guardrails are adoptable without the high cap.
