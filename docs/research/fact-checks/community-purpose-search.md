# Search verification: community-purpose

Checker with live web search, run 2026-10-09. Ledger: `analysis/ledger-community-purpose.json` (10 claims).

**Method note.** 12 WebSearch calls used (the hard cap): 10 standard, 2 extended. Page fetching (WebFetch/curl) is blocked in this sandbox, so every verdict rests on the quoted extracts the search engine returned, not on full pages. Where an extract did not show a specific number, that number is labelled prior knowledge. Prior "checks" in the ledger were made without search and were treated as hypotheses, not evidence.

## Verdict table

| # | Claim (short) | Verdict | Searched | Key evidence |
|---|---|---|---|---|
| 0 | SL concurrency: 88,220 (29 Mar 2009); 53,016 (19 Feb 2024); 2025 ~47-49k | corrected | yes (2) | 2025 max was 49,798 on 24 Mar 2025; monthly peaks 45,270-49,798; "flat year, nothing over 48k after Q1". 2009 and Feb-2024 figures not found in extracts. |
| 1 | 26,785 regions Nov 2025 (17,589 / 9,196), >28,000 mid-2024, -270 private in 2024 | confirmed | yes (2) | Cited post confirms all Nov 2025 counts and the >28,000 mid-2024 point; -270 sub-claim not in extracts. |
| 2 | CSM7 59,109 / 16.63% record; CSM20 49,870 from 55 candidates, second-highest | confirmed | yes | CCP post 14 Nov 2025: 55 candidates, 49,870 voters, "eclipsed only by CSM 7". |
| 3 | Lin et al. ICWSM 2017, 45M comments, 10 subreddits, moderation effect | confirmed | yes | AAAI/Stanford abstract matches every element. |
| 4 | Virtual Ability: 2007, 501(c)(3) Apr 2008, island Aug 2008, first Linden Prize 2009, 850+/1,300+ | corrected | yes | Co-won 2009 prize with Studio Wikitecture ($10k each); current site says "over 1,000 members"; months partly unverified. |
| 5 | ADL 2022 86% / 77% (from 71%); 2019 19% quit games | corrected | yes | Numbers hold; 19% is of harassed gamers (18-45), and 2022 figures are mis-cited to the 2019 press release. |
| 6 | Club Penguin: 12M users / up to $700M 2007; 200M by 2013; closed 30 Mar 2017; CPR 11M+, police shutdown 13 Apr 2022 | confirmed | yes | $700M 2007, 11M+ accounts, 13 Apr 2022 PIPCU shutdown, 3 arrests 12 Apr confirmed; 12M / 200M / 30 Mar not in extracts. |
| 7 | BURN2 since 2003, only virtual regional of 100+, Deep Hole, five main events/yr | corrected | yes | Deep Hole and "only virtual regional / only one allowed to burn the Man" confirmed (self-description); no source dates BURN2 to 2003; "five events" not found. |
| 8 | SL20B: 60 regions, 24 Shop & Hop + 36 festival, 425+ performers, four stages | confirmed | yes | Official blog: 480+ merchants across 24 regions; Schultz: 36 festival sims, "over 425 performers on four stages". 425+ is Schultz-only, not a Linden release. |
| 9 | Castronova 2001: 3,600 survey, $3.42/hr, Russia-Bulgaria, PP $0.0107 | confirmed | yes | CESifo WP 618 abstract gives $3.42, $0.0107, Russia-Bulgaria; survey size and "platinum piece" wording not in abstract. |

## Claim-by-claim notes

### 0. Second Life concurrency figures: corrected (2025 part)
- Source blog's own 2025 round-up (https://danielvoyager.wordpress.com/2025/12/31/second-life-monthly-maximum-concurrency-peaks-for-2025/): yearly maximum 49,798 on 24 March 2025 (a March post says 23 March); monthly maxima Jan 49,375, Feb 48,222, Apr 47,830, Jun 45,719, Jul 45,596, Aug 45,270, Sep 46,356, Oct 46,865, Nov 47,838, Dec 47,929. Blog: "a flat year ... no major high peaks over 48,000 since the start of the year". So "roughly 47,000-49,000" should read "roughly 45,000-49,800 (max 49,798, 24 Mar 2025)".
- Not found: 88,220 / 29 Mar 2009 and 53,016 / 19 Feb 2024 (two searches). A forum post citing the blog gives only ranges (2009/10 max ~85-88k; 2022 max ~46-53k; https://community.secondlife.com/forums/topic/496221-question-for-lindens/page/4/). Prior knowledge keeps these plausible (Engadget 88,199 for the same week).
- Data caveats surfaced: forum thread (https://community.secondlife.com/forums/topic/529998-2025-second-life-concurrency-statistics-are-out/) says the public counter stuck at 39,122 in summer 2024 and may have been turned off; the Dec 2025 post says the API feeds were broken and December "is missing a lot of data".
- 2026: as of 24 Jan 2026 the peak had "only just surpassed 47,000", daily max 41-46k (https://danielvoyager.wordpress.com/2026/01/26/second-life-daily-user-concurrency-as-of-24th-january-2026/).

### 1. Region counts: confirmed
- https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/ (data 2 Nov 2025, from the independent Grid Survey): 26,785 total; 17,589 private estates; 9,196 Linden-owned; total "passed 28,000 in mid-2024".
- Comparison points in the same post: 5 Jan 2025 = 27,769 (17,939 / 9,830); 22 Jun 2025 = 27,731 (17,757 / 9,974). The 2025 drop is mostly Linden-owned (-634, retiring first-generation Linden Homes), not private estates (-350). That resolves the earlier checker's "numbers do not reconcile" concern and weakens the brief's cost-driven framing for 2025.
- The "-270 (~1.5%) private estates during 2024" sub-claim lives in the Jan 2025 post and was not in any extract: unverified.
- Later: 26,858 on 25 Jan 2026 (blog tag page); 27,239 on 8 Jul 2026 (forum profile, unverified).

### 2. EVE CSM: confirmed
- https://www.eveonline.com/news/view/heres-your-csm-20 (14 Nov 2025): "55 candidates", "49,870 voters", "second highest voter turnout ever recorded, eclipsed only by CSM 7". Wright-STV, up to 10 ranked candidates; two members (Mick Fightmaster, Val Auroris) appointed from 11th-20th places.
- Wording: 49,870 is voters/ballots, not votes. CSM7's 59,109 / 16.63% was not searched (budget); the official "eclipsed only by CSM 7" corroborates it as the record. No turnout percentage is published for CSM20.

### 3. Eternal September study: confirmed
- https://ojs.aaai.org/index.php/ICWSM/article/view/14884 (Vol 11, pp 132-141). Abstract: >45M comments, 10 subreddits added to the default set; language does not converge to Reddit-wide norms; temporary dip then recovery in scores; complaints do not rise; "strong moderation also helps keep upvotes common and complaint levels low"; attention clusters on fewer posts.

### 4. Virtual Ability: corrected
- https://virtualability.org/history/: name chosen Jan 2008; 501(c)(3) received 2008 (month not in extract); Virtual Ability Island opened August 2008 (with Alliance Library System); 2009 took over Healthinfo Island and Cape Able.
- AFP 1 May 2009 (https://www.solardaily.com/reports/Virtual_mobility_for_disabled_wins_Second_Life_prize_999.html): Virtual Ability and Studio Wikitecture named co-winners of the first-ever Second Life prize, $10,000 each. So "won the first Linden Prize" should be "co-won" (prize name from prior knowledge; extract calls it "the first-ever Second Life prize").
- Membership: https://virtualability.org/about-us says "over 1,000 members from six continents". No extract gave 1,300+ (2025) or 850+ (2014).
- 2026: L$250,000 "Mobility Without Limits" wheelchair design contest funded by Linden Lab (https://modemworld.me/2026/07/28/virtual-ability-launches-l250000-wheelchair-design-contest-in-second-life/).

### 5. ADL harassment figures: corrected (denominator and attribution)
- 2019 PDF (https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf): "23 percent of online multiplayer gamers who have been harassed avoid certain games ... while 19 percent have stopped playing certain games altogether"; only 27% said harassment had no impact. Denominator = harassed gamers aged 18-45.
- 2022: House letter to the FTC citing ADL's Dec 2022 report (https://trahan.house.gov/UploadedFiles/Letter_to_FTC_on_multiplayer_online_gaming_industry.pdf): 86% any harassment, 77% severe. ADL's own page (https://www.adl.org/resources/report/hate-no-game-hate-and-harassment-online-games-2022) extract showed only "fourth consecutive year" of increases; "up from 71%" is prior knowledge (2021 report).
- Attribution: the ledger's URL is the 2019 press release; the 2022 figures should cite the 2022 report page.

### 6. Club Penguin: confirmed
- Input/Inverse (https://www.inverse.com/input/gaming/club-penguin-rewritten-disney-london-police-shutdown-arrests): Disney purchased Club Penguin in 2007 "for a whopping $700 million"; Rewritten "boasted more than 11 million accounts". NME/WDWNT: shut 13 April 2022 by City of London Police (PIPCU) under a Disney copyright investigation; three arrested 12 April; operators handed the site to police. Destructoid says "over ten million users".
- Not in extracts (prior knowledge): 12M users at purchase, ~200M by 2013, 30 March 2017 closure date (extracts say only "closed in 2017").

### 7. BURN2: corrected
- https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/ and modemworld.me 2015: "BURN2 occupies a region in Second Life year-round called Deep Hole"; "the only virtual world event out of more than 100 real world Regional groups and the only regional event allowed to burn the man"; "the first sanctioned Burning Man regional in the virtual world"; "Burning Man has always had a presence in Second Life since its beginning, BURN2 is the latest incarnation".
- No extract dates BURN2 to 2003. Prior knowledge: Burning Life (Linden Lab) 2003-2009; BURN2 community-run and sanctioned from 2010. "Five main events a year" not found; sources say "events year around, culminating in an annual major festival ... in the fall" (12 regions in 2021, 4 in 2016). Latest extract is 2021; 2026 status unchecked.

### 8. SL20B: confirmed, with a sourcing fix
- Official blog (https://community.secondlife.com/blogs/entry/13615-...) and secondlife.com/sl20b: Shop & Hop "480 participating merchants across 24 regions"; three-day Music Fest 22-24 June. Schultz (https://ryanschultz.com/2023/06/): 22 June-11 July 2023, sixty sims, 24 Shop & Hop + 36 Festival, "Live Stage Performances (Over 425 performers on four stages)" 25 June-2 July. modemworld.me says 20 Shop & Hop regions (minority figure).
- The 425+/four-stage figure appears only in Schultz's guide; the brief's attribution of it to Linden Lab's press release is unsupported.

### 9. Castronova 2001: confirmed
- CESifo WP 618 abstract (https://www.cesifo.org/en/publications/2001/working-paper/virtual-worlds-first-hand-account-market-and-society-cyberian): hourly wage about USD 3.42; GNP per capita between Russia and Bulgaria; currency unit traded at USD 0.0107, "higher than the Yen and the Lira"; ~12,000 permanent residents, ~60,000 present at any time; "40 computers in San Diego".
- Survey n (3,619) and "platinum piece" not in abstract; a secondary blog says "over three thousand players" and gives "77th highest GNP per capita", confirming that the 77th/$2,266 figure comes from the 2001 paper, not a 2005 Guinness measurement (correction to the brief body, as the earlier checker noted).

## Additional findings
1. Concurrency data has gaps: counter stuck at 39,122 in summer 2024 (forum), blog API feeds broken Dec 2025. Treat the 2024-2025 series as indicative.
2. 2026 status: SL peak concurrency just over 47,000 (Jan 2026); regions 26,858 (Jan 2026) and 27,239 (Jul 2026, unverified); Daniel Voyager reported 620,000 monthly active users on 19 Dec 2025; SL23B ran in 2026.
3. The 2025 region decline was mostly Linden-owned (retired first-gen Linden Homes), not private estates.
4. CSM20: STV with up to 10 rankings; two of the seats were appointed by CCP, so the council is not purely elected.
5. Virtual Ability is active in 2026 (L$250,000 Linden-funded contest) but states "over 1,000 members", below the brief's 1,300+.
6. ADL 19%: of harassed gamers, so roughly 14% of all surveyed gamers quit a game; the brief's "harassment makes 19% quit" overstates.
