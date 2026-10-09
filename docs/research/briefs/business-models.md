# Business models and unit economics of virtual worlds — findings brief for "nolife"

## Method note

Written 2026-10-09. This revision is grounded in **20 live WebSearch calls** (the full hard cap). Page fetching (WebFetch/curl) is blocked in this sandbox, so every figure comes from the quoted extracts that the search tool returned, not from reading the underlying pages; where an extract came from a secondary site (blog, calculator, aggregator) rather than a filing or company post, that is said inline. Figures that could not be searched are kept from the earlier draft and labelled **(prior knowledge, unsearched)**. Derived numbers (per-DAU, per-hour) are my arithmetic on searched inputs and are labelled "derived".

Verified live: Roblox FY2024, Q2 2025 and FY2025 results; Roblox DevEx and rewarded-video ads; Fortnite Creator Economy 2.0 terms and the Nov/Dec 2025 changes; Second Life 2026 fee schedule and Linden Lab's Dec 2024 cumulative-payout disclosure; VRChat creator-economy mechanics and 2024 layoffs; Rec Room's 2025 layoffs and 2026 shutdown; The Sandbox 2025 restructuring and Decentraland's 2022 DAU dispute; Meta Reality Labs 2024-2025 losses and the March 2026 Horizon Worlds reversal; IMVU VCOIN launch terms; Minecraft Marketplace cumulative payouts; ENGAGE XR 2025 results, Virbela's sale, Teams Premium price; WoW/FFXIV prices; mobile CPI benchmarks.
Not verified live: Roblox 2024 full-year hours; Second Life concurrency/region counts and Marketplace commission; VCOIN's end date; Zepeto's current P&L; Habbo's current revenue; server cost per CCU-hour (no search budget left; stays derived from prior knowledge of cloud pricing).

---

## Findings

### 1. Second Life / Linden Lab: land rent, premium, and currency fees

- **Private-region tier (effective 15 June 2026):** Full Region with Land Capacity Bonus falls from **US$239 to US$209/month**; standard Full Region (20K capacity) from **US$209 to US$199/month**; Homestead, OpenSpace and Mainland tiers unchanged. Reported from Linden Lab's 8 June 2026 announcement by a long-running SL blog. (Source: https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/)
- **Premium (effective 8 July 2026):** monthly **$11.99 -> $12.99**; annual **$99.00 -> $119.88**; Premium Plus annual **$249 -> $287.88**. (Source: same post)
- **LindeX buy fee:** minimum fee **$1.49 -> $0.49**; the extract also reports the fee percentage "increasing from 10% to 11%" and a maximum fee moving to $29.99, but the scope of that line is garbled in the source and should be checked on secondlife.com. (Source: https://modemworld.me/tag/fees/)
- One-time **Full-region setup fee $349** (2019 figure; may have changed) (Source: https://ryanschultz.com/2019/05/29/linden-lab-announces-a-mix-of-good-news-and-bad-news-for-second-life-users/amp/). Marketplace commission raised to **10%** in 2019; process-credit (cash-out) fee **1.5%, $3 min / $15 max** (2016 schedule) (Source: https://community.secondlife.com/blogs/entry/1922-faster-credit-processing-amp-upcoming-changes-to-fees/). Later changes to these two fees were not found.
- **Linden Lab's Dec 2024 disclosure (Brad Oberwager, via VentureBeat, relayed by SL blogs):** Linden has spent **>$1.3B** building SL over 20 years and paid **~$1.1B cumulatively to creators**; the in-world economy is **~$650M/yr**; **$78M was paid to creators in 2023**; Linden says it keeps a **10% cut** ("90/10 revenue share"). (Source: https://modemworld.me/2024/12/20/ ; https://blog.kowatek.com/?p=88910)
- Historical cash-out: **$60M in 2015** (Ebbe Altberg) and **$55M in 2009**. (Source: https://www.hypergridbusiness.com/?p=50226)
- **Company revenue:** a 2026 third-party company profile estimates **~$55M/yr, ~200 employees**; weakly sourced. (Source: https://yespress.io/linden-lab) The earlier draft's $75-100M range is **(prior knowledge, unsearched)**; the truth is probably between the two.
- Scale (peak concurrency ~88k in 2009, ~30-50k now; ~31k regions at 2010 peak vs ~22-25k) and the 2020 sale to Oberwager/Waterfield are **(prior knowledge, unsearched)**.

**Unit-economic shape.** At ~$200-209/month a Full Region remains a very high-margin rental against a sim-host cost on the order of $20-50/month **(prior knowledge, unsearched)**. The 2026 move is telling: Linden *cut* region tier and *raised* premium and LindeX fees, i.e. it is shifting weight from the land tax toward membership and currency spread as the estate base erodes. Land tier still scales with footprint, not with activity.

### 2. Roblox: engagement-share at scale, with a 10-K cost structure

- **FY2024 (10-K, Feb 2025):** revenue **$3,602.0M (+29%)**; bookings **$4,369.1M (+24%)**; net loss **$935.4M**; average DAU **82.9M (+21%)**, Q4 DAU 85.3M; Q4 hours **18.7B**; average daily paying users **~1.04M** (from 852k). (Source: https://www.sec.gov/Archives/edgar/data/1315098/000131509825000033/rblx-20241231.htm ; https://www.pocketgamer.biz/roblox-revenue-up-32-in-q4-2024-as-losses-narrow)
- **DevEx 2024: $922.8M (+25%)**; Q4 2024 $280M; Q3 2024 $231.5M. (Source: https://gameindustrylibrary.com/documents/roblox-10-k-fy2024-february-2025 ; https://www.marketbeat.com/earnings/reports/2025-2-6-roblox-corp-stock)
- **Infrastructure and trust & safety:** **$448.0M in H1 2024 (+3%)**; Q3 +4% y/y, +6% q/q (AI investment); Q4 +2% y/y, "13% of revenue and 9% of bookings". In 2023 the line was ~31% of revenue and DevEx ~26%. (Source: https://www.barchart.com/story/news/29329133/roblox-rblx-q3-2024-earnings-call-transcript ; https://www.barchart.com/story/news/24100927/roblox-expects-its-highest-revenue-ever-in-2024-and-its-biggest-losses-too-what-should-investors-do-now) Derived: full-year 2024 infra+T&S is roughly **$0.9B** (H1 $448M plus two quarters of ~$230M).
- **Derived benchmarks (2024):** infra+T&S ~$0.9B / 82.9M DAU ≈ **$11/DAU/yr ≈ $0.9/DAU/month**; over ~73B engagement hours **(hours: prior knowledge, unsearched)** ≈ **1.2 cents per engaged hour**; bookings per DAU ≈ **$52.7/yr**. DevEx is ~21% of bookings; infra+T&S ~21%.
- **Q2 2025:** revenue ~$1.08B (+21%); bookings **$1,437.6M (+51%)**; DAU **111.8M (+41%)**; hours **27.4B (+58%)**; monthly payers 23.4M, **$20.48 bookings per payer**; **ABPDAU $12.86/quarter**; DevEx **$316.4M (+52%)**; FCF $176.7M. (Source: https://www.sec.gov/Archives/edgar/data/1315098/000131509825000261/q225shletterex992.htm ; https://s27.q4cdn.com/984876518/files/doc_financials/2025/q2/Q2-25-Press-Release.pdf)
- **FY2025 (reported 5 Feb 2026):** revenue **~$4.9B (+36%)**; bookings **~$6.8B (+55%)**; net loss ~$1.07B; Q4 DAU **144M (+69%)**; Q4 hours **35B (+88%)**; Q4 monthly payers ~37M; **Q4 DevEx $477M (+70%)**, top-1,000 creators averaged **$1.3M**; Q4 FCF $307M. 2026 guidance: bookings **$8.28-8.55B**; Roblox will move to quarterly guidance in 2027 because viral hits are unpredictable. (Source: https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf ; https://transcripts.platformaeronaut.com/summaries/RBLX-4Q25-AI-Summary ; https://investgame.net/news/pdf/2026-02-06-q4-2025-supplemental-materials/) Derived: Q4 2025 bookings per DAU ≈ **$15.3/quarter (~$61/yr run-rate)**; full-year 2025 DevEx is likely **~$1.4-1.5B** (Q2 $316M + Q4 $477M plus two unsearched quarters) — estimate.
- **DevEx rate:** sources conflict. Third-party calculators report the standard rate as **$0.0038/Robux** (one dates the $0.0035 -> $0.0038 rise to Sept 2025; my prior knowledge dates it to Sept 2023), others still quote $0.0035. An **April 2026** announcement reportedly raises the rate **42% (to ~$0.0054)** from **8 June 2026** for spend by age-verified US adults in eligible experiences. Minimum cash-out **30,000 earned Robux**. (Source: https://www.creation.dev/learn/roblox-developer-exchange-explained ; https://rowatcher.com/news/devex-math-in-2026-what-you-actually-take-home-per-1-000-players ; https://bloxodes.com/tools/roblox-devex-calculator) Epic's own comparison puts the Roblox creator take at **~25% of in-experience spend** (Source: https://gamesbeat.com/fortnite/).
- **Ads:** **Rewarded video** (opt-in, up to 30s, full-screen) launched **April 2025** with **Google Ad Manager** as the demand pipe; creators receive a revenue share, but no percentage is published. (Source: https://corp.roblox.com/newsroom/2025/04/roblox-scales-video-ads-partners-with-google ; https://ppc.land/roblox-expands-google-advertising-partnership-with-rewarded-video-launch/) Immersive billboard/portal ads (2024), Shopify commerce and regional pricing are **(prior knowledge, unsearched)**.
- **Safety:** global age verification for chat rolled out Jan 2026; **45% of DAUs** had completed it by 31 Jan 2026. (Source: https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf)

### 3. Fortnite Creator Economy 2.0

- Launched 22 March 2023: **40% of net revenue** from the Item Shop and most real-money purchases (after store fees) goes into a monthly **engagement pool** split across all islands, Epic's own included. (Source: https://www.fortnite.com/news/unreal-editor-for-fortnite-and-creator-economy-2-0-are-here-new-worlds-await ; https://techcrunch.com/2023/03/22/epic-launches-unreal-editor-for-fortnite-will-give-40-of-all-revenue-to-creators)
- **No official annual payout total was found**; secondary sites say "hundreds of millions" since 2023. The earlier draft's ~$320M for 2023 is **(prior knowledge, unsearched)**. (Source: https://generalistprogrammer.com/tutorials/how-much-do-uefn-creators-make)
- **Formula rewrite effective 1 Nov 2025:** creators who bring **new or lapsed players get 75% of those players' pool contribution for six months**; retention is measured per island; **only players who have made at least one purchase count**, to kill fraudulent engagement; inputs are minutes played, acquisition, playtime around V-Bucks spending, island retention. (Source: https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items)
- **In-island item sales from Dec 2025:** creators keep **100% of V-Bucks value through end-2026**, **50% thereafter**; in real-money terms about **74% of player spend now and ~37% later** after 12-30% store fees. Paid "Sponsored Row" Discover placement is auctioned. (Source: https://fchq.io/news/huge-monetization-changes-coming-soon ; https://www.cgmagonline.com/news/fortnite-creators-will-be-able-to-sell ; https://www.tubefilter.com/?p=188408)

### 4. Minecraft Marketplace

- Cumulative payouts **>$500M (£375M)** with **~295 partner organisations** (secondary industry analysis; no Microsoft confirmation found). Creator share commonly reported as **~70%** of net after the ~30% store fee; Microsoft only says "the majority". (Source: https://corq.studio/insights/minecraft-marketplace-inside-the-platforms-500-million-creator-economy/ ; https://www.minecraftpal.com/news/80/how-marketplace-creators-make-money ; https://www.fastcompany.com/40561114/how-microsofts-marketplace-is-monetizing-the-minecraft-ecosyste) Marketplace Pass price and payout terms: not public; $3.99/mo is **(prior knowledge, unsearched)**.

### 5. IMVU and VCOIN

- SEC no-action letter **18-19 Nov 2020**: unlimited supply at a **fixed $0.004 (250 per $1)**, the first token the SEC let be converted back to fiat; issued by MetaJuice (Together Labs). **750,000 wallets** twelve months after launch. (Source: https://perkinscoie.com/news/press-release/perkins-coie-obtains-sec-staff-relief-imvus-new-blockchain-digital-asset-vcoin ; https://gamesbeat.com/vcoin-digital-currency-hits-750000-wallets-on-imvu/ ; https://www.crowdfundinsider.com/2020/11/169326-imvu-receives-sec-no-action-letter-for-digital-asset-vcoin/)
- **No report of VCOIN being discontinued was found**; the earlier draft's "~2023 wind-down" is **(prior knowledge, unsearched, low confidence)**.

### 6. VRChat, Rec Room, Habbo, Zepeto

- **VRChat creator economy:** credits sell in bundles from **600 for $4.99 to 12,000 for $99.99** (~$0.0083 each); payout at **~$0.005 per credit**, so creators earn **~50% of store spend**; **30,000-credit minimum**, once-daily payouts via **Tilia to PayPal with a 1.5% fee**; Avatar Marketplace opened May 2025. VRChat **laid off 30% in June 2024**. (Source: https://creators.vrchat.com/economy/faq/ ; https://creators.vrchat.com/economy/payout ; https://wiki.vrchat.com/wiki/Creator_Economy ; https://www.tubefilter.com/?p=186451) VRChat Plus price ($9.99/mo, $99.99/yr) is **(prior knowledge, unsearched)**.
- **Rec Room:** raised **$294M**, peak **$3.5B valuation** (2021); **laid off ~half its staff in Aug 2025** to ~100 people; its own post-mortem: on UGC items it keeps **~30 cents per dollar** vs **~70 cents** on first-party items after 30% store fees; creators crossed **$1M/quarter in Q3 2025**; despite runway to 2029, it announced it **"can't make the business work" and shuts down 1 June 2026** after 150M lifetime players; final creator payout 1 June 2026. (Source: https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue ; https://roadtovr.com/rec-room-layoff-half-staff-august-2025/ ; https://www.geekwire.com/2026/rec-room-shutting-down-seattles-3-5b-social-gaming-platform-says-it-cant-make-the-business-work/ ; https://virtual.reality.news/news/rec-room-shutting-down-june-1-key-deadlines-for-creators/)
- **Habbo (Sulake):** revenue **€56.2M in 2010**; owned by Azerion since 2018; not broken out in Azerion's FY2025 (€540.6M group revenue). (Source: https://en.wikipedia.org/wiki/Sulake ; https://www.globenewswire.com/news-release/2026/04/17/3276396/0/en/azerion-group-publishes-its-2025-annual-report.html)
- **Zepeto (Naver Z):** Preqin profile shows revenue **~$46.3M and EBITDA ~-$42.5M** (year unstated); Naver deconsolidated Naver Z in 2024. (Source: https://www.preqin.com/data/profile/asset/zepeto/394765 ; https://quartr.com/events/naver-corporation-035420-q1-2025_FLDNba4j)

### 7. Decentraland / The Sandbox

- **Decentraland:** Oct 2022 DappRadar counted **38 active wallets/day** vs the Foundation's claimed **~8,000 daily users**; MANA ~**$0.067**, market cap ~$134M, about -76% over a year (undated exchange snapshot); no 2025 layoffs found (the earlier draft's "2024 layoffs" is unsearched). (Source: https://tech.slashdot.org/story/22/10/10/1952220/its-lonely-in-the-metaverse-decentralands-38-daily-active-users-in-a-13b-ecosystem ; https://www.bitrue.com/ar/price/mana)
- **The Sandbox:** **28 Aug 2025** Animoca cut **>half of ~250 staff**, installed Robby Yung as CEO and sidelined the co-founders; 2025 reporting put DAU at **"a few hundred", many bots**; SAND **$0.28 vs $8.40 ATH (-97%)**; an estate sold for **$450,000 in Dec 2021 now valued ~$1,025**; sector-wide land sales down 72-95%. (Source: https://cointelegraph.com/news/the-sandbox-restructuring-ai-layoffs-cofounders-role-shift ; https://blockworks.com/news/sandbox-co-founders-ousted-layoffs ; https://forklog.com/en/the-sandbox-restructures-cuts-half-of-workforce-and-appoints-new-ceo/amp)

### 8. Meta Horizon / Reality Labs

- Reality Labs operating loss **$17.7B (2024)** and **$19.19B (2025)** on **~$2.2B revenue**; Q1 2025 -$4.2B, Q2 -$4.5B, **Q4 2025 -$6.2B**. (Source: https://www.shacknews.com/article/147618/facebook-meta-reality-labs-fy25-losses ; https://www.digitalmusicnews.com/2025/07/31/meta-reality-labs-q2-2025/)
- Horizon Worlds: **<200k MAU** (WSJ, Oct 2022); **$50M Creator Fund (2025)** paying monthly bonuses on time spent, retention and purchases, bonuses paid without fees; Meta announced on ~17 March 2026 that VR support would end 15 June 2026, then **reversed within ~48 hours**, leaving VR in maintenance mode while development moves to mobile (45M lifetime app downloads). (Source: https://www.theblock.co/post/177471/meta-falls-short-of-user-goal-for-horizon-worlds-wsj ; https://developers.meta.com/horizon/blog/gdc-2025-horizon-worlds-create-earn-bonuses-desktop-editor-tools ; https://euronews.com/next/2026/03/20/meta-u-turns-on-horizon-worlds-vr-shutdown-after-user-backlash ; https://techcrunch.com/2026/03/19/meta-decides-not-to-shut-down-horizon-worlds-on-vr-after-all/) The 47.5% combined take on in-world items is **(prior knowledge, unsearched)**.

### 9. Subscription MMOs vs F2P

- **WoW:** US base **$14.99/month** (2026); Blizzard raises prices **up to 37% in the UK, Turkey, Kazakhstan, Georgia from 22 June 2026**, the first such increase in two decades. (Source: https://www.icy-veins.com/wow/news/wow-subscription-prices-to-rise-by-up-to-37-in-select-regions-renew-before-june-22/ ; https://www.recharge.com/blog/en-gb/world-of-warcraft-subscription-cost-2026-guide)
- **FFXIV:** plans from **$12.99/month**; "30M+ registered" is a secondary-site claim; no 2025-26 price rise found. (Source: https://subger.com/en/th/service/final-fantasy-xiv)
- Derived: a subscriber yields ~$150-180/yr; Roblox's F2P ABPDAU is **~$53/yr (2024) rising to ~$61/yr run-rate (Q4 2025)**, with only ~1.3% of DAUs paying on any given day (1.04M of 82.9M in 2024).

### 10. Enterprise / education licensing

- **ENGAGE XR:** 2025 revenue **€1.9M (2024: €3.3M, -43%)**, EBITDA loss €2.8M, cash €1.6M. (Source: https://www.investegate.co.uk/announcement/rns/engage-xr-holdings-cdi---exr/final-results/9595981)
- **Virbela:** eXp World Holdings **sold Virbela back to its co-founders on 29 Nov 2024**. (Source: https://inman.com/2024/12/27/exp-world-holdings-sells-virbela-the-firm-that-made-its-virtual-world/amp)
- **Microsoft Mesh:** bundled in **Teams Premium at $10/user/month (annual)**, which also covers town halls, webinars, Places. (Source: https://www.microsoft.com/en-my/microsoft-teams/premium)

### 11. Store taxes and hardware subsidies

- Rec Room's disclosure is the cleanest statement of the tax: **30% store fee first, then creator share**, leaving the platform 30 cents of a UGC dollar; Epic's 12-30% store-fee math gives the same shape. Meta's near-cost Quest pricing recovered via a 30% store cut is **(prior knowledge, unsearched)**.

### 12. Benchmarks for a new persistent world

- **Server cost per CCU-hour:** **(prior knowledge, unsearched, derived)** a 4-8 vCPU cloud game server (~$0.15-0.35/hr) hosting 50-150 avatars gives **~$0.002-0.006 per CCU-hour** of compute plus ~$0.001-0.003 for CDN/voice. Roblox's all-in infra+T&S of **~1.2 cents per engaged hour (2024, derived from searched $0.9B and unsearched 73B hours)** is the realistic ceiling at scale.
- **Moderation + infra per DAU:** Roblox **~$0.9/DAU/month** (derived, 2024). A new world with less automation should budget **$1.5-3/DAU/month** for its first years (estimate).
- **CAC:** Liftoff 2025 casual CPI **$1.41 iOS / $0.14 Android**; mid-core **$3.65 iOS / $0.73 Android**; tier-one blogs cite **~$4.22 iOS / $2.97 Android**; Adjust's blended 2026 gaming CPI **~$0.56 (+30% y/y)**; AppsFlyer puts 2025 mobile-gaming UA spend at **$25B**; D30 ROAS 47% iOS vs 15% Android. No published cost-per-paying-user benchmark was found; the earlier $30-60 figure is **(prior knowledge, unsearched)**. (Source: https://liftoff.ai/?p=34267 ; https://foxdata.com/en/blogs/2026-mobile-game-user-acquisition-cost-benchmarks-how-much-should-you-spend/ ; https://admiral.media/mobile-game-marketing-benchmarks/) With ~1.3% of DAUs paying, paid install CAC of $1-4 converts to **$75-300 per payer**, which no social world has ever recovered; Roblox, Fortnite, VRChat all grew organically.
- **LTV anchors:** Roblox ~$53-61 bookings/DAU/yr; SL premium $119.88/yr (2026) and estate owners ~$2,400-2,500/yr at $199-209/month; MMO subs ~$150-180/yr. Plan on **$30-60/yr blended ARPU** (estimate).

---

## Patterns / root causes

1. **Land rent taxes persistence, not success.** SL's tier and Decentraland/Sandbox LAND both charge for space regardless of visits. Linden's 2026 cut to region tier while raising premium and LindeX fees shows the land line is the one that erodes; The Sandbox's $450k-to-$1,025 estate shows the same model collapsing in 18 months when buyers were speculators, not residents.
2. **Engagement pools align platform and creator revenue and are now the standard.** Roblox DevEx grew from $923M (2024) to a ~$1.4-1.5B run-rate (2025) in lock-step with bookings; Epic's 40% pool and Meta's $50M fund pay on retention. But pools are power-law: Roblox's top 1,000 average $1.3M while the median earns ~nothing, and both Roblox and Epic had to re-engineer formulas (purchaser-only engagement, per-island retention, verified-adult rate) to stop farming.
3. **The 30% store tax decides creator share.** Rec Room keeps 30c of a UGC dollar after Apple/Google/Meta take 30c and the creator 40c; Epic's "100% of V-Bucks" is ~74% of cash; Roblox's ~25% creator share exists because 20%+ of bookings leave as store fees before anyone is paid.
4. **UGC without scale does not fund a mid-size world.** Rec Room (150M lifetime players, $294M raised, creators at $1M/quarter) still shut down; VRChat cut 30% at record usage; ENGAGE XR shrank to €1.9M. Only Roblox, with 144M DAU, has turned engagement-share into positive free cash flow, and it still books a $1B GAAP loss.
5. **Subsidy is not a model.** Reality Labs lost $37B across 2024-25 for <1M Horizon MAU; the March 2026 VR shutdown-and-reversal shows the product is sustained by corporate will, not economics.
6. **Trust & safety is a fifth of the bill.** Roblox spends about as much on infrastructure and safety (~$0.9B) as it pays creators, and its 2026 guidance explicitly adds safety spend.
7. **Currency control is margin and compliance.** Linden's 10% cut plus LindeX spreads, Roblox's 30%-of-face DevEx, VRChat's 2:1 credit spread are all the same lever; VCOIN's transferable fixed-price token won an SEC letter and 750k wallets but no visible economy.

## Design implications for nolife

1. **Price activity, not acreage.** Charge compute-minutes, storage and voice near cost; keep idle persistence close to free so creators' fixed costs stay small and the platform's revenue rises only when people show up.
2. **Run an engagement pool of 35-45% of net revenue (Fortnite's number) with purchaser-weighted, per-community retention metrics from day one**, and publish the formula; Epic's Nov 2025 rewrite (purchasers only, 75% acquisition bonus, per-island retention) is the current best practice to copy.
3. **Own billing on web/PC** so the creator share can be 50-70% of consumer spend (VRChat/Minecraft/Epic-window territory) rather than the 25-30% that mobile store fees force; treat app stores as top-up channels.
4. **Pay communities, not only asset-makers:** reserve 10-20% of the pool for groups/venues measured by distinct returning members, because the Fortnite/Roblox pools reward maps, not the people who make a place worth returning to.
5. **Budget $1-3 per DAU per month for infra plus trust & safety** (Roblox's ~$0.9 is the automated floor) and model ~1.2-2 cents per engaged hour all-in.
6. **Keep the currency closed and non-transferable** with published, modest spreads (<=10% total round-trip, below Linden's 10% + LindeX fees); avoid VCOIN/MANA-style tokens.
7. **Add a subscription stabilizer at $10-13/month** (SL $12.99, VRChat Plus ~$9.99, WoW $14.99) bundling stipend, storage and avatar features to cover fixed costs without taxing creators.
8. **Assume near-zero paid CAC**; at ~1-2% payer rates, mobile CPIs of $1-4 imply $75-300 per payer. Build invitation, events and group mechanics as the acquisition engine.
9. **Stay hardware-agnostic**; Horizon's 2026 reversal shows what depending on a subsidized headset platform costs.
10. **Plan for the Rec Room failure mode**: a world with tens of millions of players, a working creator payout and years of runway still failed on a 30-cents-per-dollar margin. Model the cash loop before launch.

## Open questions

1. Official Linden Lab revenue mix after the June/July 2026 repricing (land vs premium vs LindeX), and the exact scope of the "10% -> 11%" LindeX fee change.
2. Roblox FY2025 10-K line items: full-year DevEx and infrastructure & trust-and-safety dollars (searched results give Q2/Q4 only).
3. Whether the DevEx base rate changed in Sept 2023 or Sept 2025 (sources conflict), and the actual creator share of rewarded-video ad revenue.
4. Epic's audited cumulative Creator Economy 2.0 payouts for 2023-2025 (none published in searched sources).
5. Current status of VCOIN (no discontinuation report found).
6. Microsoft's official Minecraft Marketplace cumulative payout and partner split.
7. Horizon Worlds mobile MAU after the 2026 pivot.
8. VRChat's and Rec Room's total creator payouts and Rec Room's final payout amount.
9. Real moderation cost per DAU for a 100k-1M DAU world (no company publishes it).

## Sources

- https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/
- https://modemworld.me/tag/fees/
- https://modemworld.me/2024/12/20/
- https://blog.kowatek.com/?p=88910
- https://www.hypergridbusiness.com/?p=50226
- https://yespress.io/linden-lab
- https://ryanschultz.com/2019/05/29/linden-lab-announces-a-mix-of-good-news-and-bad-news-for-second-life-users/amp/
- https://community.secondlife.com/blogs/entry/1922-faster-credit-processing-amp-upcoming-changes-to-fees/
- https://www.sec.gov/Archives/edgar/data/1315098/000131509825000033/rblx-20241231.htm
- https://www.pocketgamer.biz/roblox-revenue-up-32-in-q4-2024-as-losses-narrow
- https://gameindustrylibrary.com/documents/roblox-10-k-fy2024-february-2025
- https://www.marketbeat.com/earnings/reports/2025-2-6-roblox-corp-stock
- https://www.barchart.com/story/news/29329133/roblox-rblx-q3-2024-earnings-call-transcript
- https://www.barchart.com/story/news/24100927/roblox-expects-its-highest-revenue-ever-in-2024-and-its-biggest-losses-too-what-should-investors-do-now
- https://www.sec.gov/Archives/edgar/data/1315098/000131509825000261/q225shletterex992.htm
- https://s27.q4cdn.com/984876518/files/doc_financials/2025/q2/Q2-25-Press-Release.pdf
- https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf
- https://transcripts.platformaeronaut.com/summaries/RBLX-4Q25-AI-Summary
- https://investgame.net/news/pdf/2026-02-06-q4-2025-supplemental-materials/
- https://www.creation.dev/learn/roblox-developer-exchange-explained
- https://rowatcher.com/news/devex-math-in-2026-what-you-actually-take-home-per-1-000-players
- https://bloxodes.com/tools/roblox-devex-calculator
- https://corp.roblox.com/newsroom/2025/04/roblox-scales-video-ads-partners-with-google
- https://ppc.land/roblox-expands-google-advertising-partnership-with-rewarded-video-launch/
- https://www.fortnite.com/news/unreal-editor-for-fortnite-and-creator-economy-2-0-are-here-new-worlds-await
- https://techcrunch.com/2023/03/22/epic-launches-unreal-editor-for-fortnite-will-give-40-of-all-revenue-to-creators
- https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items
- https://fchq.io/news/huge-monetization-changes-coming-soon
- https://www.cgmagonline.com/news/fortnite-creators-will-be-able-to-sell
- https://www.tubefilter.com/?p=188408
- https://gamesbeat.com/fortnite/
- https://generalistprogrammer.com/tutorials/how-much-do-uefn-creators-make
- https://corq.studio/insights/minecraft-marketplace-inside-the-platforms-500-million-creator-economy/
- https://www.minecraftpal.com/news/80/how-marketplace-creators-make-money
- https://www.fastcompany.com/40561114/how-microsofts-marketplace-is-monetizing-the-minecraft-ecosyste
- https://perkinscoie.com/news/press-release/perkins-coie-obtains-sec-staff-relief-imvus-new-blockchain-digital-asset-vcoin
- https://gamesbeat.com/vcoin-digital-currency-hits-750000-wallets-on-imvu/
- https://www.crowdfundinsider.com/2020/11/169326-imvu-receives-sec-no-action-letter-for-digital-asset-vcoin/
- https://creators.vrchat.com/economy/faq/
- https://creators.vrchat.com/economy/payout
- https://wiki.vrchat.com/wiki/Creator_Economy
- https://www.tubefilter.com/?p=186451
- https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue
- https://roadtovr.com/rec-room-layoff-half-staff-august-2025/
- https://www.geekwire.com/2026/rec-room-shutting-down-seattles-3-5b-social-gaming-platform-says-it-cant-make-the-business-work/
- https://virtual.reality.news/news/rec-room-shutting-down-june-1-key-deadlines-for-creators/
- https://en.wikipedia.org/wiki/Sulake
- https://www.globenewswire.com/news-release/2026/04/17/3276396/0/en/azerion-group-publishes-its-2025-annual-report.html
- https://www.preqin.com/data/profile/asset/zepeto/394765
- https://quartr.com/events/naver-corporation-035420-q1-2025_FLDNba4j
- https://tech.slashdot.org/story/22/10/10/1952220/its-lonely-in-the-metaverse-decentralands-38-daily-active-users-in-a-13b-ecosystem
- https://www.bitrue.com/ar/price/mana
- https://cointelegraph.com/news/the-sandbox-restructuring-ai-layoffs-cofounders-role-shift
- https://blockworks.com/news/sandbox-co-founders-ousted-layoffs
- https://forklog.com/en/the-sandbox-restructures-cuts-half-of-workforce-and-appoints-new-ceo/amp
- https://www.shacknews.com/article/147618/facebook-meta-reality-labs-fy25-losses
- https://www.digitalmusicnews.com/2025/07/31/meta-reality-labs-q2-2025/
- https://www.theblock.co/post/177471/meta-falls-short-of-user-goal-for-horizon-worlds-wsj
- https://developers.meta.com/horizon/blog/gdc-2025-horizon-worlds-create-earn-bonuses-desktop-editor-tools
- https://euronews.com/next/2026/03/20/meta-u-turns-on-horizon-worlds-vr-shutdown-after-user-backlash
- https://techcrunch.com/2026/03/19/meta-decides-not-to-shut-down-horizon-worlds-on-vr-after-all/
- https://www.icy-veins.com/wow/news/wow-subscription-prices-to-rise-by-up-to-37-in-select-regions-renew-before-june-22/
- https://www.recharge.com/blog/en-gb/world-of-warcraft-subscription-cost-2026-guide
- https://subger.com/en/th/service/final-fantasy-xiv
- https://www.investegate.co.uk/announcement/rns/engage-xr-holdings-cdi---exr/final-results/9595981
- https://inman.com/2024/12/27/exp-world-holdings-sells-virbela-the-firm-that-made-its-virtual-world/amp
- https://www.microsoft.com/en-my/microsoft-teams/premium
- https://liftoff.ai/?p=34267
- https://foxdata.com/en/blogs/2026-mobile-game-user-acquisition-cost-benchmarks-how-much-should-you-spend/
- https://admiral.media/mobile-game-marketing-benchmarks/
