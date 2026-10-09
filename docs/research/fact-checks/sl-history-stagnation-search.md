# Search verification: Second Life history and technical stagnation

Run date: 2026-10-09. Checker: independent fact-checker with live WebSearch.

## Method note

- 12 WebSearch calls used (hard cap reached; 10 standard, 2 extended with domain filters). No page fetching was possible (WebFetch/curl blocked in sandbox), so every verdict rests on the search engine's quoted extracts of the cited pages, not full reads.
- Claims 3 (45 fps / script starvation) and 4 (mesh, Viewer 3.0.0, 23 Aug 2011) were not searched because the budget was spent on numeric/dated/2025-26 claims; they are marked unverifiable / prior knowledge.
- The two earlier checkers had no web access; their notes were treated as hypotheses, not evidence. Several of their guesses (e.g. that Homestead LI rose to 5,625 in 2023; that the 22,500 figure is a 2019/2023 increase) were NOT supported by the sources found.

## Verdicts by claim index

### 0. Peak concurrency 88,200 (Q1 2009) / 88,220 (29 Mar 2009); 2025 high 49,798 (24 Mar 2025); Oct 2025 peaks 42-45K
Verdict: confirmed.
- Daniel Voyager (2025-10-20): "The highest peak for the Second Life user concurrency was when it reached 49,798 on 24th March 2025"; all-time high "88,220 on 29th March 2009 at 1:28pm SLT". Wikipedia: 88,200 in Q1 2009.
- Monthly maxima 2025 (Voyager 2025-12-31): Jan 49,375 (27 Jan), Feb 48,222, Aug 45,270 (low), Oct 46,865 (26 Oct), Nov 47,838, Dec 47,929. The blog calls 2025 "a flat year".
- Nuance: the "October 2025 daily peaks averaging 42,000-45,000" statement could not be checked from extracts (October's monthly maximum was 46,865, which is consistent with daily peaks averaging below that). Voyager's monthly figures differ slightly between posts (July 45,596 vs 45,333). All numbers come from one blog using the SL Grid Survey; bot-inflation caveat stands.
- Extra context: 2024 peak 53,016 (19 Feb 2024); post-2020 peak 60,068 (20 Apr 2020, pandemic); 2026 peak to date 48,802 (1 Apr 2026).
- Sources: https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/ ; https://danielvoyager.wordpress.com/2025/12/31/second-life-monthly-maximum-concurrency-peaks-for-2025/

### 1. MAU ~500K Oct 2024, 600K Oct 2025, 620K Dec 2025; new users half mobile / half Project Zero
Verdict: confirmed (single-source chain: Oberwager -> New World Notes -> Voyager).
- Voyager 2025-10-26 quotes Oberwager via NWN: "we're now at 600,000 MAU", up from 500,000 in 2024, and credits new users "roughly half and half via the mobile app and Project Zero, the streaming option".
- Voyager 2025-12-19: "Second Life Now At 620,000 Monthly Active Users"; original interview not located in extracts.
- Voyager 2024-10-30 / NWN Nov 2024: ~500,000 MAU; DAU "significantly less"; Oberwager: "our DAU has gone down, that's very concerning".
- Correction of framing: the "long-running ~600,000" baseline is Wagner James Au's own estimate (relayed since 2018), not a company figure.
- Unreconciled: Voyager (May 2026) gives 1.15M-1.45M "unique users who log in at least once during a 30-day period", a different and much larger measure than the company's 600-620K MAU. Definitions are not published.
- Sources: https://danielvoyager.wordpress.com/2025/10/26/ ; https://danielvoyager.wordpress.com/2025/12/19/second-life-now-at-620000-monthly-active-users/ ; https://nwn.blogs.com/nwn/2024/11/linden-lab-sl-future-philip-rosedale-brad-oberwager.html ; https://danielvoyager.wordpress.com/2026/05/11/second-life-daily-user-concurrency-update-10th-may-2026/

### 2. 256 m region, one simulator per core; Full 100 av / 22,500 LI; Homestead 20 / 5,000; Openspace 10 / 1,000
Verdict: corrected (figures right; era/scope labelling wrong in earlier checks).
- SL wiki Land page: Full region "up to 100 avatars per server host CPU core" and 22,500 LI; Homestead 5,000 LI / 20 avatars (also LL knowledge base); Openspace 1,000 LI / 10 avatars.
- The increase was announced November 2016 (not 2019 or 2023): Mainland Full 15,000 -> 22,500; Homestead 3,750 -> 5,000; Openspace 750 -> 1,000. Private-estate Full regions were set at 20,000 LI with a paid upgrade to 30,000.
- The earlier checker's "Homestead 5,625 post-2023" figure appears in no source found; treat 5,000 as current. The 22,500 figure is the Mainland value; private Full regions are 20,000 (30,000 with fee). The brief should say so.
- Sources: https://wiki.secondlife.com/wiki/Land ; https://modemworld.me/2016/11/03/lab-reveals-li-prim-allowance-changes-in-second-life-in-full ; https://community.secondlife.com/knowledgebase/english/homestead-regions-r1033/

### 3. 45 fps simulator frame, scripts starved first
Verdict: unverifiable, not searched (budget). Prior knowledge of both earlier checkers and this checker: consistent.

### 4. Mesh in Viewer 3.0.0, 23 Aug 2011, payment-info + IP quiz gate
Verdict: unverifiable, not searched (budget). Prior knowledge: consistent.

### 5. EEP: 2017 -> Oct 2018 project viewer -> 20 Apr 2020 (6.4.0.540188); PBR: project viewer 2 Dec 2022 -> grid-wide week of 27 Nov 2023
Verdict: corrected.
- EEP: confirmed. Modem World: viewer 6.4.0.540188 dated 15 Apr, promoted to release Monday 20 Apr 2020.
- PBR project viewer: the earliest release found is glTF/PBR Materials project viewer 7.0.0.578161 on 14 Feb 2023 (Aditi-only). The 2 Dec 2022 date was not confirmed from extracts; a December 2022 Modem World item exists but the extract did not show it as a viewer release. State "Aditi project viewer by early 2023 (Dec 2022 at earliest, unconfirmed)".
- PBR grid-wide: confirmed with day-level precision. Deployed to the SLS Main channel Tuesday 28 Nov 2023; viewer 7.0.1.6894459864 (dated 17 Nov) promoted to release the same day. "Week of 27 Nov 2023" is correct.
- 2017 announcement and October (vs November) 2018 project viewer: not checked.
- Sources: https://modemworld.me/2020/04/27/2020-viewer-release-summaries-week-17/ ; https://modemworld.me/2023/11/17/2023-week-46-sl-ccug-meeting-summary-pbr-status-current-release-plan/ ; https://modemworld.me/2023/11/28/ ; https://community.secondlife.com/blogs/entry/14536-second-life-pbr-materials-official-launch

### 6. Sansar sold to Wookey, confirmed 24 Mar 2020; Altberg "could no longer sponsor"; TechCrunch "disaster", "considerable resources"
Verdict: confirmed (core facts); quotations unverified.
- Linden Lab press release Tuesday 24 Mar 2020 confirmed the sale to Wookey Project Corp (San Francisco startup with almost no public footprint); rumours reported 21 Mar. Wookey took "full and total ownership" and contracts Tilia for token issuance/redemption; Second Life and Tilia stayed with LL; many Sansar staff moved to Wookey.
- TechCrunch article exists: "Second Life-maker calls it quits on their VR follow-up" (techcrunch.com/2020/03/24/...). The "disaster" / "considerable resources" wording and the Altberg financial-sponsorship quote did not appear in extracts; do not reproduce as verbatim quotes.
- Sources: https://roadtovr.com/sansar-spin-off-linden-lab-refocus-second-life/ ; https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/ ; https://techcrunch.com/2020/03/24/second-life-maker-calls-it-quits-on-their-vr-follow-up-sansar

### 7. Oculus Rift project viewer 4.1.0.317313 suspended 8 Jul 2016, quality standards, no official VR since
Verdict: confirmed.
- Modem World: viewer 4.1.0.317313 released Friday 1 Jul 2016 (Windows only, DK2 and CV1); BUG-20130 filed 5 Jul; Oz Linden: it "didn't meet our standards for quality" and LL "can't say at this point when or even if we may release another Project Viewer". Withdrawal date given as 6 Jul in one roundup and 8 Jul in the headline post; say "6-8 July 2016". UploadVR called the suspension indefinite. Nothing found contradicting "no official VR support since".
- Sources: https://modemworld.me/2016/07/08/second-life-oculus-rift-support-suspended/ ; https://modemworld.me/2016/07/02/second-life-oculus-rift-viewer-4-1-0-317313/ ; https://uploadvr.com/second-life-suspends-oculus-rift-support-vr/

### 8. (Claim index 8 in ledger) Acquisition 9 Jul 2020 (Waterfield, Oberwager, Raj Date), Tilia regulatory condition; AWS complete ~19 Nov 2020
Verdict: unverifiable, not searched (budget). Prior knowledge of all checkers: consistent; the Raj Date naming and the exact AWS completion date remain unchecked.

### 9. (Claim index 9 in ledger) $1.3B spent, $1.1B to creators, ~$650M/yr economy, ~10% take, $78M (2023) / $73M (2020) / $65M (2019)
Verdict: confirmed for the headline figures; the annual series is unverified.
- $1.3B invested and $1.1B cumulative creator earnings: on LL's own secondlife.com/create page (links to GamesBeat). Figures were given by Oberwager at a 6 Dec 2024 Blogger Town Hall, embargoed until Dean Takahashi's VentureBeat/GamesBeat piece of 20 Dec 2024. Economy "about $650 million a year"; LL "shares 90% of transactions with creators and only takes a 10% cut".
- $78M (2023), $73M (2020), $65M (2019): not found in any extract. Found instead: $55M cashed out in 2009 (+11% on 2008); "over $60 million" redeemed per Ebbe Altberg (Hypergrid Business, May 2015, referring to the prior year). The VentureBeat piece reportedly compared 2023 creator payouts with Roblox, so the $78M figure may well be there, but it is unconfirmed. Label as prior knowledge.
- Sources: https://modemworld.me/2024/12/20/ ; https://secondlife.com/create ; https://www.hypergridbusiness.com/2015/05/ebbe-sl-users-cashed-out-60-mil-last-year/ ; https://venturebeat.com/business/second-lifes-economy-grows-65-to-567m

Note on indexing: the ledger's "claims" array has 10 entries (0-9); the brief's numbering above follows the array order exactly.

## Additional findings (new, relevant to designing a successor)

1. Project Zero (browser/streamed viewer) is being shut down: Modem World, 22 Apr 2026, "Linden Lab announces Project Zero to end". The brief treats Project Zero as one of the two halves of the 2025 new-user funnel; that half has since been discontinued. The MAU rebound story needs re-examining against this.
2. Funnel vs retention: at the September 2025 LL Zoom call, the Lab said mobile + Project Zero could reach ~10x the people trying SL, but "only around 7% of those coming into SL are actively being retained" (Modem World). Acquisition was solved; retention was not.
3. DAU is declining even as MAU rose: Oberwager (Nov 2024): "our DAU has gone down, that's very concerning". A successor should publish DAU/MAU ratio, not MAU alone.
4. MAU definitions are unreconciled: Voyager (May 2026) estimates 1.15M-1.45M unique 30-day logins vs the company's 600-620K MAU. Any successor metric must define "active" (session length threshold, bots excluded).
5. Concurrency context: pandemic peak 60,068 (20 Apr 2020); 2024 peak 53,016 (19 Feb 2024); 2025 peak 49,798; 2026 peak to date 48,802 (1 Apr 2026). The concurrency trend 2020-2026 is slowly downward while reported MAU rose, consistent with shorter/lighter mobile and streamed sessions.
6. Land-capacity tiers: the last LI increase was November 2016 (Mainland Full 22,500; private Full 20,000 with paid 30,000 upgrade; Homestead 5,000; Openspace 1,000). No capacity-tier change has been found since; the content budget per region has been frozen for a decade.
7. Sansar sale terms: Wookey took all Sansar staff who stayed and contracts Tilia for token handling; Sansar users kept accounts. Linden Lab kept Tilia, i.e. it retained the money-transmission asset and shed the world. For a successor, the payments/compliance layer is the asset that survives product failure.
8. MFA became mandatory on all SL web properties (including Project Zero) in March 2025, a late security modernisation relevant to a successor's baseline.
