# The smaller surviving social worlds of 2026, and new entrants

Landscape brief for the design of "nolife" (a Second Life successor). Prepared 2026-10-09.

## Method note

- 25 WebSearch calls were used (the hard cap). Page fetching (WebFetch/curl) is blocked in this sandbox, so every "verified" fact below rests on the quoted extracts that the search tool returned, not on reading the pages themselves. Where a search returned nothing dated 2026, the fact is labelled **(prior knowledge, unverified)** and should be treated as a hypothesis to re-check.
- Live-verified (at least one 2025/2026-dated extract): Resonite, ChilloutVR, Avakin Life, Palia, Sky, Hytale, Pax Dei, Spatial, Viverse (partial), NeosVR shutdown, Sinespace (two weak signals), Mona (pivot post, undated), Virbela (partial), Engage XR (partial).
- Not verified live for 2026 (only old extracts came back): Overte/Vircadia, Breakroom, Sansar/Wookey, Dreams, Core/Manticore, Nowhere, Nvidia Omniverse, Frame, and any 2026 "next Second Life" entrant. A search explicitly for 2026 platforms pitched as a Second Life successor returned only 2014-2017 Sansar coverage.
- Concurrency numbers come from third-party Steam trackers (Steambase, tracker.gg, live-player-count, IsThereAnyDeal) and only count the Steam client; several of these platforms have non-Steam launchers, so Steam figures are a floor, not a total.

## Findings

### A. Open-creation social VR worlds (the Second Life-shaped survivors)

**Resonite (Yellow Dog Man Studios)**
- Launched in Steam Early Access on 6 October 2023 as the spiritual successor to NeosVR; built on the in-house FrooxEngine (prior knowledge: C#/.NET, not Unity or Unreal), by former Neos lead Tomas "Frooxius" Mariancik. (Source: https://en.wikipedia.org/wiki/Resonite; https://uploadvr.com/resonite-vr-steam-early-access)
- The Neos split: Frooxius resigned from Solirax on 24 April 2023 over a dispute with CEO Karel Hulec about cryptocurrency features; the remaining team said on 22 September 2023 there was no path to reconciliation. NeosVR's online cloud services were shut down on 20 August 2025 and the game was later delisted from Steam (single Wikipedia-mirror source). (Source: https://en.wikipedia.org/wiki/NeosVR)
- Scale in 2026: Steam trackers show roughly 170-200 concurrent players (Steambase 194 in late July 2026; tracker.gg 199 with a 24h peak of 276; monthly averages 170-195 across Feb-Jun 2026; all-time Steam peak ~1,183-1,263 at launch). About 1,576 Steam reviews, very positive. (Source: https://steambase.io/games/resonite; https://tracker.gg/population/steam/2519830; https://live-player-count.com/game/resonite)
- Platform/devices: PC VR and desktop mode (prior knowledge). Business model: free client; Patreon/membership funding plus paid storage tiers (prior knowledge). What works: fully in-world creation (everything is built inside the world with a node-based visual language and live collaborative editing), persistent user worlds, and a strong maker culture ("Creator Jam"). (Source: https://voicesofvr.com/?p=14108)
- Status: live, small, flat-to-slightly-growing.

**ChilloutVR (Alpha Blend Interactive, Germany)**
- Launched in early access 2021 on Steam (prior knowledge: Unity engine; PC VR and desktop). Patreon-funded studio; the Patreon shows a small membership and describes a German studio "working on ChilloutVR and other games". (Source: https://www.patreon.com/chilloutvr/about)
- Scale in 2026: about 34 concurrent Steam players (Steambase, updated July-August 2026); monthly averages 29-35 across H1 2026; March 2026 peak 111; previous peak 189 on 8 June 2025. (Source: https://steambase.io/apps/chilloutvr)
- Status: live but effectively dormant as a platform; no 2026 patch coverage surfaced (last indexed patch notes were 2022). (Source: https://steamdb.info/patchnotes/19748411)

**Overte (and Vircadia), open-source High Fidelity descendants**
- Overte forked from Vircadia in 2022; both descend from the High Fidelity codebase; Apache 2.0; Overte is run by a German-registered non-profit modelled on KDE e.V., with democratically elected board members. Overte's docs claim body tracking and scaling to 500 users in one world. (Source: https://ryanschultz.com/tag/overte/; https://overte-website-sphinx.readthedocs.io/de/latest/)
- Vircadia has repositioned itself as an "open source agent-based metaverse ecosystem" for "mass human and agent (AI) based immersive worlds", self-hosted, "hundreds of agents simultaneously", with features marked "coming soon" (undated GitHub page). (Source: https://www.github.com/vircadia)
- No 2026 release coverage was found. Status: live as open-source projects with volunteer-scale usage; no MAU data exists. (prior knowledge, unverified: Overte ships periodic dated releases; usage is tens of concurrent users.)

**Sinespace / Breakroom (Sine Wave Entertainment, London)**
- Sinespace: Unity-based free-to-play virtual world, beta launched November 2016; creators build and sell content with Unity and its SDK, including private servers for custom MMOs. Sine Wave started as a Second Life content brand before spinning out. (Source: https://en.wikipedia.org/wiki/Sinespace; https://gamesbeat.com/sine-wave-entertainment-launches-breakroom-3d-social-hub-for-remote-teams-in-vr-pc-or-mobile-devices/)
- Breakroom (2020): enterprise/education spin-off, VR/PC/mobile, launched at $500/month for up to 50 users, free for educators; clients named by the WSJ included Virgin Group and Torque Esports; adopted High Fidelity's spatial audio. (Source: https://ryanschultz.com/2020/05/28/editorial-the-wall-street-journal-looks-at-breakroom-and-other-virtual-office-spaces-as-an-emerging-business-trend/; https://ryanschultz.com/tag/3d-audio/)
- 2026 status: Ryan Schultz's site states that "as of 2026, Sinespace has pretty much shut down, but like many metaverse platforms, a volunteer-run operation continues." A July 2026 brand-monitoring listing still describes it in the present tense. No Breakroom news after ~2022 surfaced. (Source: https://ryanschultz.com/first-time-visitor-welcome/; https://parse.gl/brands/sine-space)
- Verdict: commercially dead, residually alive.

**Sansar (Wookey Project Corp.)**
- Linden Lab's VR successor to Second Life (2017); sold to Wookey Project Corp. in March 2020, with Tilia retained for payments; Wookey said it would evolve Sansar "as the premier platform for live events and entertainment". (Source: https://uploadvr.com/linden-lab-sells-sansar-focus-second-life/; https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/)
- Latest dated coverage found is UploadVR's late-2021 report that Sansar went offline without explanation (website unreachable, Steam client failing to connect). No 2024-2026 coverage surfaced at all. (Source: https://uploadvr.com/sansar-offline-without-explanation/)
- Prior knowledge, unverified: Sansar came back online in 2022 and has remained reachable on Steam with single-digit to low-double-digit concurrency, run by a skeleton Wookey team; it is effectively a zombie platform. Treat as "status unknown, presumed minimal".

**OpenSimulator grids (Kitely, OSgrid, etc.)** (prior knowledge, unverified; not on the brief's list but the closest living relative of the Second Life use case)
- Open-source re-implementation of the Second Life server protocol, usable with SL-compatible viewers (Firestorm); Hypergrid Business tracks a few hundred public grids, on the order of tens of thousands of active users combined, with Kitely selling regions and a cross-grid marketplace. Fully in-world creation, persistent land, adult-majority user base. Worth a dedicated verification pass.

### B. Life-sim / cozy social worlds (mobile-first, mass-market)

**Avakin Life (Lockwood Publishing, Nottingham)**
- Launched 2013 (prior knowledge: Unity; iOS/Android, plus Steam). Lockwood announced in March 2026 that Avakin Life passed 500 million lifetime downloads with 1.6 million monthly active players and roughly 220,000 DAU in 2025. (Source: https://www.pcgamesinsider.biz/news/75555/avakin-life-surpasses-500-million-downloads-cementing-12-year-legacy-as-a-global-social-powerhouse/)
- Avakin Life officially launched on Steam on 27 May 2026 after an Early Access period, citing 200 million registered mobile users. (Source: https://www.pocketgamer.biz/avakin-life-officially-launches-on-steam-after-200m-registered-users-on-mobile/)
- Business model: subscriptions with exclusive items plus in-game currency sales priced $1-99; 2023 revenue GBP 22.35m with EBITDA of GBP -11.17m (data-profile site, unverified). A third-party iOS-only estimate shows ~176k MAU and ~$10k+/month, which badly understates the whole. (Source: https://www.preqin.com/data/profile/asset/lockwood-publishing-limited/398573; https://appgoblin.info/apps/740737088)
- What works: a Second Life-style life-sim (apartments, fashion, social hubs) delivered on phones with a first-party catalogue rather than UGC. Status: live, 12+ years, shrinking from a 2024 "7 million monthly" figure to 1.6m MAU. (Source: https://www.cbinsights.com/company/lockwood-publishing)

**Palia (Singularity 6, owned by Daybreak since July 2024)**
- Cozy MMO, launched 2023 (prior knowledge: Unreal Engine 5; PC, Switch, Epic/Steam). Free-to-play with cosmetic shop. (Source: https://en.wikipedia.org/wiki/Palia)
- 2026: Spring Spectacle update 17 March 2026; Royal Highlands expansion announced 10 March and released 12 May 2026, at which point Palia announced 10 million players; Sunkissed Summer series (Amberlight Affair, 6 July 2026; Beauty and the Beach, August 2026) added ranch critters, "teleport-to-friend" and duo dances. Monthly cadence switched to irregular in early 2026 ahead of the expansion. (Source: https://gamesbeat.com/?p=321353; https://massivelyop.com/2026/06/30/cozy-mmo-palia-is-teasing-amberlight-affair-with-a-new-ranching-critter-and-a-beach-theme; https://butwhytho.net/2026/08/palia-beauty-and-the-beach-update/)
- What works: persistent player housing with a strong decoration loop, low-stakes social play. Unsourced claims of a 20-30% DAU decline by August 2026 exist and should not be relied on. (Source: https://simplify.jobs/c/Singularity6)

**Sky: Children of the Light (thatgamecompany; NetEase co-publishes in Asia)**
- Launched 2019 on iOS; now on PS4, PC, iOS, Android and Switch; free-to-play with cosmetics and season passes. Passed 300 million downloads, announced around thatgamecompany's 20th anniversary (2026). Holds a Guinness record (August 2023) for 10,000+ users at a concert-themed virtual-world event. (Source: https://www.kitguru.net/gaming/mustafa-mahmoud/sky-children-of-the-light-surpasses-300-million-downloads-as-thatgamecompany-celebrates-20th-anniversary/; https://thatgamecompany.com/thatgamecompanys-sky-children-of-the-light-breaks-a-guinness-world-rec/)
- No current MAU disclosed. What works: wordless, friendship-centred social design that reaches a global, cross-device audience without UGC. Status: live, with "new projects in development" alongside continued Sky investment.

### C. Creator sandboxes and games platforms

**Dreams (Media Molecule / Sony, PS4)**
- Launched February 2020 (prior knowledge; proprietary engine). Live support ended 1 September 2023; servers remain online for sharing creations; a May 2023 server migration imposed a 5GB sharing cap per user; no PS5/PSVR2/PC version. No 2026 change surfaced. (Source: https://delistedgames.com/?p=21345; https://www.uploadvr.com/dreams-psvr-live-service-support-discontinued/; https://mixed-news.com/en/sony-discontinues-dreams-creative-app-with-metaverse-potential/)
- Status: frozen archive; a cautionary tale about a brilliant in-world creation toolset with no economy and no platform strategy.

**Core (Manticore Games)**
- Unreal-based free game-creation platform, open alpha 2020, Epic Games Store; raised $15m (Epic-led) and $30m Series B. Its standalone spin-off Out of Time launched on Epic 25 September 2025, moved to Steam, and was shut down and delisted roughly six months later for lack of players. No report that Core itself has been shut down surfaced in two searches; status is unconfirmed. (Source: https://en.wikipedia.org/wiki/Core_(video_game); https://rogueliker.com/out-of-time-offline/; https://www.siliconrepublic.com/start-ups/manticore-games-core-platform)

**Hytale (Hypixel Studios)**
- Cancelled by Riot in 2025, bought back by the founders, then launched in early access on 13 January 2026; passed one million players shortly after launch; Chapter 1 expansion previewed July 2026. Buy-to-play ($19.99/$34.99/$69.99 tiers); founder says pre-purchases funded two years of development and he has committed to ten years of support. (Source: https://en.wikipedia.org/wiki/Hytale; https://insider-gaming.com/hytale-expects-one-million-players-at-early-access-launch/; https://www.pcgamesn.com/hytale/guide)
- Prior knowledge: custom engine; PC first; server-hosting ecosystem (physgun etc.) already exists. Status: live, the largest 2026 new entrant in this category, but a block-game, not a social world.

**Pax Dei (Mainframe Industries, publisher New Tales)**
- Early access 18 June 2024; 1.0 launched 16 October 2025 on Steam/Epic/Microsoft Store and PC Game Pass day one, with a full wipe and a promise of no further wipes; buy-to-play at ~$30 with a 7-day trial. Dev team cut from 60 to 43 before 1.0. 2026 roadmap: Grace and economy, then Verse 5 (Feudal Shrines) and Verse 6 (Feudal Alliances). Steam concurrency in mid-2026 roughly 400-740, two-week peak 11,531. (Source: https://playpaxdei.com/news/1-0/pax-dei-1-0-releases-october-16-a-new-chapter-begins; https://www.sportskeeda.com/mmo/pax-dei-lays-25-dev-team-keep-studio-alive; https://isthereanydeal.com/game/pax-dei/info/; https://massivelyop.com/?p=601106)
- Relevance: "NPC-less" player-built society and housing on a persistent map is the closest a modern MMO has come to Second Life's land model, and it is struggling.

### D. Web/XR "metaverse" platforms

**Spatial (Spatial Systems)**
- Pivot history: VR meetings, then NFT galleries and cultural events ($25m raise), then a Unity creator toolkit with mobile games. On 28 May 2026 Spatial announced it would sunset Free and Pro creator tiers and discontinue 3D World hosting on 27 July 2026, deleting creator files after that date; enterprise customers continue. CEO Jinha Lee blamed the rising cost of hosting and scaling open multiplayer 3D worlds. The company is refocusing on original IP via its in-house studio Wooster Games, whose Animal Company is described as its top-earning Meta Quest game. (Source: https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/; https://venturebeat.com/arvr/spatial-raises-25m-and-pivots-to-nft-art-and-metaverse-events)
- HTC's Viverse published a "Spatial.io alternative: move to VIVERSE" migration pitch. (Source: https://news.viverse.com/post/spatial-io-alternative-move-to-viverse)

**Viverse (HTC)**
- Viverse Create v1.0 (August 2024): no-code, browser-based, built on PlayCanvas, Sketchfab library, VRM avatar import; February 2025 added Viverse Worlds hosting; a performance-based Viverse Partner Program pays creators on engagement; a 2026 Open Brush art jam is running. (Source: https://www.silicon.co.uk/press-release/htc-launches-no-code-virtual-world-builder-with-viverse-create; https://www.businesswire.com/news/home/20250226130250/en; https://www.businesswire.com/news/home/20251115808819/en)
- Prior knowledge, unverified: HTC's Viverse took over the PlayCanvas engine from Snap in 2025. No usage figures exist. Status: live, HTC-subsidised, positioning as the home for refugees from Spatial.

**Mona (Monaverse)**
- $14.6m Series A (June 2022) led by Protocol Labs, Archetype and Collab+Currency; web-based multiplayer worlds and Unity toolkit. A later (undated) company post says Mona is "simplifying" and the main focus is now a marketplace for 3D digital art. (Source: https://www.businesswire.com/news/home/20220629005466/en/; https://monaverse.com/blog/embracing-the-future-exciting-changes-at-mona)
- Status: pivoted away from being a world.

**Nowhere (urnowhere.com)**
- Video-first "human-centric" metaverse where users appear as live video in a floating nonagon; launched 2021 around an events festival. No 2026 coverage found. Prior knowledge, unverified: it narrowed to B2B events and education. (Source: https://tynmagazine.com/metaverse-nowhere-is-the-metaverse-for-entertainment/; https://www.timeout.com/newyork/things-to-do/nowhere-fest)

### E. Enterprise and education worlds

- **Virbela / Frame**: founded 2012 by behavioural psychologists; owned by eXp World Holdings, returned to its founders in 2024; Frame is the WebXR product (desktop/mobile/VR); a listing shows an $800k seed round on 22 June 2026 (unverified). (Source: https://www.virbela.com/why-virbela/technology; https://beta.motherbase.ai/startup/93394-virbela/; https://fundup.ai/recently-funded-startups/company/a5f8cc1ea0f2ba7ce3875a94478ea9d4bdbd335b7e3b6f6c98f81dd80023cdd6/virbela)
- **Engage XR**: Euronext Growth Dublin-listed (EXR); persistent 3D meeting/training environments; events up to 1,000 simultaneous participants; explicitly does not require every participant to own a headset. (Source: https://geo.sig.ai/compare/engage-xr-vs-facebook) Prior knowledge: has pivoted toward AI-avatar training products.
- **Nvidia Omniverse** (prior knowledge, unverified): never a consumer world; in 2024 Nvidia retired the Omniverse Create/View apps in favour of OpenUSD SDKs and industrial digital twins. Not a competitor to nolife; a possible interchange-format precedent (OpenUSD).
- **Breakroom**: see Sinespace above.

### F. 2026 "next Second Life" entrants

- A direct search for platforms pitched in 2026 as a Second Life successor returned only 2014-2017 coverage of Linden Lab's own "next-generation virtual world" (Sansar), which was designed around separate "experiences" rather than one continuous world and sold objects rather than land. (Source: https://bit-tech.net/news/gaming/pc/second-life-successor-in-development/1/; https://www.technologyreview.com/s/603422/second-life-is-back-for-a-third-life-this-time-in-virtual-reality/)
- No 2026 launch explicitly marketed as the "next Second Life" was found. The only genuinely new 2026 worlds found are Hytale (block sandbox) and Avakin's Steam launch; the 2026 trend is exits (Spatial creator tiers, NeosVR 2025, Sinespace) rather than entrants.

## Patterns

1. **Scale cliff.** Below the big platforms, the open-creation VR worlds live on 30-200 Steam concurrent users (ChilloutVR ~34, Resonite ~190). The mass-market survivors are mobile-first, non-UGC life-sims or cozy games (Avakin 1.6m MAU, Palia 10m lifetime players, Sky 300m downloads). Nobody in 2026 combines mass scale with in-world creation except the covered giants (Roblox, VRChat).
2. **Hosting cost kills open UGC hosting.** Spatial's stated reason for sunsetting creator tiers was the growing cost of hosting open multiplayer 3D worlds; Dreams imposed 5GB caps; Sansar went dark in 2021. Free world hosting without a land/storage fee is structurally unsustainable at small scale.
3. **Community-funded worlds outlast VC-funded ones.** Resonite (Patreon), Overte (non-profit), OpenSim grids (volunteer/self-hosted) and the volunteer remnant of Sinespace persist; Mona, Spatial and Sansar (VC or corporate) pivoted or faded. Lockwood survived 12 years on subscriptions plus currency sales despite a GBP -11m EBITDA in 2023.
4. **Governance disputes are existential for small platforms.** The Neos split over crypto features destroyed NeosVR within two years and spawned its successor.
5. **The product that works is "home + friends + dressing up".** Avakin, Palia and Sky all centre persistent housing or a persistent home-space, cosmetics, and low-stakes co-presence; none depend on user scripting.
6. **Buy-to-play persistent sandboxes are fragile.** Pax Dei launched 1.0 with a 25% staff cut and sits at several hundred concurrent; Hytale's early access is the exception, carried by a decade of Minecraft-server community.
7. **Enterprise survivors sell seats, not worlds.** Virbela/Frame, Engage, Breakroom and Spatial Enterprise persist on per-seat or per-event contracts; their worlds are disposable.

## Which of them actually serve the Second Life use case

Scoring on: persistent homes, creation in-world, adult users, real economy.

| Platform | Persistent homes | In-world creation | Adult users | Economy | Verdict |
|---|---|---|---|---|---|
| Resonite | yes (user worlds) | yes, fully in-world | yes | no fiat economy | closest spiritual match, tiny |
| ChilloutVR | yes | upload via Unity | yes | none | dormant |
| OpenSim grids | yes (land) | yes, SL-identical | yes | partial (Kitely market) | literal clone, unverified in 2026 |
| Sinespace | yes | Unity SDK | yes | had one | shut down 2026 |
| Sansar | experiences | external tools | yes | had Tilia | presumed zombie |
| Avakin Life | yes (apartments) | no | yes (18+ skew) | first-party only | serves social/home half |
| Palia | yes (plots) | decoration only | mixed | cosmetic shop | serves home half |
| Sky | no | no | mixed | cosmetic | no |
| Dreams | no | yes | mixed | none | frozen |
| Pax Dei | yes (plots) | building, crafting | yes | in-game only | serves land half |
| Viverse / Spatial / Mona | hosted scenes | external tools | mixed | none | no |

Only Resonite and (unverified) OpenSimulator grids cover all four pillars, and both are two orders of magnitude smaller than Second Life.

## Design implications for nolife

- Charge for persistence from day one. Every platform that hosted open worlds for free either capped, charged, or shut down. A land/storage fee (Second Life's tier, Kitely's region pricing, Resonite's storage tiers) is the proven model; present it as "rent for your home" rather than a subscription.
- Build creation in-world, not in Unity. Resonite's maker culture and Dreams' output both came from tools inside the world; ChilloutVR, Sinespace, Spatial and Viverse all made Unity/PlayCanvas the real editor and never grew a creator economy.
- Ship desktop and mobile first, VR optional. Every survivor with more than a few hundred concurrent users is phone- or desktop-led (Avakin, Palia, Sky, Hytale); VR-first worlds plateau at a few hundred.
- Make the home and the wardrobe the core loop, and keep scripting as a power-user layer. Avakin, Palia and Sky retain adults on housing, decoration and cosmetics; nolife's onboarding should produce a furnished home and a dressed avatar before it exposes a scripting panel.
- Design governance to survive a founder split. Resonite was born from a dispute over monetisation; a published charter on what will never be added (e.g. crypto speculation) and open-source or escrowed server code are retention features for adult creators.
- Plan for a volunteer-run afterlife. Sinespace, Dreams and OpenSim show communities keep worlds alive if the server can be self-hosted; offering self-hostable regions (Hypergrid-style) is both a selling point and an exit guarantee.
- Target the Spatial and Sansar diaspora. Spatial deleted creator worlds on 27 July 2026 and Viverse is openly recruiting them; a glTF/VRM-compatible importer plus a migration offer is a cheap acquisition channel.
- Budget honestly: a Second Life-style world at 1.6m MAU (Avakin) ran at a GBP 11m loss in 2023 on GBP 22m revenue; nolife's unit economics must assume server cost per concurrent user that scales with UGC complexity, and price tier accordingly.

## Open questions

- Is Sansar actually online in October 2026, and does Wookey still process Tilia payouts? No post-2021 coverage surfaced.
- Is Core (coregames.com) still operating after Out of Time's closure, and did Manticore lay off staff in 2026?
- What are the 2026 active-user figures for OpenSimulator grids (Hypergrid Business monthly stats) and for Resonite's non-Steam launcher?
- Did HTC's Viverse acquire PlayCanvas, and has Viverse published any creator-payout or usage numbers?
- Has any 2026 startup actually marketed itself as "the next Second Life" (candidates to check: Linden Lab's own mobile/roadmap announcements, Lamina1, any Resonite-adjacent forks)?
- What is Palia's real retention after the Royal Highlands expansion, given unsourced claims of a 20-30% DAU decline by August 2026?
- Are Dreams' servers still online in 2026, and does Sony have a sunset date?

## Sources

- https://steambase.io/games/resonite
- https://tracker.gg/population/steam/2519830
- https://live-player-count.com/game/resonite
- https://en.wikipedia.org/wiki/Resonite
- https://en.wikipedia.org/wiki/NeosVR
- https://uploadvr.com/resonite-vr-steam-early-access
- https://voicesofvr.com/?p=14108
- https://steambase.io/apps/chilloutvr
- https://www.patreon.com/chilloutvr/about
- https://steamdb.info/patchnotes/19748411
- https://ryanschultz.com/tag/overte/
- https://overte-website-sphinx.readthedocs.io/de/latest/
- https://www.github.com/vircadia
- https://en.wikipedia.org/wiki/Sinespace
- https://ryanschultz.com/first-time-visitor-welcome/
- https://parse.gl/brands/sine-space
- https://gamesbeat.com/sine-wave-entertainment-launches-breakroom-3d-social-hub-for-remote-teams-in-vr-pc-or-mobile-devices/
- https://ryanschultz.com/2020/05/28/editorial-the-wall-street-journal-looks-at-breakroom-and-other-virtual-office-spaces-as-an-emerging-business-trend/
- https://uploadvr.com/linden-lab-sells-sansar-focus-second-life/
- https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/
- https://uploadvr.com/sansar-offline-without-explanation/
- https://www.pcgamesinsider.biz/news/75555/avakin-life-surpasses-500-million-downloads-cementing-12-year-legacy-as-a-global-social-powerhouse/
- https://www.pocketgamer.biz/avakin-life-officially-launches-on-steam-after-200m-registered-users-on-mobile/
- https://www.preqin.com/data/profile/asset/lockwood-publishing-limited/398573
- https://appgoblin.info/apps/740737088
- https://www.cbinsights.com/company/lockwood-publishing
- https://en.wikipedia.org/wiki/Palia
- https://gamesbeat.com/?p=321353
- https://massivelyop.com/2026/06/30/cozy-mmo-palia-is-teasing-amberlight-affair-with-a-new-ranching-critter-and-a-beach-theme
- https://butwhytho.net/2026/08/palia-beauty-and-the-beach-update/
- https://simplify.jobs/c/Singularity6
- https://www.kitguru.net/gaming/mustafa-mahmoud/sky-children-of-the-light-surpasses-300-million-downloads-as-thatgamecompany-celebrates-20th-anniversary/
- https://thatgamecompany.com/thatgamecompanys-sky-children-of-the-light-breaks-a-guinness-world-rec/
- https://delistedgames.com/?p=21345
- https://www.uploadvr.com/dreams-psvr-live-service-support-discontinued/
- https://mixed-news.com/en/sony-discontinues-dreams-creative-app-with-metaverse-potential/
- https://en.wikipedia.org/wiki/Core_(video_game)
- https://rogueliker.com/out-of-time-offline/
- https://www.siliconrepublic.com/start-ups/manticore-games-core-platform
- https://en.wikipedia.org/wiki/Hytale
- https://insider-gaming.com/hytale-expects-one-million-players-at-early-access-launch/
- https://www.pcgamesn.com/hytale/guide
- https://playpaxdei.com/news/1-0/pax-dei-1-0-releases-october-16-a-new-chapter-begins
- https://www.sportskeeda.com/mmo/pax-dei-lays-25-dev-team-keep-studio-alive
- https://isthereanydeal.com/game/pax-dei/info/
- https://massivelyop.com/?p=601106
- https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/
- https://venturebeat.com/arvr/spatial-raises-25m-and-pivots-to-nft-art-and-metaverse-events
- https://news.viverse.com/post/spatial-io-alternative-move-to-viverse
- https://www.silicon.co.uk/press-release/htc-launches-no-code-virtual-world-builder-with-viverse-create
- https://www.businesswire.com/news/home/20250226130250/en
- https://www.businesswire.com/news/home/20251115808819/en
- https://www.businesswire.com/news/home/20220629005466/en/
- https://monaverse.com/blog/embracing-the-future-exciting-changes-at-mona
- https://tynmagazine.com/metaverse-nowhere-is-the-metaverse-for-entertainment/
- https://www.timeout.com/newyork/things-to-do/nowhere-fest
- https://www.virbela.com/why-virbela/technology
- https://beta.motherbase.ai/startup/93394-virbela/
- https://geo.sig.ai/compare/engage-xr-vs-facebook
- https://bit-tech.net/news/gaming/pc/second-life-successor-in-development/1/
- https://www.technologyreview.com/s/603422/second-life-is-back-for-a-third-life-this-time-in-virtual-reality/
