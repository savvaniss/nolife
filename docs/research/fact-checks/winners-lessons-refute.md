# Adversarial fact-check: "What the winners did right" brief

**Checked:** 2026-10-09. **Lens:** adversarial refutation. **Input:** scratchpad/research/winners-lessons.md

## Verification status (read first)

No claim could be live-verified. In this run:

- The shared WebSearch budget for the turn (200 calls across all agents) was already exhausted before this checker started; every WebSearch call returned "budget used up".
- WebFetch failed with DNS `ENOTFOUND` for every source host attempted: ir.roblox.com, corp.roblox.com, sec.gov, create.fortnite.com, unrealengine.com, en.wikipedia.org, na.finalfantasyxiv.com, rockstargames.com, discord.com, minecraft.net, habbo.com. Only api.github.com resolved, and it returned 403 without auth. The proxy status endpoint could not be read (blocked by the permission classifier).
- At least one fetch was attempted per claim (0-9). All failed.

Per the task rules, every claim therefore defaults to **unverifiable**. The "Checker's prior-knowledge note" under each claim is the checker's own recollection (knowledge through mid-2026), not evidence, and is given only to flag where a re-check should focus. Nothing below should be quoted externally until a run with working network re-fetches the primary sources.

---

## Claim-by-claim

### [0] Roblox Q2 2025: 111.8M DAU, 27.4B hours (quarter ended June 30, 2025)
- **Verdict:** unverifiable (fetch of ir.roblox.com Q2 2025 release failed; search budget exhausted).
- **Checker's prior-knowledge note:** Consistent with the Q2 2025 release of July 31, 2025 as recalled (DAU 111.8M +41% YoY, hours 27.4B +58%, bookings ~$1.44B, revenue ~$1.08B). No contradiction expected; the number is company-reported and should be cited as such.
- **Re-check at:** https://ir.roblox.com/news/news-details/2025/Roblox-Reports-Second-Quarter-2025-Financial-Results/default.aspx ; the 8-K exhibit at sec.gov (CIK 0001315098).

### [1] DevEx payouts $741M (2023) and $923M (2024, +25%); rate $0.0038/Robux since Sept 2023
- **Verdict:** unverifiable (fetch of Q4/FY2024 release failed).
- **Checker's prior-knowledge note:** $923M for 2024 (+25%) and $741M for 2023 match recollection of Roblox's FY releases. The rate increase from $0.0035 to $0.0038 per Robux was announced at RDC in September 2023 and took effect around then; 100,000 Robux = $380 is arithmetic on that rate. One nuance the brief glosses: "DevEx payouts" in Roblox's releases is "earnings paid to developers/creators" and includes all DevEx cash-outs, not just game-pass revenue. Also worth checking whether Roblox's FY2025 release (Feb 2026) restated the series.
- **Re-check at:** https://ir.roblox.com/news/news-details/2025/Roblox-Reports-Fourth-Quarter-and-Full-Year-2024-Financial-Results/default.aspx ; https://create.roblox.com/docs/production/earning-on-roblox

### [2] UEFN + Creator Economy 2.0 launched March 22, 2023; 40% of net revenue pooled; $320M paid in 2023
- **Verdict:** unverifiable (fetches of create.fortnite.com and unrealengine.com failed).
- **Checker's prior-knowledge note:** Launch date March 22, 2023 (GDC) matches recollection. The pool is described by Epic as 40% of Fortnite's **net revenue from the Item Shop and most real-money purchases** (not literally all net revenue). The $320M figure for 2023 comes from Epic's 2024 ecosystem update (GDC/March 2024), not from the launch article the researcher cites, so the citation is misattributed even if the number is right. Engagement payouts in 2023 covered roughly nine months. Also, Epic's own islands (Battle Royale etc.) draw from the same pool, which was a point of creator complaint in 2024.
- **Re-check at:** https://create.fortnite.com/news/introducing-unreal-editor-for-fortnite ; https://create.fortnite.com/news (search "Fortnite ecosystem 2023").

### [3] Travis Scott "Astronomical" (April 23, 2020): 12.3M concurrent, 27.7M unique across five shows
- **Verdict:** unverifiable (Wikipedia fetch failed).
- **Checker's prior-knowledge note:** Matches Epic's own announcement as recalled: 12.3M concurrent at the April 23 premiere, 27.7M unique players over five shows (April 23-25), 45.8M total views. No contradiction expected. The "~$20M" earnings figure in the brief body is a Forbes estimate, not an Epic/Scott statement.
- **Re-check at:** https://en.wikipedia.org/wiki/Astronomical_(concert) ; Epic's Fortnite news post of April 2020.

### [4] Rockstar announced Aug 11, 2023 that Cfx.re joined Rockstar; RP servers may monetize via subscriptions/cosmetics, not loot boxes
- **Verdict:** unverifiable (FiveM Wikipedia and Rockstar Newswire fetches failed).
- **Checker's prior-knowledge note:** The Newswire post "Cfx.re is now a part of Rockstar Games" is dated August 11, 2023 as recalled. The monetization policy, however, was **not** part of that announcement: Rockstar published an updated roleplay-server policy later (recollection: November 2023), permitting subscriptions, cosmetics and donations and prohibiting loot boxes, real-money purchase of gameplay-affecting currency/items, gambling with real money and use of licensed/third-party IP. The claim bundles two events with different dates; the Wikipedia FiveM page may not carry the policy detail. Treat the date as applying to the acquisition only.
- **Re-check at:** https://www.rockstargames.com/newswire ; https://support.rockstargames.com (search "Roleplay and Cfx.re servers").

### [5] Minecraft 300M copies (announced Oct 15, 2023); Microsoft acquired Mojang Sept 15, 2014 for $2.5B
- **Verdict:** unverifiable (Wikipedia and minecraft.net fetches failed).
- **Checker's prior-knowledge note:** 300M "sold" was announced at Minecraft Live on October 15, 2023. The Microsoft/Mojang deal was **announced** September 15, 2014 and **closed** November 6, 2014; the brief's phrasing "acquired on Sept 15, 2014" should say "announced". $2.5B matches.
- **Re-check at:** https://en.wikipedia.org/wiki/Minecraft ; https://news.microsoft.com (Sept 15, 2014 release).

### [6] FFXIV 30M registered players (Jan 2024); lottery housing in patch 6.1 (April 2022); 45-day auto-demolition
- **Verdict:** unverifiable (Lodestone fetch failed).
- **Checker's prior-knowledge note:** 30M "registered players" (cumulative accounts, incl. free trial, not actives) was announced at Fan Festival Tokyo, January 2024. The lottery system shipped with patch 6.1 on April 12, 2022 (and had a well-known results bug at launch). Auto-demolition is 45 days without the owner entering the estate; note that Square Enix has suspended the demolition timer multiple times (COVID period, regional disasters), so it is not continuously enforced. The cited Lodestone housing guide documents the lottery and demolition rules but is not the source for the 30M figure; that needs a separate press/Lodestone news citation.
- **Re-check at:** https://na.finalfantasyxiv.com/lodestone/playguide/contentsguide/housing/ ; https://na.finalfantasyxiv.com/lodestone/news/ (Jan 2024).

### [7] Zepeto: 400M+ cumulative users, ~70% female, ~70% Gen Z; ~$150M raised Nov 2021 led by SoftBank Vision Fund 2 at ~$1B valuation
- **Verdict:** unverifiable (Wikipedia fetch failed). Flagged as **likely needs correction** on the funding amount.
- **Checker's prior-knowledge note:** Naver Z's Series B closed around November 30, 2021 at roughly **KRW 220 billion (about $180-190M)**, led by SoftBank Vision Fund 2 with HYBE, YG, JYP and others participating; the "$150M" figure circulated in pre-close reporting (Bloomberg) and understates the final round. Valuation of roughly KRW 1.2 trillion (~$1B) matches. "400M cumulative users" is a company claim from 2023; demographics (~70% female, majority Gen Z) are company marketing figures with no independent support. Also note Zepeto launched August 2018 under Snow Corp. and was spun out as Naver Z in May 2020.
- **Re-check at:** https://en.wikipedia.org/wiki/Zepeto ; https://naverz-corp.com/ ; SoftBank Group press release Nov 2021.

### [8] Discord 200M+ MAU (2024-2025); Activities/Embedded App SDK March 2024; Social SDK March 2025
- **Verdict:** unverifiable (Wikipedia and discord.com fetches failed).
- **Checker's prior-knowledge note:** Discord's public line "more than 200 million monthly active users" dates from 2024 and was repeated in 2025. The Embedded App SDK and public Activities launch was March 18, 2024; the Discord Social SDK was announced at GDC on March 17-18, 2025. The developer docs URL cited is a hub page, not a dated announcement; cite the Discord blog posts instead. The brief's October 2025 vendor breach (~70k government-ID images, via third-party support vendor) matches recollection; "teen-by-default from March 2026" is a company plan announced early 2026 and should be verified against discord.com/safety.
- **Re-check at:** https://discord.com/blog ; https://discord.com/developers/docs/discord-social-sdk/overview.

### [9] Habbo launched August 2000; 273M avatars by 2012; Habbo Hotel: Origins (2005 recreation) launched June 2024
- **Verdict:** unverifiable (Wikipedia and habbo.com fetches failed).
- **Checker's prior-knowledge note:** Habbo (as Hotelli Kultakala) launched in Finland in August 2000. The "273 million avatars created" figure is a Sulake claim from 2012 and counts registrations, not users (many people hold multiple avatars across hotels). Habbo Hotel: Origins launched in mid-2024 (recollection: open launch around June 2024 after a closed test) and recreates the 2005-era Shockwave client. Azerion took control of Sulake in 2020. Treat the Origins month as approximate until confirmed.
- **Re-check at:** https://en.wikipedia.org/wiki/Habbo ; https://www.habbo.com/origins ; Azerion press releases.

---

## Additional findings (checker's knowledge; not live-verified, relevant to the successor design)

1. Roblox's own "where the money goes" disclosure puts the creator share of each consumer dollar at roughly a quarter to under a third after app-store fees, and Roblox has publicly targeted raising creator earnings to over $1B TTM (stated at RDC, September 2025). A successor promising a 70% creator share must model app-store fees (30% on iOS/Android) that make 70% net impossible on mobile unless the platform absorbs them.
2. Epic's 40% engagement pool includes Epic's own first-party islands, which is why creator complaints about Battle Royale "competing" for the pool surfaced in 2024; a successor's engagement pool should exclude first-party content or publish it separately.
3. Rockstar's RP policy (late 2023) also bars servers from using assets from other Rockstar/Take-Two titles and from running real-money gambling; it is the clearest public template for a "roles-first" economy that stays legally safe, and the brief should cite the policy page, not the acquisition post.
4. FFXIV's 45-day demolition has been suspended repeatedly (pandemic, disasters), which shows a scarcity mechanic needs an explicit pause policy to avoid goodwill damage.
5. Second Life itself (missing from the brief): Linden Lab shipped an official mobile viewer in beta in 2024 and sold its Tilia payments business to Thunes in 2023; Linden Lab has been owned by a private investor group (Waterfield/Oberwager) since 2020. Any successor plan should account for Tilia-style money-transmitter licensing as a prerequisite for real-money cash-out.
6. Meta's Horizon Worlds pivoted to mobile and lowered its age floor in 2024-2025 while Reality Labs kept posting multibillion-dollar quarterly losses; this is the strongest recent evidence that "best graphics" alone does not create purpose, and it should be in the "what did not work" section.
7. Discord's October 2025 vendor breach and subsequent age-assurance rollout mean a successor cannot rely on Discord as its identity/age layer; own identity and age verification from day one.

## Method note

Fetch attempts per claim are listed above. Zero succeeded. The verdicts should be re-run in a session with WebSearch budget and working DNS; the "re-check at" URLs are the primary sources to use.
