# Second Life economy and creator ecosystem: postmortem brief for "nolife"

Prepared 2026-10-09. Method note: 13 web searches (extended mode) completed; direct WebFetch of primary pages failed in this environment (DNS resolution blocked), and the shared search budget was exhausted before a planned second round. Every fact below is therefore drawn from search-result excerpts of the cited pages. Facts that rest on a single secondary source, or that the sources themselves contest, are marked. Figures from Linden Lab (LL) are company claims; LL is private and publishes no audited financials.

## Findings

### 1. Size of the economy over time (company claims, not audited)

- Lifetime user-to-user transactions passed US$1 billion by May 2009; the in-world economy was running at "nearly USD 50 million each month" and had grown 94% year-over-year from Q2 2008 to Q2 2009. (Source: https://www.hypergridbusiness.com/2009/09/second-life-economy-tops-1-billion/)
- 2008 user-to-user transactions were about US$350 million. (Source: https://www.tabahresear.ch/wp-content/uploads/2021/06/Tabah_Research_ab_en_009.pdf)
- In 2009 the total economy grew 65% to US$567 million, which LL said was about 25% of the entire U.S. virtual-goods market; Gross Resident Earnings (money residents earned, not merely transacted) were US$55 million in 2009, up 11% over 2008. Note the gap: a $567M "GDP" produced $55M of resident earnings, roughly 10%. (Source: https://en.wikipedia.org/wiki/Economy_of_Second_Life)
- Q1 2010: 517,349 accounts transferred or received L$ in the quarter; user-held L$ balances were flat at L$6.9 billion (about US$27M at L$255/US$). (Source: https://www.engadget.com/2010-04-28-second-life-q1-2010-metrics.html; https://community.secondlife.com/news/featured-news/second-life-economy-stable-in-q2-2010-r106/)
- LL's 2010 retrospective note: after the CFO departed, "the Lab began to look with increasing favor on user-to-user transactions as a measure of the Second Life economy"; LL laid off one-third of staff in 2010. The headline "GDP" metric is therefore a gross flow chosen for PR effect, not value added. (Source: https://www.engadget.com/2010-07-10-the-virtual-whirl-a-brief-history-of-second-life-2009.html)
- Mid-2010s: a later CEO interview put GDP at around US$500 million with users cashing out "in excess of $60 million last year". (Source: https://en.wikipedia.org/wiki/Economy_of_Second_Life)
- 2020: residents earned and cashed out US$73 million (Fortune, Feb 2022). (Source: https://www.fortune.com/2022/02/07/metaverse-avatar-work-make-money-nft)
- January 2022 (High Fidelity investment press release, platform's 19th year): "annual GDP of $650 million USD with 345 million transactions of virtual goods, real estate, and services". That implies an average transaction of about US$1.88. (Source: https://www.prnewswire.com/news-releases/high-fidelity-invests--in-second-life-301459959.html; https://www.lindenlab.com/releases/high-fidelity-invests-in-second-life)
- 2024 (GamesBeat, citing Philip Rosedale and LL): LL has spent about US$1.3 billion building SL and paid out about US$1.1 billion to creators over its lifetime; about US$78 million paid to creators in the past year; about US$500 million paid out since 2018; economy "close to 10 times" the payout number, i.e. about US$650M/yr. Rosedale also said SL became profitable in 2005 having raised only US$25 million. (Source: https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/)
- No 2025 or 2026 GDP figure was found in this session's searches; the US$650M number has been repeated since 2022 without visible update, which itself suggests a flat economy.

Independent check: the Economics Design newsletter and TheNextWeb pieces repeat LL's numbers rather than measuring independently. No third-party measurement of SL GDP exists in the sources found. (Source: https://www.newsletter.economicsdesign.com/p/insights-second-life-metaverse-economies; https://thenextweb.com/news/think-second-life-died-it-has-a-higher-gdp-than-some-countries)

### 2. Linden Dollar, LindeX and Tilia

- The L$ floats on the LindeX exchange, with limit orders and market orders. December 2006 rate was about L$270/US$1; a 2006 TheStreet piece tracked L$305 to L$274 over three months. (Source: https://money.cnn.com/2006/12/08/technology/sl_lindex/index.htm; https://www.thestreet.com/investing/monitoring-the-linden-supply-10318938)
- June 2008 to June 2017: the rate stayed in a band of L$240 to L$270 per US$, averaging about L$252 in June 2017. LL manages this through its own L$ sales (the "Linden supply"), so it behaves as a managed, soft-pegged currency rather than a free float. (Source: https://en.wikipedia.org/wiki/Economy_of_Second_Life; https://bitcoinwiki.org/wiki/Economy_of_Second_Life)
- 2023 to 2026: converter sites show roughly L$320 per US$ (one cites L$319.5 for December 2023, another 320 as of September 2026). These are secondary converters, not LindeX data, but the direction (about 25% L$ depreciation versus the 2008-2017 band) is consistent across them. (Source: https://exchangerate.guru/ld/usd/1/; https://ld.currencyrate.today/usd)
- Tilia: on 1 August 2019 a wholly owned LL subsidiary, Tilia Inc., a registered money services business and licensed money transmitter, took over all USD balances and payout requests; residents had to accept Tilia's terms to cash out. Commentary at the time: LL had to become a licensed transmitter at federal and state level or "hit a wall in its ability to make pay-outs". (Source: https://community.secondlife.com/news/tools-and-technology/tilia-officially-begins-operations-today-in-second-life-r39/; https://modemworld.me/2021/09/06/in-the-press-second-life-tilia-pay-the-metaverse/)
- J.P. Morgan invested in Tilia (2022). Tilia was later acquired by Thunes, a cross-border payments company; LL's FAQ says USD balances are now managed through "Tilia Wallet" and bank-deposit payouts were to follow. LL's own help page states it cannot pay out by wire; PayPal (and later Skrill) are the routes. (Source: https://www.finextra.com/newsarticle/41162/jp-morgan-invests-in-second-lifes-payment-platform-tilia; https://lindenlab.freshdesk.com/support/solutions/articles/31000176356-thunes-acquisition-faq; https://community.secondlife.com/knowledgebase/english/account-balance-r1/)
- Fee stack on the way out (community accounting, not an official schedule): 10% Marketplace commission, 3.5% L$ sell fee on LindeX, plus a per-transaction processing fee and payout fees, giving an effective take of roughly 20% on a Marketplace sale cashed to USD, against the "90/10" headline on LL's creator marketing page. (Source: https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/; https://secondlife.com/create)
- March 6, 2023: LL changed L$ buy/sell fees in the same "Infrastructure Investment Update" that cut full-region tier; the 2023 Modem World commentary frames this as "redistributing their means of revenue generation to be less reliant on a single product (land)". Exact old/new percentages could not be read from the primary page in this session. (Source: https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/; https://modemworld.me/2023/03/06/ll-announce-fee-changes-for-second-life-land-and-lindex/)

### 3. Land: pricing history, estates versus mainland, and the region count

Pricing timeline (private full region, 65,536 m2, one server core):
- Classic era (circa 2007-2015): US$1,000 setup plus US$295/month for a full private region; mainland tier for an equivalent area was US$195/month. (Source: https://community.secondlife.com/forums/topic/140885-how-much-does-a-full-region-from-ll-actually-cost/)
- Openspace regions (light-use quarter-load sims) were sold in March 2008 at US$250 setup/US$75 per month; in October 2008 Jack Linden announced an increase to US$375/US$125 effective 1 January 2009 with no grandfathering, because they were "used about twice as much as expected". The resulting outrage is the canonical SL case of retroactive land repricing. Homesteads were then introduced at US$95/month (5 January 2009) with a planned rise to US$125 on 15 July 2009, later grandfathered at US$95 for existing holders. (Source: https://harperganesvoort.wordpress.com/2008/10/28/linden-lab-raising-tier-on-openspace-property/; http://www.slentre.com/second-life-news-linden-lab%C2%AE-price-rises-for-openspace-sim-owners-causes-outrage/; https://wiki.secondlife.com/wiki/Linden_Lab_Offiziell:Openspaces_FAQ)
- 2016: a one-time "buy-down" let existing owners reduce full-region tier to US$195/month (grandfathered). (Source: https://modemworld.me/2018/06/20/second-life-major-private-region-pricing-restructure-announced/)
- July 2018: full and Homestead tier cut 15% and setup fees reduced; one analyst estimated this removed roughly L$300,000/month from LL's land revenue line (a rough figure in L$, so about US$1,200/month, which seems too small; treat as unreliable). (Source: https://modemworld.me/2018/06/20/second-life-major-private-region-pricing-restructure-announced/; https://modemworld.me/2019/12/02/thoughts-on-second-life-fees-tier-and-revenue/)
- March 6, 2023: full regions cut US$20/month to US$209 (so US$229 before); a 30K-LI upgraded full region is US$239. (Source: https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/)
- Current LL pricing pages (cached, several years old) show full region US$349 setup and US$199/month; the two LL pages conflict with the 2023 announcement. Best reading: 2008 = US$1,000 + US$295/mo; 2025 = roughly US$349 + US$199-209/mo. Setup fell about 65% and tier about 30% nominal, over a period in which US CPI rose about 50%, so real tier fell by roughly half. (Source: https://secondlife.com/land/private-pricing; https://secondlife.com/corporate/pricing)
- Residents still argue the price is far above hosting cost ("SL regions cost pennies in resources yet we pay yacht prices"). (Source: https://community.secondlife.com/forums/topic/528802-the-math-doesnt-lie-%E2%80%93-sl-regions-cost-pennies-in-resources-yet-we-pay-yacht-prices/)

Region count (fan-run Grid Survey via Daniel Voyager; LL publishes no official series):
- Peak: 31,988 total regions on 13 June 2010; private estates peaked around 26,605 (26 October 2008, single ambiguous source). (Source: https://danielvoyager.wordpress.com/2015/11/09/second-life-regions-drop-under-the-25-000-mark/; https://gridsurvey.com/)
- July 2014: private estates fell below 19,000 for the first time since June 2008; total about 26,000. November 2015: 24,985 total, 17,888 private, 7,097 Linden-owned. (Source: https://danielvoyager.wordpress.com/2014/07/28/private-estates-drops-below-19-000-regions-in-second-life/; https://danielvoyager.wordpress.com/2015/11/09/second-life-regions-drop-under-the-25-000-mark/)
- January 2023: 27,659 total, 18,370 private, 9,289 Linden-owned. Start of 2025: 27,769 total, 17,939 private, 9,830 Linden-owned. End of 2025: 26,884 total (-3.19% in the year), 17,636 private (-1.69%), 9,248 Linden-owned (-5.92%, from retiring first-generation Linden Home continents). April 2026: 26,983 total, 17,668 private, 9,315 Linden-owned. (Source: https://danielvoyager.wordpress.com/2023/10/17/second-life-private-estates-declining-during-2023/; https://danielvoyager.wordpress.com/2025/01/05/first-2025-main-grid-regions-goes-live-for-second-life/; https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/; https://danielvoyager.wordpress.com/2026/04/08/second-life-grid-shows-positive-region-growth-since-start-of-2026/)
- Reading: private estates (the fee-paying, creator-run part of the grid) fell from about 26,600 (2008) to about 17,600 (2026), a 34% decline; the only growth since 2019 is Linden-owned land tied to the Premium subscription's free Linden Home (Bellisseria). The map has been roughly flat at 27,000 regions for a decade.

Mainland versus estates: mainland regions are owned by LL ("nobody" in the estate listing) and sold by parcel with tier charged per m2 stepped tiers; private regions are bought whole by a resident and sub-let. Mainland lacks estate-owner controls, so serious communities and businesses run on estates, which is where the 2008-2014 decline concentrated. (Source: https://community.secondlife.com/forums/topic/472286-difference-between-mainland-region-and-private-region/; https://community.secondlife.com/knowledgebase/english/private-regions-r59/)

Why land is the core revenue and why that is a tax on growth: a 2006 NBC piece states plainly that land is "the one resource that is limited, and the main source of revenue for Linden", plus LindeX commissions. Every region is a fixed monthly cost to its holder regardless of visitors, so builders and community hosts pay the most while LL's marginal server cost per region has fallen (AWS migration completed 2020). LL's post-2018 fee moves (Marketplace commission up, L$ fees up, tier down) are an explicit attempt to shift revenue off land. (Source: https://www.nbcnews.com/id/wbna15163036; https://modemworld.me/2023/03/06/ll-announce-fee-changes-for-second-life-land-and-lindex/)

### 4. Marketplace and creator earnings

- January 20, 2009: LL bought the two third-party web marketplaces Xstreet SL (ex-SL Exchange) and OnRez, closed OnRez on 11 February 2009, and rebuilt Xstreet as the Second Life Marketplace. Commentators noted at the time this foreclosed the possibility of a marketplace serving multiple virtual worlds. (Source: https://lindenlab.wordpress.com/2009/01/20/xstreet-sl-and-onrez-to-join-linden-lab/; https://www.engadget.com/2009-01-21-linden-lab-acquires-onrez-xstreet-onrez-to-close.html; https://kotaku.com/linden-lab-buys-second-life-virtual-marketplaces-onrez-5136087)
- December 2, 2019: Marketplace commission doubled from 5% to 10%, "the first commission increase since the Marketplace debuted a decade earlier", to offset investment in Marketplace features; listing-enhancement fees cut 10% the same day. Because the old 5% rounded down, L$5 items had paid zero commission; at 10% they pay L$1, so the effective increase on cheap items exceeded 2x. (Source: https://community.secondlife.com/news/featured-news/the-return-of-last-names-and-changes-to-marketplace-events-premium-r771/; https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/; https://akatandamouse.wordpress.com/2020/01/02/increased-marketplace-fees/)
- Creator income distribution, 2023 (Rosedale/LL statements reported by WN Hub): 21,152 creators earned real money; 6,446 earned more than US$1,000; 139 earned more than US$100,000; 14 earned at least US$1 million. So about 0.07% of earning creators are millionaires and 30% clear US$1,000/yr; the long tail is hobby income. (Source: https://wnhub.io/news/other/item-46605)
- Combining with the US$78M annual payout: the 14 seven-figure earners alone account for at least US$14M (18%+) of payouts; the 139 six-figure earners plausibly take 40-50%. This is an inference, not a reported figure.
- A third-party "Gameplay 2025" page claims median active Marketplace seller revenue of L$85,000/month (about US$340); methodology is unstated, treat as unreliable. (Source: https://www.playsecondlife.com/gameplay_2025/)
- Anshe Chung (Ailin Graef): in November 2006 announced net worth exceeding US$1 million "from profits entirely earned inside a virtual world", starting from a US$9.95 account in 2004 and 32 months of land subdivision and rental; holdings cited as 36 km2 of virtual land on about 550 simulators. LL could not verify (holdings spread across many names), and the figure is net worth valued at in-world land prices, not realised income. Anshe Chung Studios took Samwer-brothers VC in January 2007. (Source: https://en.wikipedia.org/wiki/Anshe_Chung; https://fortune.com/2006/11/27/anshe-chung-first-virtual-millionaire; https://www.bloomberg.com/news/articles/2006-11-25/second-lifes-first-millionaire; https://www.gamespot.com/articles/second-life-realtor-makes-1-million/1100-6162315/)
- Note the structural fact: the first SL millionaire was a landlord, not a content creator; her margin was the spread between LL tier and resident rent.

### 5. Premium and Premium Plus subscriptions

- Premium: US$11.99/month or US$99/year (post-2019 pricing; was US$9.95 earlier, not verified this session). Includes weekly L$ stipend and a free Linden Home (the Bellisseria continent that drove Linden-owned region growth 2019-2024). (Source: https://community.secondlife.com/news/featured-news/introducing-premium-plus-for-your-second-life-r1268/; https://wiki.secondlife.com/wiki/Linden_Lab_Official:New_Linden_Homes_2019)
- Premium Plus launched (2021) at US$29.99/month or US$249/year (promo US$24.99); by May 2025 forum posts give US$20.75/month on annual billing. LL's own pricing pages show conflicting figures (US$287.88/year on one, US$11.75 on another). (Source: https://community.secondlife.com/news/featured-news/introducing-premium-plus-for-your-second-life-r1268/; https://community.secondlife.com/forums/topic/527554-the-new-price-for-premium-plus-will-you-take-it/; https://secondlife.com/corporate/pricing)
- September 2025: "Premium Plus without stipend" at US$11.99/month billed annually or US$15.99 monthly, a cheaper tier that drops the L$ stipend, i.e. LL unbundling the currency subsidy from the land/feature perks. (Source: https://community.secondlife.com/news/featured-news/why-premium-plus-without-stipend-might-be-your-perfect-match-r11224/)
- Lifetime memberships offered for the platform's birthday: US$859 (Premium) and US$1,899 (Premium Plus), upgrade from a 2023 lifetime Premium US$1,150. Selling lifetime subscriptions is a classic late-lifecycle cash-pull. (Source: https://lindenlab.freshdesk.com/support/solutions/articles/31000170266-secondlifetime-premium-secondlifetime-premium-plus)

### 6. The 2007 gambling ban and the 2008 banking ban

- Gambling: LL banned all wagering on or about 25 July 2007, reportedly in response to an FBI inquiry. Casinos were among the largest tier payers, so LL expected revenue losses as casino owners cancelled region agreements. (Source: https://techcrunch.com/?p=7759; https://www.technologyreview.com/2007/08/08/224424/money-trouble-in-second-life/)
- Ginko Financial: an in-world "bank" paying 0.10% to 0.145% per day (44% to 70% annualised), with much of its book reportedly in casinos. The gambling ban triggered a run in late July/August 2007; Ginko owed depositors about L$200 million (about US$750,000) and could not pay. The same week about US$12,000 was stolen from the World Stock Exchange. Observers (Duranske) said the run was triggered by the ban but was inevitable given the rates. (Source: https://en.wikipedia.org/wiki/Ginko_Financial; https://ebiquity.umbc.edu/blogger/2007/08/08/second-life-economic-crisis-bank-run-on-ginko-financial/; https://www.nakedcapitalism.com/2007/08/bank-run-at-second-life.html)
- Banking ban: announced 8 January 2008, effective 22 January 2008, after multiple scam complaints; thereafter only entities with real-world banking licences could offer interest. Virtual stock exchanges were not covered. NBC later framed the Ginko crash as foreshadowing the 2008 financial crisis. (Source: https://techcrunch.com/2008/01/08/virtual-banking-banned-in-second-life; https://www.nbcnews.com/news/amp/wbna27846252)
- Economic effect: the bans removed the two activities with the highest L$ velocity and the highest tier spend per region, and ended unregulated in-world finance. The economy nevertheless grew 65% in 2009, so the bans did not kill growth; they shifted LL permanently toward regulatory caution that culminated in Tilia (2019). No source quantified the share of 2007 tier revenue from casinos.

### 7. What the economy got right, and how it constrained growth

Got right (documented above): a convertible currency with a stable band for a decade; real property rights that supported a landlord class and venues; a web marketplace; US$1.1B lifetime creator payouts (company claim), with thousands of people earning four figures a year and over a hundred earning six figures as of 2023; profitability by 2005 on US$25M raised.

Constrained growth:
- Cost of entry for builders: a full region cost US$1,000 + US$295/month in the classic era and still about US$199-209/month today, before any content; Openspace repricing (2008) and Homestead repricing (2009) taught holders that land cost could rise retroactively. (Sources in section 3)
- Hoarding and rentier economics: the largest fortunes (Anshe Chung) came from subdividing and renting land, i.e. arbitrage on LL's tier, not from making things; LL's own revenue depended on exactly that intermediary layer. (Sources in section 4)
- Content silos and no portability: LL bought and absorbed the independent marketplaces in 2009 rather than let a cross-world marketplace emerge; content export is permission-locked and the Marketplace serves only SL. (Sources in section 4)
- Fee creep as growth stalled: Marketplace 5% to 10% (2019), L$ fees up (2023), subscription tiers multiplied (2021, 2025), lifetime memberships sold; tier cuts were financed by taxing transactions instead. (Sources in sections 2, 4, 5)
- Flat grid: total regions about 27,000 since 2015; private estates down about a third from the 2008 peak; GDP claim stuck at US$650M from 2022 to 2024. (Sources in sections 1 and 3)

## Patterns / root causes

1. Revenue was tied to a fixed, rationed input (land) instead of to activity. LL's income scaled with regions rented, not with visitors, creations or trades. Any resident who built something popular paid the same tier as an empty sim, and a community that grew needed more regions at full price. The platform therefore taxed exactly what should have compounded.
2. The platform's chosen headline metric (gross transaction volume) overstated health. US$567M of 2009 "GDP" yielded US$55M of resident earnings; US$650M in 2022-24 yields about US$78M of payouts. The ratio of about 1:8 to 1:10 has barely moved in fifteen years, which indicates a mature closed loop (money cycling among residents and back to LL as fees), not expansion.
3. Winner-take-most creator economics arose naturally: 14 of 21,152 earning creators at US$1M+, 139 at US$100k+. Without discovery mechanisms that favour new creators, a marketplace of a decade's age accumulates incumbents.
4. Fee changes were used as the growth lever once user growth ended: every price move after 2015 was a reshuffle (tier down, commission and currency fees up), never a pricing model that scaled with the economy.
5. Regulatory shocks forced centralisation. Gambling (2007) and banking (2008) were banned outright rather than licensed in-world; cashing out eventually required a licensed money transmitter (Tilia 2019), later sold to a payments company (Thunes). Each step made the economy safer and less open.
6. Vertical integration foreclosed interoperability: buying Xstreet/OnRez (2009) made the Marketplace a captive channel; no SL content can be legitimately moved to another world, so a creator's catalogue is a sunk cost that keeps them in but attracts no one new.

## Design implications for nolife

1. Charge for activity, not for area. Replace monthly region tier with metered compute and bandwidth billed to the experience owner, with the first N visitor-hours free, so an empty build costs near zero and a popular one pays from its own revenue.
2. Make the primary revenue line a small, published take on transactions (one visible rate, under 10% all-in including cash-out), and publish the total fee stack so the "90/10 that is really 80/20" problem cannot arise.
3. Prohibit the rentier spread by design: land or space is leased from the platform at cost-plus and cannot be sublet at a markup; communities get space allocations tied to activity, which removes the land-baron layer that SL's first millionaire exemplified.
4. Report value added (creator net earnings, cash-out, median creator income), not gross volume, and publish the series openly so independent trackers (as Grid Survey does for regions) do not have to reverse-engineer it.
5. Build cash-out on a licensed, regulated rail from day one (the Tilia lesson) with bank payouts in major markets, and plan for gambling and financial-service rules per jurisdiction rather than blanket bans that strand capital.
6. Keep a floating but managed currency only if the platform commits to publishing supply and sink data weekly; otherwise denominate in fiat and avoid the 25% depreciation SL's L$ has undergone since 2017.
7. Guarantee portability: creator assets are exportable in an open format (glTF/USD) with signed licence metadata; the marketplace is an open protocol that third-party stores can plug into, reversing the 2009 Xstreet lock-in.
8. Protect new creators with discovery that is not pay-to-rank: time-boxed "new creator" slots, revenue-share caps on listing enhancements, and a published distribution of earnings so the community sees whether the long tail is growing.
9. Never reprice retroactively. Write a pricing covenant (grandfathering by default, advance notice of 12 months) so the 2008 Openspace shock cannot recur.
10. Lower the builder's entry cost to zero: free persistent space for any creator up to a resource budget, scaling with the creator's earned revenue, so the ladder from hobbyist to professional does not start with a US$1,000 cheque.

## Open questions

- No 2025 or 2026 GDP or payout figure was found; is the US$650M/US$78M pair still LL's claim, or has it fallen? Linden Lab's blog and any 2025-26 GamesBeat interviews should be read directly.
- Exact pre/post percentages of the March 2023 L$ buy/sell fee change and the current LindeX sell fee and Tilia payout fee (needed to compute the true all-in creator take).
- Official LL revenue and the land share of it have never been published; the best published estimate is dated 2006 ("main source of revenue"). Is there any 2015+ statement from Altberg or Oberwager on revenue mix?
- Private-estate peak: 26,605 regions in October 2008 rests on one ambiguous source; the Grid Survey archive should be checked.
- Casino share of 2007 tier revenue and the size of the L$ sell-off after the gambling ban were never quantified in sources found.
- How much of the US$1.1B lifetime payout is land-rental income (Anshe Chung style) versus content sales? LL has never split it.
- Premium Plus current pricing is inconsistent across LL's own pages; the authoritative current price needs confirmation.
- Whether the 2023-2026 L$ depreciation to about L$320/US$ reflects LL deliberately increasing supply (stipends, Premium Plus bonuses) or falling demand.
- Primary pages (Wikipedia, LL blog, GamesBeat, Grid Survey) could not be fetched in this session; all figures above should be rechecked against them before publication.

## Sources

- https://en.wikipedia.org/wiki/Economy_of_Second_Life
- https://en.wikipedia.org/wiki/Second_Life
- https://gamesbeat.com/linden-lab-has-spent-1-3b-building-second-life-and-paid-1-1b-to-creators/
- https://wnhub.io/news/other/item-46605
- https://www.prnewswire.com/news-releases/high-fidelity-invests--in-second-life-301459959.html
- https://www.lindenlab.com/releases/high-fidelity-invests-in-second-life
- https://www.hypergridbusiness.com/2009/09/second-life-economy-tops-1-billion/
- https://www.tabahresear.ch/wp-content/uploads/2021/06/Tabah_Research_ab_en_009.pdf
- https://www.engadget.com/2010-04-28-second-life-q1-2010-metrics.html
- https://community.secondlife.com/news/featured-news/second-life-economy-stable-in-q2-2010-r106/
- https://www.engadget.com/2010-07-10-the-virtual-whirl-a-brief-history-of-second-life-2009.html
- https://www.fortune.com/2022/02/07/metaverse-avatar-work-make-money-nft
- https://www.newsletter.economicsdesign.com/p/insights-second-life-metaverse-economies
- https://thenextweb.com/news/think-second-life-died-it-has-a-higher-gdp-than-some-countries
- https://money.cnn.com/2006/12/08/technology/sl_lindex/index.htm
- https://www.thestreet.com/investing/monitoring-the-linden-supply-10318938
- https://bitcoinwiki.org/wiki/Economy_of_Second_Life
- https://exchangerate.guru/ld/usd/1/
- https://ld.currencyrate.today/usd
- https://community.secondlife.com/news/tools-and-technology/tilia-officially-begins-operations-today-in-second-life-r39/
- https://modemworld.me/2021/09/06/in-the-press-second-life-tilia-pay-the-metaverse/
- https://www.finextra.com/newsarticle/41162/jp-morgan-invests-in-second-lifes-payment-platform-tilia
- https://lindenlab.freshdesk.com/support/solutions/articles/31000176356-thunes-acquisition-faq
- https://community.secondlife.com/knowledgebase/english/account-balance-r1/
- https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/
- https://secondlife.com/create
- https://community.secondlife.com/news/featured-news/infrastructure-investment-update-buysell-fee-change-and-land-pricing-effective-mar-6-2023-r1376/
- https://modemworld.me/2023/03/06/ll-announce-fee-changes-for-second-life-land-and-lindex/
- https://community.secondlife.com/forums/topic/140885-how-much-does-a-full-region-from-ll-actually-cost/
- https://harperganesvoort.wordpress.com/2008/10/28/linden-lab-raising-tier-on-openspace-property/
- http://www.slentre.com/second-life-news-linden-lab%C2%AE-price-rises-for-openspace-sim-owners-causes-outrage/
- https://wiki.secondlife.com/wiki/Linden_Lab_Offiziell:Openspaces_FAQ
- https://modemworld.me/2018/06/20/second-life-major-private-region-pricing-restructure-announced/
- https://modemworld.me/2019/12/02/thoughts-on-second-life-fees-tier-and-revenue/
- https://secondlife.com/land/private-pricing
- https://secondlife.com/corporate/pricing
- https://secondlife.com/land/pricing
- https://community.secondlife.com/forums/topic/528802-the-math-doesnt-lie-%E2%80%93-sl-regions-cost-pennies-in-resources-yet-we-pay-yacht-prices/
- https://gridsurvey.com/
- https://danielvoyager.wordpress.com/2014/07/28/private-estates-drops-below-19-000-regions-in-second-life/
- https://danielvoyager.wordpress.com/2015/11/09/second-life-regions-drop-under-the-25-000-mark/
- https://danielvoyager.wordpress.com/2023/10/17/second-life-private-estates-declining-during-2023/
- https://danielvoyager.wordpress.com/2025/01/05/first-2025-main-grid-regions-goes-live-for-second-life/
- https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/
- https://danielvoyager.wordpress.com/2026/04/08/second-life-grid-shows-positive-region-growth-since-start-of-2026/
- https://community.secondlife.com/forums/topic/472286-difference-between-mainland-region-and-private-region/
- https://community.secondlife.com/knowledgebase/english/private-regions-r59/
- https://www.nbcnews.com/id/wbna15163036
- https://lindenlab.wordpress.com/2009/01/20/xstreet-sl-and-onrez-to-join-linden-lab/
- https://www.engadget.com/2009-01-21-linden-lab-acquires-onrez-xstreet-onrez-to-close.html
- https://kotaku.com/linden-lab-buys-second-life-virtual-marketplaces-onrez-5136087
- https://community.secondlife.com/news/featured-news/the-return-of-last-names-and-changes-to-marketplace-events-premium-r771/
- https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/
- https://akatandamouse.wordpress.com/2020/01/02/increased-marketplace-fees/
- https://www.playsecondlife.com/gameplay_2025/
- https://en.wikipedia.org/wiki/Anshe_Chung
- https://fortune.com/2006/11/27/anshe-chung-first-virtual-millionaire
- https://www.bloomberg.com/news/articles/2006-11-25/second-lifes-first-millionaire
- https://www.gamespot.com/articles/second-life-realtor-makes-1-million/1100-6162315/
- https://community.secondlife.com/news/featured-news/introducing-premium-plus-for-your-second-life-r1268/
- https://wiki.secondlife.com/wiki/Linden_Lab_Official:New_Linden_Homes_2019
- https://community.secondlife.com/forums/topic/527554-the-new-price-for-premium-plus-will-you-take-it/
- https://community.secondlife.com/news/featured-news/why-premium-plus-without-stipend-might-be-your-perfect-match-r11224/
- https://lindenlab.freshdesk.com/support/solutions/articles/31000170266-secondlifetime-premium-secondlifetime-premium-plus
- https://techcrunch.com/?p=7759
- https://www.technologyreview.com/2007/08/08/224424/money-trouble-in-second-life/
- https://en.wikipedia.org/wiki/Ginko_Financial
- https://ebiquity.umbc.edu/blogger/2007/08/08/second-life-economic-crisis-bank-run-on-ginko-financial/
- https://www.nakedcapitalism.com/2007/08/bank-run-at-second-life.html
- https://techcrunch.com/2008/01/08/virtual-banking-banned-in-second-life
- https://www.nbcnews.com/news/amp/wbna27846252
