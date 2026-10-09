# Networking, persistence and scale for a shared persistent world (2026) — brief for "nolife"

## Method note

This pass used **20 of 20 WebSearch calls** (16 standard, 1 extended, 3 standard in the final batch) on 2026-10-09. Page fetching (WebFetch/curl) is blocked in this sandbox, so every "verified" fact below rests on the quoted extracts returned by the search tool, not on a full read of the page. Where an extract was from a secondary site (forum, competitor marketing, aggregator) that is said inline.

**Verified live in this run:** Star Citizen meshing status (Feb and Aug 2026), EVE's FWST-8/M2-XFE records, Edgegap and GameLift Servers rate cards, Photon Fusion pricing, ODIN pricing, Discord Social SDK launch, Hathora's 2026 shutdown, Dual Universe's 2025 shutdown, Firestorm Zero's shutdown, Roblox server-size and DataStore budgets, Unreal Iris status, Fortnite "Big Battle", Improbable's 2023 financials and MPG sale, MSquared's concurrency claims.

**Not verifiable in this run (labelled "prior knowledge, unsearched" or "unverified"):** the Dolby.io Communications API sunset date (two searches found no official notice), any MSquared 10k+ event in 2024-2025 (two searches found none), Hadean Aether Wars, the 2019 Unity/Improbable dispute dates, Linden Lab's AWS bill, Nakama/Heroic Labs, Unity Multiplayer Services, Epic Online Services, Vivox, VRChat/Horizon caps, Nanite-in-UGC, and the Second Life region/fee figures (those last were verified by sibling agents in an earlier pass and are marked [sibling-verified]).

## Findings

### 1. Second Life: one process per region, 100 avatars, and what the cloud changed

- A region is a 256 m x 256 m area run by one simulator process; Full regions are capped at 100 avatars, Homesteads at 20, Openspaces at 10; the simulator targets 45 physics frames/s and scripts are the first thing starved under load. [sibling-verified] (Source: https://wiki.secondlife.com/wiki/Land ; https://wiki.secondlife.com/wiki/Statistics)
- The AWS move completed in late 2020/early 2021 and re-hosted the same one-process-per-region model without changing caps. Linden Lab has never published what it cost or saved; the only visible price signal was the March 2023 cut of the full-region fee by US$20/month to US$209. [sibling-verified; AWS spend itself: prior knowledge, unsearched] (Source: https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/ ; https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/)
- **Firestorm Zero** (the pixel-streamed browser viewer on Amazon GameLift, launched 14 March 2025, sold as streaming hours, e.g. L$250 for 5 hours) **was shut down by mid-2025**: the week-26 (27 June 2025) Project Zero user-group summary says it was closed "for the time being", unused time refunded, because of the work of maintaining two streaming products and because the Lab had to migrate Project Zero to a new platform "at the behest of their streaming provider". No exact shutdown date was given. (Source: https://modemworld.me/2025/06/27/ ; https://modemworld.me/2025/03/14/using-firestorm-in-your-browser-for-second-life/)
- Grid-wide 12-month average peak concurrency was ~49,600 in 2024-25. [sibling-verified] (Source: https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/)

### 2. EVE Online: single shard bought with time dilation — the real numbers

- CCP's own battle reports give the verified records. **Fury at FWST-8** (October 2020): local count topped 6,000 as the Keepstar anchored, and CCP states "two Guinness World records" were awarded for the battle. **M2-XFE** (December 2020/January 2021 "second timer"): the battlefield system peaked at **6,739 pilots**, breaking the FWST-8 record of 6,557; across the three Delve systems a combined peak of **13,770** players at 23:23 EVE time, ~35% of everyone online; two nodes (T5ZI-S and M2-XFE) each carried 5-6k pilots. (Source: https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe ; https://www.eveonline.com/news/view/fury-at-fwst-8-battle-report)
- The "8,825 players" figure in the prior draft did not appear in any CCP source and should be dropped. Time dilation (10% floor, shipped November 2011) and the 2013 PCU record of 65,303 were not searched. (prior knowledge, unsearched) (Source: https://www.eveonline.com/news/view/introducing-time-dilation-tidi)
- Pattern unchanged: thousands in one solar system is achieved by slowing simulation time, which a social world with voice cannot do.

### 3. Star Citizen: static meshing shipped, dynamic meshing still "quasi" in late 2026

- Alpha 4.0 (Pyro) shipped with **static server meshing**: a shard made of several dedicated servers, each owning a territory, joined by a replication layer. Digital Trends reported 4.0 allowed **up to 500 players on the same shard**, where a server previously supported 100. A March 2024 meshing test reportedly had 800 players together. (Source: https://www.digitaltrends.com/gaming/star-citizen-500-player-server-update/ ; https://starcitizen.tools/Server_meshing)
- **February 2026**: CTO Benoit Beausejour said in a livestream that the "quasi-dynamic" work (spinning servers up and down without crashing the host) was still ongoing, with no release date; an internal test reportedly requested 200 servers. (Source: https://massivelyop.com/2026/02/06/star-citizen-cto-outlines-progress-on-server-meshing/)
- **27 August 2026 "Letter from the Chairman"**: instancing in Alpha 4.10 is described as "the first use case of dynamic server meshing", which CIG calls *Quasi Dynamic Server Meshing* because persistent-universe territories are not yet being subdivided; the planned fix is to spin up extra servers as load rises and split busy territories. (Source: https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27)
- CIG has claimed servers "ran better with up to 400 players in one area" than one server simulating the whole universe — a livestream claim, not an independent measurement. (Source: https://starcitizen.tools/Player_count)
- Funding (~US$800M by 2025) and the 19 Dec 2024 Live date were not searched. (prior knowledge, unsearched)

### 4. Improbable / SpatialOS / MSquared: 10,000 is a capability claim, not an observed persistent-world load

- The "over 10,000 live participants with customisable avatars in one space" figure is Improbable's own 2022 claim for Morpheus. (Source: https://improbable.io/blog/an-improbable-story-accelerating-into-the-metaverse-and-what-comes-next ; https://www.telecomtv.com/content/digital-platforms-services/uks-improbable-banks-150-million-to-help-make-the-metaverse-dream-a-reality-44148/)
- Observed numbers are smaller: ScavLab (Midwinter, May 2021) peaked at **4,144 real players** in one dense world; an Improbable-linked write-up described it as "near to 2,000 live players" in a compact space with simulated clients added as stress; CNBC reports **4,500** players in the Yuga Labs demonstration (2022). (Source: https://www.mcvuk.com/business-news/tennis-for-two-thousand-the-story-behind-improbables-mass-event-in-scavlab/ ; https://www.cnbc.com/2023/06/16/softbank-backed-improbable-outlines-plan-for-msquared-metaverse.html)
- MSquared raised US$150M in April 2022 (a16z, SoftBank Vision Fund 2). In November 2024 it powered a BBC Philharmonic virtual concert (MAX-R consortium) — no attendance figure found. **Two searches found no 2024 or 2025 MSquared event with 10k+ concurrent users**; treat any such claim as unverified. (Source: https://www.businesswire.com/news/home/20220407005101/en/ ; https://www.improbable.io/news/improbables-msquared-venture-powers-groundbreaking-bbc-philharmonic-virtual-concert)
- Corporate trajectory: losses of £150M (2021) and £19M (2022); sale of The Multiplayer Group to Keywords for £76.5M (US$97.1M), December 2023; first profit in 2023 (revenue £66M, profit £11M, or £13M pre-tax depending on source), cash £185M at end-2023, achieved through "growth, stringent cost control, and asset divestment". No 2025 results surfaced. (Source: https://www.cnbc.com/2023/12/18/metaverse-firm-improbable-sells-gaming-unit-for-97-million.html ; https://www.pocketgamer.biz/web3-tech-firm-improbable-makes-profit-for-first-time-after-metaverse-pivot ; https://en.wikipedia.org/wiki/Improbable_(company))
- The January 2019 Unity ToS dispute and Worlds Adrift's July 2019 shutdown were not searched. (prior knowledge, unsearched)

### 5. Dual Universe and Hadean: single-shard projects that did not survive

- Dual Universe (Novaquark) used "CSSC" (Continuous Single-Shard Cluster): the server split players into cube-shaped shards by location across many machines; a 2019 alpha test put 30,000 *simulated* players plus real testers on one planet. It **was delisted from Steam on 25 July 2025 and its servers shut down on 27 August 2025**; it continues only as the player-hosted "myDU", with an open-source model under consideration. (Source: https://en.wikipedia.org/wiki/Dual_Universe ; https://mmos.com/news/novaquark-explains-how-dual-universes-server-works)
- Hadean's EVE: Aether Wars (GDC 2019, ~14k concurrent entities including bots) and High Fidelity's 90-person documented crowd: not searched. (prior knowledge, unsearched; High Fidelity sibling-verified) (Source: https://www.highfidelity.com/backlog/creating-crowds-in-vr-eabbc325dcfc)

### 6. Fortnite and Roblox: the instance model

- Fortnite's standard match is 100 players per server instance (Epic's Iris documentation itself says "up to 100 players per server instance"). **"Big Battle"** is a 50v50 Limited Time Mode; the data-mined v21.40 description reduced it to 40 per team ("Big Battle - Zero Build"), i.e. still ≤100 in one place. (Source: https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine ; https://www.thegamer.com/fortnite-50v50-big-battle-mode-returning-zero-build/ ; https://fortnitenews.com/leak-big-battle-ltm-coming-to-fortnite/)
- **Unreal Iris** is still an opt-in system running alongside legacy replication; a third-party studio blog states it remains marked Experimental in the UE 5.7 docs and the legacy system is the default. No evidence it is Fortnite's shipping default. (Source: https://dev.epicgames.com/documentation/en-us/unreal-engine/introduction-to-iris-in-unreal-engine ; https://www.strayspark.studio/blog/iris-replication-unreal-engine-opt-in-2026)
- **Roblox server size**: a secondary source states that from 24 July 2024 any creator can set up to **200** players per server, while a beta allowed **700**; a 2025 DevForum thread reports the 700-player program can no longer be joined publicly. A community experiment world ("700 Chairs for 700 Players") reports 671 players seated in one server. Earlier RDC coverage spoke of "up to 600 players per server at no extra cost". None of this is an official engineering blog; the 700 number is real but gated. (Source: https://devforum.roblox.com/t/is-it-still-possible-to-opt-into-700-player-servers/4210626 ; https://www.laps4.com/preguntas-y-respuestas/cual-es-el-nuevo-limite-de-amigos-en-roblox-2025 ; https://devforum.roblox.com/t/increase-server-size/306199)
- **Roblox DataStore budgets** (official docs): per-server GetAsync/SetAsync budget = 60 + 10 × players requests/minute; sorted/version calls 5 + 2 × players; per-key throttle queue of 30 requests, beyond which 301-306 errors drop requests; Open Cloud universe limits 10 MB/min write, 20 MB/min read, 300 requests/min. The 4 MB per-key size cap was not visible in the extract (prior knowledge, unsearched). (Source: https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits ; https://create.roblox.com/docs/cloud/guides/data-stores/throttling)
- Roblox's 2025 infrastructure + trust & safety line of US$1,153.5M and its Sentinel open-sourcing were sibling-verified; platform concurrency records and 3D-asset moderation pipeline were not searched. (Source: https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm)

### 7. Middleware and voice in 2026

- **Photon Fusion 2 / Quantum 3**: the free tier is now **100 CCU** for commercial use (one app per customer) in addition to the old 20 CCU non-commercial tier; a "Plus" package adds 100 paid CCU for US$95/year (200 total); Photon says Fusion 2 "is capable of supporting over 200 players in a single room". A third-party guide lists paid plans at US$125/month for 500 CCU, US$250 for 1,000, US$500 for 2,000, excluding dedicated-server compute. (Source: https://blog.photonengine.com/new-200-ccu-plus-package-100-paid-100-free/ ; https://doc.photonengine.com/photon/v1/pricing ; https://crux.supercraft.host/blog/photon-fusion-pricing-2026/)
- **Discord Social SDK**: announced 17 March 2025 with voice in closed beta; opened to all developers with in-game voice and text by August 2025; reported as free; players do not need Discord accounts. (Source: https://techcrunch.com/2025/03/17/discord-launches-sdk-to-help-developers-enhance-social-experiences-in-their-games ; https://alternativeto.net/news/2025/8/discord-social-sdk-launches-to-all-devs-with-in-game-voice-chat-and-cross-platform-play/)
- **4Players ODIN** (WebRTC-based 3D voice): free up to 25 CCU; pay-as-you-go **€0.29 per peak concurrent user per month**, falling to €0.19 above 80,000 PCU; a "Mini" plan from €9.90 with 100 voice PCU, no per-minute or egress fees. (Source: https://odin.4players.io/pricing ; https://odin.4players.io/mini)
- **Dolby.io Communications APIs**: no official sunset notice could be found in two searches. A third-party API profile describes them as a legacy product superseded by Dolby OptiView (ex-Millicast/THEO), with docs redirecting to OptiView and SDK reference repos archived since August 2024; competitors (Stream) publish migration guides off the Dolby.io Conference SDK. The prior draft's "EOL announced 2024, shutdown 2025" remains **unverified**. (Source: https://github.com/api-evangelist/dolby-io ; https://getstream.io/video/docs/ios/advanced/migration-from-dolby/)
- Vivox, Unity Multiplayer Services, Epic Online Services, Nakama/Heroic Labs: not searched. (prior knowledge, unsearched)

### 8. Costs per concurrent user — and the vendor that vanished

- **Hathora is gone.** Fireworks AI acquired Hathora (announced 4 March 2026 per an industry blog); the team moves to AI inference and gaming customers were offboarded to Nitrado's GameFabric. Frost Giant said Hathora would wind down "at the end of April" 2026; one blog gives 5 May 2026 as the support end (unconfirmed). Stormgate lost online play; Splitgate 2 and Predecessor migrated. (Source: https://gamesbeat.com/?p=318174 ; https://www.techspot.com/news/111969-stormgate-servers-go-dark-following-ai-focused-hosting.html ; https://mcvuk.com/?p=229291 ; https://crux.supercraft.host/blog/hathora-shut-down-where-to-go-after-may-2026/)
- **Edgegap** pay-as-you-go: **US$0.00115 per dedicated vCPU-minute (≈US$0.069/vCPU-hour)**, raised from US$0.001/min on 1 January 2025; US$0.10/GB egress; 2 GB RAM per vCPU; fractional vCPUs down to 1/4; commitment discounts of 20-30%; bare-metal fleets from US$250/month. (Source: https://edgegap.com/pricing ; https://edgegap.com/blog/announcement-offering-changes-for-2025)
- **Amazon GameLift Servers**: c6i.large (2 vCPU, 4 GiB) at **US$0.109/hour Linux on-demand** in US East (Ohio), ≈US$0.055/vCPU-hour, plus client data transfer (rate not in extract; US$0.09/GB is prior knowledge); Spot is cheaper and AWS suggests it for sessions ≤30 min. (Source: https://aws.amazon.com/gamelift/servers/pricing/ ; https://docs.aws.amazon.com/gameliftservers/latest/developerguide/gamelift-intro-pricing.html)
- A Gameye glossary uses US$0.07/vCPU-hour as its illustrative market rate, consistent with the two cards above. (Source: https://gameye.com/glossary/vcpu/)
- **Worked estimate (analyst's, using the verified rates):** a 2-4 vCPU cell holding 100 avatars costs US$0.14-0.28/hour compute; at 20-50 kbps per client, 100 clients consume 0.9-2.3 GB/hour (US$0.09-0.23 at US$0.10/GB). Total **≈US$0.002-0.005 per avatar-hour** before voice and persistence. Voice via ODIN adds ≈€0.29 per *peak* user per month, i.e. for a user online 30 h/month about €0.01/hour. A 10,000-CCU world therefore runs at ≈US$50-100/hour of server cost (≈US$0.5-1M/year) — small next to Roblox's US$1.15B infra+T&S line.
- Pixel streaming remains the outlier at ≈US$1-6 per user-hour (sibling-verified), and Firestorm Zero's closure shows even a well-funded operator could not sustain two streaming products. (Source: https://thegabmeister.com/p/unreal-pixel-stream-aws/ ; https://modemworld.me/2025/06/27/)

## Patterns / root causes

1. **The unit of simulation is the unit of everything.** Second Life's one-core/one-region process fixed caps, pricing and lag together; the AWS move re-hosted it unchanged. Star Citizen's shards are still "a set number of servers, each allocated to areas" in August 2026.
2. **Large single places are bought with time (EVE: 6,739 in a system under TiDi), money (Star Citizen: 500-player shards after a decade; Improbable: half a billion dollars), or simplification (ScavLab's 4,144 in a stripped-down arena).** No search found a persistent, physics-simulated, voice-enabled world sustaining >1,000 avatars in one place.
3. **The 10k claims are capability statements.** Improbable's "over 10,000" is a 2022 marketing figure; its observed peaks are 4,144 and 4,500 at scripted events. Dual Universe's single shard worked technically and the company shut it down in August 2025.
4. **The platforms that scaled did it with many 100-200 person instances** (Fortnite 100, Big Battle ≤80, Roblox default ≤200 with 700 as a gated beta) plus soft instance boundaries.
5. **Vendor risk is now the top infrastructure risk, not price.** Hathora (AI pivot, 2026), Dolby.io Communications (quietly legacy), Firestorm Zero (closed because the streaming provider forced a migration) all removed a dependency inside 12-18 months. Prices themselves have converged at US$0.055-0.07/vCPU-hour.
6. **Persistence stays a budgeted key-value problem.** Roblox's per-server request budgets (60 + 10 × players/min) and per-key queues are the shipped model; in-memory world state (SpatialOS, Dual Universe) is the model that died.
7. **Infrastructure is cheap; moderation and content are not.** Cents per avatar-hour versus a billion-dollar T&S line.

## Design implications for nolife

1. **Two-layer world model**: a presence layer (position, pose, voice, chat at 5-10 Hz, interest-managed through relays/SFU) that can show 1,000-5,000 avatars in a place, and a simulation layer (physics, scripts, vehicles) spatially sharded into cells of 50-150 interacting avatars. Crowds are visible; physical interaction is per cell.
2. **Elastic cells with an authoritative entity store**, Star Citizen replication-layer style: cell crashes become reconnects, not lost places. Sell land by area and content budget, never "one server".
3. **Realistic per-place targets for 2026**: 100-150 fully simulated avatars per cell with voice; 500-1,000 per contiguous place across cells (the Star Citizen 4.x shard envelope); 2,000-5,000 only in a declared event mode with impostor avatars, pre-mixed audio and simplified interaction (the ScavLab envelope). Do not promise 10,000.
4. **Multi-vendor by construction.** Containerised cell servers that run on Edgegap, GameLift Servers, Nitrado GameFabric or bare metal with one deployment manifest; voice behind an abstraction that can swap ODIN, Discord Social SDK or self-hosted SFU; never a sole-source streaming client.
5. **Persistence as documents plus event log** with Roblox-style per-cell and per-creator write budgets, snapshots and rollback for land owners.
6. **Scripting sandbox (Luau or WASM) with per-script budgets** and throttling of the worst offender, not SL's "scripts starve first".
7. **Interest management, avatar LOD/impostors beyond ~30 m and a 50-200 kbps per-client bandwidth cap** as the main scale levers; Iris-style prioritised replication if on Unreal, but treat Iris as experimental.
8. **Instance softness** (friends-follow, join-where-my-people-are, cross-instance chat, auto-merge of thin instances) beats instance size.
9. **Budget moderation before capacity**; automated review of every uploaded 3D asset and script.
10. **Pixel streaming as a time-capped funnel only**, and only with a provider contract that survives platform migrations.

## Open questions

- Which Star Citizen 4.x patch is live in October 2026 and whether 4.10 instancing has expanded beyond "quasi-dynamic"; the current official per-shard count.
- Whether Roblox's 700-player tier will re-open publicly, and the Luau CPU budget per player it implies.
- Any independently measured MSquared event in 2024-2026 (attendance, update rate, avatar fidelity, per-attendee cost).
- Official Dolby.io Communications API end-of-service date and whether its spatial-audio customers moved to ODIN, Vivox or Discord.
- Nitrado GameFabric's post-Hathora rate card and whether Edgegap's US$0.00115/min holds in 2027.
- Whether Iris leaves Experimental in UE 5.8+ and what per-server gain Epic attributes to it.
- Linden Lab's AWS spend versus pre-2020 colocation, and whether Project Zero (as distinct from Firestorm Zero) is still running.
- Whether a WebGPU client can render a 100-avatar presence layer at 60 fps on 2026 mid-range phones.

## Sources

Verified live in this run (search extracts):
- https://massivelyop.com/2026/02/06/star-citizen-cto-outlines-progress-on-server-meshing/
- https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27
- https://starcitizen.tools/Server_meshing
- https://starcitizen.tools/Player_count
- https://www.digitaltrends.com/gaming/star-citizen-500-player-server-update/
- https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe
- https://www.eveonline.com/news/view/fury-at-fwst-8-battle-report
- https://improbable.io/blog/an-improbable-story-accelerating-into-the-metaverse-and-what-comes-next
- https://www.telecomtv.com/content/digital-platforms-services/uks-improbable-banks-150-million-to-help-make-the-metaverse-dream-a-reality-44148/
- https://www.cnbc.com/2023/06/16/softbank-backed-improbable-outlines-plan-for-msquared-metaverse.html
- https://www.cnbc.com/2023/12/18/metaverse-firm-improbable-sells-gaming-unit-for-97-million.html
- https://www.pocketgamer.biz/web3-tech-firm-improbable-makes-profit-for-first-time-after-metaverse-pivot
- https://en.wikipedia.org/wiki/Improbable_(company)
- https://www.mcvuk.com/business-news/tennis-for-two-thousand-the-story-behind-improbables-mass-event-in-scavlab/
- https://www.improbable.io/news/improbables-msquared-venture-powers-groundbreaking-bbc-philharmonic-virtual-concert
- https://www.businesswire.com/news/home/20220407005101/en/
- https://en.wikipedia.org/wiki/Dual_Universe
- https://mmos.com/news/novaquark-explains-how-dual-universes-server-works
- https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine
- https://dev.epicgames.com/documentation/en-us/unreal-engine/introduction-to-iris-in-unreal-engine
- https://www.strayspark.studio/blog/iris-replication-unreal-engine-opt-in-2026
- https://www.thegamer.com/fortnite-50v50-big-battle-mode-returning-zero-build/
- https://fortnitenews.com/leak-big-battle-ltm-coming-to-fortnite/
- https://devforum.roblox.com/t/is-it-still-possible-to-opt-into-700-player-servers/4210626
- https://devforum.roblox.com/t/increase-server-size/306199
- https://www.laps4.com/preguntas-y-respuestas/cual-es-el-nuevo-limite-de-amigos-en-roblox-2025
- https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits
- https://create.roblox.com/docs/cloud/guides/data-stores/throttling
- https://blog.photonengine.com/new-200-ccu-plus-package-100-paid-100-free/
- https://doc.photonengine.com/photon/v1/pricing
- https://crux.supercraft.host/blog/photon-fusion-pricing-2026/
- https://techcrunch.com/2025/03/17/discord-launches-sdk-to-help-developers-enhance-social-experiences-in-their-games
- https://alternativeto.net/news/2025/8/discord-social-sdk-launches-to-all-devs-with-in-game-voice-chat-and-cross-platform-play/
- https://odin.4players.io/pricing
- https://odin.4players.io/mini
- https://github.com/api-evangelist/dolby-io
- https://getstream.io/video/docs/ios/advanced/migration-from-dolby/
- https://gamesbeat.com/?p=318174
- https://www.techspot.com/news/111969-stormgate-servers-go-dark-following-ai-focused-hosting.html
- https://mcvuk.com/?p=229291
- https://crux.supercraft.host/blog/hathora-shut-down-where-to-go-after-may-2026/
- https://edgegap.com/pricing
- https://edgegap.com/blog/announcement-offering-changes-for-2025
- https://aws.amazon.com/gamelift/servers/pricing/
- https://docs.aws.amazon.com/gameliftservers/latest/developerguide/gamelift-intro-pricing.html
- https://gameye.com/glossary/vcpu/
- https://modemworld.me/2025/06/27/
- https://modemworld.me/2025/03/14/using-firestorm-in-your-browser-for-second-life/

Sibling-verified in an earlier pass:
- https://wiki.secondlife.com/wiki/Land
- https://wiki.secondlife.com/wiki/Statistics
- https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/
- https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/
- https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/
- https://www.highfidelity.com/backlog/creating-crowds-in-vr-eabbc325dcfc
- https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm
- https://thegabmeister.com/p/unreal-pixel-stream-aws/

Prior knowledge, unsearched (to verify before external use):
- https://www.eveonline.com/news/view/introducing-time-dilation-tidi
- https://en.wikipedia.org/wiki/Eve_Online
- https://robertsspaceindustries.com/funding-goals
- https://blog.unity.com/news/our-response-to-improbables-blog-post
- https://en.wikipedia.org/wiki/Worlds_Adrift
- https://hadean.com/
- https://heroiclabs.com/nakama/
- https://unity.com/products/multiplayer
- https://unity.com/products/vivox
- https://dev.epicgames.com/en-US/services
- https://creators.vrchat.com/worlds/
- https://create.roblox.com/docs/cloud-services/data-stores
