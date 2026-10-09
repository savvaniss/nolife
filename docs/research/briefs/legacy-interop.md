# Legacy content, interoperability and the people a successor must serve

Landscape brief for "nolife" (successor to Second Life). Date: 2026-10-09.

## Method note

- 25 WebSearch calls were used (the hard cap). Page fetching (WebFetch/curl) was blocked in this sandbox, so every "live" fact below rests on the quoted extracts that the search tool returned, not on reading the pages. Where an extract was ambiguous or dated, that is flagged.
- Facts marked **(prior knowledge)** were not confirmed by a live search extract and should be re-verified before being quoted externally. They are mostly long-stable technical facts (file formats, viewer behaviour, ToS history) rather than 2026 numbers.
- Several 2026 items are known only from headlines (e.g. "Record high active user numbers for OpenSim grids in July 2026") where the body text could not be retrieved; these are labelled "headline only".
- Big gaps that searches did not close: a current (2025/2026) Kitely or DigiWorldz price list; an official SL age/gender breakdown after 2008; any VRChat official age/gender split; 2026 Community Round Table minutes; the body of the July 2026 Hypergrid Business stats report.

## Findings

### 1. OpenSimulator / Hypergrid in 2026

**Scale.** Hypergrid Business's January 2026 monthly tally put public OpenSim grids at 162,771 standard-region equivalents, 44,867 monthly active users and 493,939 registered users (after adjusting OSgrid's region count); the October 2025 report had 147,614 regions, 46,244 actives, 492,301 registered. The raw OSgrid region figure was inflated to roughly 988,206 standard regions by a single user modelling all of North America, of which the author estimated 825,435 was the "experiment" (Source: https://www.hypergridbusiness.com/2026/01/opensim-land-grows-as-traffic-slows-slightly/). Earlier record-high reports put monthly actives at 41,145 (first crossing 40,000), 44,061 and 47,169 at different points, so the whole hypergrid is a ~45k-monthly-active population (Source: https://hypergridbusiness.com/?p=73088). A July 2026 headline reads "Record high active user numbers for OpenSim grids in July" (headline only; body not retrieved) (Source: https://www.hypergridbusiness.com/?p=79149).

**OSgrid.** OSgrid describes itself as the largest free OpenSimulator grid and is Hypergrid-enabled, with Lbsa Plaza as its hub (Source: https://osgrid.org/). It is also the cautionary tale: in February 2025 it announced it would wipe its database on March 21, giving users "five weeks to save your stuff" (Source: https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff). In spring 2026 it went offline again after hitting "asset filesystem metadata size limits"; by the third week of downtime the maintenance tracker had moved from 40% to 83%, with completion expected ~June 21, 2026, and "its active users numbers are dramatically down, since people can no longer log in". Kitely's CEO offered redelivery of Kitely Market purchases to Kitely avatars for stranded OSgrid buyers (Source: https://www.hypergridbusiness.com/?p=79686). OSgrid's homepage still showed an asset-maintenance notice with "Estimated Completion: June 22, 2026" at search time (Source: https://osgrid.org/). Residents have a history of fearing "the current downtime might break more than it will fix, citing OSgrid's history of losing assets" (Source: https://hypergridbusiness.com/?p=57002).

**Kitely.** No 2025/2026 price list surfaced. The last confirmed tiers (2015, still referenced on Kitely's own blog) are Starter World $14.95/mo (1 region, 15,000 prims, 10 avatars), Standard World $19.95/mo (4 regions, 60,000 prims, 40 avatars), Advanced World $39.95/mo (16 regions, 120,000 prims, 80 avatars) (Source: https://www.kitely.com/virtual-world-news/2015/06/01/60-off-large-worlds-and-dedicated-memory-guarantee/). An undated later Kitely post adds "Mega Worlds" of up to 64 regions / 150,000 prims with a dedicated server at $119.95/mo ($89.95 promotional) (Source: https://www.kitely.com/virtual-world-news/feed/). Kitely is the only grid that suspends idle regions and reloads them on teleport, trading a few seconds of load time for cost (Source: https://www.hypergridbusiness.com/2015/06/kitely-cuts-prices-60-for-large-regions). Kitely Market is the de-facto hypergrid store, delivering to avatars on other grids (Source: https://www.hypergridbusiness.com/?p=79686).

**DigiWorldz.** Last concrete figures: a 16,000-prim region at $15/mo with no setup fee; +1,000 prims for $2.50 up to 100,000 prims for $100; a 10,000-prim entry region at $8/mo; 2x2 varregion $20, up to 6x6 for $30; private grids from $200 for the first server (Source: https://www.hypergridbusiness.com/2015/04/digiworldz/). A 2021 giveaway valued standard regions at $20/mo (Source: https://www.hypergridbusiness.com/2021/04/digiworldz-giving-away-25-free-regions/). Treat all three price lists as historical; current pages were not retrievable.

**OAR/IAR archives (prior knowledge).** OpenSimulator's OAR (OpenSim Archive) packages a whole region: terrain, parcels, all objects with their inventory and scripts, and the assets they reference, as a gzipped tar with an XML manifest. IAR (Inventory Archive) does the same for a user's inventory subtree. Both are console-level operations (`save oar`, `save iar`), so on hosted grids the operator must expose them; Kitely exposes OAR export/import in its web UI, OSgrid lets self-hosted region owners run them, and these archives were the mechanism OSgrid told users to rely on before the 2025 wipe. OAR/IAR carry asset UUIDs and creator names but no cryptographic provenance, which is why hypergrid content theft is a recurring complaint.

### 2. Second Life's content-export rules and content stack

**Export permission.** The "Export" permission bit was proposed in September 2012 by the Firestorm team with OpenSim developers, explicitly as a way to let creators opt in to portable content and so "inspire more creators to move to OpenSim grids"; the same article notes the bit "would not protect against copybot-type hacking attacks" and that "the vast majority of stolen content today originates on and is distributed inside Second Life" (Source: https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/). (prior knowledge) OpenSimulator implemented the Export flag in 0.8 (2014); Firestorm honours it on OpenSim grids. Second Life itself never adopted the Export bit.

**Viewer export in SL.** Kokua (2013) added Collada .DAE export that "honors object permissions, so only objects you created and own can be exported", using code from Singularity (Source: https://modemworld.me/2013/08/24/). (prior knowledge) Firestorm's behaviour in SL is the same creator-only rule: an object exports only if the logged-in avatar is the creator of every prim and every texture; non-creator textures are dropped. Linden Lab's own viewer supports no object export at all, only "Save As" for textures/sounds/animations you created. Copybot (2006, built on libsecondlife) proved that any viewer can replay the asset stream it receives, which led to the Lab's "Copybot is a ToS violation, not a technical problem" stance and the DMCA-based IP process that persists today.

**2013 ToS.** Linden Lab's August 2013 revision of ToS Section 2.3 ("Service Content License") led creators to fear the company "might appropriate their creations and sell or license them without their permission"; in-world meetings (29 Sept 2013) and a legal panel followed (Source: https://modemworld.me/2013/09/30/tos-in-world-meeting-september-29th-a-personal-perspective/). The Lab's 16 July 2014 revision limited its licence to use "inworld or otherwise on the Service" and made sub-licensing contingent on "some affirmative action on the user's part"; critics noted "affirmative action" was never defined (Source: https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/; https://community.secondlife.com/blogs/entry/1294-updates-to-section-23-of-the-terms-of-service/). Lesson: a successor's content licence will be read by creators who have been burned.

**What SL content is (prior knowledge).** Prims (parametric primitives with cut/hollow/twist), sculpts (2007, 64x64 RGB displacement textures), mesh (2011, uploaded as Collada .DAE and stored as the Lab's proprietary llmesh LOD bundle), LSL scripts (compiled to Mono bytecode server-side; no official export of compiled state), Bento (2016, 133-bone skeleton with wings/tail/face bones), Bakes-on-Mesh (2019, system-layer textures baked onto mesh bodies), and PBR materials (official launch 2024: "all of Second Life will now be capable of using PBR Materials") (Source: https://community.secondlife.com/blogs/entry/14536-second-life-pbr-materials-official-launch). Avatar look in 2026 is almost entirely third-party mesh bodies/heads (Maitreya, Legacy, LeLutka etc.) sold no-mod, no-transfer, which is the real portability barrier: the rights, not the formats.

**glTF.** glTF mesh import has been possible since mid-2024 with a public release in the official viewer in mid-2025; meshes are converted internally to the same llmesh format as Collada (Source: https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/). The full glTF *scene* importer (hierarchy, materials, animations from Blender) discussed in 2024 was in April 2025 "broken down into smaller, more easily managed projects", with Land Impact rules "still TBD" (Source: https://modemworld.me/2025/04/04/2025-week-14-sl-ccug-meeting-summary/; https://modemworld.me/2024/06/08/). In July 2026 Geenz Linden asked creators what they would want from "a variant of glTF that enables extensibility much more easily"; requests included glTF hierarchies with proper origins and OpenUSD support (Source: https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/).

**Project Zero and mobile.** Project Zero streamed the official viewer from AWS to a browser, launched early 2025 and stayed in beta; in September 2025 the Lab said Zero plus the mobile app had produced a "10x" increase in people trying SL versus download-first sign-up. On 21 April 2026 Linden Lab announced it was ending Project Zero, 14 months after launch; later CCUG summaries list it as closed (Source: https://modemworld.me/tag/project-zero/; https://modemworld.me/category/second-life/sl-tech/sl-user-group-meetings/). SL Mobile remains a native beta app (2026.2.1086 in March 2026 added a new-user chatbot; 2026.5.194024 in May 2026) with a new mobile engineering manager (Radix Linden, Unity background) focused on "a smooth, seamless experience" (Source: https://modemworld.me/2026/05/28/). Philip Rosedale returned as CTO and board member in late 2024 and led the March 2025 round table on "Enhancing Project Zero and the 2025 Roadmap" (Source: https://modemworld.me/2025/03/11/linden-lab-announces-march-2025-community-round-table/).

**2026 roadmap signals.** No official 2026 roadmap document was found. January 2026 CCUG/TPVD notes: viewer roadmap "still being worked on" around a "first impressions" push; 2026.02 to include screen-space reflections for Linden Water under PBR/HDR; WebRTC voice targeted for a March 2026 grid-wide deployment (Source: https://modemworld.me/2026/01/18/20265-week-3-sl-ccug-and-open-source-tpvd-meetings-summary/). SL23B ran 18 June to 19 July 2026 (Source: https://modemworld.me/2026/04/14/).

### 3. Avatar / asset portability standards

**VRM.** VRM 1.0 is a glTF 2.0 profile with VRMC_vrm, VRMC_materials_mtoon, VRMC_springBone, VRMC_node_constraint and VRM-Animation; UniVRM is the official Unity implementation and migrates 0.x files (Source: https://github.com/vrm-c/univrm; https://vrm.dev/vrm1/). Neither VRChat nor Resonite imports VRM natively: VRChat goes through Unity + VRChat SDK3 (community converters target VRM 0.0) (Source: https://beyonddev.gumroad.com/l/vrm), while Resonite's Assimp-based importer recommends GLB/glTF and VRM users rename .vrm to .glb or use the community "ResoPon VRM" converter (Source: https://wiki.resonite.com/Avatar_Creation; https://wiki.resonite.com/ResoPon_VRM; https://zenn.dev/unipocket/articles/9528faa8dc4c8d). (prior knowledge) VRM remains the only widely adopted *open* humanoid-avatar interchange format; adoption is Japan-centric (VRoid, Cluster, VSeeFace).

**OpenUSD.** AOUSD ratified Core Specification 1.0 in March 2026, added Aras, Booz Allen, C-Infinity, Mobiltech, Qualcomm, SGDL and XGRIDS, and launched a "Characters, Motion, and Interactivity" interest group to standardise "skeletal animation, blend shapes, and interactive behaviors" (Source: https://www.linuxfoundation.org/press/aousd_prmarch2026; https://aousd.org/news/aousd_newmembers_march2026). On 21 July 2026 it added ByteDance, Huawei, Physicl and Unity, began ISO certification of Core Spec 1.1 and opened a public GitHub repository (Source: https://www.linuxfoundation.org/press/aousd-drives-global-3d-data-interoperability-ai-workflows-with-core-spec-milestones-and-members). Trade press reads this as the consortium becoming a formal standards body (Source: https://www.sovereignmagazine.com/article/bytedance-huawei-and-unity-join-3d-data-standards-body-as-openusd-pursues-iso-certification).

**Metaverse Standards Forum.** Over 2,500 members by July 2023; two tiers (free Participants, voting Principals); it coordinates rather than writes standards (Source: https://metaverse-standards.org/news/blog/happy-birthday-metaverse-standards-forum). It has since incorporated as an independent consortium (Source: https://metaverse-standards.org/news/press-releases/metaverse-standards-forum-incorporates/). Working groups include "3D Asset Interoperability using USD and glTF", "Interoperable Characters/Avatars" and "Digital Fashion Wearables for Avatars" (Source: https://users.aalto.fi/~ltuuri/apu/metaverse/). President Neil Trevett was still presenting it at AWE on 16 June 2026 on the "Open Metaverse Browser Initiative" with RP1 (Source: https://voicesofvr.com/1745-key-open-standards-enabling-the-open-metaverse-browser-initiative-with-metaverse-standards-forum/). No 2026 membership count was found.

**Ready Player Me.** Netflix acquired RPM on 19 December 2025 (team moved to Netflix Games); public services including the PlayerZero creator shut down 31 January 2026; apps can no longer create or update avatars; sources conflict on whether saved avatars stay usable (Source: https://genies.com/blog/ready-player-me-shutdown; https://learn.framevr.io/blog/rpm-closure; https://avatarsdk.com/blog/2026/07/07/ready-player-me-migration-guide/). Union Avatars reportedly went offline in July 2026 (vendor-sourced roundup) (Source: https://avatarsdk.com/blog/2026/08/31/avatar-platforms-2026-whos-alive-whos-gone/).

**VRChat avatar economy.** Avatar Marketplace announced 14 May 2025; sellers must be 18+, 30-day-old account, verified email, and apply separately from the world/group programme; minimum 600 VRChat Credits per distinct avatar; avatars may not use colliders/stations to move faster than others; no advertising cheaper external prices; payouts require $100 earned credits, max one request per two weeks, up to 30 days processing, with fees by method; rules effective 15 August 2025. The revenue split is unpublished ("creators pocket the largest cut"); a community estimate is ~15.3% deducted (Source: https://creators.vrchat.com/economy/guidelines; https://hello.vrchat.com/legal/economy; https://ask.vrchat.com/t/avatar-marketplace-faq-for-sellers/43555?page=8; https://www.tubefilter.com/?p=186451).

### 4. Who the audience is

**Second Life demographics.** No official breakdown after 2008 was found. 2008 Linden Lab data: 41% female, 39% North America, 32% Western Europe; males logged ~60/40 more active hours (Source: https://www.yupingliu.com/wordpress/tag/statistics/). A 2025 arXiv cross-platform study sampled 960 male and 522 female SL users with mean ages ~45 (men) and ~38.6 (women) (Source: https://arxiv.org/pdf/2505.00287). A 2012 academic survey found residents "significantly older, more educated, and less religious" than general internet users (Source: https://pubmed.ncbi.nlm.nih.gov/22544305). A 2025-26 YipitData panel (n=374) covers spending only (Source: https://ask.yipitdata.com/insights/second-life-residents-gaming-platform-payments). (prior knowledge) SL requires 18+ for the main grid (16-17 on restricted estates); the Lab has said the median age is mid-40s and tenure is long: a large share of actives have accounts older than ten years.

**What residents say they want.** Searches returned no 2025-26 synthesis. Recurring themes across the archived forum and blog record are stability over features ("lag, inventory loss, failed teleports, concurrency limits"), retention ("nobody, in 10 years, has been able to fix user retention"; ~10,000 sign-ups a day with "a handful remaining" in 2014), hardware barriers and "nothing to do" for newcomers (Source: https://forums-archive.secondlife.com/327/14/363267/1.html; https://gwynethllewelyn.net/2014/03/28/understanding-second-lifes-culture/; https://list-archives.secondlife.com/opensource-dev/2010-September/003365.html). The 2026 CCUG requests (glTF hierarchies with proper origins, USD support) show creators asking for modern pipelines (Source: https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/).

**Communities.** Education: VWBPE 2026 ran 19-21 March 2026 in SL and OpenSimulator with a Philip Rosedale keynote (Source: https://secondlife.com/destination/vwbpe); secondary sources claim 2,200-3,500 attendees a year and a past year with 45 countries / 80 presentations (Source: https://commons.ggc.edu/digitallearning/?p=110; https://community.secondlife.com/t5/Featured-News/Virtual-Worlds-Best-Practices-in-Education-Starts-March-18th/ba-p/2914664). Disability: Virtual Ability Inc. (founded 2007 by Gentle Heron) reports "over 1,000 members from six continents", about a quarter of whom are family, carers, clinicians or researchers (Source: https://virtualability.org/about-us). Music: Cafe Musique alone has hosted 600+ performers since 2015 and runs 60+ live shows a week; the SL International Symphony Orchestra (2022) has 100+ musician-actors; SL22B (20 June-20 July 2025) recruited DJs, live performers, dance troupes and roleplay storytellers (Source: https://secondlife.aditi.lindenlab.com/destination/aism; https://modemworld.me/2025/03/27/sl22b-performer-applications-open/). No roleplay population figure was found.

**VRChat.** ~120,000 average weekend concurrents by 2025; ~149,000 peak on New Year's Eve 2025-26; company-cited record 158,192 concurrents (a Japanese concert) and ~100,000 daily average concurrents; Steam-only trackers show 45-62k monthly averages and a 78,613 Steam peak (Source: https://roadtovr.com/vrchat-key-stats-japan-growth-concurrents/; https://backiee.wasmer.app/http_en_wikipedia_org/wiki/VRChat; https://tracker.gg/population/steam/438100). Japan ranks first in official-site visits (Sensor Tower via Mogura). No official age/gender split; Twitch audience skews male 20-24; one trans support group had 36,000+ members in December 2024 (Source: https://backiee.wasmer.app/http_en_wikipedia_org/wiki/VRChat). (prior knowledge) VRChat's ToS age floor is 13 with 18+ age verification launched 2025.

## Patterns

1. **The hypergrid is small, cheap and fragile.** ~45k monthly actives spread across hundreds of grids; regions cost $8-40/month; the largest free grid has suffered a database wipe (2025) and a multi-week asset outage (2026). The people most likely to migrate to a successor already know how to pack an OAR and have lost content before.
2. **Rights, not formats, are the barrier.** SL mesh is Collada/glTF in, proprietary llmesh out; avatars are no-mod third-party bodies. Every export path (Kokua, Firestorm, OpenSim Export bit) reduces to "creator of every part", and SL never shipped the Export flag. A successor cannot import an SL resident's look; it can only import what they made.
3. **Linden Lab modernises slowly and retreats from access experiments.** glTF took 2024-2025 to reach mesh-only; scene import was decomposed; Project Zero was killed after 14 months despite a "10x" trial uplift; mobile remains beta. The Lab's own CCUG is now asking about USD.
4. **Standards are converging on glTF for runtime and USD for scenes**, with AOUSD moving to ISO and adding a characters/animation group, and VRM the only live open avatar profile. Proprietary avatar services (RPM, Union) are dying; platform-native economies (VRChat Marketplace) are rising with strict KYC and minimum prices.
5. **The audience is older, long-tenured, and organised around communities** (education, disability, live music, roleplay) rather than games, and it is distinct from VRChat's younger, Japan-heavy, VR-first crowd.

## Design implications for nolife

- Ship OAR and IAR import on day one, including LSL script text and prim/sculpt/llmesh geometry; it is the only mass-migration path that exists and the OpenSim diaspora already uses it.
- Treat glTF 2.0 (with VRM 1.0 extensions for humanoids) as the canonical runtime asset and OpenUSD as the scene/authoring interchange; expose an explicit, creator-set Export permission bit from the start and honour it in every client.
- Write the content licence in plain language with a defined "affirmative action" for any platform re-use; the 2013 ToS episode is institutional memory.
- Plan for an avatar-body ecosystem: provide a first-party, open-licensed Bento/BOM-class body so migrants are not naked, and a programme for SL body vendors to opt in.
- Prioritise stability, inventory integrity and reliable teleport over graphics features; those have topped resident complaints for twenty years, and OSgrid's outages show what losing assets does to trust.
- Target desktop first, mobile-native second; do not depend on a streamed viewer as the on-ramp.
- Design for 40-60-year-olds with long tenures: text chat parity, accessibility (Virtual Ability's 1,000 members and the Radegast text-viewer lineage), event tooling for live music and classes, and group/land governance for roleplay sims.
- Keep an economy with low minimum prices and creator-friendly payout terms; VRChat's 600-credit floor and $100 payout threshold are the comparator.

## Open questions

- Current (2026) Kitely, DigiWorldz and OSgrid pricing/region counts, and whether OSgrid fully recovered after June 2026.
- The actual July 2026 OpenSim active-user record figure.
- Whether Linden Lab will ship a glTF scene importer or a USD path, and any Land Impact rules for scenes.
- Any post-2008 official SL demographic data (age, gender, tenure, country) and 2026 concurrency/daily-login figures.
- VRChat's official age/gender split and the real Avatar Marketplace revenue share.
- Whether major SL mesh-body vendors would license bodies for an Export-enabled successor.
- Status of Firestorm's export behaviour after the 2025-26 viewer merges.

## Sources

- https://www.hypergridbusiness.com/2026/01/opensim-land-grows-as-traffic-slows-slightly/
- https://www.hypergridbusiness.com/?p=79149
- https://www.hypergridbusiness.com/?p=79686
- https://hypergridbusiness.com/?p=73088
- https://osgrid.org/
- https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff
- https://hypergridbusiness.com/?p=57002
- https://www.kitely.com/virtual-world-news/2015/06/01/60-off-large-worlds-and-dedicated-memory-guarantee/
- https://www.kitely.com/virtual-world-news/feed/
- https://www.hypergridbusiness.com/2015/06/kitely-cuts-prices-60-for-large-regions
- https://www.hypergridbusiness.com/2015/04/digiworldz/
- https://www.hypergridbusiness.com/2021/04/digiworldz-giving-away-25-free-regions/
- https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/
- https://modemworld.me/2013/08/24/
- https://modemworld.me/2013/09/30/tos-in-world-meeting-september-29th-a-personal-perspective/
- https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/
- https://community.secondlife.com/blogs/entry/1294-updates-to-section-23-of-the-terms-of-service/
- https://community.secondlife.com/blogs/entry/14536-second-life-pbr-materials-official-launch
- https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/
- https://modemworld.me/2025/04/04/2025-week-14-sl-ccug-meeting-summary/
- https://modemworld.me/2024/06/08/
- https://modemworld.me/tag/project-zero/
- https://modemworld.me/category/second-life/sl-tech/sl-user-group-meetings/
- https://modemworld.me/2026/05/28/
- https://modemworld.me/2025/03/11/linden-lab-announces-march-2025-community-round-table/
- https://modemworld.me/2026/01/18/20265-week-3-sl-ccug-and-open-source-tpvd-meetings-summary/
- https://modemworld.me/2026/04/14/
- https://github.com/vrm-c/univrm
- https://vrm.dev/vrm1/
- https://beyonddev.gumroad.com/l/vrm
- https://wiki.resonite.com/Avatar_Creation
- https://wiki.resonite.com/ResoPon_VRM
- https://zenn.dev/unipocket/articles/9528faa8dc4c8d
- https://www.linuxfoundation.org/press/aousd_prmarch2026
- https://aousd.org/news/aousd_newmembers_march2026
- https://www.linuxfoundation.org/press/aousd-drives-global-3d-data-interoperability-ai-workflows-with-core-spec-milestones-and-members
- https://www.sovereignmagazine.com/article/bytedance-huawei-and-unity-join-3d-data-standards-body-as-openusd-pursues-iso-certification
- https://metaverse-standards.org/news/blog/happy-birthday-metaverse-standards-forum
- https://metaverse-standards.org/news/press-releases/metaverse-standards-forum-incorporates/
- https://users.aalto.fi/~ltuuri/apu/metaverse/
- https://voicesofvr.com/1745-key-open-standards-enabling-the-open-metaverse-browser-initiative-with-metaverse-standards-forum/
- https://genies.com/blog/ready-player-me-shutdown
- https://learn.framevr.io/blog/rpm-closure
- https://avatarsdk.com/blog/2026/07/07/ready-player-me-migration-guide/
- https://avatarsdk.com/blog/2026/08/31/avatar-platforms-2026-whos-alive-whos-gone/
- https://creators.vrchat.com/economy/guidelines
- https://hello.vrchat.com/legal/economy
- https://ask.vrchat.com/t/avatar-marketplace-faq-for-sellers/43555?page=8
- https://www.tubefilter.com/?p=186451
- https://www.yupingliu.com/wordpress/tag/statistics/
- https://arxiv.org/pdf/2505.00287
- https://pubmed.ncbi.nlm.nih.gov/22544305
- https://ask.yipitdata.com/insights/second-life-residents-gaming-platform-payments
- https://forums-archive.secondlife.com/327/14/363267/1.html
- https://gwynethllewelyn.net/2014/03/28/understanding-second-lifes-culture/
- https://list-archives.secondlife.com/opensource-dev/2010-September/003365.html
- https://secondlife.com/destination/vwbpe
- https://commons.ggc.edu/digitallearning/?p=110
- https://community.secondlife.com/t5/Featured-News/Virtual-Worlds-Best-Practices-in-Education-Starts-March-18th/ba-p/2914664
- https://virtualability.org/about-us
- https://secondlife.aditi.lindenlab.com/destination/aism
- https://modemworld.me/2025/03/27/sl22b-performer-applications-open/
- https://roadtovr.com/vrchat-key-stats-japan-growth-concurrents/
- https://backiee.wasmer.app/http_en_wikipedia_org/wiki/VRChat
- https://tracker.gg/population/steam/438100
