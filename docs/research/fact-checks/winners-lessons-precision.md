# Precision check: "What the winners did right" brief

**Checked:** 2026-10-09. **Lens:** precision (numbers, dates, names, attributions, source support).

## Verification status (read first)

No claim in this report was live-verified. Two independent blockers:

1. The session-wide WebSearch budget (200 calls, shared by every agent in the turn) was already exhausted when this checker ran. The tool refused every query.
2. The sandbox agent proxy answered **403 to CONNECT** for every primary-source host required: `ir.roblox.com`, `create.fortnite.com`, `en.wikipedia.org`, `na.finalfantasyxiv.com`, `discord.com` (confirmed via `curl $HTTPS_PROXY/__agentproxy/status`, which lists repeated `connect_rejected` entries for these hosts). WebFetch failed with `ENOTFOUND` for all ten URLs.

Per the harness rules I did not route around the limits via curl, archives or reader proxies. Every verdict below is therefore **unverifiable** for this run. The "assessment" lines record the checker's prior knowledge (cutoff mid-2026), labeled as such, so a later pass with network access knows which items are at risk. Nothing here should be quoted externally until fetched.

## Claims

| # | Claim | Verdict | Assessment (knowledge-based, NOT fetched) |
|---|---|---|---|
| 0 | Roblox Q2 2025: 111.8M DAU, 27.4B hours (quarter ended June 30, 2025) | unverifiable | Consistent with my recollection of the July 31, 2025 release (DAU +41% YoY, hours +58%, revenue ~$1.08B, bookings ~$1.44B). Cited URL is the correct press-release page pattern. Low risk. |
| 1 | DevEx $741M (2023), $923M (2024), +25%; rate $0.0038/Robux since Sept 2023 | unverifiable | Figures match my recollection of Roblox's FY2024 letter ("creators earned $923M, up 25%"); 923/741 = +24.6%, so "+25%" is a fair rounding. DevEx rate rose from $0.0035 to $0.0038 (an ~8.5% increase) with a Sept 2023 effective date and a 30,000 Robux minimum cash-out. **Source-support risk:** the FY2024 press release gives the payout totals; the DevEx rate and effective date are documented on create.roblox.com DevEx docs / the 2023 creator-economics blog, not in the IR release. |
| 2 | UEFN + Creator Economy 2.0 launched March 22, 2023; 40% net-revenue pool; $320M paid in 2023 | unverifiable | Launch date (GDC State of Unreal, March 22, 2023) and the 40% pool are consistent with my knowledge. The **$320M 2023 payout cannot be in the cited March 2023 launch article**; Epic disclosed it a year later (GDC/State of Unreal, March 2024, "paid $320M to island creators in 2023"). Claim is likely accurate, but the citation does not support the payout figure. Needs a March 2024 Epic source. |
| 3 | Astronomical: April 23, 2020; 12.3M concurrent at first show; 27.7M unique across five shows | unverifiable | Matches Epic's own statements (five shows April 23-25, 2020; 12.3M concurrent; 27.7M unique players participating 45.8M times). Low risk. |
| 4 | Rockstar announced Aug 11, 2023 that Cfx.re joined Rockstar; RP monetization policy allows subscriptions/cosmetics, bans loot boxes | unverifiable | The Aug 11, 2023 Newswire date is consistent with my knowledge. **Attribution risk:** the monetization rules were NOT part of the Aug 11 announcement; they come from Rockstar's separate "Roleplay Community Guidelines" update (published later, around Nov 2023), which permit server-access subscriptions, queue priority and cosmetics and prohibit loot boxes, real-money gambling and pay-to-win. The claim conflates two documents/dates. |
| 5 | Minecraft 300M copies (Oct 15, 2023); Microsoft bought Mojang Sept 15, 2014 for $2.5B | unverifiable | 300M was announced at Minecraft Live on Oct 15, 2023. The Mojang deal was **announced** Sept 15, 2014 and **closed** Nov 6, 2014; the claim says "acquired on Sept 15" which is the announcement date. Minor wording precision only. |
| 6 | FFXIV 30M registered (Jan 2024); lottery housing in patch 6.1 (April 2022); 45-day auto-demolition | unverifiable | 30M registered-player milestone announced at the Tokyo Fan Festival (Jan 2024); patch 6.1 released April 12, 2022 and introduced the lottery; 45 days of cumulative inactivity triggers demolition (timer is periodically suspended by SE). **Source-support risk:** the Lodestone housing guide documents lottery and demolition but not the 30M player count, which is from SE press/Fan Fest. |
| 7 | Zepeto 400M+ cumulative users, ~70% female, ~70% Gen Z; ~$150M led by SoftBank Vision Fund 2 in Nov 2021 at ~$1B valuation | unverifiable | 300M (2022) / 400M (2023) cumulative-user company claims and the ~70% female / ~70% Gen Z / 95% overseas demographics match Naver Z's marketing. **Figure risk:** the Nov 30, 2021 round was reported in KRW (about 220 billion won); USD conversions in press ranged roughly $150M-$190M, and SoftBank Vision Fund 2's own share was reported as ~200 billion won. Lead investor, month and >1 trillion won (~$1B) valuation are consistent; the "$150M" figure should be cited to a specific outlet with its conversion. |
| 8 | Discord 200M+ MAU (2024-25); Activities/Embedded App SDK March 2024; Social SDK March 2025 | unverifiable | Embedded App SDK public launch March 18, 2024 (Activities themselves existed in beta since 2021); Discord Social SDK announced at GDC, March 2025; "more than 200 million monthly active users" is Discord's own wording in 2024-2025 materials. **Source-support risk:** discord.com/developers/docs will not state MAU; cite discord.com/company or the Social SDK launch post. |
| 9 | Habbo launched Aug 2000; 273M+ avatars by 2012; Origins (2005-client recreation) launched June 2024 | unverifiable | Habbo (Hotelli Kultakala) opened in Finland in August 2000; the "273 million avatars created" figure is what the Wikipedia article cites circa 2012; Habbo Hotel: Origins (recreation of the 2005 Shockwave-era client) launched publicly in June 2024 after a spring beta. Consistent with my knowledge; low risk. |

## Summary of precision issues to fix (pending fetch)

- **[2]** Cite Epic's March 2024 disclosure for the $320M figure; the 2023 UEFN launch post cannot contain it.
- **[4]** Separate the Aug 11, 2023 acquisition announcement from the later Roleplay Community Guidelines (monetization rules).
- **[5]** "Announced" Sept 15, 2014; closed Nov 6, 2014.
- **[6], [8]** Headline user counts are not on the cited product/docs pages; cite the press or company pages.
- **[7]** Funding amount is a KRW-to-USD conversion; quote the won figure and the outlet.

## Additional findings relevant to a Second Life successor (knowledge-based, unverified)

- Roblox's Q3 2025 jump (the brief cites ~151.5M DAU) was driven by a handful of viral UGC titles; the platform's concurrency and DAU are therefore hit-dependent, which is the same fragility a successor should design around with evergreen social loops.
- Second Life's own economy is the missing comparator: Linden Lab has historically reported roughly $60M-$80M/year in creator cash-outs (USD paid out through the LindeX), i.e., a per-user creator payout far higher than Roblox's, which is the exact strength the brief says is "unserved at scale." A successor plan should quantify this against DevEx.
- Epic's Creator Economy 2.0 pool pays by engagement, which rewards retention/new-player acquisition rather than in-world sales; this has drawn creator complaints that Epic's first-party modes dominate the pool. A successor should publish the formula and exclude first-party content from the creator pool.
- Rockstar's RP guidelines prohibit real-money cash-out and real-money gambling; FFXIV bans real-money venues; Roblox restricts cash-out to verified DevEx participants (13+, with ID). The "verified-adult cash-out tier" the brief proposes has no direct precedent among the winners and will need its own compliance design (KYC, money-transmission licensing, tax reporting), which Second Life/Tilia already built; that infrastructure history is worth studying rather than re-inventing.

## Sources

None fetched in this run (proxy 403 on all hosts; search budget exhausted). URLs that must be fetched on the next pass:

- https://ir.roblox.com/news/news-details/2025/Roblox-Reports-Second-Quarter-2025-Financial-Results/default.aspx
- https://ir.roblox.com/news/news-details/2025/Roblox-Reports-Fourth-Quarter-and-Full-Year-2024-Financial-Results/default.aspx
- https://create.roblox.com/docs/production/earning-on-roblox (DevEx rate)
- https://create.fortnite.com/news/introducing-unreal-editor-for-fortnite (launch) and Epic's March 2024 "State of Unreal"/ecosystem post ($320M)
- https://en.wikipedia.org/wiki/Astronomical_(concert)
- https://www.rockstargames.com/newswire (Aug 11, 2023 Cfx.re post and Roleplay Community Guidelines)
- https://en.wikipedia.org/wiki/Minecraft
- https://na.finalfantasyxiv.com/lodestone/playguide/contentsguide/housing/ and SE 30M-player announcement
- https://en.wikipedia.org/wiki/Zepeto (and the Nov 2021 funding coverage in KRW)
- https://discord.com/company ; https://discord.com/developers/docs
- https://en.wikipedia.org/wiki/Habbo
