# Adversarial check: "Networking, persistence and scale for a shared persistent world (2026)"

Checked: `research/networking-scale-tech.md` — 10 key claims. Date of check: 2026-10-09.

## Method note (read first)

**No live web evidence was obtainable in this run.** The shared WebSearch budget (200 calls per turn) was exhausted before this checker's first query, and every WebFetch attempt failed DNS (`ENOTFOUND`) while the agent proxy log shows the gateway answering 403 to CONNECT for the same hosts (wiki.secondlife.com, modemworld.me, community.secondlife.com, roadtovr.com, thegabmeister.com, en.wikipedia.org, sec.gov, robertsspaceindustries.com). Evidence therefore comes from two tiers:

- **[S]** sibling research/verify files in this workflow (`research/sl-history-stagnation.md`, `research/sl-economy-creators.md`, `research/safety-regulation-identity.md`, `research/graphics-tech-2026.md`, `research/successors-wave2-metaverse.md`, `research/business-models.md` and their `verify/*-refute.md` / `*-precision.md` notes). Those checkers also reported being unable to fetch, so [S] is corroboration by other analysts, not by the source.
- **[K]** this checker's own knowledge to mid-2026, with the URL that should settle the point.

Per the lens, "confirmed" below means *stable, well-documented fact that matches prior knowledge and sibling corroboration with no sign of contradiction*; it is not a live-fetch confirmation. Anything number-sensitive, post-2025, or resting on a single blog is left "unverifiable" even when it is plausible.

## Claims

### [0] SL region 256 m x 256 m, one simulator process (one per core); Full 100 avatars / 22,500 LI; Homestead 20 / 5,000; Openspace 10 / 1,000 — **corrected** (low confidence)
- Region geometry (256 m, one simulator process per region) and the 100 / 20 / 10 agent-limit defaults are stable, long-documented facts. [K][S]
- The Land Impact figure is mixed across products. After Linden Lab's 2019 land-capacity increase, a **private Full region is 20,000 LI** (optionally 30,000 LI for a surcharge — the "30K-LI region" the brief itself prices at US$239), while **Mainland** regions are 351 LI per 1,024 m², i.e. ~22,464 ≈ **22,500 LI per region**. So "22,500 by product tier" conflates the Mainland rate with the private-estate product. Homestead 5,000 and Openspace 1,000 are the post-2019 values (3,750 / 750 before). [K]; `verify/sl-history-stagnation-precision.md` reached the same conclusion independently; `verify/sl-history-stagnation-refute.md` instead proposed a 2023 12.5% bump (20,000 -> 22,500; Homestead 5,625) — this checker has no recollection of such a change and treats it as unconfirmed.
- Correct statement for the brief: "Full private region 100 avatars / 20,000 LI (30,000 with upgrade); Mainland ~22,500 LI per region; Homestead 20 / 5,000; Openspace 10 / 1,000."
- Sources to re-read: https://wiki.secondlife.com/wiki/Land ; https://secondlife.com/land/private-pricing

### [1] Simulator targets 45 physics FPS (~22 ms), llGetRegionFPS capped at 45.0, scripts lowest priority — **confirmed** (prior knowledge; no live fetch)
- 45 Hz is the simulator/Havok frame rate; 1/45 s = 22.2 ms; the LSL wiki states llGetRegionFPS returns at most 45.0; "time dilation" is physics rate relative to real time; script time is whatever remains after physics, agent updates and network in each frame, so scripts starve first. [K][S: `verify/sl-history-stagnation-precision.md`, `-refute.md`]
- Nuance the brief omits: scripts have run on the Mono VM since 2008 with a hard 64 KB memory cap per script; "scripts lose first" is a scheduler rule, not a VM limitation. [S]
- Source: https://wiki.secondlife.com/wiki/Statistics ; https://wiki.secondlife.com/wiki/LlGetRegionFPS

### [2] AWS uplift complete ~19 Nov 2020 (staged ~100/~300/~1,000 regions in October), no change to per-region architecture, caps or frame budget — **confirmed** for the completion date and the "no architectural change" gist; staging numbers unverifiable
- Linden Lab confirmed all main-grid (Agni) regions on AWS around 19-20 November 2020; back-end services continued moving into early 2021. Avatar caps and the 45 Hz budget were unchanged. [K][S: `verify/sl-history-stagnation-precision.md` claim 8]
- The exact October stage sizes (100 / 300 / 1,000) rest on Inara Pey's weekly Simulator User Group summaries and could not be checked. Treat as "progressively larger batches through autumn 2020".
- Source: https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/

### [3] 6 March 2023 "Infrastructure Investment Update": full region cut US$20 to US$209 (US$239 for 30K LI); L$ buy/sell fees changed — **confirmed** (prior knowledge; no live fetch)
- US$229 -> US$209 for a full private region and US$259 -> US$239 for the 30K-LI variant, setup unchanged at US$349, Homestead unchanged at US$109, effective 6 March 2023; the same notice raised LindeX transaction fees to offset the land cut. [K][S: `verify/sl-economy-creators-refute.md` and `-precision.md` claim 3 agree on every figure]
- Minor wording: the claim says fees were "changed"; the brief body says "raised". Raised is the right direction.
- Source: https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/

### [4] Roblox "infrastructure and trust & safety" US$1,153.5M in 2025 vs US$915.4M in 2024 (+26%), mostly data-centre cost — **unverifiable**, with a flagged conflict
- The FY2025 10-K could not be fetched. The 2025 figure is plausible for the trajectory, but the **2024 comparison figure conflicts** with other evidence: Roblox's 2024 quarterly releases put this line at roughly US$233M / 249M / 257M / 266M, i.e. about **US$1.0 billion for FY2024** [K], and `research/business-models.md` plus both of its verify notes independently use ~US$1.0B for FY2024. If FY2024 was ~US$1.0B, growth to US$1,153.5M is ~15%, not 26%.
- Possible reconciliation: the FY2025 10-K may present a reclassified or re-segmented line (e.g., excluding something that was previously included), which would restate 2024 to US$915.4M. Until the filing's income-statement table is read, do not quote "+26%" or "US$915.4M for 2024" in a funding deck; quote "roughly US$1.0-1.15B a year" instead.
- The researcher's own figure appears verbatim in `research/safety-regulation-identity.md`, which cites the same 10-K URL plus a CNBC piece; the sibling checkers of that brief marked it unverifiable too.
- Source: https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm

### [5] VRChat concurrency record 158,192 (Feb 2026, Japanese-language concert), reached via 40-80 person instances — **unverifiable**
- Could not fetch Road to VR. The figure also appears in `research/successors-wave2-metaverse.md`, where it is described as a *corrected* number (implying an earlier misreport), and both of that brief's checkers left it unverifiable. VRChat publishes no official metrics; "records" are staff social posts or third-party API trackers. The trajectory (136,567 on 1 Jan 2025; 148,886 on 1 Jan 2026) is consistent. [S]
- The instance-cap half (creator-set capacity up to 40, hard cap at double, i.e. 80) matches VRChat's creator docs as of 2025 [K], and is the structurally important part for the brief: the record is platform-wide, not per-room.
- Source: https://roadtovr.com/vrchat-key-stats-japan-growth-concurrents/ ; https://creators.vrchat.com/worlds/

### [6] Pixel Streaming ~US$0.71-1.12/hr per g4dn.xlarge (Nov 2024 list), one session per instance; managed hosts ~US$6/hr; i.e. US$1-6 per user-hour — **corrected** (low confidence)
- One UE Pixel Streaming session per GPU instance in the default setup, and managed hosting at US$0.10/minute overage (Eagle 3D), are as the sibling graphics brief states. [S: `research/graphics-tech-2026.md` section 5]
- Price band: AWS us-east-1 on-demand for **g4dn.xlarge is about US$0.526/hr (Linux) and ~US$0.71/hr (Windows)**; US$1.12 does not correspond to g4dn.xlarge in us-east-1 and is probably a non-US region or a larger size. The blog's quoted range should be re-read with its region. The lower bound of the claim should therefore be ~US$0.53, and "US$1-6 per user-hour" should be "~US$0.5-6". The 200-500x-versus-native conclusion survives. [K]
- The "US$6/hour" is an *overage* rate above plan minutes, not a managed host's base rate; the brief's own body text says this correctly.
- Sources: https://thegabmeister.com/p/unreal-pixel-stream-aws/ ; https://aws.amazon.com/ec2/pricing/on-demand/ ; https://www.eagle3dstreaming.com/pricing

### [7] Star Citizen Alpha 4.0 on Live 19 Dec 2024 with static server meshing; dynamic meshing not shipped by mid-2026 — **corrected** (minor label; gist holds)
- The build CIG pushed to the LIVE channel on 19 December 2024 was labelled **"Alpha 4.0 Preview"** (it had been on PTU/EPTU earlier in December); 4.0.1 in early 2025 was the first build CIG treated as the finished 4.0. The brief body has this backwards ("after a 4.0 Preview earlier that month" — the Preview *was* the 19 Dec Live build). [K]
- Static server meshing (Stanton and Pyro on separate dedicated game servers inside one shard, joined by the Replication Layer) is correctly described. Dynamic server meshing had not shipped by this checker's knowledge horizon (mid-2026); it remained a roadmap item. [K]
- Caution on the brief body, not this claim: it refers to "CIG's 2025 CitizenCon communications". This checker's recollection is that CIG **cancelled CitizenCon 2025** to focus on development; the 2025 dynamic-meshing messaging came through monthly reports and the roadmap instead. Low confidence; verify before citing.
- Source: https://robertsspaceindustries.com/comm-link/transmission/20371-Alpha-40-Is-Here ; https://robertsspaceindustries.com/roadmap

### [8] EVE time dilation (Nov 2011) slows nodes to 10%; M2-XFE (30-31 Dec 2020) Guinness record 6,557 concurrent; many could not load in — **confirmed** (prior knowledge; no live fetch)
- TiDi shipped with the Crucible expansion on 29 November 2011; the floor is 10% of real time. [K]
- M2-XFE: Guinness "most concurrent participants in a multiplayer video-game PvP battle" = 6,557 (CCP's count); the earlier FWST-8 fight (5 Oct 2020) holds the separate "most players in a PvP battle" record at 8,825 total. On the second day of M2-XFE the node could not load the attacking fleet and CCP later reimbursed losses. [K]
- Nuance: 6,557 is *concurrent in one system* under 10% TiDi; the brief's reading that EVE's single-shard scale is bought with latency is the right one.
- Sources: https://en.wikipedia.org/wiki/Battle_of_M2-XFE ; https://www.eveonline.com/news/view/the-largest-battle-in-eve-online-history

### [9] Improbable: US$502M from SoftBank (May 2017); Unity block 10 Jan 2019; Worlds Adrift closed July 2019; MSquared US$150M (April 2022); 10k+ figures are one-off scripted events — **confirmed** for the four dated facts (prior knowledge); the characterisation of the 10k events is editorial and unverifiable
- SoftBank led a US$502M round announced 12 May 2017. Improbable published its "Unity has blocked SpatialOS" post on 10 January 2019; Unity revised its ToS within the week and Improbable + Epic announced a US$25M fund. Bossa announced the Worlds Adrift closure in May 2019 and shut servers on 26 July 2019. MSquared announced a US$150M round in April 2022 (a16z, SoftBank Vision Fund 2, Mirana). [K]
- The "10,000+ concurrent avatars" claims (Otherside trips of ~4,500 and ~7,200 in 2022; later 10k+ Morpheus events) are Improbable/Yuga figures from timed events; no independent instrumentation has been published. The researcher's framing is reasonable but is an inference, not a measurement, and should be labelled as such.
- Sources: https://en.wikipedia.org/wiki/Improbable_(company) ; https://en.wikipedia.org/wiki/Worlds_Adrift

## Summary

| # | Claim | Verdict |
|---|---|---|
| 0 | SL region/caps/LI | corrected (Full private = 20,000 LI; 22,500 is Mainland) |
| 1 | 45 FPS, scripts starve first | confirmed (prior knowledge) |
| 2 | AWS uplift Nov 2020, no arch change | confirmed (stage sizes unverifiable) |
| 3 | 6 Mar 2023 US$209 / US$239 | confirmed (prior knowledge) |
| 4 | Roblox US$1,153.5M vs US$915.4M | unverifiable; 2024 base conflicts with ~US$1.0B quarterly data |
| 5 | VRChat 158,192 Feb 2026 | unverifiable |
| 6 | Pixel streaming US$0.71-1.12/hr | corrected (Linux g4dn.xlarge ~US$0.53/hr; US$6 is an overage rate) |
| 7 | SC 4.0 Live 19 Dec 2024 | corrected (that build was "4.0 Preview"; gist holds) |
| 8 | EVE TiDi / M2-XFE 6,557 | confirmed (prior knowledge) |
| 9 | Improbable dates and amounts | confirmed; 10k characterisation editorial |

0 refuted, 3 corrected, 5 confirmed-on-knowledge, 2 unverifiable. None of the corrections changes the brief's design implications.

## Additional findings relevant to designing a successor

1. **Roblox's 2024 cost base is probably ~US$1.0B, not US$915M.** The infra + T&S line was already ~US$12/DAU-year and ~1.4 cents per engaged hour in 2024 (`verify/business-models-precision.md`), which is the realistic all-in ceiling to plan against, and it includes stock-based comp and data-centre depreciation, so cash cost per hour is lower.
2. **Second Life's Land Impact is a per-1,024 m² rate, not a per-server constant.** Mainland (351 LI / 1,024 m²) and private estates (20,000 or 30,000 LI per region) already decouple content budget from avatar cap; the successor should go further and price by area and content budget only (the brief's implication 2), which SL half-does.
3. **The Star Citizen Replication Layer's crash-recovery benefit is real but the shipped product is still labelled Alpha/Preview after US$800M+;** the brief's "do not re-derive this" warning is well supported, and CIG's 2025 communications were not a CitizenCon (likely cancelled that year) — cite monthly reports/roadmap instead.
4. **VRChat's record figures are not official.** Any concurrency comparison with VRChat should cite the exact tracker and note that staff posts are the only "official" numbers; the design-relevant fact is the 40/80 instance cap, which is documented.
5. **EVE's two Guinness records measure different things** (8,825 total participants at FWST-8; 6,557 concurrent at M2-XFE); the brief mixes them in one sentence in section 2. Use "concurrent" only for M2-XFE.
6. **Pixel-streaming cost is region- and OS-sensitive**: Linux g4dn.xlarge at ~US$0.53/hr with 2-3 sessions per instance at 720p (which several studios run) brings the per-user-hour cost to ~US$0.20-0.30, narrowing the gap to native from 200-500x to ~50-100x. The "funnel only" conclusion still holds but the number should not be quoted as US$1 minimum.
7. **Method gap for the whole workflow:** every networking/scale number in the brief and in this check now rests on prior knowledge plus sibling notes. Before any figure goes into a plan, one pass with working network access should fetch: the SL Land wiki page, the Roblox FY2025 10-K income statement, the Road to VR February 2026 piece, and CIG's 4.0 Comm-Link.
