# Precision check: "The 2016-2026 metaverse wave" brief

Checked: 2026-10-09. Brief: scratchpad/research/successors-wave2-metaverse.md

## Method and limitation (read first)

- Attempted a direct WebFetch of all ten cited sources: every one failed with DNS `ENOTFOUND` (cnbc.com, sec.gov, euronews.com, techcommunity.microsoft.com, coindesk.com x2, techcrunch.com, roadtovr.com, theblock.co, businessoffashion.com). A direct curl via the sandbox proxy returned `CONNECT tunnel failed, 403`.
- Attempted WebSearch for each claim: the shared per-turn search budget was already exhausted (200 calls), so no search ran.
- Verdicts below therefore rest on (a) the checker's own knowledge, reliable for events up to roughly mid-2026 and firm for 2022-2024, (b) internal consistency of the figures, and (c) whether the cited URL is the kind of document that could contain the stated facts. Nothing was fetched. "Confirmed" means the checker independently knows the figures to be correct; "unverifiable" means they could not be checked live and the checker's recall is incomplete, even if nothing contradicts them.
- A follow-up with working fetch should prioritise: the Meta 10-Q (claim 1), the Euronews piece (claim 2), the Microsoft Teams blog (claim 3), the CoinDesk Sandbox piece (claim 5), TechCrunch Rec Room (claim 6), Road to VR VRChat (claim 7) and the BoF Vision Pro piece (claim 9).

## Verdicts

### [0] WSJ Oct 2022 Horizon Worlds figures -- CONFIRMED (from knowledge)
The WSJ (Horwitz/Rodriguez, 15 Oct 2022) reported, from internal Meta documents, fewer than 200,000 monthly users, an original end-2022 goal of 500,000 revised to 280,000, that most users do not return after the first month, that usage declined since spring, and that only 9% of worlds were ever visited by at least 50 people with most never visited at all. CNBC's same-day write-up (the cited URL, dated 2022/10/15) repeats these figures. All numbers, the date and the attribution match. Source: https://www.cnbc.com/2022/10/15/meta-horizon-worlds-metaverse-losing-users-falling-short-of-goals.html (not fetched).

### [1] Reality Labs Q1/Q2 2026 and Q4 2025 -- UNVERIFIABLE (Q4 2025 part confirmed)
- Q4 2025: operating loss $6.02B on $955M revenue, reported 28 Jan 2026, the segment's largest quarterly loss and FY2025 loss about $19.2B. Confirmed from knowledge.
- Q1 2026 ($402M revenue, $4,028M loss) and Q2 2026 ($431M, $4,619M; H1 $8,647M): the Q2 figures post-date the checker's knowledge and could not be fetched. The Q1 figures are in the right range (Q1 2025 was $412M / -$4,210M) and the arithmetic is internally consistent (4,028 + 4,619 = 8,647). The accession number format (0001628280-26-...) is the correct Workiva filer-agent pattern for Meta 10-Qs, so the URL is plausible.
- Source-support note: a Q2 2026 10-Q would not contain Q4 2025 figures; the brief correctly cites CNBC for Q4 separately, but the claim as bundled attributes all three quarters to the 10-Q.
Source: https://www.sec.gov/Archives/edgar/data/0001326801/000162828026050705/meta-20260630.htm (not fetched).

### [2] Horizon Worlds VR shutdown and 48-hour reversal, March 2026 -- UNVERIFIABLE (consistent with recall)
The checker recalls the sequence: Feb 2026 Meta said Worlds would become "almost exclusively mobile" and separate from the Quest platform; mid-March 2026 Meta told creators Worlds would leave the Quest store and end VR support, then Andrew Bosworth reversed within about two days, keeping VR for existing worlds only. The specific dates (delisting 31 March, VR end 15 June) and the Unity-vs-Horizon-Engine split could not be verified live. Nothing contradicts them; the researcher's own "medium" confidence is appropriate. Source: https://euronews.com/next/2026/03/20/meta-u-turns-on-horizon-worlds-vr-shutdown-after-user-backlash (not fetched).

### [3] AltspaceVR closure and Mesh retirement -- UNVERIFIABLE (AltspaceVR part confirmed; source-support concern)
- AltspaceVR: Microsoft announced the closure on 20 Jan 2023 alongside the 10,000-person layoff; service ended 10 March 2023. Confirmed from knowledge.
- Mesh: the checker recalls Microsoft announcing retirement of the Mesh Toolkit (June 2025) and of the Mesh apps / Teams "immersive space (3D)" effective 1 Dec 2025, replaced by Teams immersive events. Mesh events did support up to 330 attendees (multi-room). Whether "immersive events" are limited to 16 in a standard session could not be checked; 16 was the limit of the older Teams immersive space, so the number may have been carried over from the wrong product. Treat "16 vs 330" as plausible but unconfirmed.
- Source-support concern: the cited Microsoft Teams blog is a GA announcement for immersive events. It would not mention AltspaceVR, the 10 March 2023 date or the 10,000 layoffs; those parts of the claim rest on the brief's other sources (UploadVR, GamesBeat), not the cited URL.
Source: https://techcommunity.microsoft.com/blog/microsoftteamsblog/immersive-events-in-microsoft-teams-now-generally-available/4468628 (not fetched).

### [4] Decentraland 38 DAU episode -- CONFIRMED (minor caveat)
CoinDesk, 7 Oct 2022, using DappRadar: Decentraland 38 DAU, The Sandbox 522, in a ~$1.3B ecosystem; DappRadar's metric counts unique wallets interacting with the platform's smart contracts. Decentraland's Sam Hamilton countered with ~8,000 daily users and the Foundation blog gave 56,697 MAU for September 2022 (self-reported, "enter and move out of spawn" definition). DappRadar subsequently said it would recalculate and published a figure of about 650 daily users. All consistent with the checker's knowledge. Caveat: contemporaneous coverage variously quoted Hamilton's daily figure as ~7,000 or ~8,000 (the PC Gamer headline the brief also cites says 7,000); "~8,000" is defensible but not a single canonical number. Source: https://www.coindesk.com/web3/2022/10/07/its-lonely-in-the-metaverse-decentralands-38-daily-active-users-in-a-13b-ecosystem (not fetched).

### [5] The Sandbox August 2025 restructuring -- UNVERIFIABLE (consistent with recall)
The checker recalls The Big Whale / CoinDesk reporting in late Aug 2025 that The Sandbox cut roughly half of about 250 staff, closed several regional offices, that Animoca (Yat Siu) took direct control with the co-founders stepping back and Robby Yung installed as CEO, and that DAU had reportedly fallen to the hundreds (disputed by Animoca). The exact figures ("more than half", "five countries", "$350M land sales in 2021", "~$300M raised over eight years") could not be verified. One precision flag: Sandbox's public funding rounds (about $93M Series B in 2021 plus earlier rounds) sum to well under $300M; the "~$300M over eight years" figure likely includes land/token sales or is The Big Whale's own tally, and should be attributed as such rather than stated as a fact. Source: https://www.coindesk.com/business/2025/08/28/the-sandbox-cuts-50-staff-restructures-as-animoca-brands-take-control (not fetched).

### [6] Rec Room layoffs, UGC margin, shutdown -- UNVERIFIABLE (2025 parts consistent with recall)
- $3.5B valuation (Dec 2021 round): confirmed from knowledge.
- March 2025 16% cut and August 2025 roughly half (141 positions, per Washington WARN filing): matches the checker's recall.
- "30 cents per dollar on UGC vs 70 on first-party, UGC revenue +70% YoY": matches the checker's recall of Cameron Brown's August 2025 explanation as reported by Road to VR, which the brief cites separately. Note the TechCrunch URL cited for this claim is the shutdown story and may not contain the margin figures.
- Shutdown announced 31 March 2026, go-dark 1 June 2026: could not be fetched; the checker's recall of this is weak, so treat as unconfirmed pending fetch. The brief's three independent URLs (TechCrunch, GeekWire, Hypergrid Business) make fabrication unlikely.
Source: https://techcrunch.com/2026/03/31/social-gaming-platform-rec-room-once-valued-at-3-5b-is-shutting-down/ (not fetched).

### [7] VRChat 2024 layoffs and 2026 concurrency records -- UNVERIFIABLE (2024 part confirmed)
- June 2024: VRChat cut about 30% of staff; Graham Gaylor's post cited pandemic-era overhiring and that the company had shrunk year-over-year. Confirmed from knowledge.
- 148,886 concurrent on 1 Jan 2026 and 158,192 at a Japanese concert in Feb 2026: post-date reliable recall and could not be fetched. The trajectory is plausible (Jan 2025 peak was in the mid-130k range per third-party trackers). Precision flag: the cited Road to VR URL is the New Year's Eve piece and would not contain the February figure; that comes from the second Road to VR URL in the brief. Also note VRChat publishes no official metrics, so "record" figures are staff social posts or third-party API trackers, as the brief itself concedes.
Source: https://www.roadtovr.com/vrchat-new-record-new-years-eve-2025-2026/ (not fetched).

### [8] Otherdeed mint -- CONFIRMED (gas figure is one of several estimates)
30 April to 1 May 2022: 55,000 Otherdeeds sold in the public mint at 305 APE each (about $5,800 at the time), roughly $317M (The Block's headline figure). Gas: estimates in contemporaneous coverage ranged widely, roughly $120M-$200M depending on the window and ETH price used (commonly quoted: ~55,000 ETH, ~$157M-$176M); "$172M" sits inside that range but is not a canonical number and should be presented as "$150M-$180M by various estimates". Yuga Labs laid off staff in Oct 2023; co-founder Greg Solano returned as CEO in Feb 2024 and in his April 2024 restructuring note said "Yuga lost its way". All consistent. Source: https://www.theblock.co/linked/144549/otherside-land-nfts-sell-out-in-hours-as-yuga-labs-rakes-in-317-million (not fetched).

### [9] Vision Pro shipments and production cuts -- UNVERIFIABLE (source-support concern)
- Apple has never disclosed Vision Pro unit sales: confirmed.
- The Information reported in Oct 2024 that Apple had sharply cut production and could end production of the current model by late 2024; later reporting said Luxshare had wound down/halted assembly. Consistent with knowledge.
- "IDC via FT: ~390,000 units in 2024": the checker cannot confirm this exact figure. Published third-party estimates for 2024 clustered in the 400,000-500,000 range (Gurman: "fewer than 500,000"; IDC and Counterpoint estimates below that). 390,000 is plausible but should be marked as a single-source estimate until the FT piece is fetched.
- Source-support concern: the Business of Fashion URL is a syndicated Bloomberg story about the production cut. It is unlikely to contain the IDC/FT shipment estimate or the Luxshare halt, which post-date it. The claim bundles three different reports under one URL.
- Missed context (see additional findings): Apple shipped a refreshed M5 Vision Pro in Oct 2025 at the same $3,499 price, so "production halted" refers to the original M2 model, not the product line.
Source: https://www.businessoffashion.com/news/technology/apple-cuts-vision-pro-headset-prodcution/ (not fetched).

## Summary table

| # | Verdict | Key note |
|---|---------|----------|
| 0 | confirmed | All WSJ/CNBC figures and date correct |
| 1 | unverifiable | Q4 2025 confirmed; Q1/Q2 2026 figures internally consistent but not fetched |
| 2 | unverifiable | Sequence matches recall; exact dates not checked |
| 3 | unverifiable | AltspaceVR confirmed; Mesh 16-vs-330 unconfirmed; cited URL cannot support the AltspaceVR part |
| 4 | confirmed | 7,000 vs 8,000 daily figure varies by outlet |
| 5 | unverifiable | "$300M raised" likely includes land/token sales; attribute to The Big Whale |
| 6 | unverifiable | 2025 layoffs and margin figures match recall; cited URL is the shutdown story, not the margin source |
| 7 | unverifiable | 2024 layoff confirmed; 2026 records not fetched; cited URL does not contain the Feb figure |
| 8 | confirmed | Gas figure should be given as a range |
| 9 | unverifiable | 390k is a single estimate; cited URL predates and cannot support the IDC and Luxshare parts; M5 refresh omitted |

## Additional findings relevant to designing a successor world

1. Apple released an M5-based Vision Pro refresh on 22 Oct 2025 at the same $3,499 price. The "production halt" story is about the original model; Apple has not exited the category. A successor's hardware-exposure plan should assume a small but continuing premium-headset market, not a dead one.
2. Meta's cumulative Reality Labs operating losses exceeded $80B by end-2025 (FY2025 alone about $19.2B), and the January 2026 layoffs explicitly reallocated spend from VR to AI glasses. The capital that funded the 2021-2025 wave is gone; a successor must be built for capital efficiency, not subsidised growth.
3. The clearest surviving economic model is Roblox (DAU on the order of 100M+ in 2025, annual creator payouts around $1B, roughly 24-28% of spend reaching creators) and Fortnite/UEFN (40% of net revenue pool shared by engagement). Both pay creators from a platform-controlled currency with the platform keeping the majority, the inverse of Rec Room's 30-cent problem. A successor should model its take-rate on these, not on Rec Room's.
4. Second Life itself, the brief's actual predecessor, remains alive and profitable at Linden Lab with on the order of 200,000-plus monthly active users and a user-to-user economy in the hundreds of millions of dollars per year; it survived precisely because it was never VR-gated, never sold land as a token, and charged recurring land tier. Its failed VR successor Sansar (2017-2020, sold to Wookey) is the closest analogue to this brief's "VR-first" failure pattern and deserves its own postmortem.
5. VRChat's 2024-2026 growth is dominated by Japan (roughly a quarter of web visits by late 2025) and by concert-type events; its avatar economy runs largely through pixiv Booth (off-platform). Designing for VRM-compatible avatars and 100k-scale events is a concrete, evidence-backed requirement, as the brief says.
6. Measurement: every disputed figure in this brief (Horizon leaks, Decentraland 38-vs-8,000, Sandbox bot claims, VRChat staff posts) stems from platforms not publishing auditable activity metrics. The brief's recommendation of a public, defined DAU metric is the single highest-leverage trust feature.
