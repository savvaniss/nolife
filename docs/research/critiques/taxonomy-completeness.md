# Completeness critique of `analysis/failure-taxonomy.md`

Completeness critic, 2026-10-09. Scope: what the taxonomy and the 14 research briefs do not cover, or cover too thinly, to support the design of "nolife" (a Second Life successor that fixes the old failures, carries existing communities forward, has 2026-class graphics, and relies on communities for purpose).

## Method note

- Read the full taxonomy and the headings, method notes, "Who the audience is", OpenSim/export, open-questions and design-implications sections of every non-`.prior` research brief; grepped all briefs for ~60 keywords (languages, adult content, accessibility, tax, engines, music licensing, specific competitors) to confirm absences before calling them gaps.
- 8 WebSearch calls were used (the hard cap). Page fetching is blocked in this sandbox, so every "confirmed" item below rests on the quoted extracts the search tool returned, not on the pages. Anything marked **(prior knowledge)** was not searched and should be treated as a hypothesis.
- Searches run: (1) Second Life + UK Online Safety Act age checks; (2) Linden Lab news Sept-Oct 2026; (3) Roblox Q2 2026 DAU; (4) EU Digital Fairness Act status; (5) SL users by country / non-English communities; (6) Horizon Worlds VR after June 2026; (7) inZOI and Sims Project Rene 2026; (8) payment-processor pressure on adult content.

## Verdict in one paragraph

The taxonomy is strong on the things the briefs researched: SL's architecture ratchet, land-tax economics, the successor graveyard, the 2025-26 child-safety enforcement wave, and the hosting cost structure. It is weak exactly where the project goal is most specific. "Support the futures of their communities" is served by a single demographic paragraph (1.8) and one requirement (R33); there is no census of which communities exist in SL, how large they are, what infrastructure they run on, or what would move them. The single largest resident-built purpose engine in SL, adult and romantic roleplay and the creator economy around it, is absent from the "purpose vacuum" analysis and is treated only as a regulatory liability. Non-English communities (a quarter or more of SL's historical base), consumer law on virtual currencies, the 2025 payment-processor squeeze on adult content, music licensing for the live-performance scene the requirements lean on, and the capital needed to build the thing are not researched at all. Several requirements rest on open questions the briefs themselves flagged as unresolved, and two requirements contradict the alt-survivors brief's main finding.

---

## 1. Gaps confirmed by search

### 1.1 Adult content: the unspoken purpose engine, and the payment rail that may refuse it

- Nothing in the briefs estimates what share of SL activity, land or Marketplace revenue is adult (Zindra, adult private estates, mesh bodies and animation systems sold for intimate use, escort and club economies, partnerships). The taxonomy's top failure pattern is "purpose vacuum", yet the best-documented resident-built purpose in SL is never named. The regulation brief treats adult content purely as a liability; section 1.4 lists gambling and banking as "the two activity loops with built-in stakes" and omits the third.
- Search 1: no 2025-26 reporting exists on how Linden Lab responded to the UK Online Safety Act's 25 July 2025 "highly effective" age-check duty for adult content; the only SL age-verification history found is 2012 (date-of-birth self-declaration replacing Aristotle Integrity). The regulation brief's own open question ("Did Linden Lab change SL's UK adult-content verification?") remains open. nolife's R27 ("Adult districts gated by a highly effective check") has no precedent to learn from.
- Search 8: in July 2025 Collective Shout's open letter (11 July) led Steam to remove a large number of adult titles and add a rule banning content that may violate the standards of its "payment service providers, card networks, banks"; itch.io deindexed all NSFW content on 24 July 2025 with no notice to creators; Valve said processors cited Mastercard rule 5.12.7 and brand risk, Mastercard denied requiring restrictions. No 2026 follow-up and no virtual-world case was found. This is a direct, unresearched threat to R11 (cash-out on a partnered licensed rail) and R27: a rail such as Tilia/Thunes, Stripe or any card acquirer may refuse a world whose economy includes adult goods, and the briefs never ask whether Tilia's licence or acquirer agreements restrict adult commerce today. **(prior knowledge)**: Visa/Mastercard high-risk merchant categories and the 2021 Mastercard adult-content rules (AN 5196) already impose content-review obligations; SL's Marketplace carries adult listings behind a maturity filter.

### 1.2 Non-English communities and regional law

- Search 5: the only country data are 2007-2008. Linden Lab's last published split (slide deck from Lab figures): USA 42.7%, Germany 10.4%, Japan 6%, Brazil 4%; comScore (March 2007) put Germany at 16% of 1.28M actives, more than the US. The 2008 key-metrics ranking by hours put Germany, UK, Japan ahead, Brazil sixth. No current figures exist and no brief covers localisation, machine translation in chat, non-English moderation, regional payment and cash-out methods (Pix, Konbini, SEPA), or non-English community governance.
- The winners brief notes Roblox's growth is led by Japan (+67%) and India (+64%) and VRChat's by Japan, and wave-2 recommends building for Japan, but the taxonomy's requirements (R1-R34) contain no localisation, language, or regional-law requirement at all.
- Regional minors law is covered only for UK, EU, Australia and US states. **(prior knowledge)**: Brazil's "ECA Digital" (Law 15.211/2025, signed September 2025, in force from March 2026) imposes age-assurance, parental-control and default-privacy duties on digital services likely to be accessed by minors; Brazil is historically SL's fourth-largest country. Japan's and Germany's youth-protection regimes (JuSchG, KJM) are also absent.

### 1.3 Consumer law on virtual currencies (threatens R10, R12, R7)

- Search 4: the EU Digital Fairness Act was still in consultation as of a May 2026 law-firm note, with the Commission's draft expected Q3 2026; it was not confirmed published at search time. The consultation explicitly covers virtual currencies that "obscure real-world costs", loot boxes, pay-to-progress and dark patterns; BEUC's 2026 checklist asks for a ban on premium virtual currencies and paid loot boxes. Already in force as soft law: the CPC Network's "Key Principles on In-game Virtual Currencies" (2025) require the real-money price of virtual goods to be shown at the point of purchase. One estimate puts compliance cost at EUR 500K+ for mid-size firms.
- No brief mentions the DFA, the CPC principles, or the 2024-25 CPC action against Star Stable. nolife's R10 (closed, non-transferable currency with a published spread) and R12 (stipend bundled in a subscription) are the exact mechanics under review; the taxonomy does not ask whether a dual-price display (L$ and EUR) or a non-currency pricing model is needed in the EU.
- Also absent: tax reporting for creators who cash out. **(prior knowledge)**: EU DAC7 (platform reporting since 1 January 2023) and US Form 1099-K thresholds (restored to $20,000/200 transactions by the July 2025 US tax act after the $600 rule was repealed) decide what a cash-out rail must collect from creators and when; SL's Tilia already does this and nolife's R11 should specify it. US App Store Accountability Acts (Utah, Texas; Texas SB 2420 effective 1 January 2026, enjoined by a federal court in December 2025, **prior knowledge, unverified**) would move age-signal duties to app stores and affect the taxonomy's "app stores as top-up channels" plan.

### 1.4 2026 state of named competitors

- Roblox (search 3): verified. Q2 2026 DAU 123M (+10% YoY), 29B hours, bookings ~$1.6B (+8%, low end of guidance), ABPDAU $12.66 (-2%), 27M monthly payers at $19.25, net loss $185M, Q3 guidance for year-over-year bookings and FCF declines; sequential DAU 152M -> 144M -> 132M -> 123M. The taxonomy's figure is right; it should add that management attributes the miss to lower per-hour monetisation among younger US/Canada cohorts and to a recommender change favouring retentive games, which is evidence for the taxonomy's own engagement-pool argument (R8).
- Horizon Worlds (search 6): the taxonomy says "VR shutdown announced and partly reversed Mar 2026"; the business-models brief cites a March 19-20 2026 "U-turn", while the safety brief and my search found only the shutdown schedule (Quest Store removal 31 March 2026, VR access ending 13 or 15 June 2026, Hyperscape sharing removed, Reality Labs 1,000+ roles cut, "at least $80B" burned since 2020). No post-June 2026 confirmation of either outcome surfaced. The two briefs contradict each other and the taxonomy should mark Horizon-VR's current status as unknown. Also missing from the hardware/graphics sections: Meta's Horizon Engine (Connect 2025; replaces Unity; claims 4x faster loads, "well over 100" concurrent users, automatic scaling from cloud rendering to phones) and Horizon Studio (beta "later this year"), which is a direct precedent for R17/R18's tiered-fidelity and cloud-to-mobile claims.
- Linden Lab (search 2): no September-October 2026 event found. A May 2026 third-party company profile says ~200 staff, Second Life Mobile public beta open to all, and that Patch Linden (head of product operations) has departed after nearly two decades (unverified). A Japanese roundup mentioning an SL Steam release and the LittleTextPeople acquisition is undated and almost certainly the 2012 announcement; do not use it. "Premium Plus, no stipend" launched October 2025 at US$105.12/yr less, which is relevant to R12.
- Life-sim competitors (search 7): the a-life brief's life-sim comparison stops at The Sims Online (2008). inZOI (Krafton, UE5): 87,377 peak concurrent at launch (March 2025), ~1,000-2,000 daily average by July-August 2026 depending on tracker, ModKit and in-game mod browser since June 2025, Canvas sharing platform 1.2M users and 470K uploads on day one, 1.0 slipped to early 2027. Sims "Project Rene" (Maxis, January 2026): "social, collaborative, mobile-first life-sim", "not an MMO", not a Sims 4 successor, no date. Both are the closest first-party answers to the "home + wardrobe + UGC" loop the taxonomy recommends (R33), and both show the mod/UGC sharing layer outperforming the social layer.

---

## 2. Gaps not searched (prior knowledge; treat as hypotheses)

1. **Community census.** No brief lists SL's communities with sizes, leaders, land, group tools and events: education (VWBPE), disability (Virtual Ability), live music (Cafe Musique, SLISO), roleplay (Gor, urban, fantasy, family RP), religious (Anglican Cathedral, Islam Online), national/language (German, Brazilian, Japanese, Italian, French, Spanish, Turkish, Russian regions), furry (one of SL's and VRChat's largest subcultures), LGBTQ+ and trans communities (VRChat group 36K+ is the only data point), fashion/creator events (Collabor88, Fifty Linden Fridays), breedables, military/combat sims, Bloodlines-style games, BDSM/Gor. "Support the futures of their communities" cannot be designed without this.
2. **Accessibility beyond the EAA.** Blind SL users rely on Radegast (a text/screen-reader client); deaf users rely on text-chat parity, which voice-first worlds (VRChat, Horizon) broke; Virtual Ability's accessible-build standards; the Game Accessibility Guidelines and Xbox Accessibility Guidelines; motion sickness and seated/standing options; autism communities. R33's one clause is not a requirement set.
3. **Educators' actual requirements.** Why educators left for OpenSim (private grids, student data, cost) and what they need now: institutional procurement, FERPA/COPPA for under-18 students, SSO/LMS integration, closed grids, bulk accounts, archiving. R23's "price guarantees" is not enough.
4. **Creators as a segment.** The mesh-body oligopoly (Maitreya, Legacy, eBody, LeLutka heads) sold no-mod/no-transfer; rigging and animation formats (BVH/.anim), Bakes-on-Mesh, the Blender-to-glTF pipeline; creator IP enforcement volumes (DMCA); creator income distribution beyond one town-hall summary; what creators would need to port a store. The legacy brief states the barrier is "the rights, not the formats" but no brief asks creators.
5. **Music and performance licensing.** R19/R20 rely on DJs and live performers (Cafe Musique's 60+ shows/week); SL's Shoutcast streams are largely unlicensed, Twitch's 2020 DMCA wave and Roblox/Fortnite label deals show the alternatives; a world with a published economy and 100K-concurrent events will be a licensing target. Not researched.
6. **Capital, team and time to build.** Linden spent ~$1.3B over 20 years; High Fidelity ~$73M; Sansar unknown; Rec Room raised to a $3.5B valuation and still died. No brief estimates nolife's build cost, headcount, time to a playable world, or the 2026 funding climate for "metaverse" companies after the 2022-26 exits. R34 ("fund the core world from the core economy") has no path from zero to a self-funding economy.
7. **Bots in SL's concurrency.** The a-life brief's open question ("Does SL's concurrency include bots?") is unresolved; Linden's 2023 scripted-agent registration policy exists but no share is known. The taxonomy's 48,802 peak and "1.2 avatars per region" are used uncorrected.
8. **Why OpenSim did not absorb SL.** The Hypergrid is a free SL clone with export, self-hosting and ~45K monthly actives for a decade. It is the cleanest natural experiment for R25 (portability and self-hosting as retention features) and the taxonomy never asks why it stayed at 7% of SL's population; candidate answers (no economy, asset theft, grid instability, no marketing, fragmented population) are each design-relevant. Kitely/DigiWorldz prices in the brief are 2015-era.
9. **Engine make-or-buy.** R26 forbids a sole-source engine but no brief evaluates options: UE 5.8 royalty terms, Unity's post-2023 runtime-fee reversal, Godot 4.x, O3DE, Bevy, or a custom engine (Resonite's FrooxEngine, Meta's Horizon Engine).
10. **BitCraft / SpacetimeDB** (Clockwork Labs; early access July 2025; single-shard, player-built settlements; server open-sourced) is absent from the single-shard analysis that covers EVE, Star Citizen, Dual Universe and Hadean.
11. **The benefit case.** No brief cites the loneliness/mental-health literature on social VR for older, disabled or housebound adults, which is the strongest evidence that an SL-like world should exist and the basis for the disability and education price guarantees in R23.

---

## 3. Claims in the taxonomy made without evidence, or contradicted by the briefs

- 1.8: "The Teen Grid closed in 2011, so no younger cohort replaced the 2006-2009 intake." Teens aged 16-17 were moved onto the main grid in 2011; no cohort data is cited; the inference is unsupported.
- 1.2: "Anshe Chung ... was a landlord arbitraging tier against rent, not a content creator." She also ran a large content and design business; the land-arbitrage point stands but the characterisation overreaches.
- 1.1: "45 fps frame", "scripts are starved first", "Mesh shipped on 23 August 2011" are marked unsearched but used as mechanism evidence for R5.
- 2.2 pattern 5 and section 5: "Avakin lost GBP 11M on GBP 22M revenue" is a GBP -11.17M EBITDA figure from a Preqin profile (alt-survivors: "data-profile site, unverified"); "lost" overstates it.
- 1.3: "1.2 avatars per region" divides median concurrency (bots included) by all regions, most of which are private and access-restricted; the distribution is extremely skewed, so the figure measures land oversupply, not what a newcomer sees.
- R6 ("idle persistence nearly free") and R21 ("unlimited instanced private space") contradict the alt-survivors brief's first design implication ("Charge for persistence from day one. Every platform that hosted open worlds for free either capped, charged, or shut down") and the Spatial/Dreams/Sansar evidence the taxonomy itself cites in pattern 5. The taxonomy needs to reconcile these.
- R13 ("assume near-zero paid CAC with invitations, events and groups as the acquisition engine") has no supporting evidence; SL's own 10x funnel increase came from streaming and mobile on-ramps, not invitations.
- R17/R18 assume a WebGPU client can render a 100-avatar presence layer on mid-range phones; the networking brief lists this as an open question.
- R1's 1,000-5,000 per place extrapolates from Improbable's scripted 4,144-4,500 event, which the networking brief calls "a capability claim, not an observed persistent-world load".
- 2.1 table: Rec Room "shut 1 Jun 2026" is stated as fact; the wave-2 brief lists completion as unconfirmed. Horizon row: "partly reversed Mar 2026" conflicts with the safety brief's June 2026 VR shutdown schedule (see 1.4).
- R20 cites "Anglican Cathedral founder succession" and R19 cites "BURN2"; neither appears in the briefs' headings and I could not locate the evidence in the sections read; the lead analyst should point to the source lines.
- Section 3: Animal Crossing's 31.18M units is unsearched; Smallville and the 1,052-person agent study are "not re-searched"; the conclusion ("AI changes the density problem, not the purpose problem") is reasonable but rests on unverified anchors.

---

## 4. Current events the taxonomy should carry (as of 2026-10-09)

- EU Digital Fairness Act draft expected Q3-Q4 2026 (not yet confirmed published); CPC virtual-currency principles already in force as soft law.
- July 2025 payment-processor squeeze on adult content (Steam, itch.io) with no 2026 resolution found.
- Horizon Worlds VR cutoff scheduled 13-15 June 2026; outcome unconfirmed; Horizon Engine and Horizon Studio as live precedents for tiered rendering.
- Roblox Q2 2026: DAU 123M, fourth sequential decline, Q3 guidance for bookings decline; attribution to younger-cohort monetisation and recommender changes.
- inZOI 1.0 slipped to early 2027; Sims Project Rene confirmed mobile-first social life-sim with no date.
- Linden Lab ~200 staff and Patch Linden's departure (May 2026 profile, unverified); "Premium Plus, no stipend" since October 2025.
- Still to check (not searched): GTA VI launch 19 November 2026 and its effect on FiveM/RP; Discord S-1 and teen-by-default rollout H2 2026; Brazil ECA Digital enforcement; any Ofcom action against UGC worlds.

---

## 5. Recommended gap research briefs (four)

1. `adult-economy-and-payment-rails` — size and shape of SL's adult economy; UK OSA compliance status; whether licensed rails and card networks will carry an adult-inclusive economy after July 2025.
2. `non-english-communities-and-regional-law` — current country/language mix of SL, VRChat and OpenSim; localisation and moderation needs; Brazil, Japan, Germany minors and payments law.
3. `virtual-currency-consumer-law-and-tax` — DFA, CPC principles, loot-box and premium-currency rules, DAC7/1099-K, app-store age acts; what R10/R12/R7 must change.
4. `sl-community-census-and-migration-needs` — a census of SL's communities (education, disability, music, roleplay, religious, national, furry, LGBTQ+, creators) with size, infrastructure, leaders and migration requirements, including accessibility and educator specifics.

Lower-priority gaps for a later pass: music licensing for streamed performance; build cost and funding climate; bot share of SL concurrency; why OpenSim did not absorb SL; engine make-or-buy; BitCraft/SpacetimeDB; the loneliness/benefit literature.

## Sources used in this critique (search extracts only)

- https://www.sec.gov/Archives/edgar/data/0001315098/000162828026051059/ex991-robloxq22026earnin.htm
- https://www.shacknews.com/article/150208/roblox-daus-grew-10-percent-yoy
- https://www.heuking.de/en/news-events/newsletter-articles/detail/digital-fairness-act-implementation-obligations-companies-need-to-prepare-for.html
- https://www.beuc.eu/sites/default/files/publications/BEUC-X-2026-019_Checklist_Towards_the_Digital_Fairness_Act.pdf
- https://mobidictum.com/eu-consumer-protection-push-mobile-game-revenues/
- https://www.comscore.com/Insights/Press-Releases/2007/05/Second-Life-Growth-Worldwide
- https://www.slideshare.net/slideshow/second-life-an-introduction-4356067/4356067
- https://www.yupingliu.com/wordpress/2008/09/22/second-life-demographics-update/
- https://engadget.com/ar-vr/meta-will-shut-down-vr-horizon-worlds-access-in-june-222028919.html
- https://roadtovr.com/meta-horizon-worlds-engine-upgrade-concurrent-users-horizon-studio/
- https://developers.meta.com/horizon/blog/meta-horizon-engine-at-a-glance
- https://www.pcgamesn.com/inzoi/update-june-mod-support
- https://activeplayer.io/?p=7149
- https://www.ea.com/de/games/the-sims/news/future-of-the-sims
- https://80.lv/articles/the-sims-project-rene-has-multiplayer-but-is-not-mmo/
- https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/
- https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story
- https://modemworld.me/2012/07/10/ll-revises-sl-age-verification/
- https://yespress.io/linden-lab
- https://modemworld.me/tag/linden-lab/
