# Precision check: "Second Life: history and technical stagnation"

Checked 2026-10-09. Brief under review: scratchpad/research/sl-history-stagnation.md

## Method and an important limitation

No cited page could be fetched in this run. WebFetch failed with DNS errors (getaddrinfo ENOTFOUND) on every host (danielvoyager.wordpress.com, wiki.secondlife.com, modemworld.me, roadtovr.com, gamesbeat.com), the per-turn WebSearch budget was already exhausted by other agents before my first query (0 of 14 searches executed), and a curl fallback was blocked by the permission system. The researcher reported the same DNS failure, so neither of us has read a primary page.

Verdicts below therefore rest on my own background knowledge of these events (reliable for well-covered items up to roughly 2024-25, weak for 2025 day-level figures). I use "confirmed" only where I am independently confident of the key facts, "unverifiable" where the claim hinges on figures I cannot independently confirm, and I flag any case where the cited URL probably does not contain what it is cited for. A follow-up run with working fetch should re-check the items marked unverifiable; the exact URLs to re-fetch are listed per claim.

## Verdicts

### [0] Peak concurrency 88,200 (Q1 2009) / 88,220 on 29 Mar 2009; 2025 high 49,798 on 24 Mar 2025; Oct 2025 peaks 42-45K
Verdict: unverifiable (partly consistent).
- 88,200 peak in Q1 2009 is the figure given in the Wikipedia Second Life article and is widely repeated; consistent with my knowledge.
- 88,220 on 29 March 2009, 49,798 on 24 March 2025 and the 42,000-45,000 October 2025 band are day-level readings from one fan log that I cannot check. The 2025 numbers are plausible (the mobile-app launch lifted early-2025 concurrency into the high 40Ks) but not confirmable here.
- Source mismatch: the claim cites the October 2025 Daniel Voyager post for the 2009 record. In the brief itself the 2009 figure is sourced to Wikipedia and the April 2024 Voyager post; the 2025 post may not restate it. Cite Wikipedia for the 2009 figure.
- Caveat worth adding: login-screen concurrency includes scripted agents (bots); Linden Lab added mandatory bot/scripted-agent flagging in 2024, so 2009 and 2025 series are not like-for-like.
Re-fetch: https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/ ; https://en.wikipedia.org/wiki/Second_Life

### [1] MAU ~500K Oct 2024, 600K Oct 2025, 620K Dec 2025 (Oberwager via Wagner James Au); new users half mobile, half Project Zero
Verdict: unverifiable (Oct 2024 part consistent).
- The ~500,000 MAU figure, attributed to Brad Oberwager in an October 2024 interview with Wagner James Au (New World Notes) and described as a drop from a long-cited ~600,000, matches my knowledge.
- The 600,000 (Oct 2025) and 620,000 (Dec 2025) figures and the 50/50 mobile vs Project Zero split are late-2025 statements I cannot confirm. Treat as single-source, company-reported.
- Precision note: these are executive statements relayed through a blogger, not published metrics; the brief already says so. The 2023 "750K" figure in the brief is from press coverage of the SL20B release and may use a different definition; the inconsistency the researcher flagged is real and unresolved.
Re-fetch: https://danielvoyager.wordpress.com/2025/10/26/second-life-has-600000-monthly-active-users/ ; https://wjamesau.substack.com/p/the-state-of-second-life-in-2025-560

### [2] Region 256 m x 256 m, one simulator process, one full region per CPU core; Full 100 avatars / 22,500 LI; Homestead 20 / 5,000; Openspace 10 / 1,000
Verdict: unverifiable (one figure needs checking).
- 256 m x 256 m per region, one simulator process per region: correct and long-documented.
- Avatar caps 100 / 20 / 10 and Homestead 5,000 LI, Openspace 1,000 LI: correct for the post-2019 capacity increase (Homestead was 3,750 and Openspace 750 before early 2019).
- Full region 22,500 LI: needs checking. The 2019 announcement raised private Full regions from 15,000 to 20,000 LI. 22,500 is the figure you get for a Mainland region at the post-2019 rate of 351 LI per 1,024 m2 (64 x 351 = 22,464, rounded). Unless the wiki Land page now gives 22,500 for private estates (possible if a later bonus was added), the precise Full-region figure may be 20,000 for private regions and ~22,500 for Mainland. The brief should state which tier it means.
- "One full region per server CPU core": consistent with public descriptions (historically four simulators per four-core host; on AWS one region per allocated core), but I could not read the wiki Grid page to confirm the exact wording.
Re-fetch: https://wiki.secondlife.com/wiki/Land ; https://wiki.secondlife.com/wiki/Grid ; Linden Lab 2019 land-capacity announcement.

### [3] Simulator targets 45 FPS (~22 ms frame); llGetRegionFPS never exceeds 45.0; script time is cut first under avatar/physics load
Verdict: confirmed (from background knowledge; page not fetched).
- The LSL wiki entry for llGetRegionFPS states the maximum returned value is 45.0; the simulator frame budget is 1/45 s ≈ 22.2 ms, and time dilation reports physics rate relative to real time.
- Script execution runs in the time left after physics, agent updates and network work inside the frame, so it is the first thing starved; this is documented in the Statistics bar wiki page and repeated at Simulator User Group meetings. The claim's wording ("lowest priority, cut first") is a fair summary.
Re-fetch: https://wiki.secondlife.com/wiki/LlGetRegionFPS ; https://wiki.secondlife.com/wiki/Statistics

### [4] Mesh import shipped in Viewer 3.0.0 on 23 August 2011, eight years after launch, gated behind payment info on file and an IP-rights quiz
Verdict: confirmed (from background knowledge; page not fetched).
- Linden Lab's "Mesh is here" announcement and the Viewer 3.0 release were on 23 August 2011. Second Life opened publicly in June 2003, so "eight years" is right.
- Mesh upload required payment information on file and completion of the Mesh IP tutorial/quiz; uploads also carried an L$ fee based on complexity. All correct.
Re-fetch: https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.0.0

### [5] EEP announced 2017, project viewer Oct 2018, official release 20 Apr 2020 (6.4.0.540188); PBR project viewer 2 Dec 2022 (beta grid) to grid-wide week of 27 Nov 2023
Verdict: unverifiable (broad timeline consistent; day-level dates unchecked).
- EEP was first publicly discussed in 2017 and officially released in April 2020 with viewer 6.4.0; the April 2020 release and the ~3-year span are consistent with my knowledge. I cannot confirm the exact 20 April date, the build number 540188, or that the first project viewer landed in October rather than November 2018.
- PBR: a PBR/glTF Materials project viewer limited to Aditi (beta grid) regions appeared in December 2022, and the PBR release viewer (7.0.0.x) plus grid-wide simulator support went out in late November 2023, followed by Linden Lab's "PBR Materials Official Launch" post. Consistent, but the specific days (2 Dec 2022, week of 27 Nov 2023) are not independently confirmed.
- Source note: the claim cites only the 2020 EEP post for both EEP and PBR facts; the PBR facts need their own citation (the brief lists modemworld 2022/12/03 and the LL launch post, which should be attached to this claim).
Re-fetch: https://modemworld.me/2020/04/20/second-life-eep-the-environment-enhancement-project/ ; https://modemworld.me/2022/12/03/ ; https://community.secondlife.com/blogs/entry/14536-second-life-pbr-materials-official-launch

### [6] Sansar (teased 2014) sold to Wookey Project Corp, confirmed 24 Mar 2020; Altberg: could no longer sponsor it financially; TechCrunch called it a disaster that absorbed considerable resources since 2014
Verdict: confirmed (from background knowledge; page not fetched).
- Linden Lab announced the "next generation" platform in June 2014 (named Project Sansar in 2015). The sale to Wookey Project Corp was confirmed on 24 March 2020; Linden Lab kept Second Life and Tilia.
- TechCrunch's coverage (Lucas Matney, March 2020) described the spin-off as a disaster for Linden Lab, which had focused considerable resources on the effort since first teasing it in 2014; that wording matches the claim.
- Altberg's statement that the Lab could not continue to fund Sansar and that it had been a start-up inside a profitable company is consistent with his Lab Gab / press remarks at the time.
- Minor: the cited URL is Road to VR; the TechCrunch quote should cite TechCrunch directly (the brief does so in section 6).
Re-fetch: https://roadtovr.com/sansar-spin-off-linden-lab-refocus-second-life/ ; https://techcrunch.com/2020/03/24/linden-lab-sells-off-sansar/

### [7] Oculus Rift project viewer (4.1.0.317313) suspended 8 July 2016 for not meeting quality standards; no official VR support since
Verdict: confirmed (date and reason; build number unchecked).
- Linden Lab withdrew its Oculus Rift CV1 project viewer in early July 2016, saying it did not meet the Lab's quality standards and that it could not say when or if another would follow. No official VR viewer has shipped since; Linden Lab's VR ambitions moved to Sansar and then ended with its sale.
- I cannot independently confirm the build string 4.1.0.317313; it is plausible for a July 2016 project viewer (release viewers were 4.0.x then).
Re-fetch: https://modemworld.me/2016/07/08/second-life-oculus-rift-support-suspended/ ; https://uploadvr.com/second-life-suspends-oculus-rift-support-vr/

### [8] 9 July 2020 acquisition announcement (Waterfield, Oberwager, Raj Date), conditional on U.S. financial-regulator approval because of Tilia; all main-grid regions on AWS by ~19 Nov 2020
Verdict: confirmed (from background knowledge; page not fetched).
- Linden Research announced on 9 July 2020 that it had agreed to be acquired by an investment group led by J. Randall Waterfield and Brad Oberwager; Raj Date was named as the third investor. Closing was contingent on regulatory approval tied to Tilia's money-transmitter licensing; the deal closed later in 2020 after review.
- The AWS "cloud uplift" of main-grid regions completed in November 2020, with Linden Lab confirming all regions were on AWS around 19-20 November 2020 and remaining back-end services moving into early 2021.
- Source note: the cited July 2020 post covers the acquisition only; the AWS date must be cited to the November 2020 modemworld post listed in the brief.
Re-fetch: https://modemworld.me/2020/07/09/linden-lab-announces-it-is-to-be-acquired/ ; https://modemworld.me/2020/11/19/ll-confirms-second-life-regions-now-all-on-aws/

### [9] Oberwager (Dec 2024): ~$1.3B spent, ~$1.1B paid to creators since 2003, ~$650M/yr economy, ~10% take, $78M creator payouts in 2023 (vs $73M 2020, $65M 2019)
Verdict: unverifiable (headline figures consistent; year-by-year payouts unchecked).
- The GamesBeat (Dean Takahashi) December 2024 article headline "Linden Lab has spent $1.3B building Second Life and paid $1.1B to creators" and its attribution to Oberwager match my knowledge.
- $73M cashed out in 2020 and ~$65M in 2019 are consistent with earlier Linden Lab statements (the 2020 figure appears in the Wikipedia article's economy section). The ~$650M/yr economy size, the ~10% take and the $78M for 2023 are figures I cannot independently confirm from the article text; all are company-reported.
- Precision note: "economy of $650M/yr" and "paid $1.1B to creators" are different measures (gross transaction volume vs. cash-out); the brief should not mix them when computing the Lab's take.
Re-fetch: https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/ ; https://modemworld.me/2024/12/20/second-life-1-3b-to-build-1-1b-paid-to-creators/

## Summary table

| # | Claim | Verdict |
|---|-------|---------|
| 0 | Peak concurrency 2009 vs 2025 | unverifiable (2009 figure consistent; 2025 day-level figures unchecked; wrong URL for 2009 figure) |
| 1 | MAU 500K / 600K / 620K | unverifiable (Oct 2024 consistent; late-2025 figures single-source) |
| 2 | Region size, caps | unverifiable (22,500 LI may be Mainland; private Full = 20,000 since 2019 unless later raised) |
| 3 | 45 FPS, scripts starve first | confirmed (background knowledge) |
| 4 | Mesh 23 Aug 2011, gating | confirmed (background knowledge) |
| 5 | EEP / PBR timelines | unverifiable (broad timeline consistent; exact days/build numbers unchecked) |
| 6 | Sansar sale 24 Mar 2020 | confirmed (background knowledge) |
| 7 | Rift viewer suspended Jul 2016 | confirmed (build number unchecked) |
| 8 | Acquisition 9 Jul 2020; AWS Nov 2020 | confirmed (AWS date cited to wrong URL) |
| 9 | $1.3B / $1.1B / $650M / $78M | unverifiable (headline consistent; detail figures unchecked) |

## Additional findings the brief missed (relevant to designing a successor)

1. The Second Life viewer has been open source (GPL, later LGPL) since January 2007. That, not neglect alone, is why Firestorm and 15+ third-party viewers exist; OpenSimulator (2007 onward) re-implemented the server side of the same protocol and added Hypergrid teleports between independent grids. A successor that wants community clients without ceding the UI should study this precedent: an open protocol plus a well-funded first-party client.
2. Philip Rosedale returned to Linden Lab as a strategic advisor in January 2022, with his company High Fidelity investing cash, patents and staff into Linden Lab after High Fidelity's own virtual-world product (2016-2019) failed to find users. Two Rosedale-led successors (High Fidelity, and indirectly Sansar) failed on the same user-acquisition problem; graphics or VR were not the differentiator.
3. The dominant performance problem residents experience is client-side rendering of unoptimized user-made avatars (mesh bodies, attachments), not region simulation. Linden Lab's main mitigation was Avatar Rendering Complexity / "jelly dolls" (2016), which hides heavy avatars on the viewer. A successor needs enforced per-asset budgets (triangle, texture, draw-call) at upload time, not a post-hoc client cutoff.
4. Concurrency numbers include scripted agents. Linden Lab moved in 2024 to require bots to be flagged as scripted agents and restricted bots gathering data on parcels; any comparison of 2009 vs 2025 concurrency is bots-confounded, and a successor should publish human-only metrics from day one.
5. Content-generation layering is worse than the brief states: besides prims, sculpts (2007), mesh (2011), normal/specular materials (2013), Bakes on Mesh (2019), and PBR (2023), the avatar itself still runs on the 2003 skeleton with "Bento" bones added in 2016, and the mesh-body ecosystem (third-party bodies with proprietary rigging) is the main lock-in and the main migration obstacle for any successor. A migration path must solve avatar bodies and rigging, not just static mesh.
6. Script limits are hard-coded per script (64 KB memory under Mono) with no per-region scheduling fairness beyond the frame-wide starvation rule; this is why creators ship dozens of small scripts per object and why "script lag" scales with object count. A successor should budget by owner/parcel rather than by frame leftover.
7. Linden Lab's own 2025 funnel data (mobile + streaming) is the first time the company has quantified access as the constraint; however, Project Zero streaming was sold as prepaid time blocks, implying the server-side rendering cost per hour exceeded what a free tier could absorb. A successor planning server-side rendering as a first-class tier needs a unit-economics model for GPU hours per user hour.
