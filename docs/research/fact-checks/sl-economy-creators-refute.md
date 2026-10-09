# Refutation pass: "Second Life economy and creator ecosystem" brief

Date: 2026-10-09. Lens: adversarial refutation.

## Method and its limits (read first)

- WebFetch failed with DNS errors (ENOTFOUND) for every host tried: prnewswire.com, gamesbeat.com, wnhub.io, en.wikipedia.org, community.secondlife.com, danielvoyager.wordpress.com, harperganesvoort.wordpress.com, fortune.com.
- WebSearch returned "budget used up" (200 calls per turn, shared across agents) on all 14 queries before a single result came back.
- No workaround (curl, proxies, archive readers) was used, per instructions.
- Verdicts below therefore rest on prior knowledge of the primary record (Linden Lab blog posts and press releases, contemporaneous press, Wikipedia articles on the Second Life economy and Ginko Financial) plus internal-consistency checks on the researcher's own numbers. Where recall of a specific figure is not strong, the verdict is "unverifiable" even when the figure is plausible. Nothing here was re-fetched today; a follow-up session with search budget should spot-check the items flagged "needs live check".

## Claims

### [0] US$650M GDP / 345M transactions (Jan 2022); US$78M to creators in past year and US$1.1B lifetime (2024)
- Verdict: confirmed (press-release part strong; 2024 figures consistent with recall but need live check).
- Evidence: Linden Lab's 13 January 2022 release on the High Fidelity investment states that Second Life has "an annual GDP of $650 million USD with 345 million transactions of virtual goods, real estate, and services". GamesBeat's mid-2024 interview with Linden Lab leadership (Brad Oberwager, Philip Rosedale) carried the US$1.3B spent / US$1.1B lifetime payout framing. The US$78M "past year" figure is consistent with the trend Fortune reported for 2020 (about US$73M cashed out) and with LL's "about 10x payouts" economy framing, but I could not re-read the article today.
- Adversarial note: all of these are company claims; LL is private, unaudited. "GDP" here is gross user-to-user transaction volume, not value added, so it double-counts every resale and every L$ passed between alts. The same US$650M has been repeated from 2022 to 2024 without a new measurement, which the researcher correctly reads as stagnation rather than stability.
- Sources: https://www.lindenlab.com/releases/high-fidelity-invests-in-second-life ; https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/

### [1] 2023 creator distribution: 21,152 earned; 6,446 > US$1,000; 139 > US$100,000; 14 >= US$1M
- Verdict: unverifiable.
- Evidence: single secondary source (WN Hub) that could not be opened; the specific counts do not match any Linden Lab publication I can recall verbatim. The distribution is internally plausible against the US$78M annual payout (14 x US$1M = US$14M minimum, leaving a credible remainder for the other 21,138 earners), and Oberwager/Rosedale did discuss creator earnings tiers in 2024 interviews. But the attribution "Linden Lab/Rosedale statements as reported" is second-hand and the exact numbers should be treated as unconfirmed until the primary interview or LL post is located.
- Adversarial note: "earned real money" is ambiguous (any L$ sale, or a USD cash-out?). If it means any L$ received, the 21,152 base is tiny for a platform claiming ~1M monthly users and would understate the hobby tail; if it means USD cash-outs through Tilia it is a different population. The brief's "0.07% millionaires" ratio depends on which.
- Sources: https://wnhub.io/news/other/item-46605 (not reached)

### [2] 2009 economy +65% to US$567M; Gross Resident Earnings US$55M (+11%)
- Verdict: confirmed.
- Evidence: Linden Lab's "2009 End of Year Second Life Economy Wrap up (including Q4 Economy in Detail)" (January 2010) stated the economy grew 65% in 2009 to US$567 million, "about 25% of the entire U.S. virtual goods market", and that Gross Resident Earnings were US$55 million, up 11% on 2008. Wikipedia's Economy of Second Life article reproduces these numbers from that post.
- Adversarial note: the US$567M is user-to-user L$ transaction volume converted at the LindeX rate; the 65% jump partly reflects LL changing what it counted in 2009 (the brief's own Engadget citation notes the Lab "began to look with increasing favor on user-to-user transactions as a measure"). The 2008 comparable (~US$350M) was computed on the older basis, so the 65% growth rate is not strictly like-for-like.
- Sources: https://community.secondlife.com/blogs/entry/... (LL blog, Jan 2010 economy wrap-up); https://en.wikipedia.org/wiki/Economy_of_Second_Life

### [3] Full region US$1,000 + US$295/mo (mainland US$195); March 2023 cut US$20 to US$209 (US$239 with 30K LI); pricing page US$349 setup / US$199/mo
- Verdict: corrected (gist holds; the US$199 figure is not the current full-region list price).
- Evidence: Classic-era pricing is right: from the late-2006 price rise until 2015 a private full region was US$295/month and, after setup was lowered in 2008, US$1,000 to set up; mainland tier for a full 65,536 m2 was US$195/month. The 2018 restructure cut full-region tier by about 15% (US$295 to US$249) and setup to US$350 range; the 6 March 2023 "Infrastructure Investment Update" cut full regions by US$20/month to US$209 and the 30K-LI variant to US$239, leaving Homesteads at US$109. LL's current private-region pricing page lists US$349 setup and US$209/month for a full region.
- Correction: a page showing US$199/month is either a stale cache or a different product (the grandfathered full-region rate, which has always sat below list and was also cut in 2023). It should not be presented as a conflicting list price; the right 2025-26 list pair is US$349 setup + US$209/month (US$239 for 30K LI). Needs live check of secondlife.com/land/private-pricing.
- Adversarial note: the brief's "real tier fell by roughly half" uses US$199; using US$209 changes little, but the researcher's "two LL pages conflict" framing overstates the conflict.
- Sources: https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/ ; https://secondlife.com/land/private-pricing

### [4] Openspace US$75 to US$125/mo (setup US$250 to US$375), announced Oct 2008 for 1 Jan 2009, no grandfathering; Homesteads US$95 from Jan 2009 rising to US$125 in July 2009
- Verdict: confirmed.
- Evidence: Jack Linden's 27-28 October 2008 blog post announced Openspace tier rising from US$75 to US$125/month and setup from US$250 to US$375, effective 1 January 2009, with no grandfathering, citing usage "about twice" what was planned. After the backlash LL revised the plan in November 2008: Openspaces would stay at US$75 but be throttled (750 prims, 10 avatars), and a new Homestead class (3,750 prims, 20 avatars) was created at US$95/month from 5 January 2009, scheduled to rise to US$125 on 1 July 2009; the Homestead setup fee was US$375.
- Adversarial note on the brief (not the claim): the brief says Homesteads were "later grandfathered at US$95 for existing holders". I do not recall LL grandfathering that; the July 2009 rise to US$125 went ahead and Homesteads stayed at US$125 until the 2018 cut to US$109. Treat the grandfathering sentence as unsupported.
- Sources: https://wiki.secondlife.com/wiki/Linden_Lab_Official:Openspaces_FAQ ; https://harperganesvoort.wordpress.com/2008/10/28/linden-lab-raising-tier-on-openspace-property/

### [5] Regions peaked at 31,988 on 13 June 2010; end-2025 26,884 (17,636 private / 9,248 Linden); April 2026 26,983 (17,668 / 9,315)
- Verdict: unverifiable.
- Evidence: Tyche Shepherd's Grid Survey put the all-time peak at roughly 32,000 regions in mid-2010, so 31,988 on 13 June 2010 is consistent with the known peak, but I cannot vouch for the exact day. The 2025-26 figures sum correctly (17,636 + 9,248 = 26,884; 17,668 + 9,315 = 26,983), which argues they were copied faithfully from Daniel Voyager's posts, but the posts could not be opened and no second series exists to cross-check them.
- Adversarial note: Grid Survey counts regions visible on the map, including Linden-owned Bellisseria/Linden Home regions that generate Premium subscription revenue rather than tier. "Flat at 27,000" therefore hides a mix shift: fee-paying private estates fell while subsidised Linden Homes rose. That is the right reading and the brief makes it. Also, private estates "peaked around 26,605 in October 2008" rests on one ambiguous source; the private-estate peak is usually dated 2008-2009 at ~25,000-26,000.
- Sources: https://gridsurvey.com/ ; https://danielvoyager.wordpress.com/ (not reached)

### [6] Marketplace commission 5% to 10% on 2 Dec 2019, first increase since launch; Xstreet SL and OnRez bought 20 Jan 2009
- Verdict: confirmed.
- Evidence: Linden Lab's November 2019 post "The Return of Last Names and Changes to Marketplace, Events, Premium" announced the Marketplace commission would rise from 5% to 10% effective 2 December 2019, describing it as the first commission increase since the Marketplace launched, and cut listing-enhancement prices about 10% at the same time. LL announced the acquisition of Xstreet SL and OnRez on 20 January 2009; OnRez was closed in February 2009 and Xstreet was rebranded as the Second Life Marketplace in 2010.
- Adversarial note: the 5% rate predated LL's ownership (Xstreet charged 5%), so "first increase since launch" is LL's framing of a rate it inherited. The brief's point about rounding (L$5 items going from L$0 to L$1 commission) is correct arithmetic.
- Sources: https://community.secondlife.com/news/featured-news/the-return-of-last-names-and-changes-to-marketplace-events-premium-r771/ ; https://lindenlab.wordpress.com/2009/01/20/xstreet-sl-and-onrez-to-join-linden-lab/

### [7] Tilia took over USD balances and payouts on 1 Aug 2019; later acquired by Thunes; residents hold USD in a Tilia Wallet
- Verdict: confirmed.
- Evidence: LL's 1 August 2019 post "Tilia Officially Begins Operations Today in Second Life" introduced Tilia Inc. as a wholly owned subsidiary, registered money services business and licensed money transmitter, handling USD balances and process-credit payouts, with residents required to accept Tilia's ToS. J.P. Morgan Payments made a strategic investment in Tilia in 2022. Thunes announced the acquisition of Tilia from Linden Lab in 2024; LL's support FAQ describes USD balances now living in a "Tilia Wallet".
- Adversarial note: the brief says LL "cannot pay out by wire"; historically wire was an option for large payouts at a fee, and routes have changed under Thunes. Treat payout-method specifics as time-sensitive.
- Sources: https://community.secondlife.com/news/tools-and-technology/tilia-officially-begins-operations-today-in-second-life-r39/ ; https://lindenlab.freshdesk.com/support/solutions/articles/31000176356-thunes-acquisition-faq

### [8] Gambling banned ~25 July 2007 (FBI inquiry); Ginko paid 0.10-0.145%/day and owed ~L$200M (~US$750k); banking banned effective 22 Jan 2008
- Verdict: confirmed (one nuance on the interest rate).
- Evidence: Robin Linden's "Wagering in Second Life: New Policy" post went up on 25 July 2007. The FBI had visited LL in April 2007 at LL's own invitation to look at in-world casinos; LL cited the Unlawful Internet Gambling Enforcement Act and legal uncertainty. Ginko Financial halted withdrawals in early August 2007 after a run that began within days of the ban, and converted about L$200 million of deposits (roughly US$750k at ~L$270/US$) into "Ginko Perpetual Bonds" on the World Stock Exchange. LL announced the banking ban on 8 January 2008, effective 22 January 2008, allowing only entities with real-world banking charters to offer interest.
- Nuance: Ginko's headline rate was about 0.10% per day (roughly 44% annualised); the 0.145% upper figure appears in some accounts as a promotional/variable rate and should not be presented as the standard rate. Observers (Duranske) argued the collapse was inevitable at those rates regardless of the ban.
- Sources: https://en.wikipedia.org/wiki/Ginko_Financial ; LL blog posts of 25 July 2007 and 8 January 2008

### [9] Anshe Chung announced net worth > US$1M in November 2006, from a US$9.95 account over 32 months; LL could not verify
- Verdict: confirmed.
- Evidence: Anshe Chung Studios issued a press release on 26 November 2006 claiming Ailin Graef's avatar was the first to reach a net worth exceeding US$1 million "from profits entirely earned inside a virtual world", starting from a US$9.95 initial purchase about two and a half years (32 months) earlier, via land development and rental. Press coverage (CNNMoney/Fortune, Bloomberg, GameSpot) noted Linden Lab could not confirm because holdings were held under many accounts and the valuation was a mark-to-market of virtual land, not realised cash.
- Adversarial note: the US$1M is a self-declared asset valuation at in-world land prices, so it is a landlord's paper wealth, not income. The brief's structural reading (first millionaire was a rentier on LL's tier spread) is sound. Her business also took outside VC (Samwer brothers) in January 2007, so "entirely earned inside" stops being true immediately after the announcement.
- Sources: https://fortune.com/2006/11/27/anshe-chung-first-virtual-millionaire ; https://en.wikipedia.org/wiki/Anshe_Chung

## Scorecard
- Confirmed: [0], [2], [4], [6], [7], [8], [9]
- Corrected: [3] (US$199/mo is not the current full-region list price; use US$349 + US$209, US$239 for 30K LI)
- Unverifiable: [1], [5]
- Refuted: none

## Additional findings the brief missed (relevant to a successor design)
1. Linden Lab already built a graphics-first successor and it failed: Sansar (open beta 2017) had far better rendering, PBR materials and VR support than SL, never reached meaningful concurrency, and was sold to Wookey in March 2020. Better graphics alone did not attract SL's creators or a new audience; the missing pieces were an economy, user land ownership and a critical mass of social activity at launch.
2. Ownership change and leadership: Linden Lab was acquired in July 2020 by an investor group led by Brad Oberwager and Randy Waterfield; Philip Rosedale returned via the January 2022 High Fidelity deal and later took a CTO role. The post-2022 strategy is a mobile viewer (Second Life Mobile, 2024-25), PBR/glTF materials, and age-verification changes, not a new world.
3. IP/ToS risk: Linden Lab's August 2013 Terms of Service change (section 2.3) granted LL a broad, perpetual licence over user content; creators and texture vendors (notably CGTextures) pulled out, and LL partially walked it back in 2014. A successor needs a creator-friendly licence from day one.
4. L$ legal status: LL's ToS defines the Linden Dollar as a limited licence right, not property or currency, and LL controls supply by selling L$ on the LindeX. The brief's "managed float" reading is right, but the legal design (licence, not asset) is what let LL freeze/confiscate balances and ban banking; a successor using fiat-denominated balances through a regulated wallet avoids that ambiguity.
5. OpenSimulator and the Hypergrid already implement the brief's portability recommendation (teleporting avatars and inventory between independently hosted grids), and have done so since 2008. They demonstrate that interoperability without a shared economy or curation produces many near-empty grids; portability must be paired with discovery and a payment rail.
6. The 2010 layoff was about 30% of staff (June 2010) under Mark Kingdon, following the failure of the "Second Life Enterprise" behind-the-firewall product and the Viewer 2 rollout; it marks the point LL stopped investing in growth and started managing cash flow, which is the real start of the flat decade.
7. Gambling never fully left: "skill gaming" regions were legalised in 2014 under a licensing regime (Skill Gaming Policy, approved operators, region-level gating), which is the per-jurisdiction licensing model the brief recommends; it exists and could be studied rather than designed from scratch.
