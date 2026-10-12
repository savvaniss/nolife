# Constraints and requirements for a successor

**Summary.** nolife must be built inside constraints that did not exist when Second Life launched. Regulators now treat a self-declared birth date as worthless: the UK age-check duty has applied since 25 July 2025 ([Inforrm](https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/)), Brazil's ECA Digital since 17 March 2026 ([Demarest](https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/)), and the Roblox settlements fixed a six-band chat template backed by liquidated damages ([Roblox](https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat)). Card schemes, not governments, decide whether an adult economy can cash out. Hosting is cheap, roughly $0.002-0.005 per avatar-hour ([AWS](https://aws.amazon.com/gamelift/servers/pricing/)), but safety, payouts and staff are not, so persistence rent must carry the platform. The modal PC is an RTX 5070 ([Digital Citizen](https://www.digitalcitizen.life/nvidia-rtx-5070-most-popular-gpu-steam-hardware-survey-september-2026/)), VR is under 2% of Steam ([rec0ded88](https://rec0ded88.com/statistics/vr-gaming-headset-ownership/)), and 100-150 simulated avatars per cell is the envelope. Purpose comes from groups with a schedule, roles and scarcity, none of which Linden Lab measured. Thirty requirements, R1 to R30, follow, each with cause, evidence and test.

## How to read this document

This is the reader-facing version of sections 5 and 6 of the project's failure taxonomy. It is written from the project's research briefs on safety and regulation, business models, graphics, networking and community purpose, the four gap briefs, their fact-check verdicts and the three critiques; no new web research was done. Every number carries an inline citation to the page the project's search extracts surfaced. Page fetches were blocked throughout, so "verified" means a search extract matched the claim, not that the page was read. Where a search-backed checker corrected a brief, the corrected value is used; figures resting on prior knowledge or a single secondary site are labelled. The critiques were written against an earlier draft with different requirement numbers; their objections (persistence cannot be free, the currency must stay transferable between users, the platform's margin must be stated beside the creator take, borrowed constants need a test) are absorbed into the list below, which is reproduced word for word from the revised taxonomy.

The product under design is nolife. Its predecessor is Second Life, operated by Linden Lab.

## 1. Regulation and safety

### 1.1 Minors and age assurance: the dated obligations

The common thread of 2025-26 is that a date-of-birth field no longer counts as age assurance, and that evidencing compliance is itself a duty: every substantive Ofcom age-assurance fine has been paired with a second fine for failing to answer an information request ([xident](https://xident.io/blog/age-assurance-evidence-ofcom-information-request-second-fine-2026/)).

| Regime | In force | What it requires | Teeth |
|---|---|---|---|
| UK Online Safety Act | Age-check duty from 25 July 2025 ([Inforrm](https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/)) | "Highly effective" checks for pornographic and primary-priority content; applies to any user-to-user service reachable from the UK | Up to GBP 18M or 10% of turnover; a small adult service was fined GBP 50,000 ([The Register](https://www.theregister.com/2025/11/21/ofcom_osa_fine_undress/)) |
| EU DSA Article 28 guidelines | Published 14 July 2025 ([CMS](https://cms.law/en/fra/news-information/protecting-minors-in-the-digital-space)) | Verification for adult content, minors private by default, annual risk review; non-binding and exempting micro and small enterprises until they scale | Commission's supervisory yardstick |
| Australia under-16 ban | 10 December 2025 ([eSafety](https://www.esafety.gov.au/node/2109)) | Ten social platforms; Roblox and Discord exempt only as "primary purpose" games, a list eSafety says is not static | Designation risk for a world framed as social |
| Roblox state settlements (template) | April to September 2026 ([Bloomberg](https://www.bloomberg.com/news/articles/2026-04-21/roblox-settles-with-states-for-35-8-million-over-child-safety); [SDPB](https://www.sdpb.org/crime-courts/2026-07-13/roblox-settlement-yields-tighter-restrictions-over-8-million-for-south-dakota); [Kansas AG](https://www.ag.ks.gov/Home/Components/News/News/365/1292)) | Six age bands with adjacent-band chat by default; adult-to-under-16 contact only via verified connections ([Roblox](https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat)) | $35.8M for three states, $9.8M Kansas, liquidated damages on breach |
| Brazil ECA Digital | 17 March 2026 ([Demarest](https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/)) | Any service "likely to be accessed by minors" wherever operated; self-declaration rejected; parental tools; loot-box age gate ([Mayer Brown](https://www.mayerbrown.com/en/insights/publications/2026/04/enforcement-of-brazils-eca-digital-introduces-new-obligations-for-companies)) | Fines to R$50M |
| Indonesia PP Tunas | Enforceable March 2026, minimum age 16 ([AVPA](https://avpassociation.com/indonesia/)) | Roblox must verify every Indonesian user; unverified accounts lose communication ([Malay Mail](https://www.malaymail.com/news/world/2026/03/31/indonesia-summons-meta-google-for-failing-to-enforce-under16-age-limits-under-new-childprotection-law/214489)) | The template others will copy |
| Germany, Malaysia, India, Turkey | Various | JuSchG precautions and KJM-approved verification (single source) ([ungovr](https://law.ungovr.org/age/de)); Malaysia 16 ([Bernama](https://bernama.com/en/world/news.php?id=2573981)); India parental consent under 18 ([MediaNama](https://www.medianama.com/2025/01/223-data-protection-rules-2025-children-data-india/)); Turkey 15 ([JURIST](https://www.jurist.org/news/2026/04/turkiye-lawmakers-approve-bill-restricting-social-media-access-for-children-under-15/)) | Per-region thresholds, not one global gate |
| US app stores | Texas in force pending appeal; California AB 1043 from 2027 ([Pearl Cohen](https://www.pearlcohen.com/fifth-circuit-stays-injunctions-against-texas-app-store-accountability-act/); [Alston](https://www.alstonprivacy.com/california-enacts-digital-age-verification-law/)) | OS providers pass a declared age range, not a birth date ([Apple](https://developer.apple.com/forums/thread/810754)) | App clients must consume the signal |

Sources disagree on the South Dakota figure: the taxonomy's source says "over $8 million" while the same outlet's package figure is $15M over four years with $8.6M guaranteed, so the running total of Roblox settlements should be quoted as a range. Verification creates its own breach surface: Discord's support vendor exposed about 70,000 government-ID images ([The Record](https://therecord.media/discord-government-docs-exposed-breach)), which is why R21 forbids stored ID images. Embodied harassment remains unprosecutable; UK police concluded in 2024 that a virtual assault could not viably be charged ([LBC](https://lbc.co.uk/news/police-investigate-rape-metaverse)), so platform controls are the only layer (R23).

### 1.2 Adult content and the payment rail

Second Life's Adult gate is still a self-declared birth date, as it has been since 2012 ([Modemworld](https://modemworld.me/2012/07/10/ll-revises-sl-age-verification/)); residents in 2026 say "there is no official age verification in SL" ([SL forums](https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/)). No Linden statement on the Online Safety Act was found. VRChat verifies 18+ through Persona since January 2025 and bans pornography platform-wide ([VRChat wiki](https://wiki.vrchat.com/wiki/Age_Verification)), so a gated Adult district with a real economy has no studied precedent.

The binding constraint is the card schemes. In July 2025 Valve removed adult titles after acquirers cited Mastercard Rule 5.12.7; Mastercard denied evaluating any game ([TechCrunch](https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story)); itch.io deindexed all NSFW content ([TheSixthAxis](https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/)) and DLsite lost Visa and Mastercard ([Automaton](https://automaton-media.com/en/news/dlsite-disables-visa-mastercard-payment-after-attempt-to-outsmart-credit-card-companies/)). Visa's VIRP puts adult content (MCC 5967) in Tier 1 and Mastercard's AN 5196 requires uploader verification, pre-publication review and complaint handling ([LegitScript](https://www.legitscript.com/regulatory-and-card-brand-compliance/adult-escort-and-dating-merchants-are-your-practices-in-line-with-virp-updates/); [VerifyMy](https://verifymy.io/resources/regulation/card-brand-requirements)). Stripe prohibits adult content outright and Adyen restricts it ([Conduct Atlas](https://conductatlas.com/platform/stripe/stripe-restricted-businesses-list/adult-content-prohibition-and-restriction/); [Adyen](https://adyen.com/legal/list-restricted-prohibited)). The two outcomes on record: Tumblr's 2018 ban cost about 29% of page views within three months ([TNW](https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/)); OnlyFans reversed its 2021 ban within a week once scheme controls were agreed ([CBC](https://www.cbc.ca/lite/story/1.6148524)). Second Life and Tilia were not named in 2025, plausibly because the merchant category is "virtual currency" (unsearched). R22 is written to keep that position deliberately rather than by accident.

### 1.3 The currency, consumer law and tax

Any cash-out-able item combined with chance is gambling somewhere: Linden banned wagering on 25 July 2007 after inviting in the FBI ([TechCrunch](https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/)). Blockchain tokens forfeit Steam distribution ([TechRadar](https://www.techradar.com/news/steam-is-now-banning-all-games-that-engage-in-cryptocurrency-or-nft-trading)) and invite Howey analysis; the SEC's 2023 NFT orders still stand ([FKKS](https://advertisinglaw.fkks.com/post/102inw4/the-cats-out-of-the-bag-secs-theory-impacts-nft-industry)). On the consumer side, the CPC Network's March 2025 principles require fiat prices on paid currency and on items priced in it, exact-amount purchase without bundles and the 14-day withdrawal right, and a stipend paid in a currency also sold for cash gets no gameplay-only carve-out ([Linklaters](https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr); [Bird & Bird](https://www.twobirds.com/en/insights/2025/global/regulatory-spotlight-virtual-currency-vs-consumer-law-part-2)). Star Stable was the first target ([Forbrukertilsynet](https://www.forbrukertilsynet.no/eng-articles/national-consumer-authorities-and-commission-take-action-on-harmful-practices-in-the-gaming-industry)); BEUC asked for an outright ban on paid in-game currencies ([TechCrunch](https://techcrunch.com/2024/09/12/bad-credits-consumer-group-files-eu-suit-over-manipulative-payments-in-games-like-fortnite-and-minecraft-calls-for-a-ban)); the Digital Fairness Act is unpublished and expected in November 2026 ([Heuking](https://www.heuking.de/en/news-events/newsletter-articles/detail/digital-fairness-act-implementation-obligations-companies-need-to-prepare-for.html); [Slaughter and May](https://thelens.slaughterandmay.com/post/102m222/digital-fairness-act-european-commission-publishes-responses-to-consultation)). Tax: DAC7 obliges platform operators, including non-EU ones, to collect identity and payout data from EU sellers and report quarterly with no floor for services ([Fonoa](https://www.fonoa.com/blog/dac7overview)); the US 1099-K threshold reverted to more than $20,000 and 200 transactions ([IRS](https://irs.gov/newsroom/irs-issues-faqs-on-form-1099-k-threshold-under-the-one-big-beautiful-bill-dollar-limit-reverts-to-20000)), the trigger Linden already uses ([SL wiki](https://wiki.secondlife.com/wiki/Linden_Lab_Official:Required_Tax_Documentation_FAQ)).

### 1.4 AI inhabitants, likeness, biometrics and accessibility

EU AI Act Article 50 applies from 2 August 2026: a plain-language notice or persistent badge, never a generic "assistant" label, and agents must say on whose behalf they act; the marking duty for generative systems already on the market is deferred to 2 December 2026 under the Digital Omnibus ([Stephenson Harwood](https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/)). The NO FAKES Act advanced in committee in June 2026 ([GovTrack](https://www.govtrack.us/congress/bills/119/s4591)); BIPA and Colorado treat biometrics as consent-only ([FPF](https://fpf.org/blog/old-laws-new-tech-as-courts-wrestle-with-tough-questions-under-us-biometric-laws-immersive-tech-raises-new-challenges/)). Bots were 51% of web traffic in 2024 ([Imperva](https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/)), which is why R13 publishes bot share. The European Accessibility Act covers storefront and account flows from 28 June 2025 ([Osborne Clarke](https://www.osborneclarke.com/insights/eu-accessibility-act-time-start-implementation-projects-now)).

## 2. Unit economics

### 2.1 What things cost

| Line | Benchmark | Source |
|---|---|---|
| Simulation compute | $0.055-0.07 per vCPU-hour (GameLift c6i.large $0.109/h; Edgegap $0.00115/vCPU-minute) | [AWS](https://aws.amazon.com/gamelift/servers/pricing/); [Edgegap](https://edgegap.com/blog/announcement-offering-changes-for-2025) |
| Per avatar-hour | $0.002-0.005 before voice and persistence (derived) | same |
| Voice | EUR 0.29 per peak concurrent user per month | [ODIN](https://odin.4players.io/pricing) |
| Infrastructure plus trust and safety at scale | Roblox $915.4M in 2024 (~$0.92 per DAU per month, ~1.24 cents per engaged hour) and $1,153.5M in 2025 | [EDGAR tools](https://app.edgar.tools/companies/RBLX) |
| Same line, a less automated world | $1.5-3 per DAU per month (estimate) | [business-models brief] |
| Pixel streaming | Project Zero about $1.75 per streamed hour (unsearched); raw GPU floor about $0.53/h for a Linux g4dn.xlarge | [Gabmeister](https://thegabmeister.com/p/unreal-pixel-stream-aws/) |
| Consumer ceiling for streaming | $19.99/month with a 100-hour cap | [NVIDIA](https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now) |
| Paid acquisition | Mobile CPIs of $1-4 imply $75-300 per payer at 1-2% payer rates | [Liftoff](https://liftoff.ai/?p=34267) |

Sources disagree on Roblox's 2024 safety-and-infrastructure line: the FY2025 10-K table gives $915.4M, while summing the 2024 quarterly releases gives about $1.0B, so quote "roughly $0.9-1.0B" rather than a growth rate. Firestorm Zero, Linden's streamed browser viewer, closed within three months of launch in 2025 when the streaming provider forced a migration ([Modemworld](https://modemworld.me/2025/06/27/)), and Hathora, a game-hosting vendor, wound down in spring 2026 after an AI pivot ([GamesBeat](https://gamesbeat.com/?p=318174)): vendor risk, not price, is now the top infrastructure risk (R20).

### 2.2 What the platform keeps

| Platform | Creator share of consumer spend | Mechanism | Source |
|---|---|---|---|
| Rec Room | Platform kept 30c of a UGC dollar after store fees; shut down 1 June 2026 with runway to 2029 | 30% store fee first, then creator share | [Rec Room](https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue) |
| Roblox | ~25% of in-experience spend; DevEx $922.8M in 2024, more than $1.5B in 2025 | Engagement-weighted pool; 42% uplift on verified-adult spend from June 2026 | [SEC](https://www.sec.gov/Archives/edgar/data/1315098/000131509825000033/rblx-20241231.htm); [Quartr](https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf); [Roblox](https://about.roblox.com/newsroom/2026/04/roblox-fuels-high-fidelity-games-over-18-players-increases-qualifying-devex-rate-42) |
| Fortnite | 40% of net revenue into a pool; "100% of V-Bucks" on in-island sales is about 74% of cash | Since 1 November 2025 only purchasing players count, with a 75% bounty for new or lapsed players | [Epic](https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items) |
| VRChat | ~50% creator, ~30% store, ~20% VRChat plus Tilia | Credits paid out at $0.005 each | [VRChat](https://creators.vrchat.com/economy/welcome-to-the-ce) |
| Second Life | "90/10" marketing; users estimate 20-31% all-in | Marketplace 10% since 2 December 2019, LindeX fees reportedly 10% to 11% in 2026 | [Ryan Schultz](https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/); [SL forums](https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/) |

Revenue anchors: Roblox books about $53-61 per DAU per year ([Quartr](https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf)); Second Life Premium is $12.99 a month or $119.88 a year from July 2026 and a full private region costs $349 setup plus $199 a month from 15 June 2026 ([Modemworld](https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/)); Avakin's 1.6M MAU produced GBP 22M of revenue on a negative EBITDA (Preqin, unverified) ([PocketGamer.biz](https://www.pcgamesinsider.biz/news/75555/avakin-life-surpasses-500-million-downloads-cementing-12-year-legacy-as-a-global-social-powerhouse/)). Second Life's economy is about $650M a year of gross flow, of which about $78M cashed out to creators in 2023 (one secondhand summary) ([Modemworld](https://modemworld.me/2024/12/20/second-life-1-3b-to-build-1-1b-paid-to-creators/)).

### 2.3 The reconciliation

The arithmetic the first draft never showed (all of it unsearched analyst arithmetic on the inputs above). Reference scale: 600K MAU, 150K DAU, $100M a year of new money in. Costs: safety plus infrastructure at $1.5-3 per DAU per month is $2.7-5.4M; payment costs at about 3% are $3M; 150 staff at about $150K loaded are $22.5M; about $28-31M before any creator pool. Under the first draft's model (idle persistence nearly free, take under 10%) revenue is about $8M of take plus 60K subscriptions at $120, about $15M, which covers nothing. With persistence charged (20,000 paid regions or estates at about $100 a month, $24M; Second Life's 17.6K private estates at $109-199 sit in that range ([Daniel Voyager](https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/))), the same subscriptions, a 5% round-trip spread and cash-out fee (about $9M) and a 10% commission on primary sales only (about $10M), revenue is about $50M, enough for costs plus a creator pool of 20-30% of platform net revenue on a thin margin. Three conclusions drive R6, R7 and R8: persistence rent is load-bearing; the creator-facing take can stay near 15% only because rent and subscriptions carry the platform; and the pool must be a share of platform revenue, not Epic's 40% of gross spend.

## 3. Hardware baseline, October 2026

| Tier | Device class | Evidence |
|---|---|---|
| Reference (PC) | The modal Steam GPU is the RTX 5070 at 5.86% in September 2026, with 32 GB of RAM overtaking 16 GB for the first time ([Digital Citizen](https://www.digitalcitizen.life/nvidia-rtx-5070-most-popular-gpu-steam-hardware-survey-september-2026/)) | An 8-12 GB xx60/xx70 card is the target; one month's survey swings, so use rolling averages |
| Lite (console, headset, mid phone) | Switch 2 at 23.68M units by 30 June 2026 ([Gematsu](https://www.gematsu.com/2026/08/switch-2-worldwide-sales-top-23-68-million-switch-tops-156-59-million)); Epic's Lumen Lite targets 60 fps on it in UE 5.8, as a Beta scalability preset ([Guru3D](https://www.guru3d.com/story/unreal-engine-58-debuts-lumen-lite-and-productionready-megalights/)) | VRChat caps Quest avatars at 20,000 triangles ([VRChat](https://docs.vrchat.com/docs/vrchat-202115)) |
| Compat (browser, low Android) | WebGPU shipped in Chrome, Safari 26 and desktop Firefox; Linux Firefox, Samsung Exynos and older Android still need WebGL2 ([gpuweb](https://github.com/gpuweb/gpuweb/wiki/Implementation-Status)) | Roblox's low-end Android floor is a 200-stud draw distance, with 500 claimed for late 2026 but unverified ([Roblox DevForum](https://devforum.roblox.com/t/rdc26-what-we-announced/4865880)) |
| VR (optional) | About 1.77% of Steam users had a headset in January 2026 ([rec0ded88](https://rec0ded88.com/statistics/vr-gaming-headset-ownership/)); Quest shipped 1.7M units in Q1-Q3 2025, down 16%; Vision Pro about 45,000 in 2025 ([The Register](https://www.theregister.com/2026/01/02/apple_vision_pro_meta_quest_sales_drop/)) | Sources disagree on Vision Pro (one outlet prints 4,500, likely a quarterly figure); either way VR is a view, not a client |

Linden said in January 2025 that about half of Second Life's users lack high-end machines ([Modemworld](https://modemworld.me/2025/01/02/)); that, not the 100-avatar cap, is the debt R2 discharges. Third-party avatar platforms are a dead dependency: Ready Player Me shut its creator and APIs on 31 January 2026 after the Netflix acquisition ([Genies](https://genies.com/blog/ready-player-me-discontinued-alternatives)).

### Concurrency per place

100-150 fully simulated avatars per cell is the 2026 envelope. Fortnite runs 100 per instance ([Epic](https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine)); Roblox allows 200 per server publicly, with a 700 tier that can no longer be joined ([Roblox DevForum](https://devforum.roblox.com/t/is-it-still-possible-to-opt-into-700-player-servers/4210626)); Star Citizen gives about 500 per shard and in August 2026 still called its meshing "quasi-dynamic" ([Star Citizen](https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27)); EVE's 6,739-pilot record needed time dilation ([CCP](https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe)); Improbable's 4,144 was a scripted event, not persistent-world load ([TriplePoint](https://pressreleases.triplepointpr.com/2021/06/01/improbable-and-midwinter-entertainment-bring-more-than-4000-scavengers-players-together-in-a-single-game-world/)). Whether a WebGPU client can draw a 100-avatar presence layer on a mid-range phone is open.

## 4. Community-purpose design levers

The sociology research reduces to one claim nolife can test: retention concentrates in people attached to a group with a recurring time and place, and Second Life supplied places, never roles, schedules or scarcity. The causal effect of group membership is held by Bungie, Square Enix and Linden and published by none; the Destiny clan result is correlational ([ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1875952117301350)), so R11 is a hypothesis to measure with a holdout, not a finding.

Five levers have evidence behind them.

- **Groups as the substrate.** What lasted in Second Life was resident-built on the group object: 2-10 roles, a ban list, land and a fixed maturity rating ([SL wiki](https://wiki.secondlife.com/wiki/Group)). Virtual Ability has more than 1,000 members on its own estate with a text-first region for deaf residents ([Virtual Ability](https://virtualability.org/about-us)); the Anglican Cathedral survived its founder's exit because a team existed ([Episcopal Cafe](https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/)). Whole communities move on institutional continuity (R18).
- **Roles over features.** Mentors, hosts, DJs and teachers are why people are needed somewhere: Cafe Musique has hosted more than 600 performers since February 2015 ([Second Life](https://secondlife.com/destinations/music/livemusic)); Helping Hands runs scheduled sign-language classes in VRChat ([VRChat Legends](https://vrchat-legends.fandom.com/wiki/Helping_Hands)). Venues that worked were staffed, against unstaffed corporate builds like a shop "filled with brochures but never having any staff" ([TechRadar](https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2)) (R15).
- **A calendar and one scarce ritual.** BURN2 has been community-run since 2010 on a year-round region ([Ryan Schultz](https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/)); SL20B used sixty regions from 22 June to 11 July 2023 ([Ryan Schultz](https://ryanschultz.com/2023/06/19/your-guide-to-sl20b-second-life-celebrates-its-20th-birthday-with-sixty-sims-june-22nd-july-11th-2023/)); an Animal Crossing graduation drew 83,000 retweets because it was postable ([Newsweek](https://www.newsweek.com/animal-crossing-new-horizons-teacher-help-students-graduate-pandemic-1498760)). No independent attendance data exists for any Second Life event (R15).
- **Scarcity.** FFXIV has allotted all housing by lottery since patch 6.1 in 2022 ([Inverse](https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1)) and its 45-day demolition timer has been suspended repeatedly ([TechRaptor](https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily)); Habbo never re-issues a rare ([Habbo](https://www.habbo.com/community/article/22292/update-state-habbo-economy)); NoPixel sells 32 seats by written application with a paid donator whitelist ([Sportskeeda](https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide)) (R16, R17).
- **Moderation as culture.** Lin et al. found that subreddits with strong moderation kept upvotes common and complaints low through massive growth ([AAAI](https://ojs.aaai.org/index.php/ICWSM/article/view/14884)); the ADL's 2022 survey found 86% of adult gamers harassed and 77% severely ([House letter citing ADL](https://trahan.house.gov/UploadedFiles/Letter_to_FTC_on_multiplayer_online_gaming_industry.pdf)), and in 2019 19% of harassed gamers had stopped playing certain games ([ADL](https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf)). Growth does not destroy culture; absence of moderation does (R23).

Governance is the weakest lever: EVE's CSM20 drew 49,870 voters from 55 candidates ([CCP](https://www.eveonline.com/news/view/heres-your-csm-20)), but it is advisory, NDA-bound and elected per account, and no world has shipped a binding council (R19). Density is a design target, not a measured constant: Second Life's roughly 1,820 km² against a 49,000 peak is about 3.7 hectares per avatar ([Daniel Voyager](https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/)), and the 0.1 ha target in R12 is set to be re-measured.

## 5. Requirements

Each requirement is reproduced word for word from the taxonomy, with its cause and test. The evidence line below each one names the facts it rests on.

**R1.** Elastic cells of 50-150 simulated avatars under a presence layer; published SLOs of 100-150 per cell and 500-1,000 per place. Cause: 1.1, 2.2 #2. Test: 150-avatar cell load test with voice at launch; p95 cell frame time within SLO at monthly peak, quarterly.

**Evidence.** A Second Life region runs one simulator process capped at 100 avatars ([SL wiki](https://wiki.secondlife.com/wiki/Land)); Fortnite's 100 per instance ([Epic](https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine)), Roblox's public 200 ([Roblox DevForum](https://devforum.roblox.com/t/is-it-still-possible-to-opt-into-700-player-servers/4210626)) and Star Citizen's ~500-player quasi-dynamic shards ([Star Citizen](https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27)) bracket the envelope; EVE's 6,739 needed time dilation ([CCP](https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe)).

**R2.** Per-tier asset budgets (triangles, textures, bones, draw distance) with auto-generated fallbacks, enforced server-side across Reference (RTX 4060-class), Lite (Switch 2, Quest 3, mid Android) and Compat (WebGL2, low Android) tiers; over-budget content is impostored or hidden. Cause: 1.1, 1.9, section 5. Test: pipeline down-converts or rejects on all tiers; ≥60 fps on Lite devices at 100-avatar presence, monthly.

**Evidence.** No Second Life asset carries a per-tier budget, so the hardware floor rose with the catalogue and ~50% of users lack high-end machines ([Modemworld](https://modemworld.me/2025/01/02/)); VRChat's Quest cap of 20,000 triangles ([VRChat](https://docs.vrchat.com/docs/vrchat-202115)) and Roblox's 200-stud floor ([Roblox DevForum](https://devforum.roblox.com/t/rdc26-what-we-announced/4865880)) are the shipped precedents; the tiers map to section 3.

**R3.** Versioned formats (glTF 2.0 + VRM 1.0 runtime, OpenUSD interchange) with a published compatibility policy: conversion is platform-funded and retirement needs a converter plus 24 months' notice. Cause: 1.1, 1.9. Test: policy published; zero assets unconverted after a retirement date.

**Evidence.** EEP took from 2017 to 20 April 2020 ([Modemworld](https://modemworld.me/2020/04/27/2020-viewer-release-summaries-week-17/)); PBR went grid-wide on 28 November 2023 ([Modemworld](https://modemworld.me/2023/11/28/)) and in July 2026 the Lab was still asking what creators want from glTF ([Modemworld](https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/)); Meta's engine switch stranded Unity-built worlds ([Road to VR](https://roadtovr.com/meta-horizon-worlds-engine-upgrade-concurrent-users-horizon-studio/)); Ready Player Me's hosted avatars died on 31 January 2026 ([Genies](https://genies.com/blog/ready-player-me-discontinued-alternatives)).

**R4.** The platform ships the newcomer client continuously on a documented protocol; third-party clients are expected and blessed. Cause: 1.1. Test: protocol and third-party policy public; first-session completion on the first-party client ≥ any third-party client, annually.

**Evidence.** Firestorm had 542,967 unique users in 30 days in 2015 ([Hypergrid Business](https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/)) and in June 2025 the Lab put it on its own download page ([Modemworld](https://modemworld.me/2025/06/19/)); Linden's CEO named "the not very intuitive viewer interface" as the second-login blocker in 2014 ([Modemworld](https://modemworld.me/2014/06/29/ebbe-altberg-on-user-retention-now-and-in-the-future/)). The client is an asset; the debt is that nobody owned the newcomer interface.

**R5.** Sandboxed scripting (Luau or WASM) with per-owner CPU, memory and network budgets that throttle the worst offender. Cause: 1.1. Test: a runaway script degrades only its owner's budget in a 150-avatar cell; script-caused frame overruns <1% of cell-hours.

**Evidence.** The Second Life simulator targets 45 frames per second and scripts are starved first ([SL wiki](https://wiki.secondlife.com/wiki/Statistics)); Roblox's shipped model is a per-server budget of 60 + 10 × players requests per minute ([Roblox](https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits)); SLua reached main-grid beta in December 2025, additive to LSL ([Modemworld](https://modemworld.me/2026/03/18/)).

**R6.** Persistence is charged from day one as rent (home, estate, inventory above a trial allowance); activity is priced near cost; the revenue mix is published annually. Cause: 1.2, 1.7, 2.2 #1, section 5 arithmetic. Test: price list with rent, allowance and activity rates, no free world-hosting tier; rent plus subscriptions ≥50% of platform revenue at month 24.

**Evidence.** Section 2.3's arithmetic; Spatial deleted its free and Pro worlds on 27 July 2026 over hosting cost ([UploadVR](https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/)); Rec Room shut down with runway to 2029 ([Rec Room](https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue)); OpenSim's free or $15-40 regions ([Kitely](https://www.kitely.com/virtual-world-news/2015/06/01/60-off-large-worlds-and-dedicated-memory-guarantee/)) produced one-twelfth of Second Life's users ([Hypergrid Business](https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/)); Linden's 2026 cuts moved weight from land to subscriptions ([Modemworld](https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/)).

**R7.** One published fee stack: own billing on web and PC (app stores as top-ups only); all-in take on creator sales ≤15% round trip, 0% on resale; the platform's required margin stated beside it. Cause: 1.2, 1.5, 2.2 #4. Test: fee page and web billing live; effective take within 2 points of published (annual audit); store-routed money-in ≤25% by month 12.

**Evidence.** Marketplace commission doubled to 10% on 2 December 2019 ([Ryan Schultz](https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/)) and users estimate the all-in take at 20-31% against "90/10" ([SL forums](https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/)); Rec Room kept 30c after store fees ([Rec Room](https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue)); VRChat's ~50/30/20 split shows where the store tax goes ([VRChat](https://creators.vrchat.com/economy/welcome-to-the-ce)). The inference from Rec Room is "own the billing", not "pay creators more".

**R8.** A creator pool of 20-30% of platform net revenue, weighted by returning purchasing users with anti-farming rules, 10-20% reserved for venues, formula published. Cause: 1.4, 2.2 #4, section 4. Test: formula and payout schedule published; ≥40% of DAU-hours in creator-run places by month 12, reviewed semi-annually.

**Evidence.** Roblox paid $922.8M of DevEx in 2024 ([SEC](https://www.sec.gov/Archives/edgar/data/1315098/000131509825000033/rblx-20241231.htm)) and more than $1.5B in 2025 ([Quartr](https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf)); Epic's pool counts only purchasing players since 1 November 2025 ([Epic](https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items)) and has paid $1B with 47% of play hours in creator islands ([GamesBeat](https://gamesbeat.com/epic-games-has-paid-out-1-billion-to-creators-since-launching-unreal-editor-for-fortnite-in-2023/)); Horizon's $50M fund also paid on retention and failed ([Meta](https://developers.meta.com/horizon/blog/gdc-2025-horizon-worlds-create-earn-bonuses-desktop-editor-tools)). Venues get a reserve because pools reward maps, not hosts ([TechRadar](https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2)).

**R9.** One closed currency, transferable between users but not off-platform, at a published fixed or daily-fixed rate with fiat shown at every price, exact-amount purchase, no bundles, no chance mechanics paying anything cash-out-able; stipends carry fiat display. Cause: section 5 consumer law, 2.2 #3. Test: every price shows fiat, one currency, no loot boxes; zero CPC-type findings; DFA text reviewed within 90 days of publication.

**Evidence.** Section 1.3: the CPC principles ([Linklaters](https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr)), the Star Stable action ([Forbrukertilsynet](https://www.forbrukertilsynet.no/eng-articles/national-consumer-authorities-and-commission-take-action-on-harmful-practices-in-the-gaming-industry)) and the DFA expected in November 2026 ([Heuking](https://www.heuking.de/en/news-events/newsletter-articles/detail/digital-fairness-act-implementation-obligations-companies-need-to-prepare-for.html)); the 2007 gambling ban ([TechCrunch](https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/)); Ginko's ~L$200M collapse ([Wikipedia](https://en.wikipedia.org/wiki/Ginko_Financial)); metaverse land volume fell 96% in 2022 ([The Block](https://www.theblock.co/post/197062/ncrooks@theblock.co)). "Transferable between users" keeps the user-to-user economy the first draft's "non-transferable" would have banned.

**R10.** Cash-out on a licensed, partnered rail settling the platform currency under KYC, with tax data (W-9/W-8, DAC7) collected at payout onboarding and an adult-specialist acquirer pre-qualified in reserve. Cause: 1.9, section 5. Test: rail contract names its adult-content policy, tax data captured before first payout; payout failure <1%, no 1099-K or DAC7 misses.

**Evidence.** Tilia, Linden's licensed rail since 2019, was sold in 2024 with a five-year partnership ([Modemworld](https://modemworld.me/2024/04/26/summary-of-tilia-acquisition-lab-gab-sl-round-table-news/)); DAC7 ([Fonoa](https://www.fonoa.com/blog/dac7overview)) and the $20,000/200 1099-K threshold ([IRS](https://irs.gov/newsroom/irs-issues-faqs-on-form-1099-k-threshold-under-the-one-big-beautiful-bill-dollar-limit-reverts-to-20000)); Stripe prohibits adult content ([Conduct Atlas](https://conductatlas.com/platform/stripe/stripe-restricted-businesses-list/adult-content-prohibition-and-restriction/)), hence the adult-specialist acquirer in reserve.

**R11.** First hour = first group: every new account lands in a hosted, scheduled cohort; success is "met a person or joined a group"; measured by randomised holdout. Cause: 1.3, 1.4 (never measured). Test: cohort scheduling and holdout live; D30 of treated vs holdout published at month 6, kept only if the lift exceeds the industry D30 base.

**Evidence.** Second Life's retention went from about 10% at 90 days in 2007 ([Andrew Chen](https://andrewchen.com/interesting-graph-on-second-life-usage/)) to about 7% in September 2025 ([Modemworld](https://modemworld.me/tag/project-zero/)), the industry base rate, so the funnel is not the lever; Virtual Ability's mentor-by-appointment model ([Virtual Ability](https://virtualability.org/history/)) and Helping Hands' scheduled classes ([VRChat Legends](https://vrchat-legends.fandom.com/wiki/Helping_Hands)) are the precedents; the clan effect is correlational ([ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1875952117301350)), hence the holdout.

**R12.** Density management with a measured SLO: public hubs target one avatar per 0.1 ha at peak; thin instances merge, empty districts close, newcomers route to live events. Cause: 1.3. Test: merge, close and routing live; median people visible in a newcomer's first session ≥10, SLO re-set after six months.

**Evidence.** 76,000 peak avatars over ~30,000 regions in 2008 is under three per region ([ABC News](https://abcnews.go.com/Technology/PCWorld/story?id=6688909)); 32,000 over 26,663 in 2025 is ~1.2 ([Daniel Voyager](https://danielvoyager.wordpress.com/2025/08/11/second-life-statistics-august-2025-update/)); only 9% of Horizon worlds ever had 50 visitors ([CNBC](https://www.cnbc.com/2022/10/15/meta-horizon-worlds-metaverse-losing-users-falling-short-of-goals.html)). Public-hub density was never measured, which is why the SLO is re-set after six months.

**R13.** Publish first-hour, D7, D30, D90, DAU/MAU, peak concurrency and bot share on a fixed cadence with a documented "active" definition and a third-party-readable API. Cause: 1.5, 2.2 shared trait. Test: metrics page and API live; quarterly publication without gaps, third-party reproduction of concurrency within 5%.

**Evidence.** Linden has published no MAU or DAU series with a definition; a 2023 "750K" is irreconcilable with 2024's "500K" ([Engadget](https://www.engadget.com/2010-07-10-the-virtual-whirl-a-brief-history-of-second-life-2009.html)); Decentraland's 38 wallets a day against a claimed 8,000 ([Nasdaq](https://www.nasdaq.com/articles/the-final-word-on-decentralands-numbers)); the 2009 peak of 88,220 included bots ([Engadget](https://www.engadget.com/2009-12-25-second-life-user-concurrency-spends-year-in-slow-decline.html)); bots were 51% of web traffic in 2024 ([Imperva](https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/)).

**R14.** Desktop and web (WebGPU, WebGL2 fallback) at launch, native mobile within 12 months; VR optional, never required for identity or inventory; pixel streaming only as a time-capped funnel at a published cost per hour. Cause: 1.6, 1.7, 2.2 #2. Test: two clients at launch and a mobile date; mobile ≥30% of DAU by month 24, streaming cost per retained user published.

**Evidence.** VR is ~1.77% of Steam ([rec0ded88](https://rec0ded88.com/statistics/vr-gaming-headset-ownership/)) and shrinking ([The Register](https://www.theregister.com/2026/01/02/apple_vision_pro_meta_quest_sales_drop/)); Second Life's Oculus viewer lasted a week in July 2016 ([Modemworld](https://modemworld.me/2016/07/08/second-life-oculus-rift-support-suspended/)); High Fidelity's VR users ran ~100x below plan ([Modemworld](https://modemworld.me/2019/04/11/high-fidelity-changes-direction-the-reality-of-vr-worlds-today-tomorrow/)); the Unity mobile app sits at 2.5 stars on 1M+ downloads ([Google Play](https://play.google.com/store/apps/details?id=com.lindenlab.secondlife&hl=en_US)); Project Zero ended 21 April 2026 after 14 months ([Modemworld](https://modemworld.me/tag/project-zero/)) against a $19.99 consumer ceiling ([NVIDIA](https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now)).

**R15.** A civic calendar on day one (a weekly rhythm and one annual scarce ritual on a region that exists only then), first-party events as synchronised ~100-avatar instances, and roles (host, mentor, DJ, moderator, builder) as first-class objects with slots, badges, stipends and a named deputy for any role owning land or a calendar. Cause: 1.4. Test: calendar with named owners, role and deputy fields in groups; ≥25% of MAU attend a scheduled event monthly, ≥80% of venues survive a leader's 90-day absence.

**Evidence.** Section 4: BURN2 ([Ryan Schultz](https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/)), SL20B's sixty regions ([Ryan Schultz](https://ryanschultz.com/2023/06/19/your-guide-to-sl20b-second-life-celebrates-its-20th-birthday-with-sixty-sims-june-22nd-july-11th-2023/)), Cafe Musique ([Second Life](https://secondlife.com/destinations/music/livemusic)), the Cathedral's succession ([Episcopal Cafe](https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/)); Fortnite's concerts ran in ~100-player instances ([Epic](https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine)). The deputy rule comes from the one documented founder succession.

**R16.** Scarce shared public land by lottery with full-price tickets and a 45-day use-it-or-lose-it rule with refunds and a published pause policy; private homes are rented under R6 and never auto-demolished. Cause: 1.2, section 4 FFXIV. Test: rules published; public-parcel occupancy ≥70% at peak.

**Evidence.** FFXIV's lottery since 2022 ([Inverse](https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1)) and its repeatedly suspended 45-day timer ([TechRaptor](https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily)), hence the published pause policy; Habbo's rares ([Habbo](https://www.habbo.com/community/article/22292/update-state-habbo-economy)); a flat per-region fee penalises emptiness, not success ([Modemworld](https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/)), so private homes are rented, never demolished.

**R17.** Curated, seat-capped roleplay estates with whitelisting, access and ban lists, roles as ranks, damage-enabled parcels and paid queue priority under published rules (cosmetics and priority yes; pay-to-win and loot boxes no). Cause: 1.4, section 5 census, section 4 GTA RP. Test: estate tools and rules live; ≥50 whitelisted estates with weekly events by month 12.

**Evidence.** NoPixel's 32 seats and application ([Sportskeeda](https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide)); GTA RP's 221,062 Steam peak in May 2026 ([Steam Charts](https://steamcharts.com/app/2676230)); Rockstar absorbed Cfx.re in August 2023 ([GWO](https://gameworldobserver.com/2023/08/11/cfx-re-joins-rockstar-deal-fivem-redm-roleplay)); Second Life's 1920s Berlin ran ten years on access lists and ranks ([Ryan Schultz](https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/)); Bloodlines asks consent before a bite ([Second Life](https://go.secondlife.com/destination/bloodlines)). Paid priority is a queue, not a paywall; Pax Dei's capped plots sit at a few hundred concurrent ([MassivelyOP](https://massivelyop.com/?p=566277)).

**R18.** Continuity for migrating communities: a charter import (group, roles, members, ban list, rating, calendar and land in one transaction), OAR/IAR import, a 12-24-month chat and event bridge with SL, and glTF/VRM export of own-created inventory. Cause: 1.6, 1.9. Test: charter and OAR import demonstrated with a named community; ≥10 named SL institutions migrated with membership by month 18.

**Evidence.** Sansar carried no inventory, identity or social graph and "wasn't making enough money" by 24 March 2020 ([Hypergrid Business](https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/)); Club Penguin Rewritten reached ~11M users by preserving the original ([Vice](https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/)); Habbo Origins relaunched the 2005 client in June 2024 ([80.lv](https://80.lv/articles/the-original-2005-habbo-hotel-opens-its-doors-later-today)); educators moved for OAR/IAR backups ([Hypergrid Business](https://hypergridbusiness.com/?p=35085)); the group object is the unit to import ([SL wiki](https://wiki.secondlife.com/wiki/Group)).

**R19.** Constitutional change control: a published charter, 12 months' notice and grandfathering for persistence price rises, public change-review for client-affecting updates, and an elected advisory assembly whose published vote must be answered in writing (no world has shipped a binding council). Cause: 1.5. Test: charter and assembly rules published; zero retroactive price changes, assembly responses on record.

**Evidence.** Openspace tier rose from $75 to $125 in October 2008 without grandfathering ([SL forums archive](https://forums-archive.secondlife.com/356/24/291220/1.html)); Zindra forced ~850 move tickets in 2009 ([SL wiki](https://wiki.secondlife.com/wiki/Zindra)); the 2013 ToS made Renderosity and CG Textures ban their assets ([Hypergrid Business](https://www.hypergridbusiness.com/2013/09/outrage-grows-over-new-second-life-terms)); VRChat's EAC update drew 22,000 votes in 24 hours ([Dazed](https://www.dazeddigital.com/science-tech/article/56662/1/why-thousands-of-users-are-abandoning-the-worlds-most-popular-vr-game)); Meta reversed its Horizon VR shutdown within ~48 hours ([TechCrunch](https://techcrunch.com/2026/03/19/meta-decides-not-to-shut-down-horizon-worlds-on-vr-after-all/)); CSM20's 49,870 voters show an advisory body can hold turnout for fifteen years ([CCP](https://www.eveonline.com/news/view/heres-your-csm-20)).

**R20.** Portability, sunset and vendor covenant: self-hostable cells, escrowed server images, export of own-created content, 12 months' notice before any shutdown, cells deployable on two hosting providers, swappable voice, and the engine choice documented with its exit cost. Cause: 2.2 #1, 1.9 (OSgrid's wipe shows self-hosting needs escrow). Test: escrow, export tools and a failover demo at launch; annual restore test and failover drill pass.

**Evidence.** Hathora wound down in spring 2026 after an AI pivot ([GamesBeat](https://gamesbeat.com/?p=318174)); Firestorm Zero closed when its provider forced a migration ([Modemworld](https://modemworld.me/2025/06/27/)); OSgrid wiped its asset database in 2025 and was offline three weeks in 2026 ([Hypergrid Business](https://www.hypergridbusiness.com/?p=79686)), so self-hosting needs escrow; NeosVR's cloud went off on 20 August 2025 and the community survived by forking ([Wikipedia](https://en.wikipedia.org/wiki/NeosVR)); Dual Universe's servers closed on 27 August 2025 and it lives on as self-hosted myDU ([Wikipedia](https://en.wikipedia.org/wiki/Dual_Universe)).

**R21.** Age assurance as a configurable regional module: on-device estimation or wallet credential (no stored ID images), per-region thresholds, feature gating rather than binary bans, parental surfaces, adjacent-band chat and private-by-default for minors, OS age signals for app clients, and Adult districts gated by an Ofcom-grade check that also unlocks Adult-tagged commerce. Cause: section 5. Test: UK, EU, Brazil, Indonesia and Texas profiles configured; zero regulator findings, assurance completion rate published.

**Evidence.** Section 1.1 in full: the UK duty ([Inforrm](https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/)), the DSA guidelines ([CMS](https://cms.law/en/fra/news-information/protecting-minors-in-the-digital-space)), Australia's primary-purpose test ([eSafety](https://www.esafety.gov.au/node/2109)), the Roblox template ([Roblox](https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat)), Brazil ([Demarest](https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/)), Indonesia ([AVPA](https://avpassociation.com/indonesia/)), Texas ([Pearl Cohen](https://www.pearlcohen.com/fifth-circuit-stays-injunctions-against-texas-app-store-accountability-act/)) and Discord's 70,000 leaked IDs ([The Record](https://therecord.media/discord-government-docs-exposed-breach)), which is why no ID image is stored.

**R22.** Adult content as a measured, controlled first-class purpose: maturity-tagged spend and cash-out instrumented from day one; uploader verification, consent records and pre-publication review for Adult-tagged goods; consumer purchases coded as platform currency, never an adult MCC; a deindex-but-sell switch; exclusion from general cash-out held only as a processor-triggered contingency. Cause: 1.4, section 5 rails. Test: controls and switch demonstrated, rail policy on file; adult share of spend published, no processor action.

**Evidence.** Adult-flagged regions were 5.69% of the grid in November 2009 ([SL wiki](https://wiki.secondlife.com/wiki/Adult_content)) and Au's 2008 book put ~18% of land in "mature activity" ([VentureBeat](https://venturebeat.com/technology/book-review-the-making-of-second-life)); no Lab figure for the adult share of L$ flow exists. The July 2025 Valve, itch.io and DLsite episodes ([TechCrunch](https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story); [TheSixthAxis](https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/); [Automaton](https://automaton-media.com/en/news/dlsite-disables-visa-mastercard-payment-after-attempt-to-outsmart-credit-card-companies/)), the VIRP and AN 5196 rules ([LegitScript](https://www.legitscript.com/regulatory-and-card-brand-compliance/adult-escort-and-dating-merchants-are-your-practices-in-line-with-virp-updates/)), Tumblr's 29% ([TNW](https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/)) and OnlyFans' reversal ([CBC](https://www.cbc.ca/lite/story/1.6148524)) set the controls; itch.io's deindex-but-sell preserved creator income.

**R23.** Always-on embodied safety primitives (personal boundary default-on, one-gesture mute/block/vanish, instance kick/lock, evidence buffer on report, earned trust ranks gating upload, voice and proximity) with incident-based KPIs (reports per 1,000 user-hours, time-to-action) published quarterly and audit logs for information requests. Cause: section 5. Test: primitives present, KPI definitions published; median time-to-action <24h, quarterly report on schedule.

**Evidence.** Meta's Personal Boundary of 4 February 2022, default-on and later adjustable ([ISPR](https://ispr.info/2022/02/08/meta-establishes-four-foot-personal-boundary-to-deter-vr-groping/)); UK police could not charge a virtual assault in 2024 ([LBC](https://lbc.co.uk/news/police-investigate-rape-metaverse)); VRChat's behaviour-earned trust ranks gate upload and voice ([VRChat](https://docs.vrchat.com/docs/vrchat-safety-and-trust-system)); Roblox's Sentinel caught 35% of detected cases proactively ([Roblox](https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection)) and the company filed 24,522 NCMEC reports in 2024 ([Roblox](https://s27.q4cdn.com/984876518/files/doc_news/2025/Aug/15/Roblox-Response-8-15-25.pdf)); Ofcom fines un-evidenced compliance ([xident](https://xident.io/blog/age-assurance-evidence-ofcom-information-request-second-fine-2026/)), hence the audit logs.

**R24.** Platform-hosted, escrowed life-support for value-bearing scripted objects (breedables, pets, vendor-dependent HUDs) with a designed end-of-life conversion to a food-independent state. Cause: 2.2 #5, section 3. Test: escrow API and conversion exist; zero value-bearing objects bricked by vendor exit.

**Evidence.** Ozimals bunnies hibernated when a creditor closed the food server in May 2017 while food-independent pets survived ([Boing Boing](https://boingboing.net/2017/05/20/breedables-vs-drm.html)); KittyCatS breeders describe a trait-inflation boom and bust ([SL forums](https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/)); inside Second Life a-life worked only as a scarcity economy.

**R25.** Every AI inhabitant is disclosed (badge, notice, on whose behalf it acts), has a purpose, is capped at a published fraction of visible occupants and withdraws as humans arrive; no companion loops for minors; voices licensed or synthetic with provenance; cognition tiered (scripted, on-device, frontier) with a published cost per agent-hour. Cause: section 3 (density only, not purpose), section 5 AI Act. Test: badge, cap and cost model implemented; human D30 in agent-filled places ≥ comparable human-only places (else the cap is lowered); agent cost ≤10% of the safety-plus-infrastructure budget.

**Evidence.** Article 50's disclosure forms and 2 August 2026 date ([Stephenson Harwood](https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/)); Project Sid's 1,000 agents were four-hour runs the authors call preliminary ([arXiv](https://arxiv.org/pdf/2411.00114)); no vendor publishes a cost per NPC-hour ([Inworld](https://docs.inworld.ai/models)); Character.AI banned open-ended chat for under-18s from November 2025 ([Bloomberg](https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots)) and settled the Setzer case in January 2026 ([JURIST](https://www.jurist.org/news/2026/01/google-and-character-ai-agree-to-settle-lawsuit-linked-to-teen-suicide)); 63% of 1,799 Quantic Foundry respondents chose the most negative option on generative AI ([Quantic Foundry](https://quanticfoundry.com/2025/12/18/gen-ai/)). Nothing in the corpus shows agent-filled density retaining humans.

**R26.** Onboarding produces a furnished home and a dressed avatar before any scripting panel, with a first-party open-licensed avatar body and a consumer interface separate from the creator interface. Cause: 1.3 (transfer from non-UGC worlds assumed). Test: two interfaces, home and avatar in the first session; first-session completion ≥60%.

**Evidence.** Viewer 2's "Basic mode" of 2011 offered 24 preset avatars and its retention effect was never published ([Modemworld](https://modemworld.me/2011/04/11)); IMVU (~7M MAU claimed) ([TechCrunch](https://techcrunch.com/2021/01/25/imvu-35-million-funding/)) and Avakin (1.6M MAU, no UGC) ([PocketGamer.biz](https://www.pcgamesinsider.biz/news/75555/avakin-life-surpasses-500-million-downloads-cementing-12-year-legacy-as-a-global-social-powerhouse/)) survive on dress-up; Zepeto reached 20M MAU avatar-first ([KED Global](https://m.kedglobal.com/newsView/ked202203040009)). The transfer from non-UGC worlds is assumed, hence the completion test.

**R27.** Accessibility as a shipped client: a first-party text client (Radegast successor) covering chat, inventory, teleport, object list and voiced GPS; speech-to-text and text-to-speech of chat (XAG 119); keyboard-only navigation; motion-sickness and seated options; funded maintenance. Cause: section 5 census. Test: text client ships at launch with an XAG 119 and GAG checklist; a Virtual Ability-scale community (≥1,000 members) operating by month 12.

**Evidence.** Blind residents rely on Radegast, a volunteer text client with no release since February 2022 (unverified) ([AppleVis](https://applevis.com/comment/73862)); Virtual Ability's 1,000-plus members and Cape Able ([Virtual Ability](https://virtualability.org/about-us)); XAG 119 asks for speech-to-text and text-to-speech of chat ([Microsoft](https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119)) and the Game Accessibility Guidelines a voiced GPS ([GAG](https://gameaccessibilityguidelines.com/?p=263)); the EAA applies from 28 June 2025 ([Osborne Clarke](https://www.osborneclarke.com/insights/eu-accessibility-act-time-start-implementation-projects-now)).

**R28.** Education tier: institutional SSO, bulk student accounts, private regions with OAR-equivalent export, General-rated enforcement, a class-region price under US$50/month and a written persistence commitment. Cause: 1.5, section 5 census. Test: tier page and SSO live; ≥20 accredited institutions by month 18.

**Evidence.** The education discount ended on 1 January 2011 ([THE Journal](https://thejournal.com/Articles/2010/11/03/Linden-Lab-To-End-Second-Life-Educational-Discounts.aspx)), doubling costs, and was restored on 24 July 2013 ([Hypergrid Business](https://hypergridbusiness.com/2013/07/second-life-restores-half-off-discount-to-educators)), by which time "Linden Lab blew it" ([Hypergrid Business](https://www.hypergridbusiness.com/2013/08/educators-wary-of-latest-linden-offer/)); a 2014 study found cost and persistence decisive ([SCITEPRESS](https://www.scitepress.org/Papers/2014/49578/)); VWBPE still ran 19-21 March 2026 in Second Life ([Second Life](https://secondlife.com/destination/vwbpe)). The exodus is the one measurable loss from a governance shock.

**R29.** Language as a shard key: language-tagged community homes with per-language discovery and onboarding; paid localisation for at least Portuguese, Spanish, Japanese and German; local prices and cash rails; chat translation with its retention effect measured; an open avatar pipeline (VRM/glTF import, off-platform marketplaces). Cause: 1.8, 1.1. Test: four localised flows, two local rails and VRM import live; non-US DAU ≥40% and ≥30% of avatar items off-platform by month 24.

**Evidence.** comScore put 61% of active residents in Europe in March 2007 ([comScore](https://www.comscore.com/Insights/Press-Releases/2007/05/Second-Life-Growth-Worldwide)); the June 2010 cuts closed the Singapore and UK offices ([Engadget](https://www.engadget.com/2010-06-07-linden-lab-laying-off-staff-closing-singapore-office.html)) and ended funded localisation ([Gilbane](https://gilbane.com/?p=2016)); Japan is VRChat's largest web market at 37% of visits ([Sensor Tower](https://sensortower.com/ja/blog/vrchat-high-popularity-in-japan-JP)) on BOOTH's ~10.4bn-yen 3D-model trade ([Real Sound](https://realsound.jp/tech/2026/02/post-2303955.html)); regional pricing lifted Roblox's paying users 26% in Brazil and 52% in the Philippines ([Roblox](https://about.roblox.com/newsroom/2025/04/roblox-launches-regional-pricing-for-in-experience-items)); no study shows chat translation moving retention ([Roblox](https://about.roblox.com/newsroom/2024/02/roblox-introduces-ai-powered-real-time-chat-translations-in-16-languages)).

**R30.** Funding posture written down: a published runway plan to self-funding at a Linden-scale audience (≤600K MAU) with fixed costs sized to survive at 100K MAU, no sibling product, and growth features funded only after rent and subscriptions cover costs. Cause: 1.7, 2.2 #1. Test: cost and runway plan published with a headcount cap; operating costs covered by recurring revenue by month 36.

**Evidence.** Linden has run since the June 2010 restructuring on ~160 staff and a ~10% take ([Kowatek](https://blog.kowatek.com/?p=88910)), ~200 per one 2026 profile ([Yespress](https://yespress.io/linden-lab)); sources disagree and neither is official. Sansar was the sibling that "wasn't making enough money" ([Hypergrid Business](https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/)); Reality Labs lost $17.7B in 2024 and $19.19B in 2025 ([Shacknews](https://www.shacknews.com/article/147618/facebook-meta-reality-labs-fy25-losses)); Rec Room died with runway ([Rec Room](https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue)); survivors are cheap to keep alive, from Active Worlds ([Wikipedia](https://en.wikipedia.org/wiki/Active_Worlds)) to Resonite on Patreon at ~190 concurrent ([Steambase](https://steambase.io/games/resonite)). Second Life was profitable by 2005 on $25M raised ([Wikipedia](https://en.wikipedia.org/wiki/Economy_of_Second_Life)) and gained 50% more regular users in 2020 ([Ryan Schultz](https://ryanschultz.com/2020/05/24/linden-lab-ceo-ebbe-altberg-second-life-has-seen-a-50-increase-in-regular-monthly-users-because-of-the-pandemic/)): a Linden-scale audience can fund a Linden-scale company, and the plan must say so in numbers.

## Sources

- https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/
- https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/
- https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat
- https://aws.amazon.com/gamelift/servers/pricing/
- https://www.digitalcitizen.life/nvidia-rtx-5070-most-popular-gpu-steam-hardware-survey-september-2026/
- https://rec0ded88.com/statistics/vr-gaming-headset-ownership/
- https://xident.io/blog/age-assurance-evidence-ofcom-information-request-second-fine-2026/
- https://www.theregister.com/2025/11/21/ofcom_osa_fine_undress/
- https://cms.law/en/fra/news-information/protecting-minors-in-the-digital-space
- https://www.esafety.gov.au/node/2109
- https://www.bloomberg.com/news/articles/2026-04-21/roblox-settles-with-states-for-35-8-million-over-child-safety
- https://www.sdpb.org/crime-courts/2026-07-13/roblox-settlement-yields-tighter-restrictions-over-8-million-for-south-dakota
- https://www.ag.ks.gov/Home/Components/News/News/365/1292
- https://www.mayerbrown.com/en/insights/publications/2026/04/enforcement-of-brazils-eca-digital-introduces-new-obligations-for-companies
- https://avpassociation.com/indonesia/
- https://www.malaymail.com/news/world/2026/03/31/indonesia-summons-meta-google-for-failing-to-enforce-under16-age-limits-under-new-childprotection-law/214489
- https://law.ungovr.org/age/de
- https://bernama.com/en/world/news.php?id=2573981
- https://www.medianama.com/2025/01/223-data-protection-rules-2025-children-data-india/
- https://www.jurist.org/news/2026/04/turkiye-lawmakers-approve-bill-restricting-social-media-access-for-children-under-15/
- https://www.pearlcohen.com/fifth-circuit-stays-injunctions-against-texas-app-store-accountability-act/
- https://www.alstonprivacy.com/california-enacts-digital-age-verification-law/
- https://developer.apple.com/forums/thread/810754
- https://therecord.media/discord-government-docs-exposed-breach
- https://lbc.co.uk/news/police-investigate-rape-metaverse
- https://modemworld.me/2012/07/10/ll-revises-sl-age-verification/
- https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/
- https://wiki.vrchat.com/wiki/Age_Verification
- https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story
- https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/
- https://automaton-media.com/en/news/dlsite-disables-visa-mastercard-payment-after-attempt-to-outsmart-credit-card-companies/
- https://www.legitscript.com/regulatory-and-card-brand-compliance/adult-escort-and-dating-merchants-are-your-practices-in-line-with-virp-updates/
- https://verifymy.io/resources/regulation/card-brand-requirements
- https://conductatlas.com/platform/stripe/stripe-restricted-businesses-list/adult-content-prohibition-and-restriction/
- https://adyen.com/legal/list-restricted-prohibited
- https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/
- https://www.cbc.ca/lite/story/1.6148524
- https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/
- https://www.techradar.com/news/steam-is-now-banning-all-games-that-engage-in-cryptocurrency-or-nft-trading
- https://advertisinglaw.fkks.com/post/102inw4/the-cats-out-of-the-bag-secs-theory-impacts-nft-industry
- https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr
- https://www.twobirds.com/en/insights/2025/global/regulatory-spotlight-virtual-currency-vs-consumer-law-part-2
- https://www.forbrukertilsynet.no/eng-articles/national-consumer-authorities-and-commission-take-action-on-harmful-practices-in-the-gaming-industry
- https://techcrunch.com/2024/09/12/bad-credits-consumer-group-files-eu-suit-over-manipulative-payments-in-games-like-fortnite-and-minecraft-calls-for-a-ban
- https://www.heuking.de/en/news-events/newsletter-articles/detail/digital-fairness-act-implementation-obligations-companies-need-to-prepare-for.html
- https://thelens.slaughterandmay.com/post/102m222/digital-fairness-act-european-commission-publishes-responses-to-consultation
- https://www.fonoa.com/blog/dac7overview
- https://irs.gov/newsroom/irs-issues-faqs-on-form-1099-k-threshold-under-the-one-big-beautiful-bill-dollar-limit-reverts-to-20000
- https://wiki.secondlife.com/wiki/Linden_Lab_Official:Required_Tax_Documentation_FAQ
- https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/
- https://www.govtrack.us/congress/bills/119/s4591
- https://fpf.org/blog/old-laws-new-tech-as-courts-wrestle-with-tough-questions-under-us-biometric-laws-immersive-tech-raises-new-challenges/
- https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/
- https://www.osborneclarke.com/insights/eu-accessibility-act-time-start-implementation-projects-now
- https://edgegap.com/blog/announcement-offering-changes-for-2025
- https://odin.4players.io/pricing
- https://app.edgar.tools/companies/RBLX
- https://thegabmeister.com/p/unreal-pixel-stream-aws/
- https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now
- https://liftoff.ai/?p=34267
- https://modemworld.me/2025/06/27/
- https://gamesbeat.com/?p=318174
- https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue
- https://www.sec.gov/Archives/edgar/data/1315098/000131509825000033/rblx-20241231.htm
- https://quartr.com/events/roblox-rblx-q4-2025_ozGB34Pf
- https://about.roblox.com/newsroom/2026/04/roblox-fuels-high-fidelity-games-over-18-players-increases-qualifying-devex-rate-42
- https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items
- https://creators.vrchat.com/economy/welcome-to-the-ce
- https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/
- https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/
- https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/
- https://www.pcgamesinsider.biz/news/75555/avakin-life-surpasses-500-million-downloads-cementing-12-year-legacy-as-a-global-social-powerhouse/
- https://modemworld.me/2024/12/20/second-life-1-3b-to-build-1-1b-paid-to-creators/
- https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/
- https://www.gematsu.com/2026/08/switch-2-worldwide-sales-top-23-68-million-switch-tops-156-59-million
- https://www.guru3d.com/story/unreal-engine-58-debuts-lumen-lite-and-productionready-megalights/
- https://docs.vrchat.com/docs/vrchat-202115
- https://github.com/gpuweb/gpuweb/wiki/Implementation-Status
- https://devforum.roblox.com/t/rdc26-what-we-announced/4865880
- https://www.theregister.com/2026/01/02/apple_vision_pro_meta_quest_sales_drop/
- https://modemworld.me/2025/01/02/
- https://genies.com/blog/ready-player-me-discontinued-alternatives
- https://dev.epicgames.com/documentation/en-us/unreal-engine/iris-replication-system-in-unreal-engine
- https://devforum.roblox.com/t/is-it-still-possible-to-opt-into-700-player-servers/4210626
- https://starcitizen.tools/Comm-Link:Letter_from_the_Chairman_-_2026-08-27
- https://www.eveonline.com/news/view/the-second-timer-in-m2-xfe
- https://pressreleases.triplepointpr.com/2021/06/01/improbable-and-midwinter-entertainment-bring-more-than-4000-scavengers-players-together-in-a-single-game-world/
- https://www.sciencedirect.com/science/article/pii/S1875952117301350
- https://wiki.secondlife.com/wiki/Group
- https://virtualability.org/about-us
- https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/
- https://secondlife.com/destinations/music/livemusic
- https://vrchat-legends.fandom.com/wiki/Helping_Hands
- https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2
- https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/
- https://ryanschultz.com/2023/06/19/your-guide-to-sl20b-second-life-celebrates-its-20th-birthday-with-sixty-sims-june-22nd-july-11th-2023/
- https://www.newsweek.com/animal-crossing-new-horizons-teacher-help-students-graduate-pandemic-1498760
- https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1
- https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily
- https://www.habbo.com/community/article/22292/update-state-habbo-economy
- https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide
- https://ojs.aaai.org/index.php/ICWSM/article/view/14884
- https://trahan.house.gov/UploadedFiles/Letter_to_FTC_on_multiplayer_online_gaming_industry.pdf
- https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf
- https://www.eveonline.com/news/view/heres-your-csm-20
- https://wiki.secondlife.com/wiki/Land
- https://modemworld.me/2020/04/27/2020-viewer-release-summaries-week-17/
- https://modemworld.me/2023/11/28/
- https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/
- https://roadtovr.com/meta-horizon-worlds-engine-upgrade-concurrent-users-horizon-studio/
- https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/
- https://modemworld.me/2025/06/19/
- https://modemworld.me/2014/06/29/ebbe-altberg-on-user-retention-now-and-in-the-future/
- https://wiki.secondlife.com/wiki/Statistics
- https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits
- https://modemworld.me/2026/03/18/
- https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/
- https://www.kitely.com/virtual-world-news/2015/06/01/60-off-large-worlds-and-dedicated-memory-guarantee/
- https://www.hypergridbusiness.com/2026/05/opensim-users-land-area-both-up-this-month/
- https://gamesbeat.com/epic-games-has-paid-out-1-billion-to-creators-since-launching-unreal-editor-for-fortnite-in-2023/
- https://developers.meta.com/horizon/blog/gdc-2025-horizon-worlds-create-earn-bonuses-desktop-editor-tools
- https://en.wikipedia.org/wiki/Ginko_Financial
- https://www.theblock.co/post/197062/ncrooks@theblock.co
- https://modemworld.me/2024/04/26/summary-of-tilia-acquisition-lab-gab-sl-round-table-news/
- https://andrewchen.com/interesting-graph-on-second-life-usage/
- https://modemworld.me/tag/project-zero/
- https://virtualability.org/history/
- https://abcnews.go.com/Technology/PCWorld/story?id=6688909
- https://danielvoyager.wordpress.com/2025/08/11/second-life-statistics-august-2025-update/
- https://www.cnbc.com/2022/10/15/meta-horizon-worlds-metaverse-losing-users-falling-short-of-goals.html
- https://www.engadget.com/2010-07-10-the-virtual-whirl-a-brief-history-of-second-life-2009.html
- https://www.nasdaq.com/articles/the-final-word-on-decentralands-numbers
- https://www.engadget.com/2009-12-25-second-life-user-concurrency-spends-year-in-slow-decline.html
- https://modemworld.me/2016/07/08/second-life-oculus-rift-support-suspended/
- https://modemworld.me/2019/04/11/high-fidelity-changes-direction-the-reality-of-vr-worlds-today-tomorrow/
- https://play.google.com/store/apps/details?id=com.lindenlab.secondlife&hl=en_US
- https://steamcharts.com/app/2676230
- https://gameworldobserver.com/2023/08/11/cfx-re-joins-rockstar-deal-fivem-redm-roleplay
- https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/
- https://go.secondlife.com/destination/bloodlines
- https://massivelyop.com/?p=566277
- https://www.hypergridbusiness.com/2020/04/linden-lab-sells-sansar-to-wookey/
- https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/
- https://80.lv/articles/the-original-2005-habbo-hotel-opens-its-doors-later-today
- https://hypergridbusiness.com/?p=35085
- https://forums-archive.secondlife.com/356/24/291220/1.html
- https://wiki.secondlife.com/wiki/Zindra
- https://www.hypergridbusiness.com/2013/09/outrage-grows-over-new-second-life-terms
- https://www.dazeddigital.com/science-tech/article/56662/1/why-thousands-of-users-are-abandoning-the-worlds-most-popular-vr-game
- https://techcrunch.com/2026/03/19/meta-decides-not-to-shut-down-horizon-worlds-on-vr-after-all/
- https://www.hypergridbusiness.com/?p=79686
- https://en.wikipedia.org/wiki/NeosVR
- https://en.wikipedia.org/wiki/Dual_Universe
- https://wiki.secondlife.com/wiki/Adult_content
- https://venturebeat.com/technology/book-review-the-making-of-second-life
- https://ispr.info/2022/02/08/meta-establishes-four-foot-personal-boundary-to-deter-vr-groping/
- https://docs.vrchat.com/docs/vrchat-safety-and-trust-system
- https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection
- https://s27.q4cdn.com/984876518/files/doc_news/2025/Aug/15/Roblox-Response-8-15-25.pdf
- https://boingboing.net/2017/05/20/breedables-vs-drm.html
- https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/
- https://arxiv.org/pdf/2411.00114
- https://docs.inworld.ai/models
- https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots
- https://www.jurist.org/news/2026/01/google-and-character-ai-agree-to-settle-lawsuit-linked-to-teen-suicide
- https://quanticfoundry.com/2025/12/18/gen-ai/
- https://modemworld.me/2011/04/11
- https://techcrunch.com/2021/01/25/imvu-35-million-funding/
- https://m.kedglobal.com/newsView/ked202203040009
- https://applevis.com/comment/73862
- https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119
- https://gameaccessibilityguidelines.com/?p=263
- https://thejournal.com/Articles/2010/11/03/Linden-Lab-To-End-Second-Life-Educational-Discounts.aspx
- https://hypergridbusiness.com/2013/07/second-life-restores-half-off-discount-to-educators
- https://www.hypergridbusiness.com/2013/08/educators-wary-of-latest-linden-offer/
- https://www.scitepress.org/Papers/2014/49578/
- https://secondlife.com/destination/vwbpe
- https://www.comscore.com/Insights/Press-Releases/2007/05/Second-Life-Growth-Worldwide
- https://www.engadget.com/2010-06-07-linden-lab-laying-off-staff-closing-singapore-office.html
- https://gilbane.com/?p=2016
- https://sensortower.com/ja/blog/vrchat-high-popularity-in-japan-JP
- https://realsound.jp/tech/2026/02/post-2303955.html
- https://about.roblox.com/newsroom/2025/04/roblox-launches-regional-pricing-for-in-experience-items
- https://about.roblox.com/newsroom/2024/02/roblox-introduces-ai-powered-real-time-chat-translations-in-16-languages
- https://blog.kowatek.com/?p=88910
- https://yespress.io/linden-lab
- https://www.shacknews.com/article/147618/facebook-meta-reality-labs-fy25-losses
- https://en.wikipedia.org/wiki/Active_Worlds
- https://steambase.io/games/resonite
- https://en.wikipedia.org/wiki/Economy_of_Second_Life
- https://ryanschultz.com/2020/05/24/linden-lab-ceo-ebbe-altberg-second-life-has-seen-a-50-increase-in-regular-monthly-users-because-of-the-pandemic/
