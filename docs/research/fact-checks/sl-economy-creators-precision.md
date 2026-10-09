# Precision check: "Second Life economy and creator ecosystem" brief

Checked 2026-10-09. Brief: scratchpad/research/sl-economy-creators.md

## Method and limitation (read first)

- WebFetch of all ten cited sources failed (DNS: `getaddrinfo ENOTFOUND` for prnewswire.com, wnhub.io, en.wikipedia.org, community.secondlife.com, wordpress.com blogs, fortune.com).
- WebSearch: the shared per-turn budget (200 calls) was already exhausted by other agents; all ten searches (one per claim, extended mode) returned "web search was not performed".
- No workaround (curl, proxy readers, archives) was used, per instructions.
- Verdicts therefore rest on the fact-checker's prior knowledge of the primary sources (Linden Lab blog posts, LL press releases, Grid Survey, contemporaneous press). They are stated as such. Nothing below was live-verified against a fetched page. Claims marked "confirmed" are ones where the checker has specific, high-confidence recall of the primary source; "unverifiable" means the checker could neither confirm nor refute the specific figures.
- Separately, the researcher's own brief admits the same problem (no primary page was fetched; everything came from search snippets), so both passes share the same blind spot. Before publication, someone with working web access must open the ten primary pages.

## Claim-by-claim

### [0] US$650M GDP / 345M transactions (Jan 2022); US$78M paid to creators in past year, US$1.1B lifetime (2024)
Verdict: confirmed (from prior knowledge; not live-fetched).
- The Linden Lab / High Fidelity press release of 13 January 2022 ("High Fidelity Invests in Second Life") says SL, "now in its 19th year", has "an annual GDP of $650 million USD with 345 million transactions of virtual goods, real estate and services". Figures match.
- The 2024 GamesBeat interview with Philip Rosedale (Dean Takahashi) is the source of the US$1.3B spent / US$1.1B lifetime creator payouts / about US$78M in the past year / about US$500M since 2018. Figures match recall.
- Precision notes: (a) the prnewswire URL supports only the 2022 half of the claim; the 2024 half rests on GamesBeat, which the researcher does cite elsewhere; (b) the "US$78M" is cash-out (process credit), not total resident earnings, so it is not the same metric as 2009's "Gross Resident Earnings" (see [2]); (c) the US$650M figure has been repeated by LL since early 2022 and is a company claim with no audit.
Sources: https://www.prnewswire.com/news-releases/high-fidelity-invests--in-second-life-301459959.html ; https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/

### [1] 2023: 21,152 creators earned real money; 6,446 > US$1,000; 139 > US$100,000; 14 >= US$1M
Verdict: unverifiable.
- The checker cannot confirm these exact four numbers. They are plausible in shape (a steep power law) and consistent with Rosedale's 2024 public statements, but the checker has no specific recall of "21,152 / 6,446 / 139 / 14".
- Attribution problem: wnhub.io (WN Hub, a games-industry news aggregator) is a secondary re-report. The primary source is almost certainly the 2024 GamesBeat interview or Rosedale's 2024 conference talk. The researcher should cite the primary, and confirm whether the year is 2023 or "the past 12 months" ending mid-2024.
- The brief's derived claim that "the 14 seven-figure earners account for at least US$14M (18%+) of payouts" depends on these numbers and on US$78M being the same population; both are unconfirmed.
Sources: https://wnhub.io/news/other/item-46605 ; https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/

### [2] 2009: economy grew 65% to US$567M user-to-user transactions; Gross Resident Earnings US$55M, up 11%
Verdict: confirmed (from prior knowledge; not live-fetched).
- Linden Lab's "2009 End of Year Second Life Economy Wrap up" (blog, January 2010) states user-to-user transactions of US$567 million in 2009, up 65% over 2008, and Gross Resident Earnings of US$55 million, up 11% over 2008; the same post carries the "about 25% of the US virtual goods market" line. Wikipedia's Economy of Second Life article reproduces these.
- Arithmetic check: 567 / 1.65 = 344, consistent with the brief's separate "about US$350M in 2008".
- Precision note: "Gross Resident Earnings" is LL's term for residents' net positive L$ flow converted to USD-equivalent, not cash actually withdrawn; the brief's 1:10 "GDP to earnings" ratio compares this against 2024 cash-out, which is a different metric. The direction of the argument survives, the exact ratio does not.
Sources: https://en.wikipedia.org/wiki/Economy_of_Second_Life ; Linden Lab blog, January 2010 economy wrap-up.

### [3] Full region: US$1,000 setup + US$295/mo (mainland US$195); 6 March 2023 cut by US$20 to US$209 (US$239 with 30K LI); current pages US$349 setup / US$199/mo
Verdict: corrected (partially; from prior knowledge).
- US$1,000 setup + US$295/month is correct for roughly 2008-2015, but it was not the price "historically" in general: islands launched at about US$1,250 setup + US$195/month; in November 2006 LL raised new-island pricing to US$1,675 setup + US$295/month (existing islands grandfathered at US$195); setup was cut to US$1,000 in 2008; setup later fell to US$600 and, in July 2018, to US$349 while tier fell from US$295 to US$249. Mainland tier for a 65,536 m2 allotment at US$195/month is correct.
- March 2023 Infrastructure Investment Update: a US$20 cut to full-region tier is consistent with recall (US$229 to US$209; the 30K-LI variant US$259 to US$239). Setup remained US$349.
- "Current LL pricing pages list US$199/month": the checker cannot confirm any US$199 full-region price. US$199 does not match any announced price point the checker knows of (US$295, US$249, US$229, US$209, grandfathered US$195 / US$179). The researcher already flagged the page as cached and conflicting; treat US$199 as unconfirmed and likely a stale or mis-scraped figure. The announced post-March-2023 price is US$209 (US$239 for 30K LI).
- Corrected reading: 2008 = US$1,000 + US$295/mo; 2018 = US$349 + US$249/mo; 2023 onward = US$349 + US$209/mo (US$239 for 30K LI).
Sources: https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/ ; https://modemworld.me/2018/06/20/second-life-major-private-region-pricing-restructure-announced/ ; https://secondlife.com/land/private-pricing

### [4] Oct 2008 Openspace tier US$75 to US$125 (setup US$250 to US$375) effective 1 Jan 2009, no grandfathering; Homesteads US$95 from Jan 2009 rising to US$125 in July 2009
Verdict: confirmed (from prior knowledge; not live-fetched).
- Jack Linden's blog post of 27 October 2008 announced Openspace tier rising from US$75 to US$125/month and setup from US$250 to US$375, effective 1 January 2009, with no grandfathering, citing usage "about twice" what was planned. The harperganesvoort post is dated the next day, 28 October 2008; the LL announcement itself is 27 October.
- After the backlash LL revised the plan (early November 2008): a new Homestead product at US$95/month from 5 January 2009, scheduled to rise to US$125 on 1 July 2009; Openspaces kept at US$75 but with heavily restricted use (750 prims). The "planned rise to US$125 in July 2009" is correct. The brief's extra detail that existing Homestead holders were later grandfathered at US$95 is only partly right: the US$95 rate was extended for existing holders for a period, but Homestead list price became US$125 and stayed there until the July 2018 cut to US$109.
Sources: https://harperganesvoort.wordpress.com/2008/10/28/linden-lab-raising-tier-on-openspace-property/ ; https://wiki.secondlife.com/wiki/Linden_Lab_Official:Openspaces_FAQ

### [5] Regions peaked at 31,988 on 13 June 2010; end-2025: 26,884 (17,636 private / 9,248 Linden); April 2026: 26,983 (17,668 / 9,315)
Verdict: unverifiable.
- The 31,988 peak on 13 June 2010 matches the checker's recall of Grid Survey / Daniel Voyager ("the all-time high of 31,988 regions on 13th June 2010"), so that part is likely right.
- The end-2025 and April 2026 counts cannot be confirmed. Source-date problem: the cited post is dated 4 November 2025 and therefore cannot contain end-of-2025 or April 2026 numbers; the researcher must cite the January 2026 and April/May 2026 posts (or gridsurvey.com directly). The brief's own text cites additional Voyager posts, so the attribution in the claim list is simply the wrong post.
- The private-estate peak of 26,605 (October 2008) is flagged by the researcher as resting on one ambiguous source; the checker's recall is that private estates peaked around 2008-2009 in the mid-20,000s, so the figure is plausible but unconfirmed.
Sources: https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/ ; https://gridsurvey.com/

### [6] Marketplace commission 5% to 10% on 2 Dec 2019, first increase since Marketplace launched; Xstreet SL and OnRez bought 20 Jan 2009
Verdict: confirmed (from prior knowledge; not live-fetched), with one precision note.
- LL's 25 November 2019 post ("The Return of Last Names, and Changes to Marketplace, Events, Premium") announced the Marketplace commission rising from 5% to 10% effective 2 December 2019, described as the first increase since the Marketplace launched, alongside a 10% cut to listing-enhancement fees and the Premium price rise. Matches.
- Xstreet SL and OnRez acquisition announced 20 January 2009; OnRez closed 11 February 2009. Matches.
- Precision note: the Second Life Marketplace itself debuted in 2010 (Xstreet SL kept running under LL until the Marketplace replaced it in October 2010); "launched after Linden Lab bought Xstreet" is true but the launch was about 20 months after the purchase, not immediately. The 5% rate predates LL ownership (SL Exchange / Xstreet charged 5%).
Sources: https://community.secondlife.com/news/featured-news/the-return-of-last-names-and-changes-to-marketplace-events-premium-r771/ ; https://lindenlab.wordpress.com/2009/01/20/xstreet-sl-and-onrez-to-join-linden-lab/

### [7] Tilia took over USD balances/payouts on 1 Aug 2019; later acquired by Thunes; Tilia Wallet
Verdict: confirmed (from prior knowledge; not live-fetched).
- LL's 1 August 2019 post "Tilia Officially Begins Operations Today in Second Life" describes Tilia Inc. as a wholly owned subsidiary, registered money services business and licensed money transmitter, taking over USD balances and process-credit payouts; residents had to accept Tilia's ToS. Matches.
- J.P. Morgan Payments took a stake in Tilia in October 2022. Thunes (Singapore cross-border payments) announced its acquisition of Tilia in January 2024; LL's FAQ refers to the "Tilia Wallet". Matches. The brief should add the dates (Oct 2022, Jan 2024).
Sources: https://community.secondlife.com/news/tools-and-technology/tilia-officially-begins-operations-today-in-second-life-r39/ ; https://lindenlab.freshdesk.com/support/solutions/articles/31000176356-thunes-acquisition-faq

### [8] Gambling ban ~25 July 2007 (FBI inquiry); Ginko paid 0.10-0.145%/day, owed ~L$200M (~US$750k); banking ban effective 22 Jan 2008
Verdict: confirmed (from prior knowledge; not live-fetched), with a causal-wording note.
- LL's "Wagering in Second Life: New Policy" was posted 25 July 2007 and took effect immediately. The FBI link is correct but indirect: LL invited the FBI to inspect in-world casinos in April 2007; the ban followed three months later amid the US UIGEA climate.
- Ginko Financial advertised roughly 0.10% per day (about 44% annualised); some promotions went higher, so the 0.10-0.145% band is defensible. Withdrawals froze in late July 2007; deposits were converted to "Ginko Perpetual Bonds" in August; outstanding liabilities of about L$200 million (roughly US$750,000 at ~L$267/US$) are the figures reported at the time. Matches.
- Banking ban: announced 8 January 2008, effective 22 January 2008; only institutions with a real-world banking charter could offer interest. Matches.
Sources: https://en.wikipedia.org/wiki/Ginko_Financial ; https://techcrunch.com/2008/01/08/virtual-banking-banned-in-second-life

### [9] Anshe Chung Nov 2006: net worth > US$1M from a US$9.95 account over 32 months; LL could not verify (holdings across many names)
Verdict: corrected (minor; from prior knowledge).
- The Anshe Chung Studios press release of 26 November 2006 announced net worth exceeding US$1 million "from profits entirely earned inside a virtual world", starting from a US$9.95 initial investment, and the business was land development, subdivision and rental. Correct.
- "32 months": the press release itself says the fortune was built "over a period of two and a half years" (about 30 months); Graef joined SL in March 2004, which gives 32 months to November 2006. Either phrasing is defensible but the brief should quote the release's "two and a half years" rather than present 32 as a sourced figure.
- LL's inability to verify: Linden Lab said it could not confirm the figure because her holdings were spread across multiple accounts/avatars and because the valuation was at in-world land prices. Correct.
- Fortune's URL date (27 November 2006) is consistent; the famous BusinessWeek cover was May 2006 and is a different piece.
Sources: https://fortune.com/2006/11/27/anshe-chung-first-virtual-millionaire ; https://en.wikipedia.org/wiki/Anshe_Chung

## Summary table

| # | Claim | Verdict | Key issue |
|---|-------|---------|-----------|
| 0 | $650M GDP / 345M tx; $78M, $1.1B | confirmed* | Two sources, not one; cash-out is not "earnings" |
| 1 | 21,152 / 6,446 / 139 / 14 creators | unverifiable | Secondary source; cite GamesBeat/Rosedale primary |
| 2 | 2009: $567M, +65%; GRE $55M, +11% | confirmed* | GRE is not cash-out; ratio comparison is loose |
| 3 | $1,000+$295; 2023 cut to $209; "$199" | corrected | $199 unconfirmed; pre-2008 price was $1,675 setup; 2018 step missing |
| 4 | Openspace $75 to $125; Homestead $95 | confirmed* | LL post dated 27 Oct 2008; Homestead list price did go to $125 |
| 5 | Peak 31,988; 2025/2026 counts | unverifiable | Cited Nov-2025 post cannot hold end-2025/Apr-2026 data |
| 6 | 5% to 10% on 2 Dec 2019; Xstreet 2009 | confirmed* | Marketplace launched Oct 2010, not at acquisition |
| 7 | Tilia 1 Aug 2019; Thunes; Wallet | confirmed* | Add dates: JPM Oct 2022, Thunes Jan 2024 |
| 8 | Gambling ban 25 Jul 2007; Ginko; bank ban 22 Jan 2008 | confirmed* | FBI link is indirect (April 2007 invitation) |
| 9 | Anshe Chung $1M, $9.95, 32 months | corrected | Release says "two and a half years" |

\* confirmed from the checker's prior knowledge of the primary source; not live-fetched in this session.

## Additional findings the brief missed (relevant to designing a successor)

1. Skill gaming was re-legalised in 2014. LL's Skill Gaming Policy (August/September 2014) allows licensed operators on designated "Skill Gaming Regions" for residents in approved jurisdictions. The brief's design implication #5 ("plan for gambling rules per jurisdiction rather than blanket bans") is something LL itself eventually did; the lesson is the seven-year gap, not the absence.
2. Linden Lab's own successor, Sansar (2017-2020), failed and was sold to Wookey Project Corp in 2020; LL itself was sold to an investor group led by Brad Oberwager and Randy Waterfield in July 2020. Any "successor to Second Life" plan must address why LL's in-house successor lost to its own legacy product (no economy at launch, no user content tooling parity, no land/rental layer, VR-first).
3. Pricing grandfathering precedent: in November 2006 LL raised new-island tier from US$195 to US$295 but grandfathered existing islands; in October 2008 it refused to grandfather Openspaces. The company had the covenant and broke it, which is why the 2008 episode was so damaging. A written grandfathering rule (brief's implication #9) has a direct historical basis.
4. The Marketplace replaced Xstreet SL in October 2010, so the "captive marketplace" era is 2010 onward, not 2009; the 5% commission predates LL ownership.
5. Metric comparability: 2009 "Gross Resident Earnings" (net positive L$ flow) and 2024 "paid out to creators" (USD cash-out) are different metrics; the brief's "1:8 to 1:10 ratio has barely moved" claim should be reframed as "both metrics sit near 10% of gross volume" rather than as one series.
6. Nominal GDP flat for 13+ years: US$567M (2009) to US$650M (2022-24) is about +15% nominal while US CPI rose about 40%, so real SL GDP fell roughly a quarter. The brief notes a "flat economy" but does not state the real-terms decline.
7. Premium price history: US$9.95/month until the 2019 change (announced alongside the Marketplace commission rise) to US$11.99/month and US$99/year, confirming the brief's unverified parenthetical in section 5.
8. Tilia dates: J.P. Morgan Payments investment October 2022; Thunes acquisition announced January 2024. These give the brief's "regulatory centralisation" timeline fixed points.
