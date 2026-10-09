# Search verification: successors-wave2-metaverse

Checked 2026-10-09 against the ledger at `scratchpad/analysis/ledger-successors-wave2-metaverse.json`.

## Method note

- 12 of 12 WebSearch calls used (standard mode throughout; none returned empty). Budget is now exhausted.
- Page fetching (WebFetch/curl) is blocked in this sandbox, so every verdict rests on the quoted extracts the search tool returned, not on the full articles. Where a claim bundles several facts, I searched the parts carrying numbers, dates or 2026 status; the remaining parts are marked "not searched (prior knowledge)" inside the note, and the earlier no-search checkers' agreement is recorded but not treated as evidence.
- All 10 claims were searched (two got a second search: claim 4 on DappRadar's revised figure, claim 6 on Rec Room's margin disclosure).

## Verdict table

| # | Claim (short) | Verdict | Key support |
|---|---|---|---|
| 0 | WSJ Oct 2022: Horizon <200k MAU, 500k goal cut to 280k, 9% of worlds hit 50 visitors | confirmed | The Block / CNBC / PYMNTS 15 Oct 2022 |
| 1 | Reality Labs Q1 2026 -$4,028M/$402M, Q2 2026 -$4,619M/$431M, H1 -$8,647M; Q4 2025 -$6.02B/$955M | confirmed | Shacknews, GadgetReview, vr.org on the late-July 2026 Q2 report; 10-Q not fetched; Q4 2025 part is prior knowledge |
| 2 | March 2026 Horizon VR shutdown (15 June) reversed by Bosworth within ~48h, only for Unity worlds | confirmed | Gigazine 20 Mar 2026, vr.org, UC Today; 31 Mar delisting date not in extracts |
| 3 | AltspaceVR closed 10 Mar 2023; Mesh retired 1 Dec 2025; Teams immersive events 16 vs Mesh 330 | confirmed (caveat) | The Register 2 Dec 2025, Computerworld, THE Journal; 16 = standard immersive meetings, event cap not found; AltspaceVR part prior knowledge |
| 4 | DappRadar 38 DAU (Sandbox 522), Decentraland ~8,000 DAU / 56,697 MAU, recalculated to ~650 | corrected | Nasdaq "Final Word": revised figure was 775, not ~650; all other elements confirmed |
| 5 | Sandbox Aug 2025: >half of ~250 cut, five countries, founders sidelined, DAU few hundred, $350M 2021 land, ~$300M raised | confirmed (caveats) | Blockworks, CCN, Forklog citing The Big Whale; DAU and $300M are single-source; add Robby Yung as CEO |
| 6 | Rec Room: $3.5B, 16% cut Mar 2025, ~half (141) Aug 2025, 30c vs 70c, +70% UGC, announced 31 Mar 2026 shutdown for 1 Jun 2026 | corrected | Announced 30 Mar 2026 (TechCrunch dated 31 Mar); 1 Jun noon PT confirmed; margins confirmed from Rec Room's own blog (28 Aug 2025) |
| 7 | VRChat 30% layoff Jun 2024; 148,886 on 1 Jan 2026; 158,192 at Feb 2026 Japanese concert | confirmed | VRChat wiki, UploadVR, Road to VR (corrected from 156,716), Mogura VR May 2026; layoff part prior knowledge |
| 8 | Otherdeed: 55,000 x 305 APE (~$5,800) = ~$317M, ~$172M gas; Oct 2023 layoffs; "Yuga lost its way" | confirmed (range) | The Block, Fortune, DappRadar; gas $123M (Fortune/Etherscan) to ~$172M (The Block) to ~$200M; Yuga aftermath prior knowledge |
| 9 | IDC/FT ~390,000 Vision Pro in 2024; Oct 2024 production cuts; Luxshare halt early 2025; Apple silent | confirmed | Slashdot summary of FT/IDC (1 Jan 2026): 390k in 2024, halt at start of 2025, 45k expected Q4 2025; Digitimes dates the halt as early as Nov 2024 |

## Per-claim notes

### 0. WSJ / Horizon Worlds, October 2022 -- confirmed
Extracts from The Block, CNBC and PYMNTS (all 15 Oct 2022, citing WSJ internal documents): under 200,000 MAU; 500,000 year-end target cut to 280,000; most users did not return after the first month; base shrinking since spring; 9% of worlds visited by 50 or more people, most never visited. Threshold wording varies slightly by outlet ("at least 50", "more than 50", "as many as 50"). Extra detail not in the brief: under 1% of users built worlds and the top-earning world had taken only ~$10,000.
Source: https://www.theblock.co/post/177471/meta-falls-short-of-user-goal-for-horizon-worlds-wsj ; https://www.cnbc.com/2022/10/15/meta-horizon-worlds-metaverse-losing-users-falling-short-of-goals.html

### 1. Reality Labs 2026 financials -- confirmed
Several outlets covering Meta's late-July 2026 Q2 report give Q2 2026 operating loss $4.619B on $431M revenue (revenue +16.5% YoY from $370M, credited to AI glasses with Quest sales down; loss narrower than the $5.07B consensus) and Q1 2026 loss $4.028B. H1 = $8,647M follows. The 10-Q could not be fetched; Q4 2025 (-$6.02B on $955M) was not searched and rests on prior knowledge (both earlier checkers held it at high confidence). Cumulative tallies in the coverage range from $83.6B to ~$88B, so "~$88B" must be labelled a media estimate.
Source: https://www.shacknews.com/article/150184/facebook-meta-reality-labs-q2-2026-losses ; https://vr.org/articles/meta-reality-labs-q2-2026-earnings-loss-widens-88-billion

### 2. March 2026 Horizon VR shutdown and reversal -- confirmed
Mid-March 2026 announcement (17 or 18 March depending on outlet): from 15 June users could no longer build, publish, update or access Horizon Worlds on Quest. Bosworth reversed on 19 March (Instagram Q&A; also on Threads): "We've decided to retain existing Horizon Worlds in VR for the foreseeable future", crediting fan pushback; no new VR content development, mobile remains the primary focus, VR version in maintenance. vr.org confirms the split: existing games on the legacy Unity engine continue in VR, Horizon Engine worlds remain flatscreen-only. Not found in extracts: the 31 March Quest-store delisting date (still single-sourced). Context: January 2026 layoffs cut ~1,500 Reality Labs employees.
Source: https://gigazine.net/gsc_news/en/20260320-meta-reverses-horizon-worlds-vr-support-end ; https://vr.org/articles/meta-horizon-worlds-vr-shutdown-reversal-mobile-pivot

### 3. AltspaceVR and Mesh -- confirmed with caveat
Mesh: standalone platform retired 1 Dec 2025 (Mesh PC/Quest apps, mesh.cloud.microsoft, and the Teams "Immersive space (3D)" view all ended); replaced by "immersive events" in Teams on Windows, macOS and Quest; organiser needs a commercial Teams licence plus Teams Premium. The Register: Mesh supported up to 330 participants in Unity-built environments; "immersive meetings in Teams currently support up to 16 participants in standard sessions". No explicit cap for large immersive events appeared, so the brief should say "16 in standard immersive meetings" rather than imply events are capped at 16. AltspaceVR (announced Jan 2023 with 10,000 layoffs, closed 10 Mar 2023) was not searched: prior knowledge, high confidence. The cited Teams blog cannot support the AltspaceVR part; cite a 2023 source for it.
Source: https://www.theregister.com/2025/12/02/microsoft_mesh_axed/ ; https://www.computerworld.com/article/4100319/microsoft-retires-mesh-app-launches-immersive-spaces-for-teams.html

### 4. Decentraland 38 DAU -- corrected
Correct value: DappRadar's revised Decentraland figure was **775**, not ~650 (Nasdaq: "38 (Original), 775 (Revised)"); two searches found no source for 650. Everything else confirmed: CoinDesk 7 Oct 2022 via DappRadar, Decentraland 38 vs Sandbox 522, metric = unique wallets interacting with the platform's smart contracts; Sam Hamilton countered with ~8,000 daily users on average and 56,697 September MAU; CoinDesk 11 Oct reported DappRadar recalculating, and DappRadar renamed the metric "Unique Active Wallets". Decentraland's own definition (users moving between parcels) gives ~60,000 MAU.
Source: https://www.nasdaq.com/articles/the-final-word-on-decentralands-numbers ; https://dev.coindesk.com/web3/2022/10/11/dappradar-says-its-recalculating-decentraland-user-data

### 5. The Sandbox, August 2025 -- confirmed with caveats
Blockworks, CCN, Forklog and syndicated CoinDesk (all citing The Big Whale, 28 Aug 2025): more than half of ~250 staff cut (250 was the start-2025 headcount; exact number undisclosed); affected teams in Argentina, Uruguay, South Korea, Thailand, Turkey plus the Lyon office closing; Borget to "ambassador", Madrid to "chairman", no executive powers; Animoca's Robby Yung appointed CEO under majority shareholder Animoca (Yat Siu). "A few hundred DAU, many reportedly bots" and "about $300M raised" appear but are The Big Whale's single-source figures and should be attributed, not stated flat. The "$350M of 2021 land sales" was not in extracts (prior knowledge).
Source: https://blockworks.com/news/sandbox-co-founders-ousted-layoffs ; https://www.ccn.com/news/crypto/the-sandbox-cuts-half-staff-firms-flee-metaverse/

### 6. Rec Room -- corrected (announcement date)
Correct value: shutdown announced **30 March 2026** (most outlets; the TechCrunch piece is dated 31 March), servers offline 1 June 2026 at noon PT. Confirmed timeline: new accounts, friend requests and RR+ sign-ups stopped immediately; token purchases and gift-card redemption end 1 May; creator token rewards end 18 May; final creator payout 1 June; refund window 1 May to 15 June. Company statement: costs exceeded revenue despite 150M+ lifetime players; cited weaker VR market and Meta's shift away from VR gaming. Margins confirmed from Rec Room's own 28 Aug 2025 post "Rec Room Finances and UGC Revenue": ~70 cents kept per first-party dollar after platform fees vs ~30 cents per UGC dollar after platform fees and creator cuts; UGC growing ~70% YoY; same FAQ said no debt and runway "probably into 2029". Aug 2025 ~half layoff confirmed (Road to VR); the March 2025 16% and the 141-position count were not in extracts (prior knowledge); $3.5B valuation is prior knowledge (Dec 2021). New: Snap acquired select Rec Room assets and hired some staff into its Specs Inc. subsidiary; the platform is not continuing.
Source: https://roadtovr.com/rec-room-shutdown-snap-acquisition-2026/ ; https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue ; https://roadtovr.com/rec-room-layoff-half-staff-august-2025/

### 7. VRChat records -- confirmed
148,886 concurrent on New Year's Eve 2025/26 at the Central Time ball drop (VRChat wiki, UploadVR), against normal weekend peaks of 120-125k. 158,192 at a February Japanese-language concert featuring Kaguya, corrected by VRChat's community head from an initially reported 156,716 (Road to VR); Mogura VR (May 2026) lists 158,192 as the all-time high. Caveat: sources differ on whether 158,192 is platform-wide or event-level, and VRChat publishes no official figures. The June 2024 ~30% layoff with Gaylor's reasons was not searched (prior knowledge, high confidence).
Source: https://roadtovr.com/vrchat-key-stats-japan-growth-concurrents/ ; https://wiki.vrchat.com/wiki/VRChat_anniversary ; https://www.moguravr.com/vrchat-concurrent-users-record-2026/

### 8. Otherdeed mint -- confirmed (gas as a range)
55,000 Otherdeeds at 305 APE each (~$5,800 at $19/APE per Fortune), sold out within ~3 hours of the 30 Apr 2022 9pm ET public sale; 16.7M APE, ~$317M (The Block; ~$320M elsewhere); APE-only with KYC; proceeds locked one year; 45,000 further parcels to BAYC/MAYC holders and Yuga. Gas: The Block's on-chain analysis ~$172M, Fortune/Etherscan $123M, other estimates ~$200M; give as $120M-$200M with $172M attributed to The Block. Oct 2023 layoffs and Solano's April 2024 "Yuga lost its way" not searched (prior knowledge, high confidence).
Source: https://www.theblock.co/linked/144549/otherside-land-nfts-sell-out-in-hours-as-yuga-labs-rakes-in-317-million ; https://fortune.com/2022/05/01/bored-ape-metaverse-frenzy-raises-millions-crashes-ethereum

### 9. Vision Pro shipments -- confirmed
Slashdot's 1 Jan 2026 summary of the FT: IDC estimates ~390,000 units shipped in the 2024 launch year, Luxshare halted production at the start of 2025, ~45,000 units expected in Q4 2025. Apple has never published sales. Timing caveat: Digitimes (Oct 2024) quoted a Luxshare source saying production might stop by Nov 2024 with daily output already under 1,000 (from 2,000), so "early 2025" is IDC's framing. The Information's Oct 2024 cut was not directly in extracts but matches contemporaneous coverage. The brief's BoF URL is a 2024 production-cut story and cannot carry the IDC figure; cite the FT/IDC piece. Context from the earlier checker stands: an M5 Vision Pro refresh shipped Oct 2025, so the halt was of the original model.
Source: https://apple.slashdot.org/story/26/01/01/189219/idc-estimates-apple-shipped-just-45000-vision-pros-last-quarter ; https://www.digitimes.com/news/a20241025PD219.html

## Additional findings relevant to designing a successor world

1. Rec Room closed with cash and no debt (runway "into 2029" per its Aug 2025 FAQ), after narrowing from "everyone can create" to top PC creators; the March 2026 shutdown was a judgement that UGC unit economics could not reach profitability. Runway is not safety when UGC margin is structurally below first-party margin.
2. The 30c/70c margin and 70% UGC growth come from Rec Room's own blog, a primary source; cite it directly.
3. WSJ 2022: under 1% of Horizon users built worlds and the top world earned ~$10,000, so creator supply failed alongside visitor retention.
4. Reality Labs Q2 2026 revenue grew on AI glasses while Quest fell; one report says ~70% of RL spend is moving to glasses/wearables. VR-first distribution is being defunded by its biggest backer.
5. Horizon VR survives only for legacy Unity worlds; Horizon Engine content is flatscreen/mobile-only.
6. Teams immersive events need Teams Premium for the organiser; enterprise "metaverse" persists only as a paid add-on inside an existing product, with 16-person standard sessions.
7. The Decentraland dispute was definitional (wallet-contract interaction vs parcel movement; revised 775 vs self-reported ~8,000); a successor world should publish its active-user definition.
8. The Sandbox under Animoca pivoted to a memecoin launchpad on Base and framed the cuts as "leaner team enabled by AI tools".
9. Otherdeed: ApeCoin fell ~70% after the sale because it was the sole purchase currency; proceeds were locked a year.
10. VRChat's record came at a Japanese concert; Japan is the growth engine for the one surviving social VR world.
11. Vision Pro: ~45,000 units expected in Q4 2025 after ~390k in 2024.
