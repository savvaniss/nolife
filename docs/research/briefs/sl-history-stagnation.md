# Second Life: history and technical stagnation (postmortem brief for "nolife")

Prepared 2026-10-09. Method note: 19 web searches were run (extended mode for dated/niche facts). Direct page reads via WebFetch failed in this sandbox (DNS resolution errors on every host), so facts below are taken from the search engine's quoted extracts of the cited pages rather than from a full read of each page. Where a figure rests on a single third-party blog, or where sources disagree, this is stated inline. Company-reported figures (Linden Lab press releases, executive interviews) are labelled as such; independent measurements (login-screen concurrency logs, Firestorm telemetry) are labelled separately.

## Findings

### 1. Origin and the 2006-2008 hype cycle

- Second Life launched publicly in 2003 (Linden Research, Inc., founded by Philip Rosedale). The 10th-anniversary press release in June 2013 confirms the 2003 start and reports "nearly 36 million registrations to date" and users having spent "more than 217,266 years" in-world. (Source: https://modemworld.me/2013/06/20/linden-lab-issue-press-release-celebrating-10-years-of-sl/)
- The hype peak is datable: BusinessWeek ran a Second Life cover on 1 May 2006 featuring land baron Anshe Chung, arguing the platform could challenge the Web and Windows; Reuters appointed a full-time in-world bureau chief. Slate's 2011 retrospective treats 2006 as "the year the future looked like Second Life". (Source: https://slate.com/business/2011/11/why-second-life-failed-how-the-milkshake-test-helps-predict-which-ultrahyped-technology-will-succeed-and-which-wont.html ; https://en.wikipedia.org/wiki/Anshe_Chung)
- American Apparel opened the first major real-world brand store in June 2006; IBM announced a $10 million spend on Second Life and other virtual worlds; a 2007 Forbes piece counted roughly 80 companies with a presence (Coca-Cola, H&R Block, IBM, Toyota, Dell, Reebok among them). (Source: https://en.wikipedia.org/wiki/Businesses_and_organizations_in_Second_Life ; https://www.forbes.com/forbes/2007/0702/048.html)
- The corporate retreat began before the 2008 financial crisis. Forbes (July 2007) reported marketers disappointed by small crowds, citing 360,000 residents logged in over a seven-day period, and American Apparel "all but shuttering" its shop. Brand builds by Coca-Cola and Columbia were "abandoned about as fast as they were created." (Source: https://www.forbes.com/forbes/2007/0702/048.html ; https://productmint.com/what-happened-to-second-life/)
- Interpretation supported by these sources: the brand exodus was a marketing-ROI story (empty storefronts, no foot traffic model), not a platform-outage story. The platform's actual user base kept growing for another 18 months after the brands left.

### 2. User and concurrency trajectory, 2007-2026

Independent measurement (concurrency logged from the login screen by residents; Linden Lab does not publish an official series):
- All-time peak concurrency: 88,200 in Q1 2009 per Wikipedia; the fan log's highest single reading is 88,220 on 29 March 2009. Bots are known to have inflated these numbers to an unquantified degree. (Source: https://en.wikipedia.org/wiki/Second_Life ; https://danielvoyager.wordpress.com/2024/04/09/second-life-user-daily-concurrency-april-2024-update/)
- Decline through 2009: ~77,000 mid-2009, low 50,000s by late 2009 (Alphaville Herald, citing Tateru Nino). A brief uptick in January 2010 was attributed to Avatar-film tie-in advertising (Engadget). The 2010 range in the fan log is 39,000-75,000. One 2013 analysis (Nalates) claims the peak was early 2010; this conflicts with the 2009 figure and is probably a different series. (Source: http://alphavilleherald.com/2009/12/second-life-losing-traction-concurrent-users-slide.html ; https://www.engadget.com/2010-01-14-avatars-blue-second-life-concurrency-and-transactions-rise.html ; http://blog.nalates.net/2013/01/28/second-life-2012-statistics/)
- 2025: highest peak 49,798 on 24 March 2025; by October 2025 daily peaks averaged 42,000-45,000 and the year was described as flat. Peak concurrency is therefore roughly half the 2009 record. (Source: https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/)

Company-reported active users:
- June 2013: "a million monthly active users" per CEO Rod Humble, with 400,000+ new accounts created per month and 1.2 million transactions per day. Note the gap between 36M cumulative registrations and 1M MAU: roughly 97% of sign-ups were not active. (Source: https://www.engadget.com/2013-06-20-second-life-readies-for-10th-anniversary-celebrates-a-million-a.html ; https://www.gamespot.com/news/second-life-marking-10-years-next-week-6410503)
- End of 2017: active users "between 800,000 and 900,000" (Wikipedia); a Firestorm-telemetry-derived estimate for the same period put regular users nearer 600,000. (Source: https://en.wikipedia.org/wiki/Second_Life ; https://ryanschultz.com/2019/09/18/why-second-life-still-has-600000-regular-users-after-16-years/)
- May 2020: CEO Ebbe Altberg reported a 50% increase in regular monthly users during the pandemic. (Source: https://ryanschultz.com/2020/05/24/linden-lab-ceo-ebbe-altberg-second-life-has-seen-a-50-increase-in-regular-monthly-users-because-of-the-pandemic/)
- June 2023 (20th anniversary press release, BusinessWire): approximately 750,000 MAU is the figure attributed to this release in secondary reporting; this could not be verified against the release text in this run. (Source: https://www.businesswire.com/news/home/20230621065980/en)
- October 2024: ~500,000 MAU, down from a long-running ~600,000, per executive chairman Brad Oberwager interviewed by Wagner James Au; DAU "significantly less" but not disclosed. (Source: https://danielvoyager.wordpress.com/2024/10/30/second-life-has-500000-monthly-active-users/)
- October 2025: "We're now at 600,000 MAU" (Oberwager), with new users arriving roughly half via the mobile app and half via Project Zero streaming. December 2025: 620,000. (Source: https://danielvoyager.wordpress.com/2025/10/26/second-life-has-600000-monthly-active-users/ ; https://danielvoyager.wordpress.com/2025/12/19/second-life-now-at-620000-monthly-active-users/ ; https://wjamesau.substack.com/p/the-state-of-second-life-in-2025-560)
- Contested: the 2023 "750K" and 2024 "500K" figures are hard to reconcile within 16 months; either the definition of MAU changed or one figure is wrong. No 2026 MAU figure was found.

### 3. Region/simulator architecture and its hard limits

- A region is a fixed 256 m x 256 m (65,536 m2) area run by one simulator process; the official wiki states one full region per server host CPU core (older community docs say up to four sims per server). (Source: https://wiki.secondlife.com/wiki/Land ; https://wiki.secondlife.com/wiki/Grid ; https://secondlife.fandom.com/wiki/Simulator)
- Avatar and content caps are per region product tier: Full region 100 avatars / 22,500 Land Impact; Homestead 20 avatars / 5,000 LI; Openspace 10 avatars / 1,000 LI. Homestead and Openspace are only sold to owners of a full region. (Source: https://wiki.secondlife.com/wiki/Land)
- The 256 m size was never a designed optimum. In an October 2008 sldev thread a Linden developer said "256 meters is not actually an unreasonable value," and another said changing it was not expected "because of its far-reaching effects on the platform." (Source: https://list-archives.secondlife.com/sldev/2008-October/012153.html)
- Frame budget: the simulator targets 45 physics frames per second (about 22 ms per frame); llGetRegionFPS is capped at 45.0. "Time dilation" is the physics rate relative to real time (1.0 = full speed). Script execution has the lowest priority in the frame: when avatar or physics load rises, script time is cut to hold the 22 ms frame, which is why "script lag" and unresponsive HUDs appear first. (Source: https://wiki.secondlife.com/wiki/Statistics ; https://wiki.secondlife.com/wiki/LlGetRegionFPS ; https://community.secondlife.com/forums/topic/424030-modern-sim-lag-times/ ; https://modemworld.me/2020/07/22/2020-simulator-user-group-week-30-summary/)
- Consequence: an event that draws more than ~100 people cannot exist in one place; venues work around it with multiple adjacent regions, and region crossings themselves cost frame time (older reports attribute ~5% time-dilation drops per crossing avatar; anecdotal, 2005-era). The platform has never shipped a sharded or dynamically scaled region model; the per-core, per-process simulator is the same unit it was in 2003.
- Scripting: LSL remains the only production language 23 years on. Linden Lab announced alpha testing of a Lua-based scripting option in March 2025. (Source: https://modemworld.me/2025/03/14/)

### 4. The viewer (client) and why third-party viewers mattered

- The client is a monolithic C++ OpenGL application that must stream and render arbitrary user content with no offline baking; this makes it both heavy and brittle. Linden Lab's own downloads page lists "more than fifteen third-party viewers" and names Firestorm as the most popular; Firestorm is built by volunteers (The Phoenix Firestorm Project). (Source: https://secondlife.com/downloads?lang=en-US)
- A community wiki claims Firestorm accounts for a majority of active sessions; forum posts say the same. No audited share figure was found; treat "majority" as plausible but unverified. Firestorm's own telemetry (2025) says about 80% of its users run a PBR-capable build and 8.2% remain on 7.1.9. (Source: https://secondlife.fandom.com/wiki/Firestorm ; https://www.firestormviewer.org/some-statistics-firestorm-versions-whos-running-what/)
- Why it matters: a volunteer project, not the platform owner, controls the UI most residents see. Every rendering upgrade (mesh, EEP, PBR) ships twice, and the feature only "exists" for most users once Firestorm merges it, which has historically lagged the official viewer by months. The 2025 streaming product was launched jointly with Firestorm ("Firestorm Zero"), an admission of this dependency. (Source: https://modemworld.me/2025/03/14/using-firestorm-in-your-browser-for-second-life/)

### 5. Content pipeline upgrades: what each took

- Mesh import (2011): discussed publicly from 2010 ("Mesh-ing around", Sept 2010); the project "started and stalled" more than once; a timeline was promised by end of May 2011, limited regions in July, general availability by end of August; shipped in Viewer 3.0.0 on 23 August 2011. Upload was gated behind payment-info on file and a mandatory IP-rights quiz, plus a complexity-based upload fee. Elapsed time from public discussion to release: about a year; from launch of the platform: eight years. (Source: https://modemworld.me/2010/09/14/ ; https://modemworld.me/2011/06/01/mesh-starts-rolling-in-july/ ; https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.0.0)
- EEP (Environment Enhancement Project): announced 2017; project viewer October 2018; release-candidate channels March 2019; official release 20 April 2020 with viewer 6.4.0.540188. Linden Lab's own post said it "has taken longer than anticipated." Elapsed: about three years for a sky/water settings system. (Source: https://modemworld.me/2018/10/04/ ; https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/6.1.1.525044 ; https://modemworld.me/2020/04/20/second-life-eep-the-environment-enhancement-project/)
- PBR materials: discussed at TPV developer meetings from May 2022; project viewer 7.0.0 limited to a handful of beta-grid (Aditi) regions on 2 December 2022; grid-wide simulator deployment planned for the week of 27 November 2023; official "PBR Materials Official Launch" post from Linden Lab. The launch moved lighting to linear color, added HDR with auto-exposure and tonemapping, reflection probes, and glTF-based materials; legacy diffuse/normal/specular materials still work and can be mixed. Scripts can only touch PBR via llSetPrimitiveParams and llSetRenderMaterial. Elapsed: about 18 months of public development; roughly a decade behind mainstream game engines, which standardized PBR around 2013-2015. (Source: https://modemworld.me/2022/05/14/ ; https://modemworld.me/2022/12/03/ ; https://modemworld.me/author/peysworld/page/151 ; https://community.secondlife.com/blogs/entry/14536-second-life-pbr-materials-official-launch)
- Pattern: each upgrade is additive and backward-compatible, never a migration. 2003 prims, 2011 mesh, 2013-era specular materials and 2023 PBR all coexist in the same scene, so the renderer must support every content generation ever created, and residents on old GPUs resist each step.

### 6. Project Sansar as a diversion (2014-2020)

- Sansar was first teased in 2014 as a VR-first successor. TechCrunch described the outcome as "a disaster for Linden Lab, which has focused considerable resources on the effort since it first teased the platform back in 2014," and said it "struggled to gain traction" among VR users. No dollar figure for Sansar's cost was found in any source. (Source: https://techcrunch.com/?p=1965040)
- Sold to Wookey Project Corp, confirmed by press release on 24 March 2020; Linden Lab retained Second Life and Tilia. CEO Ebbe Altberg said the company "could no longer sponsor Sansar financially" and that it had been "a start-up inside of an established, profitable company." (Source: https://modemworld.me/2020/03/24/linden-lab-confirm-the-sale-of-sansar-to-wookey-project-corp/ ; https://roadtovr.com/sansar-spin-off-linden-lab-refocus-second-life/ ; https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/)
- Implication: for roughly six years the engineering investment that could have modernized the Second Life renderer, simulator or client went into a separate product that never had meaningful concurrency and that Second Life residents could not migrate to (no inventory, land or social-graph continuity). EEP's three-year slip falls squarely inside this period.

### 7. VR, mobile and streaming

- VR: an Oculus project viewer appeared in 2014; a CV1 build (4.1.0.317313) shipped in early July 2016 and was withdrawn on 8 July 2016 because it "didn't meet our standards for quality"; Linden Lab said it could not say "when or even if" another Rift viewer would come. No official VR support has existed since. (Source: https://modemworld.me/2016/07/08/second-life-oculus-rift-support-suspended/ ; https://uploadvr.com/second-life-suspends-oculus-rift-support-vr/)
- Mobile: a closed mobile beta was run in October 2013 and never shipped. A new Unity-based app was shown in 2023; open beta for Premium subscribers announced 25 June 2024 at SL21B; made free to all users on 13 November 2024 (announced 21 November 2024). As of a Google Play developer note dated 6 October 2026 the app "is still in beta," with controls, inventory, HUDs and avatar interactions "still need[ing] improvement"; the listing shows 1M+ downloads and a 2.5-star rating. (Source: https://modemworld.me/2013/10/23/lab-confirms-sl-mobile-beta-programme/ ; https://modemworld.me/2024/06/26/sl-mobile-available-to-premium-plus-and-premium-in-open-beta/ ; https://community.secondlife.com/news/featured-news/second-life-mobile-is-here-r1550/ ; https://play.google.com/store/apps/details?id=com.lindenlab.secondlife&hl=en_US)
- Streaming ("Project Zero"): announced January 2025 as a pixel-streamed 1080p viewer, motivated by Linden Lab's statement that roughly 50% of the existing user base lacks high-end machines. Firestorm Zero launched 14 March 2025 on Amazon GameLift, sold as time passes (e.g., L$250 for 5 hours), and sold out. In September 2025 the Lab said Project Zero plus mobile produced a "10x" increase in people trying Second Life versus the download-the-viewer funnel. A later Linden Lab announcement that Project Zero is to end exists (modemworld tag page), but its date and reasons were not retrievable in this run. Predecessors OnLive SL Go and Bright Canopy died for business reasons. (Source: https://modemworld.me/2025/01/02/ ; https://modemworld.me/2025/03/14/using-firestorm-in-your-browser-for-second-life/ ; https://modemworld.me/tag/project-zero/)

### 8. Cloud migration to AWS (2020)

- Staged over autumn 2020: ~100, then ~300, then ~1,000 regions on AWS during October 2020; the last main-grid (Agni) regions moved around 19 November 2020; Linden Lab's 5 January 2021 update said the physical move completed at end of 2020; follow-up service migration continued into February 2021. (Source: https://modemworld.me/2020/10/22/ ; https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/ ; https://modemworld.me/2021/01/05/ ; https://modemworld.me/2021/02/26/lab-gab-feb-26-summary-aws-update-and-a-farewell-to-oz/)
- The "uplift" moved the same one-process-per-region simulator onto rented machines; it did not change the architecture, caps or frame budget. Its benefit was operational (hardware refresh, capacity elasticity, later the GameLift streaming), not experiential.

### 9. Ownership and leadership

- CEOs: Rosedale (2003-May 2008); Mark Kingdon from 15 May 2008; June 2010 restructuring with ~30% staff layoffs, Kingdon out June/July 2010; Rosedale interim for about four months; CFO/COO Bob Komin acting from October 2010; Rod Humble appointed December 2010 (started January 2011), resigned 24 January 2014; Ebbe Altberg from February 2014 until his death in June 2021. (Source: https://en.wikipedia.org/wiki/Linden_Lab ; https://www.engadget.com/2010-12-23-linden-lab-names-new-ceo.html ; https://gamesbeat.com/?p=10316 ; https://gamesbeat.com/?p=12968)
- Ownership: on 9 July 2020 Linden Research announced acquisition by an investment group led by J. Randall (Randy) Waterfield and Brad Oberwager (with Raj Date as third investor); closing required U.S. financial-regulator approval because subsidiary Tilia Inc. is a licensed money transmitter; the deal closed after regulatory review (reported by early 2021). Oberwager serves as executive chairman and is the public voice on metrics. (Source: https://modemworld.me/2020/07/09/linden-lab-announces-it-is-to-be-acquired/ ; https://modemworld.me/2021/01/05/ ; https://modemworld.me/tag/sl18b/page/2/)
- Six CEO transitions in six years (2008-2014), a 30% layoff, a failed sibling product and a change of control: the platform spent most of its second decade without stable strategic ownership of its core technology.

### 10. Economy, and why an ancient platform still has ~600K MAU

- Oberwager (December 2024, GamesBeat): Linden Lab has spent about $1.3 billion building Second Life and paid about $1.1 billion to creators since 2003; the economy runs at roughly $650 million a year; Linden Lab's cut is about 10% of transactions. Creators were paid $78 million in 2023 (vs $73M in 2020, $65M in 2019, ~$60M in 2015 against a then-claimed $500M GDP). 21,152 creators earned income in 2023 and 1,580 earned over $10,000 (secondary source). All are company figures. (Source: https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/ ; https://modemworld.me/2024/12/20/second-life-1-3b-to-build-1-1b-paid-to-creators/ ; https://qz.com/1976147/non-fungible-tokens-boosted-second-lifes-economy ; https://en.wikipedia.org/wiki/Second_Life ; https://www.mrphilgames.com/blog/why-nobody-has-built-a-modern-second-life)
- What this tells us: retention is driven by accumulated social capital and property (inventories, land, businesses, relationships, 20-year-old communities), not by graphics. Creator cash-out of ~$75M/year is a real livelihood for thousands; no competitor (Sansar, High Fidelity, Decentraland, Horizon Worlds) has offered a comparable income path, so creators and their customers do not leave. The 2025 rebound (500K to 620K MAU) came from lowering the entry barrier (mobile, streaming), not from PBR; graphics upgrades mostly served existing residents.

## Patterns / root causes

1. Backward compatibility as a one-way ratchet. Every asset since 2003 must keep rendering and every script must keep running; the result is additive layering (prims + mesh + legacy materials + PBR) that makes each new feature slower to build and the client heavier. Nothing is ever deprecated.
2. The simulator is the unit of everything. Land product, pricing, physics, scripts, avatar caps and server allocation are all bound to the 256 m / one-core region. Changing it was called too far-reaching in 2008 and has not been attempted since; AWS re-hosted the same unit.
3. Client ownership was ceded. The most-used viewer is volunteer-built; the Lab lost the ability to ship UX changes to the majority of users on its own schedule.
4. Strategic distraction and churn. Sansar (2014-2020), six CEO changes (2008-2014), a 30% layoff (2010) and a sale (2020) consumed the decade in which the renderer and simulator should have been rebuilt.
5. Reaching new users was deferred for 20 years. VR was abandoned in 2016; mobile was attempted in 2013 and only shipped (still in beta) in 2024; streaming arrived in 2025. The 2025 funnel data ("10x" trials, MAU +24%) shows access, not fidelity, was the binding constraint.
6. Metrics opacity. No official time series for concurrency, MAU or DAU exists; outside observers rely on login-screen scrapes and interviews, and company figures (750K vs 500K) are inconsistent. This hid the decline and blunted urgency.
7. The economy and the social graph are the moat, and they are the thing nobody has replicated: real cash-out, creator ownership of IP, and persistent property. Hype departed in 2007-2008; the residents did not.

## Design implications for nolife

1. Make the world unit elastic from day one: no fixed-size, single-process regions. Spatially partition dynamically (interest management, server meshing) so a 1,000-person event is a scaling event, not an architectural impossibility; set the avatar cap by budget, not by product tier.
2. Treat the client as a product the platform owns and ships continuously (auto-updating, modular), but publish a stable, documented protocol so community clients can exist without becoming the de facto UI. Firestorm's dominance was a symptom of a neglected first-party client.
3. Ship on current-era rendering (PBR, glTF 2.0, HDR, GPU-driven pipelines) at launch and version the asset format so later migrations are possible; define a deprecation policy from the start rather than promising eternal compatibility.
4. Launch mobile, desktop and streamed access together; Second Life's 2025 data shows half its new users now come through low-barrier clients. Target the 50% of users on weak hardware with server-side rendering as a first-class tier.
5. Keep VR optional and additive, not the product's premise; Sansar's VR-first bet was the costliest decision in the company's history.
6. Build creator economics in as the retention engine: low platform take (SL's ~10%), real cash-out, portable IP, and public economic reporting. Design a migration path for Second Life creators (importers for mesh/glTF, a scripting bridge from LSL/Lua) so the moat moves rather than being rebuilt.
7. Choose a modern sandboxed scripting language (Luau/WASM) with per-script budgets that degrade gracefully instead of a frame-wide "scripts lose first" rule; expose profiling to residents.
8. Publish metrics (MAU, DAU, peak concurrency, cash-out) on a fixed cadence; stagnation went unmeasured for a decade.
9. Governance stability: avoid building a second product inside the first; keep the roadmap on the core world and fund it from the core economy.

## Open questions

- What was Sansar's actual cost (dollars, headcount-years), and what fraction of Linden Lab engineering it absorbed 2014-2020?
- Why do the 2023 (~750K) and 2024 (~500K) MAU figures differ; did the definition of MAU change, or was 2023 inflated by the anniversary?
- Firestorm's true share of sessions (the "majority" claim is unverified).
- Why Project Zero was ended (cost per streamed hour vs willingness to pay?) and what the retention of streamed and mobile sign-ups is at 30/90 days.
- Region counts and land revenue over time (the primary revenue line) and how they moved with the 2020 cloud migration and the 2024-25 MAU swing.
- Whether a region-size or sharding change has ever been prototyped internally since the 2008 thread.
- Current DAU and median session length (Oberwager has declined to give DAU).
- Status of the Lua scripting alpha (March 2025) and whether it replaces or merely sits alongside LSL.

## Sources

- https://en.wikipedia.org/wiki/Second_Life
- https://en.wikipedia.org/wiki/Linden_Lab
- https://en.wikipedia.org/wiki/Anshe_Chung
- https://en.wikipedia.org/wiki/Businesses_and_organizations_in_Second_Life
- https://wiki.secondlife.com/wiki/Land
- https://wiki.secondlife.com/wiki/Grid
- https://wiki.secondlife.com/wiki/Statistics
- https://wiki.secondlife.com/wiki/LlGetRegionFPS
- https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.0.0
- https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/6.1.1.525044
- https://secondlife.fandom.com/wiki/Simulator
- https://secondlife.fandom.com/wiki/Firestorm
- https://list-archives.secondlife.com/sldev/2008-October/012153.html
- https://secondlife.com/downloads?lang=en-US
- https://community.secondlife.com/blogs/entry/14536-second-life-pbr-materials-official-launch
- https://community.secondlife.com/news/featured-news/second-life-mobile-is-here-r1550/
- https://community.secondlife.com/forums/topic/424030-modern-sim-lag-times/
- https://play.google.com/store/apps/details?id=com.lindenlab.secondlife&hl=en_US
- https://www.businesswire.com/news/home/20230621065980/en
- https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/
- https://gamesbeat.com/?p=10316
- https://gamesbeat.com/?p=12968
- https://wjamesau.substack.com/p/the-state-of-second-life-in-2025-560
- https://danielvoyager.wordpress.com/2024/04/09/second-life-user-daily-concurrency-april-2024-update/
- https://danielvoyager.wordpress.com/2024/10/30/second-life-has-500000-monthly-active-users/
- https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/
- https://danielvoyager.wordpress.com/2025/10/26/second-life-has-600000-monthly-active-users/
- https://danielvoyager.wordpress.com/2025/12/19/second-life-now-at-620000-monthly-active-users/
- https://modemworld.me/2010/09/14/
- https://modemworld.me/2011/06/01/mesh-starts-rolling-in-july/
- https://modemworld.me/2013/06/20/linden-lab-issue-press-release-celebrating-10-years-of-sl/
- https://modemworld.me/2013/10/23/lab-confirms-sl-mobile-beta-programme/
- https://modemworld.me/2016/07/08/second-life-oculus-rift-support-suspended/
- https://modemworld.me/2018/10/04/
- https://modemworld.me/2020/03/24/linden-lab-confirm-the-sale-of-sansar-to-wookey-project-corp/
- https://modemworld.me/2020/04/20/second-life-eep-the-environment-enhancement-project/
- https://modemworld.me/2020/07/09/linden-lab-announces-it-is-to-be-acquired/
- https://modemworld.me/2020/07/22/2020-simulator-user-group-week-30-summary/
- https://modemworld.me/2020/10/22/
- https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/
- https://modemworld.me/2021/01/05/
- https://modemworld.me/2021/02/26/lab-gab-feb-26-summary-aws-update-and-a-farewell-to-oz/
- https://modemworld.me/2022/05/14/
- https://modemworld.me/2022/12/03/
- https://modemworld.me/author/peysworld/page/151
- https://modemworld.me/2024/06/26/sl-mobile-available-to-premium-plus-and-premium-in-open-beta/
- https://modemworld.me/2024/11/15/second-life-mobile-free-to-all-users-lab-execs-discuss-the-product-and-goals/
- https://modemworld.me/2024/12/20/second-life-1-3b-to-build-1-1b-paid-to-creators/
- https://modemworld.me/2025/01/02/
- https://modemworld.me/2025/03/14/
- https://modemworld.me/2025/03/14/using-firestorm-in-your-browser-for-second-life/
- https://modemworld.me/tag/project-zero/
- https://modemworld.me/tag/sl18b/page/2/
- https://roadtovr.com/sansar-spin-off-linden-lab-refocus-second-life/
- https://uploadvr.com/second-life-suspends-oculus-rift-support-vr/
- https://techcrunch.com/?p=1965040
- https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/
- https://www.engadget.com/2010-01-14-avatars-blue-second-life-concurrency-and-transactions-rise.html
- https://www.engadget.com/2010-12-23-linden-lab-names-new-ceo.html
- https://www.engadget.com/2013-06-20-second-life-readies-for-10th-anniversary-celebrates-a-million-a.html
- https://www.gamespot.com/news/second-life-marking-10-years-next-week-6410503
- http://alphavilleherald.com/2009/12/second-life-losing-traction-concurrent-users-slide.html
- http://blog.nalates.net/2013/01/28/second-life-2012-statistics/
- https://ryanschultz.com/2019/09/18/why-second-life-still-has-600000-regular-users-after-16-years/
- https://ryanschultz.com/2020/05/24/linden-lab-ceo-ebbe-altberg-second-life-has-seen-a-50-increase-in-regular-monthly-users-because-of-the-pandemic/
- https://slate.com/business/2011/11/why-second-life-failed-how-the-milkshake-test-helps-predict-which-ultrahyped-technology-will-succeed-and-which-wont.html
- https://www.forbes.com/forbes/2007/0702/048.html
- https://productmint.com/what-happened-to-second-life/
- https://qz.com/1976147/non-fungible-tokens-boosted-second-lifes-economy
- https://www.mrphilgames.com/blog/why-nobody-has-built-a-modern-second-life
- https://www.firestormviewer.org/some-statistics-firestorm-versions-whos-running-what/
