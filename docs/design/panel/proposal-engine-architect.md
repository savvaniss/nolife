# nolife: a design proposal from the immersion-and-fidelity angle

Author stance: rendering/engine architect; shipped a UE5 title and a large UGC platform. Written 2026-10-09 from `analysis/failure-taxonomy.md` (R1-R30) and the briefs on graphics, networking, legacy interop, SL economy, SL community census, successors, business models, safety, AI inhabitants, community purpose and adult payment rails. No web search was used; figures keep the briefs' caveats (search extracts; company claims marked).

---

## 1. Thesis and premise

nolife is a persistent, user-built, adult-capable world whose bar is: the best-looking place a stranger can build in, on the hardware people actually own in October 2026, with a real economy and cash-out. It keeps what SL's communities depend on: one persistent self, owned space, in-world creation, 18+ spaces designed in, and money that comes out the other end. No 2016-2026 world offered all five; today only SL (~600-620K MAU, peak concurrency 48,802 on 1 April 2026) and the OpenSim hypergrid (~45-48K monthly actives) do (Source: https://danielvoyager.wordpress.com/2026/05/11/second-life-daily-user-concurrency-update-10th-may-2026/ ; https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/).

The name. "Get a life" is the insult SL residents have absorbed for twenty years; nolife wears it. Read as engineering, it is the first rule: no life-support. Nothing may depend on one vendor, engine, headset or food server staying alive. Ozimals bunnies hibernated for ever when their food server closed (Source: https://boingboing.net/2017/05/20/breedables-vs-drm.html); Firestorm Zero closed within three months when its streaming provider forced a migration (Source: https://modemworld.me/2025/06/27/); Ready Player Me's APIs died on 31 January 2026 (Source: https://variety.com/2025/digital/news/netflix-acquires-ready-player-me-games-avatar-creation-1236612915/); OSgrid wiped its database in 2025 (Source: https://www.hypergridbusiness.com/?p=79686). R20 and R24 are the premise.

The fidelity thesis and the budget thesis are one thesis. The single SL root cause with no counter-example in the corpus is content without budgets: a 256 m region on one process, a Land Impact formula last changed in November 2016, and twenty years of unbudgeted uploads that raised the hardware floor until, by Linden's January 2025 statement, about half of users lacked high-end machines (Source: https://wiki.secondlife.com/wiki/Land ; https://modemworld.me/2016/11/03/lab-reveals-li-prim-allowance-changes-in-second-life-in-full ; https://modemworld.me/2025/01/02/). Every UGC world that works budgets instead: VRChat ranks avatars and hides Very Poor ones on Quest, Roblox sets quality levels and a minimum draw distance, UEFN runs Fortnite's budgets (Source: https://docs.vrchat.com/docs/vrchat-202115 ; https://devforum.roblox.com/t/rdc26-what-we-announced/4865880 ; https://uefncentral.com/blog/uefn-vs-unreal-engine-5-differences). nolife looks like a UE5 title because every asset carries a per-tier budget and an auto-generated fallback (R2). Blue Mars is the warning on the other side: fidelity above the audience's hardware shrank its funnel to nothing (taxonomy 2.1). nolife is not VR-first (~1.77% of Steam users had a headset in January 2026) (Source: https://rec0ded88.com/statistics/vr-gaming-headset-ownership/), not land-token, not a sibling product, not agent-populated.

Four commitments: (1) a three-tier fidelity contract enforced server-side; (2) engine-neutral content (glTF 2.0 + VRM 1.0 runtime, OpenUSD interchange) with a replaceable renderer and a written exit cost; (3) the world supplies beauty and communities supply purpose, with roles, calendars, scarcity and institutions as first-class objects (R11, R15-R19); (4) one closed currency with fiat shown everywhere, a licensed cash-out rail and an all-in creator take at or under 15% (R7, R9, R10).

---

## 2. Who comes first and why

The fidelity angle picks the wedge: communities whose purpose is amplified by how things look, and who can move as institutions rather than as 1,300 sign-ups (R18).

1. SL's professional creators and the fashion-and-photography culture. In 2023, 21,152 creators earned real money, 6,446 over US$1,000, 139 over US$100,000 (single secondhand source) (Source: https://wnhub.io/news/other/item-46605). The top ~1,000 by revenue, above all the mesh body and head vendors, are the only people who can legally bring catalogues, because every SL export path reduces to "creator of every part" (Source: https://modemworld.me/2013/08/24/). The Founders' Foundry offer: platform-funded conversion of their catalogue to PBR and Nanite grade, 0% marketplace take for 12 months, a creator-set Export permission honoured in every client (SL never shipped the bit proposed in 2012) (Source: https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/), and a plain-language licence, because the 2013 ToS episode is institutional memory (Source: https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/).
2. Live music venues. Cafe Musique alone has hosted 600+ performers and runs 60+ shows a week; a venue is a stream URL, host and DJ roles and a tip jar (Source: https://secondlife.aditi.lindenlab.com/destination/aism). Day one: MegaLights stage lighting, parcel stream URLs, tip rails with charity splits, synchronised 100-avatar event instances (R15).

3. Roleplay and combat estates: the 1920s Berlin Project (10+ years, 100+ tenants), the Crack Den, Gor, the military community (Source: https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/). Immersion scales with fidelity; they need estate-grade tools (R17).

4. OpenSim grids and educators, who already pack OARs and left SL when the 2010 discount removal doubled their costs (Source: https://hypergridbusiness.com/?p=35085). Day one: OAR/IAR import, a class estate under US$50/month, SSO, a written persistence commitment (R28).

5. Japanese and VRM avatar creators. Japan is VRChat's largest web market and BOOTH's 3D-model trade exceeded 5.8 billion yen in 2024 (Source: https://roadtovr.com/vrchat-key-stats-japan-growth-concurrents/ ; https://creator-economy.org/vrchat-creator-economy-worlds-avatars-real-money/). Day one: VRM 1.0 import, a toon path, tolerance of off-platform marketplaces (R29).

6. Virtual Ability and text-first communities (1,000-1,300 members), who come only if the Radegast successor ships at launch (R27) (Source: https://virtualability.org/about-us ; https://applevis.com/comment/73862).

Migration: a charter import creates group, roles, members, ban list, rating, calendar and land in one transaction; OAR/IAR import; a 12-24-month chat and event bridge to SL so venues keep their audience (R18). Recruitment is the census brief's named-leader list, each one decision-maker who brings hundreds to thousands. Target: ten institutions migrated by month 18.

---

## 3. The purpose engine

SL supplied neither schedule nor roles (taxonomy 1.4); nolife gives communities instruments and makes the results visible.

Roles are objects: host, mentor, DJ, moderator, builder, performer, curator and judge, each with a schedule slot, a badge rendered on the avatar and carried into its impostor so status survives distance, a stipend source, and a mandatory named deputy for any role owning land or a calendar (R15). Groups inherit SL's substrate (2-10 roles, ban list, land ownership, fixed maturity rating) (Source: https://wiki.secondlife.com/wiki/Group). Institutions are charters: signed documents with name, rules, roles, succession, treasury and calendar; the charter is the unit of migration (R18), tenancy discounts and the assembly franchise.

Scarcity. Prime District plots go by lottery with full-price tickets and a 45-day use-it-or-lose-it rule with refunds and a published pause policy, copied from FFXIV's housing, which produced a venue scene nobody planned (R16) (Source: https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1). Curated roleplay estates are seat-capped with whitelists and paid queue priority: cosmetics and priority yes, pay-to-win and loot boxes no (R17).

Events. A civic calendar on day one: a weekly rhythm (market day, open stage, assembly) and one annual ritual on an Event Ground that exists only that week (the BURN2 pattern); first-party events run as synchronised ~100-avatar instances, and event mode lets 2,000-5,000 attend with impostors (R1, R15).

Governance. A published charter, 12 months' notice and grandfathering on persistence price rises, public change review for client-affecting updates, and an elected assembly whose vote must be answered in writing (R19); EVE's CSM turnout of 12-17% for fifteen years is the benchmark (Source: https://www.eveonline.com/news/view/heres-your-csm-20).

First hour. A new account lands in Arrival, tuned to 60 fps on every tier, inside a hosted cohort of 8-16 with a mentor (R11); gets a furnished Home and a dressed avatar in the Common Body before any build panel (R26); and is routed to the next live event. Success is "met a person or joined a group", measured by randomised holdout, D30 published at month 6. First year: tenure and behaviour raise trust rank; eight hosted events make a resident eligible for a venue stipend; a chartered group with 25 returning members can enter the plot lottery; 90 days' tenure gives an assembly vote. Targets are R15's: 25% of MAU at a scheduled event monthly, 80% of venues surviving a leader's 90-day absence.

---

## 4. World structure

Places, on one map: Districts (public, curated, scarce; a style sheet, a curator, plots by lottery, R16); Estates (rented private land from one plot to a 65,536 m² estate and beyond, with access, ban and rating controls, R17); Homes (furnished, free within the trial allowance, never auto-demolished); Wilds (low-budget sandbox decaying after 30 idle days); Event Grounds (exist only during events).

Space model. The unit is the plot (1,024 m²); lots are 4 plots, estates 64. What is rented is area plus a Scene Impact budget (section 6.5) plus a script budget, never "one server": cells are elastic, so a busy estate gets more simulation, not a bigger bill (R1, R6). Rent is charged from day one above a trial allowance (home, 2,000 inventory items, 250 MB uploads), because the taxonomy's arithmetic shows persistence rent is load-bearing (R6). Published list: plot US$3.99/month, lot US$11.99, estate US$99 (SL's full region is US$199 from June 2026) (Source: https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/), class estate (16 plots, General-rated, SSO, export) US$39, non-profit charter discount 50%. No price rises without 12 months' notice and grandfathering (R19).

Persistence. Document store plus event log with per-cell and per-owner write budgets in the Roblox pattern, hourly snapshots and owner rollback to any snapshot within 30 days (Source: https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits). Inventory-loss events per million operations are published monthly; inventory integrity outranks any rendering feature.

Discovery. Vista ranks places by liveness now, fidelity rank, curator picks and the viewer's language shard (R29); paid placement is limited to time-boxed new-creator slots; empty places are not listed.

Density. Public hubs target one avatar per 0.1 ha at peak; thin instances merge; empty Districts close for the night; newcomers route to live events; a first session shows at least ten people (R12). SL's grid-wide peak average is under two avatars per region (Source: https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/). Instance softness (friends-follow, join-where-my-people-are, cross-instance chat) beats instance size.

---

## 5. Creation and creator economy

Tools. Four on-ramps feed one pipeline: (a) Blocks, in-world parametric building (the successor to prims) that compiles to a Nanite mesh, so a 2004-style builder produces 2026-grade geometry; (b) an in-world material and light editor with a live fidelity meter; (c) Studio, a desktop authoring app that exports glTF/USD and runs the server's budget checks; (d) DCC import of glTF 2.0 and OpenUSD, and MetaHuman Creator output under the creator's own licence. Scripting is Luau in a sandbox with per-owner CPU, memory and network budgets that throttle the worst offender rather than starving everyone as SL's simulator does (R5). Generative tools are assistants with provenance-tagged output, never the world (Source: https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube).

Ownership. Creators keep their IP; the licence grants only display, transcode and cache on the service, with wider use requiring a named opt-in. Every asset carries signed provenance (creator, time, pipeline version, AI-assist flags) in C2PA style, doubling as the EU AI Act Article 50 machine-readable mark (Source: https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content). The Export bit controls whether an item leaves as glTF/VRM/USD; own-created content is always exportable (R3, R18).

Take. One published fee stack (R7): 10% on primary sales, 0% on resale, 1.5% cash-out, no listing fees, web and PC billing owned by the platform, so the round trip from a buyer's dollar to a creator's bank is at most 15%; app stores are top-ups only, capped at 25% of money-in. SL's "90/10" is 20-31% all-in by users' accounting and Rec Room kept 30c of a UGC dollar (Source: https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/ ; https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue). The required margin is printed beside the fee page. No minimum item price; US$25 payout threshold.

Creator pool. 25% of net platform revenue monthly, weighted by returning purchasing users per place with Epic's November 2025 anti-farming rules, 15% reserved for charters and venues measured by distinct returning members (R8) (Source: https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items). Formula published.

Currency and cash-out. One closed currency, transferable between users, never off-platform, at a daily-fixed rate with fiat at every price, exact-amount purchase, no bundles, no chance mechanics paying anything cash-out-able, stipends shown in fiat (R9), the CPC Network's March 2025 position (Source: https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr). No tokens. A licensed partnered rail settles the currency under KYC; W-9/W-8 and DAC7 data are collected at payout onboarding; an adult-specialist acquirer is pre-qualified (R10, R22) (Source: https://www.fonoa.com/blog/dac7overview). Purchases are coded as platform currency, never an adult MCC, plausibly why SL and Tilia were untouched in the July 2025 processor wave that hit Valve, itch.io and DLsite (Source: https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story).

Moderation of UGC. Every upload passes automated review before it is visible: CSAM hashing, likeness detection requiring a consent record, geometry and texture fingerprinting against the catalogue (the CopyBot defence SL never had: a replayed asset matches its original and is attributed), script static analysis, and pre-publication human review for Adult-tagged goods (R22). Upload rights are gated by trust rank (R23).

---

## 6. Graphics and client strategy

### 6.1 Fidelity target

A UE5-class image on the modal 2026 gaming PC, and a coherent, well-lit version of the same world on everything down to a 2021 phone in a browser. "UE5-class" in 2026 means Nanite, Lumen GI and reflections, MegaLights (production-ready in 5.8), Substrate (production-ready in 5.7), virtual shadow maps, ML upscaling and frame generation, and MetaHuman-class faces (Source: https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available ; https://www.unrealengine.com/news/unreal-engine-5-7-is-now-available). Epic's 2026 work went into running that look on Switch 2 and midrange PCs (Source: https://www.guru3d.com/story/unreal-engine-58-debuts-lumen-lite-and-productionready-megalights/).

### 6.2 Engine choice and its exit cost

Unreal Engine 5.8 (tracking 5.9/UE6) renders the Tier A and B native clients: it is the only engine with Nanite, Lumen and Lumen Lite, MegaLights, Substrate and MetaHuman Collections crowds in one package, and MetaHuman licensing opened in June 2025 to any engine and to sale (Source: https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/). Unity 6.3 has no Nanite or Lumen equivalent, and Meta's Unity-to-Horizon-Engine switch is the live example of an engine change stranding content (Source: https://unity.com/blog/unity-6-3-lts-is-now-available ; https://developers.meta.com/horizon/blog/meta-horizon-engine-at-a-glance).
Three boundaries keep the engine replaceable (R20). The engine renders a neutral format (glTF 2.0 with PBR extensions, VRM 1.0, OpenUSD) and never sees a creator .uasset. The simulation does not run in Unreal: cells are headless C++/Rust services with Jolt physics and a Luau VM (section 7), so Epic's server costs and Iris (still opt-in and Experimental in 5.7) are off the critical path (Source: https://www.strayspark.studio/blog/iris-replication-unreal-engine-opt-in-2026). Tier C runs on a non-Unreal WebGPU client, so a fallback renderer exists on day one. Exit cost, written down: re-implementing the Tier A/B renderer on Godot or in-house is 18-24 months and US$12-20M, during which the web client carries the world. Licensing: the standard EULA royalty (5% of gross above US$1M, prior knowledge, unsearched) would be material at platform scale, so a custom platform licence is negotiated before Phase 1 and budgeted at 2-4% of revenue. A UE6 transition is a renderer migration behind the neutral format, not a content migration.

### 6.3 Tiers and devices

| Tier | Devices | Renderer | Lighting | Target |
|---|---|---|---|---|
| A Reference | PC from RTX 4060/5060 (Steam modal GPU is the RTX 5070), PS5, Series X, PS5 Pro | UE: Nanite, Substrate, VSM, MegaLights, DLSS 4 / FSR 4.1 / XeSS 3 | Lumen (hardware Lumen on 12 GB+ cards) | 1440p, 60 fps, 100 full avatars |
| A+ Showcase (optional) | RTX 5070 Ti/5080+, PS5 Pro | As A plus strand hair, optional path tracing | Path-traced photo mode; PT at 30 fps + frame gen | No content may require it |
| B Lite | Switch 2, Quest 3/3S, Steam Deck, M1+ Mac, Snapdragon 8 Gen 2 / A16 and up, desktop WebGPU browser | UE native or WebGPU client; LOD chains, no Nanite on Android/Quest | Lumen Lite where supported (Switch 2, Deck, Mac), baked lightmaps + probes elsewhere, SSR | 60 fps (72 Hz on Quest), 40 full avatars + impostors |
| C Compat | WebGL2 browsers, Linux Firefox, Exynos and older Android, iGPU laptops, GTX 1060-class | WebGPU client with WebGL2 path; forward renderer | Baked lightmaps, one cascaded shadow, probe ambient | 30 fps, 300 m draw distance, 20 full avatars + 2D impostors |
| S Stream | Any, including Tier C devices | Pixel-streamed Tier A session | As A | Hour-capped add-on (6.10) |

Grounding: the RTX 5070 at 5.86% is the most common Steam GPU, followed by the 5060, 5060 Ti, 4060 and 3060 (Source: https://store.steampowered.com/hwsurvey/Steam-Hardware-Software-Survey-Welcome-to-Steam); WebGPU ships in Chrome, Safari 26 and desktop Firefox, but Linux Firefox, Exynos phones and older Android still need WebGL2 (Source: https://github.com/gpuweb/gpuweb/wiki/Implementation-Status). The browser is the zero-install entry (R14); native clients are for building and Tier A. Launch: Windows/macOS native and web; native iOS/Android within 12 months; Switch 2, PS5 and Quest in Phase 2. VR is optional (OpenXR on PC, a Tier B Quest client); identity, inventory and the economy never require it.

### 6.4 Frame budgets

Tier A, 1440p output (960p internal, Quality upscaling), 60 fps, 16.7 ms GPU: Nanite visibility and base pass 3.5 ms; Lumen GI 3.0; Lumen reflections 1.2; virtual shadow maps 2.0; MegaLights capped at 32 shadowed lights per view 1.5; 100 avatars (skinning, hair cards, cloth on the nearest 10) 3.0; translucency and Niagara 1.0; post and upscale 1.3; UI 0.2. VRAM on an 8 GB card: 2.5 GB texture pool, 1 GB Nanite streaming, 1.5 GB avatars, 1.5 GB caches and targets, 1.5 GB headroom.

Tier B on Quest 3 at 72 Hz, 13.9 ms across both eyes with fixed foveation: base 4.0; shadows 1.5; 40 avatars at 0.1 ms 4.0; translucency 1.0; post 1.5; headroom 1.9. Tier C at 30 fps, 33 ms: forward pass 12, one cascaded shadow 4, 20 avatars 8, post 3, headroom 6, billboard impostors beyond 60 m. These are SLOs: p95 frame time per reference device is published monthly (R2, R13).

### 6.5 Asset budgets per tier

Avatars (enforced at upload; the Foundry generates each lower tier automatically):

| | Tier A | Tier B | Tier C |
|---|---|---|---|
| Triangles | 120,000 | 35,000 | 20,000 |
| Materials | 12 | 6 | 2 (atlased) |
| Bones | 300 (face rig included) | 120 (VRM humanoid + spring) | 75 |
| Texture memory | 80 MB | 24 MB | 8 MB |
| Attachments | 24 | 12 | 6 |

The Tier C cap is VRChat's Quest "Very Poor" threshold; over-cap content is replaced by its tier version, never hidden.

Scenes (per 1,024 m² plot; estates scale linearly under per-view caps):

| | Tier A source | Tier B derived | Tier C derived |
|---|---|---|---|
| Source triangles (Nanite) | 5,000,000 | 1,000,000 (LOD chain) | 150,000 |
| Texture bytes | 384 MB | 96 MB | 24 MB |
| Dynamic shadowed lights | 16 | 4 | 1 |
| Unique materials | 64 | 32 | 16 |
| Physics bodies | 200 | 200 | 100 |
| Script CPU (server) | 2 ms/tick | same | same |

Per-view caps regardless of plot count: 20M visible source triangles, 2.5 GB streaming pool, 32 shadowed lights, 300 skinned meshes on A; over a cap the renderer degrades in a published order and the owner sees which assets caused it.
### 6.6 The Foundry: the UGC content pipeline

Every upload, import and Block edit runs through a server-side build farm: validate and normalise (glTF 2.0, 1 unit = 1 m, PBR); fingerprint; build the Nanite mesh; generate a 4-level LOD chain and an octahedral impostor; auto-generate collision; transcode textures to BC7/ASTC/ETC2 and KTX2 for the web; map Substrate down to simple PBR for B and C; flag emissive above the luminance cap; bake lightmaps and probes per plot for B/C, debounced hourly; assign a fidelity rank (Excellent/Good/Fair/Heavy) shown on listings and avatars. Cost: a Nanite build plus LOD chain plus transcode is 20-60 s of spot compute, about US$0.005-0.02 per asset at US$0.07/vCPU-hour; a plot bake is 2-5 GPU-minutes, US$0.02-0.05 (Source: https://edgegap.com/pricing). A million assets a year costs US$10-20K; 100,000 plots rebaking weekly, US$100-250K. CDN at 100K DAU is ~450 TB/month, US$9-18K/month. The pipeline is cheap; what it buys is that nothing unbudgeted ever reaches a client.

Format policy (R3): glTF 2.0 + VRM 1.0 at runtime, OpenUSD for interchange (AOUSD's 2026 Core Spec and characters group give USD a standards path) (Source: https://www.linuxfoundation.org/press/aousd_prmarch2026); conversion is platform-funded; retiring any format needs a converter and 24 months' notice. Neural texture compression (RTXNTC claims ~5 bits/texel, 2.5 MB versus 12 MB BCn for a 2K material) is a 2027 upgrade once SM 6.10 cooperative vectors leave preview; today the SDK is stamped do-not-ship (Source: https://github.com/NVIDIA-RTX/RTXNTC). Gaussian splats (NanoGS in Unreal) are a backdrop-only place-capture format, capped at 500K splats on B/C (Source: https://www.cgchannel.com/2026/03/free-plugin-nanogs-puts-nanite-style-gaussian-splatting-in-unreal-engine/).

### 6.7 Lighting

Lighting is platform-owned. One sky, sun and time-of-day per District or estate (owner-adjustable within a gamut, not per parcel), one exposure model, Lumen or Lumen Lite so every object is lit by its surroundings, creator lights budgeted per plot; on B/C the Foundry bakes the same scene. Full-bright is not a material option; emissive is, under a luminance cap.

### 6.8 Avatars

The avatar pipeline is owned, because the rented layer collapsed (RPM, Union Avatars) and platform-owned realism is tied to sensors (Apple Persona, Meta Hologram) (Source: https://roadtovr.com/vision-pro-persona-avatar-upgrade-visionos-26/). The Common Body is a first-party, open-licensed body and head set (realistic and stylised), built in-house rather than derived from MetaHuman so it can be open-licensed (R26), on a VRM 1.0 humanoid skeleton extended by a MetaHuman-compatible facial rig (so MetaHuman Animator from a webcam drives it on Tier A) and a Bento bone-mapping table for imported SL animations. Clothing layers composite into one atlas per avatar at the Foundry (server-side Bakes-on-Mesh), which keeps 100 avatars inside the Tier A budget. Beyond 30 m, avatars render as crowd instances or impostors that still carry outfit colour, silhouette and role badge, fed by a compact look descriptor on the presence layer. Face and eye tracking are processed on device and only abstracted animation data leaves the headset (Source: https://www.meta.com/legal/quest/eye-tracking-privacy-notice/).
### 6.9 Keeping UGC beautiful rather than ugly

SL's look comes from inconsistent scale, full-bright materials, mixed texture resolutions, no GI, 2007 prims beside 2024 mesh and sky presets fighting across parcel lines. nolife's rules, enforced by the Foundry or a District charter:

1. One scale: 1 unit = 1 m, Common Body height 1.55-1.95 m, Blocks snap to 5 cm; imports are measured and flagged.
2. One lighting model; no per-parcel sky, no full-bright.
3. PBR only, with roughness floors and normal-map validation; diffuse-only imports get inferred roughness and a Legacy flag.
4. Texture floors and caps: at least 256 px per metre at Tier A, at most 2K per material, mips always.
5. Budgets with fallbacks, not bans: over-budget content degrades to its tier version and is never hidden from the person who bought it.
6. Fidelity rank on listings, avatars and plots; Districts may set a minimum, as VRChat worlds set minimum avatar ranks.
7. District style sheets and resident curators for prime public land; estates and Wilds are free.
8. A free platform kit library of licensed Tier A materials, props, foliage and light rigs, so an amateur build starts from good materials under good light.
9. Nanite for everything static, so there is no LOD pop and no reward for low-poly ugliness.
10. Showcase, not pay-to-rank: Vista promotes by liveness and fidelity; "Lit" badges are earned.
11. Photo mode belongs to the world: anyone can request a Tier A+ farm render of any public place (10 free a month, then US$0.10), so the shareable image of nolife is always its best image.
12. Legacy content is re-made, not displayed as-is (section 10).

### 6.10 Streaming and VR

Pixel streaming costs about US$1 per user-hour of raw GPU and Project Zero reportedly ran at ~US$1.75/hour (unsearched); consumer cloud gaming caps at US$19.99/month with 100-hour limits even at NVIDIA scale, so streaming cannot be a baseline (Source: https://thegabmeister.com/p/unreal-pixel-stream-aws/ ; https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now). Tier S is a capped funnel and an add-on (R14): two free streamed hours per new account with cost per retained user published, then US$0.99/hour or 20 hours for US$14.99, with two providers contracted from day one because Firestorm Zero's closure was provider-forced. VR: OpenXR on the PC client at 90 Hz (11.1 ms, Tier B settings on Tier A hardware) and the Quest client in Phase 2.

Graphics and pipeline are the largest engineering line (a 25-person team, ~US$5M/year, plus the Foundry farm at US$0.3-0.5M/year). The trade-off accepted: creators author once at Tier A and the platform's QA surface is triple; a single mid-fidelity tier would be cheaper and would forfeit the thesis.

---

## 7. Architecture

Two-layer world model. A presence layer carries position, pose, voice, chat and the look descriptor at 5-10 Hz through interest-managed relays, so 1,000-5,000 avatars can be visible in a place; a simulation layer runs physics, scripts and object state in elastic cells of 50-150 interacting avatars (R1). Published SLOs: 100-150 fully simulated avatars per cell with voice; 500-1,000 per contiguous place (the Star Citizen 4.x envelope, still "quasi-dynamic" in August 2026 after a decade); 2,000-5,000 only in declared event mode with impostors, pre-mixed audio and simplified interaction (the ScavLab envelope: 4,144 real players in a stripped-down arena) (Source: https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27 ; https://www.mcvuk.com/business-news/tennis-for-two-thousand-the-story-behind-improbables-mass-event-in-scavlab/). nolife does not promise 10,000: EVE's 6,739 needed time dilation, which a voice world cannot use (Source: https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe).

Cells are headless C++/Rust processes (not Unreal servers) with Jolt at 30 Hz, a Luau VM with per-owner budgets (R5) and an LSL compatibility runtime, containerised with one manifest that runs on Edgegap, GameLift Servers, Nitrado GameFabric or bare metal (R20); prices have converged at US$0.055-0.07 per vCPU-hour and vendor survival, not price, is the top risk (Source: https://edgegap.com/pricing ; https://aws.amazon.com/gamelift/servers/pricing/). An authoritative entity store (documents plus event log) sits behind the cells, so a cell crash is a reconnect, not a lost place. Clients predict locally with the same Jolt build; Unreal only renders. Replication is in-house: interest management, a 50-200 kbps per-client cap, impostor tiers beyond 30 m. Voice sits behind an abstraction that can swap 4Players ODIN (EUR 0.29 per peak concurrent user per month), the Discord Social SDK (free, open since August 2025) or a self-hosted SFU (Source: https://odin.4players.io/pricing ; https://discord.com/press-releases/social-sdk-ingame-communications); captions and text-to-speech run in the same path.

Persistence: per-cell and per-owner write budgets (Roblox's 60 + 10 x players requests per minute is the precedent), hourly snapshots, 30-day owner rollback, inventory as a versioned document with integrity checks (Source: https://create.roblox.com/docs/cloud/guides/data-stores/throttling). Escrowed server images, a self-hostable cell, an annual restore test and a two-provider failover drill are published (R20).

Cost per CCU. A 2-4 vCPU cell for 100 avatars costs US$0.14-0.28/hour plus 0.9-2.3 GB/hour of egress: about US$0.002-0.005 per avatar-hour before voice (~EUR 0.01/hour) and persistence. A 10,000-CCU world costs US$50-100/hour (US$0.5-1M/year); a Linden-scale world (50K peak, ~25K average) ~US$2-3M/year all-in. Infrastructure is not the dominant line: Roblox's infrastructure plus trust and safety was US$1,153.5M in 2025, ~US$0.9 per DAU-month, and nolife budgets US$1.5-3 because it is less automated at first (Source: https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm).

Scaling. Language and region are shard keys for discovery and onboarding (R29), not identity: one account, one inventory, worldwide. Cells scale horizontally per place; the entity store is partitioned by estate; event mode is a scheduled capacity reservation.
---

## 8. AI and the living world

AI's largest role is in the pipeline, not the plaza. The Foundry uses learned models for simplification quality, texture upscaling, roughness inference on legacy imports, auto-rigging, collision and the fidelity rank; moderation uses proactive classifiers in the Roblox Sentinel pattern, which caught 35% of grooming cases before any report (Source: https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection).
AI inhabitants are a disclosed, capped stopgap for density (R25). Each carries a visible badge and a plain-language notice of what it is and on whose behalf it acts (EU AI Act Article 50 applies from 2 August 2026); each has a purpose (greeter, shopkeeper, guide, chronicler, stage crew); agents are capped at 20% of visible occupants in any public place and withdraw as humans arrive; no companion loops for minors (Character.AI banned open-ended chat for under-18s in November 2025) (Source: https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots). Voices are licensed or synthetic with provenance; no replicas of real performers without bargained terms. Cognition is tiered (scripted by default, a small on-device model for ambient talk, frontier calls only for memorable interactions) with a published cost per agent-hour, since no vendor publishes one (Source: https://inworld.ai/blog/new-ai-infrastructure-scaling-games-media-characters). Agent cost stays at or under 10% of the safety-plus-infrastructure line; human D30 in agent-filled places must match human-only places or the cap drops. Agents are avatars to the engine (same body, budgets and crowd path), so the badge is in the impostor too. A RimWorld-style director per District schedules markets, weather, festivals and small crises, so Animal Crossing's real-clock routine exists at world scale; this is pacing, not intelligence (Source: https://www.rimworldwiki.com/wiki/RimWorld).

---

## 9. Identity, safety, governance, regulation

Identity. Pseudonymous public identity with a privately held age band. Age assurance is a regional module (R21): on-device facial estimation or a wallet credential, never stored ID images (Discord's 70,000-ID leak came through its human appeals vendor) (Source: https://cyberinsider.com/discord-confirms-70000-government-ids-exposed-in-third-party-breach/); six bands with adjacent-band chat by default, minors private by default with geolocation off, parental surfaces for 10-15, OS age signals for app clients; profiles for the UK, EU, Brazil (ECA Digital, in force 17 March 2026), Indonesia (PP Tunas, minimum age 16) and Texas (Source: https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat ; https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/ ; https://avpassociation.com/indonesia/). nolife's declared primary purpose is creation and play, with Australia's "primary purpose" test in mind (Source: https://www.esafety.gov.au/about-us/industry-regulation/social-media-age-restrictions/faqs).

Adult content is a first-class, controlled purpose (R22): Adult Districts and estates gated by an Ofcom-grade "highly effective" check that also unlocks Adult-tagged commerce; uploader verification, consent records and pre-publication review for Adult-tagged goods (AN 5196 and VIRP-grade controls built pre-emptively); a deindex-but-sell switch that flips Adult listings to opt-in discovery within hours; adult share of spend published; exclusion from general cash-out only as a processor-triggered contingency. SL's Adult gate is still a self-declared birth date and Ofcom fines small services (Source: https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/).

Embodied safety (R23): personal boundary default-on with a user-set radius (Meta's 4-foot cylinder is the precedent) (Source: https://ispr.info/2022/02/08/meta-establishes-four-foot-personal-boundary-to-deter-vr-groping/); one-gesture mute/block/vanish; instance kick and lock; a rolling evidence buffer attached to reports, since UK police found VR assaults unprosecutable; consent prompts for avatar-to-avatar actions; behaviour-earned trust ranks gating upload, scripting, voice and proximity, with no rank from idle time or mass-friending (Source: https://docs.vrchat.com/docs/vrchat-safety-and-trust-system). KPIs: reports per 1,000 user-hours and median time-to-action under 24 hours, published quarterly, with audit logs. Biometrics: tracking on device, only abstracted animation data leaves, explicit consent, no sale, no gaze targeting. Likeness: a consent registry and takedown/counter-notice flow ready for NO FAKES and TAKE IT DOWN.

Accessibility (R27): a first-party text client (chat, IMs, notices, inventory, teleport, object list, voiced GPS) at launch with funded maintenance; speech-to-text and text-to-speech of chat per XAG 119; keyboard-only navigation; comfort options; EAA-compliant storefront and account flows (Source: https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119 ; https://www.osborneclarke.com/insights/eu-accessibility-act-time-start-implementation-projects-now).

Self-rule and appeals: estate and District owners set local rules within the charter; charters elect moderators; the assembly reviews client-affecting and economy changes before they take effect (R19). Appeals: human review within 72 hours, a second-level panel with assembly members for bans over 30 days, decisions summarised quarterly. Measurement (R13): first-hour, D7, D30, D90, DAU/MAU, peak concurrency and bot share published quarterly with a documented "active" definition and a third-party-readable API.

---

## 10. Legacy support

Principle: rights, not formats, are the barrier. nolife can import what a resident made; it cannot import a no-mod third-party body. So there is a complete technical import path and a vendor opt-in programme for the people who own the rest.

Imported on day one:

- OAR and IAR archives (terrain, parcels, objects with inventory and scripts, inventory subtrees); OSgrid told users to rely on them before the 2025 wipe (Source: https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff).
- SL own-created content via viewer export (Collada from Kokua/Firestorm under the creator-of-every-part rule) and original glTF (Source: https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/).
- Geometry: prims (including cut, hollow, twist) regenerated as exact meshes; sculpts reconstructed from 64x64 displacement maps; llmesh bundles read with the highest LOD as the Nanite source. All three are re-made as Nanite meshes with normalised PBR, so legacy content does not look legacy.
- Animations: Bento's 133-bone skeleton maps to the Common Body through a published table; BVH and .anim import; Bakes-on-Mesh layers composite at the Foundry.
- Scripts: an LSL compatibility runtime (events, link messages, the common ll* surface, HTTP, chat) under the same budgets as Luau; unsupported calls fail loudly; SLua scripts run with a thin shim.
- VRM 1.0 avatars import natively with MToon mapped to the toon shader; VRM 0.x is migrated. VRChat Unity-package avatars are not importable; VRM is the route (Source: https://vrm.dev/vrm1/).
- Groups and institutions: charter import (R18).

Re-made: particle systems (mapped to Niagara templates by parameter), legacy materials, lighting, and any object whose scripts depend on vendor servers, which move to platform-hosted, escrowed life-support with a designed food-independent end state (R24).

Vendor opt-in: SL body, head and furniture vendors list catalogues with platform-funded conversion and decide whether existing customers can claim a nolife copy against a signed purchase record (as Kitely offered OSgrid buyers). Dual presence: a 12-24-month chat and event bridge to SL.

---

## 11. Business model and go-to-market

Money flows: rent for persistence (section 4); a Resident subscription at US$12.99/month or US$119/year (home upkeep, 10,000 inventory items, 2 GB uploads, a stipend shown in fiat, lottery priority, 20 Tier A+ renders a month); 10% primary commission, 0% resale; a 1.5% cash-out fee and a published ≤4% round-trip spread; the Tier S add-on; education and enterprise tiers. Mix published annually (R6); no ads, no paid rank.

Unit economics at the reference scale (600K MAU, 150K DAU, US$100M/year of new money in, the taxonomy's Linden-scale reconciliation). Revenue: 15,000 estate-equivalents at US$99 = US$17.8M; 60,000 plots and lots at an average US$8 = US$5.8M; 60,000 subscriptions at US$119 = US$7.1M; 10% on US$100M of primary sales = US$10M; spread and cash-out fees ~4% on US$80M cashed out = US$3.2M; streaming, education, enterprise US$2M; total ~US$46M. Costs: infrastructure plus trust and safety at US$2 per DAU-month = US$3.6M; CDN and Foundry US$0.5M; payment costs 3% of money-in = US$3M; engine licence at 3% of revenue = US$1.4M; 120 staff at US$160K loaded = US$19.2M; creator pool at 25% of net platform revenue ~US$9M; total ~US$37M. Margin ~US$9M, thin and positive, with rent plus subscriptions at 67% of revenue (R6's ≥50% test) and R30's self-funding posture met. At 100K MAU the fixed base must fit ~US$8M of revenue, so headcount is capped at 120.

Pricing posture: regional pricing from launch (Roblox's lifted paying users 26% in Brazil and 52% in the Philippines) and local rails for Portuguese, Spanish, Japanese and German markets (R29) (Source: https://about.roblox.com/newsroom/2025/04/roblox-launches-regional-pricing-for-in-experience-items).

Funding (R30): US$75-95M to self-funding over four years (US$30M for Phases 0-1: engine, Foundry, cells, two clients, text client, launch; US$25-35M for Phase 2: mobile, consoles, Quest, marketplace and rail, localisation; US$20-25M of operating runway). Written in: no sibling product, fixed costs sized for 100K MAU, growth features funded only after rent and subscriptions cover costs. Paid acquisition is assumed near zero: at 1-2% payer rates, mobile CPIs of US$1-4 imply US$75-300 per payer, which no social world has recovered (Source: https://liftoff.ai/?p=34267). Acquisition is the migration programme, the calendar, invitations and the shareable image.

Sequencing: founders' creators first, then institutions by charter, then public open beta on desktop and web with the SL bridge live, then mobile and Japan. The claim is narrow and checkable ("your Second Life, lit"), and a public benchmark page (frame times per device, inventory-loss rate, concurrency, D30) is the launch asset (R13).

---

## 12. Roadmap sketch

Phase 0, Q4 2026 to Q2 2027: foundations. Foundry v1; headless cell server with Jolt and Luau and the 150-avatar cell test with voice (R1 gate); Unreal Tier A and WebGPU Tier C clients on one protocol; Common Body v1; text client v1; OAR/IAR and Collada import; closed alpha with 50 founders' creators and three institutions. Engine platform licence signed; fidelity contract, fee stack, charter and sunset covenant published.

Phase 1, Q3 2027 to Q2 2028: open beta on Windows, macOS and web. Districts, estates, homes, lottery, civic calendar, Arrival cohorts with holdout, charter import, SL chat bridge, marketplace with own billing and the licensed rail, age-assurance module for UK/EU/US, Adult Districts, trust ranks, first assembly election. Month-12 targets: 10 institutions migrated, ≥40% of DAU-hours in creator-run places, first-session completion ≥60%, D30 lift versus holdout published.

Phase 2, H2 2028 to 2029: native iOS and Android (Tier B/C), Switch 2 and PS5 (Tier A/B), Quest native (Tier B), Tier S funnel, localisation for Portuguese, Spanish, Japanese and German with local rails, education tier with SSO at 20 institutions, event mode at 2,000, platform-hosted life-support for scripted objects, NTC transcode when drivers allow. Targets: mobile ≥30% of DAU by month 24, non-US DAU ≥40%, rent plus subscriptions ≥50% of revenue.

Phase 3, 2030: self-funding at ≤600K MAU; event mode at 5,000; A+ Showcase path tracing; UE6 renderer migration behind the neutral format; second hosting provider in production rotation with a published failover drill; constitutional review of the charter by the assembly. Phase 4, 2031, optional: volumetric avatars, splat venue capture at scale, a certified third-party client programme.

---

## 13. Requirement coverage table

| R | Mechanism in this proposal |
|---|---|
| R1 | Presence layer to 1,000-5,000 over cells of 50-150; SLOs 100-150 per cell, 500-1,000 per place, event mode 2,000-5,000; 150-avatar cell test as a Phase 0 gate (section 7). |
| R2 | Tiers A/B/C with per-avatar and per-plot budgets enforced by the Foundry; auto LODs, impostors, atlases, bakes; over-budget content degrades to its tier version; p95 frame times published (sections 6.3-6.6). |
| R3 | glTF 2.0 + VRM 1.0 runtime, OpenUSD interchange, platform-funded conversion, 24 months' notice and a converter for any retirement (section 6.6). |
| R4 | First-party native, web and text clients shipped continuously on a documented protocol; third-party certification in Phase 4; first-session completion KPI (sections 6.3, 9, 12). |
| R5 | Luau sandbox and LSL runtime with per-owner CPU, memory and network budgets throttling the worst offender (sections 5, 7, 10). |
| R6 | Rent from day one above a trial allowance; published list (plot US$3.99, estate US$99, class estate US$39); mix published annually; rent plus subscriptions ~67% at reference scale (sections 4, 11). |
| R7 | One fee stack: own web/PC billing, 10% primary, 0% resale, 1.5% cash-out, ≤15% round trip, store money-in capped at 25%, required margin printed (section 5). |
| R8 | Pool of 25% of net platform revenue, purchaser-weighted per place with anti-farming rules, 15% reserved for charters and venues, formula published (section 5). |
| R9 | One closed currency at a daily-fixed rate, fiat everywhere, exact-amount purchase, no bundles, no chance mechanics paying anything cash-out-able, stipends in fiat (section 5). |
| R10 | Licensed partnered rail with KYC, W-9/W-8 and DAC7 at onboarding, adult-specialist acquirer pre-qualified, purchases coded as platform currency (section 5). |
| R11 | Arrival: hosted cohorts of 8-16 with a mentor, success = met a person or joined a group, randomised holdout, D30 at month 6 (section 3). |
| R12 | One avatar per 0.1 ha at peak in public hubs; merge, close, route to events; newcomer sees ≥10 people; Vista hides empty places (section 4). |
| R13 | Quarterly metrics page and API with a documented active definition and bot share; public benchmark page at launch (sections 9, 11). |
| R14 | Desktop and WebGPU/WebGL2 web at launch, native mobile within 12 months, VR optional, streaming as a capped funnel with published cost per hour and per retained user (sections 6.3, 6.10). |
| R15 | Civic calendar on day one, annual ritual on a temporary Event Ground, synchronised ~100-avatar instances, roles as objects with slots, badges, stipends and deputies (section 3). |
| R16 | District plot lottery with full-price tickets, 45-day rule with refunds and a published pause policy; homes rented and never auto-demolished (sections 3, 4). |
| R17 | Estate-grade access and ban lists, roles as ranks, HUD meters, damage parcels, seat caps, whitelists and paid queue priority under published rules; no pay-to-win or loot boxes (sections 3, 4). |
| R18 | Charter import in one transaction, OAR/IAR and Collada/glTF/VRM import, 12-24-month SL bridge, glTF/VRM/USD export of own-created inventory under the Export bit (sections 2, 10). |
| R19 | Published charter, 12 months' notice and grandfathering, assembly review of client-affecting and economy changes, written answers to votes (sections 3, 9). |
| R20 | Neutral format, non-Unreal cells, WebGPU fallback renderer, documented exit cost, two hosting providers, swappable voice, escrowed images, self-hostable cell, 12 months' shutdown notice, annual restore and failover drills (sections 6.2, 7). |
| R21 | Regional age-assurance module: on-device estimation or wallet credential, no stored ID images, six bands, minors private by default, parental surfaces, OS signals, Ofcom-grade Adult gate that also unlocks Adult commerce (section 9). |
| R22 | Adult content as a measured first-class purpose: uploader verification, consent records, pre-publication review, platform-currency coding, deindex-but-sell switch, adult share published, cash-out exclusion only as a processor contingency (sections 5, 9). |
| R23 | Boundary default-on, one-gesture mute/block/vanish, instance kick/lock, evidence buffer on report, consent prompts, trust ranks gating upload, voice and proximity; KPIs and audit logs quarterly (section 9). |
| R24 | Platform-hosted, escrowed life-support for scripted value objects with a food-independent end state; vendor-server dependencies migrated at import (section 10). |
| R25 | Agents badged and labelled (including in the impostor), purposeful, capped at 20% of occupants, withdrawing as humans arrive, no minor companion loops, provenance voices, tiered cognition with published cost per agent-hour, ≤10% of the safety-plus-infra budget, D30 parity test (section 8). |
| R26 | Furnished Home and dressed avatar in the open-licensed Common Body before any build panel; consumer client separate from Studio (sections 3, 5, 6.8). |
| R27 | Text client at launch with funded maintenance, voiced GPS, speech-to-text and text-to-speech, keyboard-only navigation, comfort options, EAA storefront (section 9). |
| R28 | Education tier: SSO, bulk accounts, class estates with OAR-equivalent export, General-rated enforcement, US$39/month, written persistence commitment; 20 institutions by Phase 2 (sections 2, 4, 12). |
| R29 | Language as a shard key for discovery and onboarding, paid localisation for Portuguese, Spanish, Japanese and German, regional pricing and local rails, VRM/glTF import, off-platform marketplaces tolerated (sections 2, 4, 11). |
| R30 | Published runway to self-funding at ≤600K MAU, fixed costs sized for 100K MAU, 120-person cap, no sibling product, growth features funded only after rent and subscriptions cover costs (section 11). |

---

## 14. Biggest risks and what you would cut first

Risks, in order.

1. Fidelity above the audience's hardware. Blue Mars died of it, and half of SL's users lacked high-end machines in 2025. The mitigation is the whole of section 6: Tier C is a real client with its own frame budget, and the Foundry derives it automatically. The test is D30 split by tier, published.

2. Engine dependency on a competitor. Epic runs Fortnite and UEFN and may fold UEFN into UE6; a licence change or ruinous royalty is possible. Mitigation: neutral format, non-Unreal servers, a WebGPU renderer in production from day one, a signed platform licence before Phase 1, and the documented exit. This is the one place where "no life-support" is not fully achieved at launch, and the proposal says so.

3. The pipeline makes things uniform rather than beautiful. Mitigation: estates and Wilds are free; style sheets constrain scale and light, not taste; the fidelity rank measures cost, not aesthetics; curators are residents.

4. Vendor and processor shocks (Hathora, Dolby.io, Firestorm Zero and the July 2025 processor wave, all inside 18 months). Mitigation: two cell-hosting providers, swappable voice, two streaming providers, platform-currency coding, a pre-qualified adult acquirer, the deindex switch.

5. Density. The world can be lit perfectly and still be empty. Mitigation is the R11/R12 machinery plus migration by charter; the honest statement is that the audience for this category may be ~0.5-1M people and the plan is profitable at Linden scale without growth.

6. Rights block migration if the major SL body vendors decline the opt-in programme; its terms are generous because the vendors are the wedge. 7. Regulatory drift on age, currency and adult content: the regional module, fiat display and pre-built controls.

Cut first, in order, if money or time runs short: (1) A+ Showcase path tracing and strand hair; (2) Tier S streaming beyond the two free trial hours; (3) Gaussian-splat venue capture; (4) AI inhabitants entirely (the director and pipeline AI stay); (5) console ports, keeping Switch 2 last because it is the Lumen Lite reference device; (6) the Quest native client, keeping OpenXR on PC; (7) event mode above 2,000. Never cut: the Tier C web client, the text client, automatic tiering, OAR/IAR and charter import, the licensed rail, and the published metrics.
