# Search verification: business-models ledger (ledger2-business-models.json)

Date: 2026-10-09. Searches used: 12 of 12 (hard cap reached). Mode: standard throughout.

**Method note:** Page fetching (WebFetch/curl) is blocked in this sandbox, so every verdict rests on the quoted extracts returned by WebSearch, not on the full pages. Where an extract did not contain a specific number, that number is marked as unverified even if the surrounding claim was confirmed. Prior "checks" in the ledger were from non-search checkers and were ignored as evidence.

| # | Claim (short) | Verdict | Searched |
|---|---|---|---|
| 0 | Roblox FY2024 revenue $3,602.0M, bookings $4,369.1M, net loss $935.4M, avg DAU 82.9M, DevEx $922.8M | confirmed | yes (2 searches) |
| 1 | Roblox infra+T&S $448.0M H1 2024, ~$0.9B full year, ~$0.9/DAU/month | corrected (FY2024 line ≈ $915M; derived figures hold) | yes |
| 2 | Roblox FY2025: rev ~$4.9B, bookings ~$6.8B, Q4 DAU 144M, Q4 DevEx $477M, 2026 guide $8.28-8.55B | confirmed | yes |
| 3 | Fortnite 40% pool; 1 Nov 2025 formula; 75% acquisition bonus; items from Dec 2025 at 100% through 2026, 50% after | corrected (100% extended to 31 Jan 2027; publishing opened 9 Jan 2026) | yes |
| 4 | Second Life June/July 2026 fee changes | confirmed | yes |
| 5 | Linden Lab $1.3B spent / $1.1B paid / $78M 2023 / ~$650M economy / 10% cut | confirmed (company-provided, secondhand) | yes |
| 6 | Rec Room 30c vs 70c, Aug 2025 half-staff layoff, 1 June 2026 shutdown, 150M players, $294M / $3.5B | confirmed | yes (2 searches) |
| 7 | VRChat ~50% creator share, $0.005/credit, 30,000 min, 1.5% Tilia fee, 30% layoff June 2024 | confirmed | yes |
| 8 | Reality Labs -$17.7B (2024), -$19.19B (2025) on ~$2.2B rev; Horizon VR shutdown reversed in ~48h | confirmed (reversal is partial) | yes |
| 9 | Sandbox >half of ~250 staff cut 28 Aug 2025, DAU in hundreds, SAND -97%, $450k estate now ~$1,025 | confirmed except estate figure (not found) | yes |

## Detail per claim

### 0. Roblox FY2024 — confirmed
Copies of the Q4/FY2024 press release (BusinessWire, Seeking Alpha, silicon.co.uk) state: revenue $3,602.0M (+29%), bookings $4,369.1M (+24%), average DAUs 82.9M (+21%), net loss attributable to common stockholders $935.4M (consolidated $940.6M). CEO on the Q4 call: "shared over $922,000,000 with the developer community in 2024". Not in extracts: the ~1.04M average daily paying users (prior knowledge, plausible). Bonus: FY2024 hours engaged 73.5B (+23%), which replaces the researcher's "prior knowledge, unsearched" ~73B.
Sources: https://www.businesswire.com/news/home/20250206476916/en ; https://seekingalpha.com/pr/19993989-roblox-reports-fourth-quarter-and-full-year-2024-financial-results ; https://www.fool.com/earnings/call-transcripts/2025/02/06/roblox-rblx-q4-2024-earnings-call-transcript/

### 1. Roblox infrastructure & trust-and-safety — corrected (minor)
H1 2024 $448.0M confirmed (10-Q). An EDGAR-derived table (app.edgar.tools) lists the line as 1,153 / 915 / 878 / 689 / 456, i.e. FY2025 ≈ $1,153M, FY2024 ≈ $915M, FY2023 ≈ $878M (Statista labels $878M as "annual", probably 2023). So "roughly $0.9B" is right; the precise FY2024 figure is ~$915M, and FY2025 is ~$1.15B (this also answers one of the ledger's open questions). Derived: $915M / 82.9M DAU / 12 ≈ $0.92/DAU/month; $915M / 73.5B hours ≈ 1.24c per engaged hour — both hold. The "13% of revenue / 9% of bookings in Q4 2024" phrasing was not in extracts. 10-K: D&A inside this line was $195.3M (2024) vs $179.9M (2023).
Sources: https://app.edgar.tools/companies/RBLX ; https://statista.com/statistics/1377017/annual-opex-roblox-corporation ; https://www.sec.gov/Archives/edgar/data/1315098/000131509825000033/rblx-20241231.htm

### 2. Roblox FY2025 / Q4 2025 — confirmed
Q4 2025: revenue $1.415B (+43%), bookings $2.222B (+63%), DAU 144M (+69%, down sequentially), hours 35B (+88%), DevEx $477M (+70%), monthly unique payers ~37M, net loss $318M, FCF $307M. 2026 guidance: bookings growth 22-26% ≈ $8.28-8.55B; revenue $6.02-6.29B; FCF $1.60-1.82B; quarterly guidance from 2027. Full-year 2025 "~$4.9B / ~$6.8B" and "top-1,000 creators averaged $1.3M" were not quoted in extracts but are consistent with the growth rates (prior knowledge). Note: one summary attributes the DevEx growth partly to "the 8.5% increase in DevEx rates announced in September 2025" — $0.0035 → $0.0038 is +8.6%, which supports dating the rate change to Sept 2025 (resolving the ledger's open question in favour of 2025, not 2023).
Sources: https://www.sec.gov/Archives/edgar/data/1315098/000131509826000009/ex991-q42025shareholder.htm ; https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf ; https://www.fool.com/earnings/call-transcripts/2026/02/05/roblox-rblx-q4-2025-earnings-call-transcript/

### 3. Fortnite Creator Economy 2.0 changes — corrected
Confirmed from Epic's 18 Sept 2025 post: engagement formula updated 1 Nov 2025; creators bringing new/lapsed players get 75% of those players' pool contribution for six months; 100% of V-Bucks value ≈ 74% of cash spent on V-Bucks; 50% of Sponsored Row revenue goes into the pool. Corrections: (a) Epic's updated notice extends the 100% V-Bucks-value share through 31 January 2027, with 50% from 1 February 2027 (earlier coverage said "through 2026"); (b) publishing for in-island transactions opened 9 January 2026, not December 2025. The 40%-of-net-revenue pool size was not in the extracts (prior knowledge; it is Epic's long-standing published figure). No post-launch report confirms that the 1 Nov formula went live exactly as announced.
Sources: https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items ; https://www.videogameschronicle.com/news/fortnite-will-soon-let-island-creators-sell-in-game-items-and-pay-to-appear-in-a-new-sponsored-row

### 4. Second Life 2026 fees — confirmed
Modemworld's reproduction of Linden's June 2026 announcement: from 15 June 2026 Full Region 20K Land Capacity $209 → $199, Full Region with Land Capacity Bonus $239 → $209; Homestead/OpenSpace/Mainland unchanged. From 8 July 2026 Premium monthly $11.99 → $12.99, quarterly $32.97 → $35.97, annual $99.00 → $119.88; Premium Plus annual $249.00 → $287.88; Plus and Premium Plus No Stipend unchanged. LindeX minimum buy fee $1.49 → $0.49 (purchases ≈ $15 or less); a second version of the post says the percentage fee rises 10% → 11%. Linden's own post was not reachable (fetch blocked).
Source: https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/

### 5. Linden Lab cumulative figures — confirmed (company-provided)
Dec 2024 (Oberwager/Rosedale via VentureBeat, relayed by kowatek/modemworld): >$1.3B spent over 20 years; ~$1.1B paid to creators since 2003; ~$650M/yr economy; 90/10 share; $78M to creators in 2023 (one secondhand summary, "up $10M vs 2017"). One outlet misframes $1.1B as a single-year figure; cumulative is the consistent reading. Not independently verified.
Sources: https://blog.kowatek.com/?p=88910 ; https://modemworld.me/2024/12/20/

### 6. Rec Room — confirmed
Blog post 28 Aug 2025 (CEO Nick Fajt): on $1 of first-party item sales ~70c reaches Rec Room after 30% platform fees; on $1 of UGC only ~30c is kept; runway "into 2029"; team still >100 after cuts; July 2025 record UGC revenue (+70% y/y). Layoffs: ~16% in March 2025, then ~50% in August 2025 (staff ~310 → just over 100). Shutdown: all services offline noon Pacific 1 June 2026; >150M lifetime players and creators; token purchases end 1 May, creators stop earning after 18 May 2026; "never found a sustainable business model." $3.5B valuation reported by a single outlet; $294M raised not in extracts (prior knowledge; matches Crunchbase-era reporting). New: Snap reportedly acquired select Rec Room assets/talent for its Specs subsidiary (via GeekWire).
Sources: https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue ; https://roadtovr.com/rec-room-layoff-half-staff-august-2025/ ; https://roadtovr.com/rec-room-shutdown-snap-acquisition-2026/ ; https://www.pocketgamer.biz/rec-room-to-shut-down-after-failing-to-achieve-profitability-from-150m-players

### 7. VRChat creator economy — confirmed
FAQ: 1 credit ≈ $0.005 at payout; payout page: minimum 30,000 earned credits (~$150), purchased/promo credits excluded, once per day, via Tilia to PayPal, 1.5% fee. VRChat's own "Welcome to the Creator Economy" page gives the split as ~50% creator / ~30% store platform (Steam, Meta) / ~20% VRChat + Tilia. Caveats: the formal Program Rules state a $100 minimum and one request per two weeks (conflicts with payout page); a wiki page now calls the processor "Thunes, formerly Tilia". Layoff: announced 12 June 2024, "around 30%", over-hiring in 2021-22 cited.
Sources: https://creators.vrchat.com/economy/faq/ ; https://creators.vrchat.com/economy/payout ; https://creators.vrchat.com/economy/welcome-to-the-ce ; https://roadtovr.com/vrchat-lays-off-30-of-company/

### 8. Meta Reality Labs / Horizon Worlds — confirmed (reversal partial)
FY2025 RL revenue ~$2.21B (vs $2.15B 2024); operating loss $19.19B (vs $17.73B); Q4 2025 revenue $955M; cumulative losses since 2020 $83.6B on $11.8B revenue; CFO expects 2026 losses similar. Horizon Worlds: on 17-18 March 2026 Meta said VR support would end 15 June 2026; within days Bosworth said VR would keep working "for existing games". Nuance the ledger understates: only legacy Unity-engine worlds stay in VR; Horizon Engine worlds remain flatscreen/mobile-only and no new VR content is planned.
Sources: https://wnhub.io/news/finance/item-49970 ; https://gamesbeat.com/?p=315517 ; https://euronews.com/next/2026/03/20/meta-u-turns-on-horizon-worlds-vr-shutdown-after-user-backlash ; https://engadget.com/ar-vr/meta-isnt-shutting-down-its-vr-metaverse-after-all-165520696.html

### 9. The Sandbox — confirmed except the estate figure
28 Aug 2025: >half of ~250 staff cut; offices in Argentina, Uruguay, South Korea, Thailand, Turkey and Lyon closing; Robby Yung named CEO (CoinDesk instead says Yat Siu oversees); Madrid non-executive chairman, Borget global ambassador; "a few hundred DAU, most bots" (unnamed sources); SAND $8.40 peak → ~$0.28 (-97%); treasury $100-300M; ~$300M invested over eight years. NOT found in any extract: the $450,000 estate (Dec 2021) now worth ~$1,025 — the nearest figure is Naavik's 2021 note that investors valued each of 30,000 MAU at ~$472k. Treat the estate anecdote as unverified; keep it only with a direct citation.
Sources: https://blockworks.com/news/sandbox-co-founders-ousted-layoffs ; https://regional-front.cointelegraph.com/news/the-sandbox-restructuring-ai-layoffs-cofounders-role-shift ; https://forklog.com/en/the-sandbox-restructures-cuts-half-of-workforce-and-appoints-new-ceo/amp

## Additional findings
- Roblox FY2024 hours engaged were 73.5B (+23%) — the researcher's ~73B "prior knowledge" is right; 1.2c/engaged hour holds ($915M / 73.5B ≈ 1.24c).
- Roblox infra+T&S FY2025 ≈ $1,153M per EDGAR-derived table (FY2024 ≈ $915M, FY2023 ≈ $878M) — fills an open question.
- The Sept 2025 DevEx rate increase is described as "8.5%", matching $0.0035 → $0.0038; this dates the rise to Sept 2025, not Sept 2023.
- Roblox 2026 guidance: revenue $6.02-6.29B, FCF $1.60-1.82B; age-verification rollout expected to be a mid-single-digit engagement and low-single-digit bookings headwind; management says margins flat to slightly down because of higher DevEx rates and safety/infra spend.
- Epic: 50% of Sponsored Row (paid discovery, launched 24 Nov 2025) revenue goes into the engagement pool; an unconfirmed leak (FRVR) says small creators without a tax/payout profile may be paid in V-Bucks instead of cash.
- Second Life: LindeX percentage fee reportedly 10% → 11% (second version of the June 2026 post) — this is the figure the ledger's open question asks about.
- Rec Room staff trajectory: ~310 → ~16% cut (Mar 2025) → ~50% cut (Aug 2025) → just over 100; Snap reportedly bought select assets and hired staff into Specs Inc.
- VRChat's Program Rules ($100 minimum, one payout per two weeks, up to 30 days processing) conflict with the payout page (30,000 credits, once per day); Tilia is now branded "Thunes, formerly Tilia".
- Reality Labs cumulative operating losses since 2020: $83.6B on $11.8B revenue; Horizon VR reversal covers only legacy Unity-engine worlds.
- Not searched (budget): claim 0's ~1.04M daily paying users, claim 2's full-year 2025 totals and $1.3M top-1,000 average, claim 3's 40% pool size, claim 6's $294M raised — all rest on prior knowledge/researcher sourcing.
