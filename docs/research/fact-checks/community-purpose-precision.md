# Precision check: "What gives virtual communities purpose" (community-purpose.md)

Checker run: 2026-10-09. Lens: precision (numbers, dates, names, attributions; does the cited source support the claim).

## Environment limitation (read first)

No claim in this report was verified against a live primary source.

- WebFetch failed with `getaddrinfo ENOTFOUND` on all ten cited hosts (danielvoyager.wordpress.com, eveonline.com, hci.stanford.edu, virtualability.org, adl.org, techcrunch.com, burningman.org, ryanschultz.com, cesifo.org). This is the same DNS failure the researcher reported in their method note.
- WebSearch was refused on every query: the per-turn search budget (200 calls, shared by all agents) was already used up before this checker ran.
- A curl probe via the agent proxy was blocked by the permission classifier. I did not attempt any other workaround.

What I could use instead: (a) sibling research briefs and verify reports in the same scratchpad, which were produced by other agents from their own search runs and so are weakly independent of this brief; (b) arithmetic consistency inside the brief; (c) the checker's own background knowledge, which is clearly labelled "prior knowledge" and is not evidence. Verdicts are therefore mostly **unverifiable**; "corrected" is used only where the problem is visible without fetching (wrong attribution, internal arithmetic, or a naming error I am confident about). The whole set should be re-run when web access is restored.

## Claim-by-claim

### [0] SL concurrency: all-time peak 88,220 on 29 Mar 2009; 2024 max 53,016 (19 Feb 2024); 2025 peaks ~47-49K
Verdict: **unverifiable** (partly corroborated in-sandbox; one figure disputed by a sibling brief).
- Corroboration: `research/sl-history-stagnation.md` independently reports "the fan log's highest single reading is 88,220 on 29 March 2009" from a different Daniel Voyager URL, and Wikipedia's rounded "88,200 in Q1 2009". Two agents, two search runs, same figure.
- Dispute: the same sibling brief (and `verify/sl-history-stagnation-precision.md`) report a 2025 high of 49,798 on 24 Mar 2025 and **October 2025 peaks of 42,000-45,000**. The researcher's "2025 peaks ran roughly 47,000-49,000 and were flat" therefore overstates the back half of 2025; the Daniel Voyager "through 2025 so far" post is dated 20 Oct 2025 and most likely shows a decline from the spring. Treat "flat" as unsupported.
- Precision caveats the brief already half-makes: the counter includes scripted agents (bots); Linden Lab only formalised bot registration in the 2020s, so 2009 and 2025 readings are not comparable. 53,016 on 19 Feb 2024 could not be checked.
- The 88,199 Engadget figure for the same period could not be checked.

### [1] Regions: 26,785 in early Nov 2025 (17,589 private + 9,196 Linden); >28,000 mid-2024; private estates net -270 (~1.5%) in 2024
Verdict: **unverifiable**, with an internal-consistency problem the researcher should resolve.
- Arithmetic check: 17,589 + 9,196 = 26,785. Consistent.
- Inconsistency: 270 is ~1.5% of ~18,000, so private estates were ~18,000 at the start of 2024 and ~17,730 at the end. The brief also says Linden-owned regions **grew** by 211 in 2024. Net change in 2024 is therefore about -59 regions. That cannot be reconciled with "crossed 28,000 in May-June 2024" and "26,785 in November 2025" unless (a) ~1,100 regions vanished in 2025 alone (the brief's own 2025 private-estate figures imply only ~140), or (b) the mid-2024 28,000 figure counted temporary regions (SL21B, Linden Homes expansion, event sims) or used a different counting basis than the November 2025 figure. Most likely (b). The brief's "decline was in region count, not acreage" conclusion is built on this comparison and should be re-derived from one consistent series.
- No sibling brief reports region counts, so no corroboration.

### [2] EVE CSM: CSM7 59,109 votes (16.63%, record); CSM20 (2025) 49,870 votes from 55 candidates, second-highest ever
Verdict: **unverifiable**.
- Prior knowledge: CSM7 (2012) being the record at 59,109 votes / 16.63% matches recall, as does CSM6 49,096 / 14.25%. The CSM20 figure (49,870) could not be checked; if correct it would indeed be the second-highest raw total in the brief's own series (next is CSM6 49,096), so "second-highest ever" is at least consistent with the brief's own numbers.
- Precision note: the researcher's own open question is the right one. CCP stopped publishing turnout percentages after the early councils, so raw vote totals across 2012 and 2025 are not comparable as participation rates; eligibility rules (minimum account age, Omega status) also changed between councils.
- No sibling brief covers the CSM.

### [3] Lin et al. (ICWSM 2017): 45M comments, 10 defaulted subreddits; linguistic fingerprints retained; higher moderation -> higher scores, fewer complaints
Verdict: **unverifiable**.
- Prior knowledge: the paper is "Better When It Was Smaller? Community Content and Behavior After Massive Growth" by Zhiyuan Lin, Niloufar Salehi, Bowen Yao, Yiqi Chen and Michael Bernstein, ICWSM 2017; the 45-million-comment / ten-subreddit / May-2014 default-set design matches. The headline finding (communities kept distinctive language; behaviour shifted toward concentrating activity on fewer posts; complaints rose) matches recall. The specific moderation result ("significantly higher average scores and lower complaint levels" in high-moderation subreddits) is the part I am least able to confirm; the direction is plausible but the brief states it with more certainty than I can support. Verify the exact wording before using it as a design justification.

### [4] Virtual Ability: founded 2007; 501(c)(3) Apr 2008; Island opened Aug 2008; first Linden Prize 2009; 850+ members (2014), 1,300+ (2025)
Verdict: **unverifiable** (partly corroborated in-sandbox).
- Corroboration: `research/sl-ux-onboarding-governance.md` independently reports "Virtual Ability, Inc. (Alice Krueger, 'Gentle Heron', founded 2007) won the first Linden Prize in 2009" and dates the Linden Prize to 2009-2010 at US$10,000.
- Precision note (prior knowledge): the 2009 Linden Prize was **shared** between Virtual Ability, Inc. and Studio Wikitecture; "won the first Linden Prize" is true but should say "co-won". Membership counts (850+ in 2014, 1,300+ in 2025) are self-reported on virtualability.org and could not be checked.

### [5] ADL: 2022 survey 86% harassed, severe 77% (up from 71%); 2019 survey 19% stopped playing certain games
Verdict: **corrected** (attribution).
- The URL cited for the 2022 figures (`.../two-thirds-of-us-online-gamers-have-experienced-severe-harassment-new-adl-study`) is the press release for ADL's **2019** "Free to Play?" report; its slug refers to that report's finding that about two-thirds (65%) of adult gamers experienced severe harassment. A 2019 press release cannot contain 2022 survey results. The 2022 figures (86% any harassment; 77% severe, up from 71% in 2021; 66% of teens, 70% of pre-teens) belong to ADL's "Hate Is No Game: Hate and Harassment in Online Games 2022" report and should be cited to that report page.
- Prior knowledge on the numbers themselves: 86%/77%/71% and the teen/pre-teen 66%/70% match my recollection of the 2022 report. The 2019 "19% stopped playing certain games entirely / 23% avoided certain games" figures are consistent with "Free to Play?". None of this was checked against the live page.
- The "~67 million people" extrapolation in the brief body is ADL's own, derived from its gamer-population estimate; it is not a count.

### [6] Club Penguin: 12M users at 2007 Disney purchase (up to $700M); ~200M registered by 2013; shut 30 Mar 2017; CP Rewritten 11M+ users, police shutdown 13 Apr 2022
Verdict: **unverifiable**.
- Prior knowledge: Disney bought New Horizon Interactive in August 2007 for US$350M plus up to US$350M in earn-outs (hence "up to $700M"); "12 million activated users / 700,000 paying subscribers" was the figure at the time; 200M+ registered accounts by 2013; shutdown announced 30 Jan 2017 and executed at the end of March 2017 (sources vary between 29 and 30 March depending on time zone); Club Penguin Rewritten taken down 13 April 2022 after City of London Police arrests, with press reports citing "over 11 million" registered users (a self-reported figure). All consistent with the claim.
- Attribution note: the TechCrunch 2017 article can support only the shutdown announcement and acquisition background; the 2022 CPR facts rest on the Vice/Wikipedia sources the brief lists elsewhere. Fine as the brief cites them too, but the key-claim line attributes everything to TechCrunch.

### [7] BURN2: burned the Man in SL since 2003; only virtual regional among 100+; year-round region "Deep Hole"; five main events a year
Verdict: **corrected** (naming/date conflation; prior knowledge, high confidence).
- The Second Life burn began in **2003 as "Burning Life"**, created and run by Linden Lab. It was handed to the community and became **BURN2 in 2010**, which is also when it became an officially sanctioned Burning Man Regional. "BURN2 has burned the Man since 2003" conflates the two eras: the event dates from 2003, the organisation and the Regional status from 2010. For the design brief this distinction matters: the ritual survived an operator-to-community handover, which is the lesson.
- Corroboration for the 2003 start: `research/sl-ux-onboarding-governance.md` lists "Burning Life / Burn2 (since 2003)".
- "Only virtual event among 100+ sanctioned regionals", "Deep Hole" as the year-round region name, and "five main events a year" could not be checked; all are plausible (Deep Hole is a real Black Rock Desert place name reused by BURN2). The burningman.org/?p=7024 link is a bare WordPress post ID and could not be resolved to a title.

### [8] SL20B (22 Jun-11 Jul 2023): 60 regions, 24 Shop & Hop + 36 community festival, 425+ performers on four stages
Verdict: **unverifiable**.
- Arithmetic check: 24 + 36 = 60. Consistent with the ryanschultz.com URL slug ("sixty-sims-june-22nd-july-11th-2023"), which is the only part of that source visible here.
- Corroboration: `research/sl-ux-onboarding-governance.md` confirms SL20B ran in June 2023 but gives no region or performer counts. The "425+ live performers, four stages" figures appear to come from Linden Lab's own press release (also cited in the brief) and are promotional, not audited. No attendance figure exists, as the brief correctly notes.

### [9] Castronova (2001): 3,600-user survey + eBay sales; Norrath hourly wage $3.42; GNP per capita between Russia and Bulgaria; platinum piece $0.0107
Verdict: **unverifiable** (consistent with prior knowledge; one adjacent statement in the brief is wrong).
- Prior knowledge: CESifo Working Paper 618 (December 2001), "Virtual Worlds: A First-Hand Account of Market and Society on the Cyberian Frontier", survey of 3,619 EverQuest players (the brief's "3,600" is a fair rounding), hourly wage US$3.42, platinum piece at US$0.0107 (1.07 cents), GNP per capita US$2,266, "77th richest country, between Russia and Bulgaria". The key claim matches.
- Error in the brief body (section 1, Castronova paragraph, not in the key-claim list): it says the "$2,266 and '77th largest economy'" figure "is dated 2005 by Guinness, so the two are not the same measurement". That is wrong. $2,266 and the 77th-place ranking are in the **2001 paper itself**; they are the same measurement as the $3.42 wage. Guinness merely re-published it later. The researcher should delete the "not the same measurement" sentence.

## Summary table

| # | Claim | Verdict | Key note |
|---|-------|---------|----------|
| 0 | SL concurrency 88,220 / 53,016 / 47-49K | unverifiable | 88,220 on 29 Mar 2009 corroborated by sibling brief; "2025 flat at 47-49K" contradicted by sibling's Oct 2025 42-45K |
| 1 | Regions 26,785 / 28,000 / -270 | unverifiable | Components sum correctly; 28,000 mid-2024 vs net -59 in 2024 vs 26,785 Nov 2025 do not reconcile; likely mixed counting bases |
| 2 | CSM7 59,109 / CSM20 49,870 | unverifiable | Consistent with recall and with brief's own series; turnout % no longer published |
| 3 | Lin et al. ICWSM 2017 | unverifiable | Authors/venue/scale match; moderation->scores result stated more firmly than I can confirm |
| 4 | Virtual Ability dates/members | unverifiable | 2007 founding and 2009 Linden Prize corroborated; prize was shared with Studio Wikitecture |
| 5 | ADL 2022 86% / 77% / 71%; 2019 19% | corrected | Cited URL is the 2019 press release; 2022 figures need the "Hate Is No Game 2022" report |
| 6 | Club Penguin 12M / $700M / 200M / 2017 / CPR 11M | unverifiable | Consistent with recall; TechCrunch can only support the 2017 shutdown part |
| 7 | BURN2 since 2003 | corrected | Burning Life (Linden-run) 2003-2009; BURN2 name and Regional status from 2010 |
| 8 | SL20B 60 regions, 425 performers | unverifiable | 24+36=60 checks; performer count is Linden PR |
| 9 | Castronova $3.42 / $0.0107 / Russia-Bulgaria | unverifiable | Matches the 2001 paper; brief's "$2,266 is a 2005 Guinness measurement" aside is wrong |

## Sources consulted

Live sources: none reachable (see limitation above). In-sandbox:
- /tmp/claude-0/-home-user-nolife/d4696900-d73b-5efa-ba36-41eadc9a535f/scratchpad/research/community-purpose.md (the brief)
- /tmp/claude-0/-home-user-nolife/d4696900-d73b-5efa-ba36-41eadc9a535f/scratchpad/research/sl-history-stagnation.md (88,220 / 29 Mar 2009; 2025 peaks)
- /tmp/claude-0/-home-user-nolife/d4696900-d73b-5efa-ba36-41eadc9a535f/scratchpad/verify/sl-history-stagnation-precision.md and -refute.md (2025 concurrency band, bot caveat)
- /tmp/claude-0/-home-user-nolife/d4696900-d73b-5efa-ba36-41eadc9a535f/scratchpad/research/sl-ux-onboarding-governance.md (Burning Life 2003, Virtual Ability 2007, Linden Prize 2009, SL20B June 2023)

Cited-but-unreached primary URLs: the ten listed in the task; all should be fetched on a re-run.
