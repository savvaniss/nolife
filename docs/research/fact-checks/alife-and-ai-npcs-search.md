# Search verification: alife-and-ai-npcs

Date: 2026-10-09. Checker with live WebSearch (12 of 12 budgeted searches used; 11 standard, 1 extended).

**Method note.** Page fetching (WebFetch/curl) is blocked in this sandbox. Every verdict below rests on the quoted extracts returned by search results, not on full reads of primary pages. Where an extract quotes a primary source (Inworld docs, Quantic Foundry post, arXiv abstract, Daniel Voyager stats) I say so; otherwise the evidence is press or blog reporting. The two earlier checkers had no search access; their notes were treated as prior knowledge only. Claims 1 and 4 were not searched (budget) and are marked unverifiable.

## Summary table

| # | Claim (short) | Verdict | Searched | Key source |
|---|---|---|---|---|
| 0 | Sims Online: 1M target, 97k subs at 6 months, EA-Land closed 1 Aug 2008 | confirmed | yes | loosewireblog.com (citing Wired, May 2003) |
| 1 | ACNH 31.18M by 31 Dec 2020 vs Switch 27.3M | unverifiable | no (budget) | - |
| 2 | Ozimals volunteer server closed May 2017; all bunnies permanently hibernated | corrected | yes | boingboing.net 2017/05/20 |
| 3 | SL ~500k MAU; 49,649 avg peak concurrency; 27,769 regions | corrected | yes | danielvoyager.wordpress.com (Nov 2024 grid stats; 2025-26 concurrency posts) |
| 4 | Stanford 1,052-person agents, 85% | unverifiable | no (budget) | - |
| 5 | Project Sid 1,000 agents, 32% of items, constitution, taxes, video-only claims | corrected | yes | arxiv.org/pdf/2411.00114; technologyreview.com |
| 6 | Inworld $500M, 2025 pivot, Character Studio retired, $5/M chars TTS | confirmed (with caveats) | yes | inworld.ai/blog; docs.inworld.ai; fish.audio pricing comparison |
| 7 | Character.AI under-18 ban 25 Nov 2025; Setzer settlement Jan 2026 | confirmed | yes | jurist.org Jan 2026; Bloomberg/TechCrunch 29 Oct 2025 |
| 8 | SAG-AFTRA NLRB charge 19 May 2025 vs Llama Productions | confirmed | yes | news.bloomberglaw.com |
| 9 | Steam 7,818/114,126, 20% of 2025 releases; Quantic Foundry 62.7% of >1.75M | corrected | yes | quanticfoundry.com/2025/12/18/gen-ai; videogameschronicle.com |

## Claim-by-claim

### 0. The Sims Online - confirmed
Loose Wire blog, citing a May 2003 Wired article: TSO "had sold 125,000 copies retail and has 97,000 active subscribers" six months after launch, and EA was "nowhere close to its target of 1 million active monthly subscribers". Harvard D3 piece: 82,000 subscriptions in the first month; Italian press, Jan 2003: 108,000 copies, below EA expectations. Launch date and 1 Aug 2008 closure were not re-searched but nothing contradicted them. Wording: the 1M figure is reported as EA's public *target*, not an "internal forecast". The original Wired piece could not be reached.
Source: https://www.loosewireblog.com/?p=2349 ; https://d3.harvard.edu/platform-digit/submission/the-sims-online-should-have-taken-its-own-advice-to-be-somebody-else-or-when-networks-fight-back/index.html

### 1. Animal Crossing: New Horizons - unverifiable (not searched, budget)
Both prior checkers recall 31.18M as Nintendo's own figure at 31 Dec 2020 and a ~27.4M calendar-2020 Switch total. Low risk; not searched.

### 2. Ozimals - corrected
Sequence confirmed, and it supports the **brief's** narrative rather than checker 1's correction: Ozimals the company closed in 2016; a volunteer, Malkavyn Eldritch, then ran the validation server; in May 2017 Edward Distelhurst / Akimeta Ltd (asserting Ozimals owed him money and claiming its IP) sent a cease-and-desist; Eldritch complied ("I do not have the means to fight this in court"). Corrections to the claim text:
- Not *all* bunnies: before shutdown Ozimals had given away items that make rabbits not need food (leaving them sterile); Boing Boing: "some rabbits will live on forever, the last of their kind".
- "Permanent" is the BBC's word; rabbits hibernate after 72 hours unfed and wake when fed, so permanence follows only from the absence of any server.
- Pufflings (another Ozimals breedable) died instantly when the servers went down.
Source: https://boingboing.net/2017/05/20/breedables-vs-drm.html ; https://archive.vrroom.studio/?p=24844 (BBC reproduction)

### 3. Second Life scale - corrected
- ~500,000 MAU (Oct 2024): confirmed; Voyager relays an interview with Linden Lab's owner giving roughly 500k MAU in mid/late Oct 2024. A community comment notes LL only releases MAU occasionally.
- Regions: Voyager's Nov 2024 grid statistics give 27,729 total (17,923 private, 9,806 Linden-owned), not 27,769. By mid-June 2026: 27,192 (17,780 private, 9,412 Linden).
- Concurrency: no "12-month average peak" of 49,649 was found. Voyager publishes daily maxima: 2025 high 49,798 (24 Mar 2025); 2026 high 48,802 (1 Mar 2026); monthly maxima Jun-Sep 2026 of 44,931 / 43,822 / 45,483 / 43,891.
Recommended wording: "~45-50k peak concurrency across ~27.2-27.7k regions". The density conclusion (1-2 people per region at best) stands and is an upper bound since concurrency counts bots.
Source: https://danielvoyager.wordpress.com/2024/11/04/second-life-grid-statistics-november-2024/ ; https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/ ; https://danielvoyager.wordpress.com/2026/04/08/second-life-user-concurrency-early-april-2026-update/

### 4. Stanford 1,000-person generative agents - unverifiable (not searched, budget)
Both prior checkers independently recall every specific. Lowest-risk claim in the set.

### 5. Project Sid - corrected
arXiv 2411.00114 "Project Sid: Many-agent simulations toward AI civilization" (Altera.AL) exists; its abstract covers 10-1000+ agents, PIANO, Minecraft, specialized roles, adhering to and changing collective rules, cultural and religious transmission, and calls the findings "preliminary". MIT Technology Review (27 Nov 2024) confirms up to 1,000 agents, tax votes swayed by pro/anti-tax agents, Pastafarian seeding in a 500-agent run, and runs of 12 in-game days (4 wall-clock hours). Corrections: cite the preprint, not "its own video"; the "32% of all Minecraft items" figure did not appear in any extract across two searches and must be flagged unconfirmed (it may be in the paper body, which could not be fetched). No independent replication found, so "unverified company claims" is fair.
Source: https://arxiv.org/pdf/2411.00114 ; https://www.technologyreview.com/2024/11/27/1107377

### 6. Inworld AI - confirmed, with caveats
Inworld's own blog ("The new AI infrastructure for scaling games, media, and characters") and docs confirm the pivot: Runtime is "Inworld's new AI orchestration platform" that "provides the same tools that powered AI characters in Studio as a composable toolkit"; the arcanumrpgs explainer reports an Inworld docs page saying "the legacy Inworld Character Studio has been retired". $5 per million characters confirmed for Inworld-TTS-1 (TTS-1-Max $10/M) via a fish.audio comparison page. The $500M valuation (Aug 2023 round) appears in TechCrunch/Lightspeed results. Caveats: the "March-September 2025" window is the third-party blog's framing only; TTS-1/TTS-1-Max are now marked deprecated in Inworld's model docs in favour of TTS-1.5-mini/max (prices unconfirmed), so $5/M is a 2025 price; Runtime docs still mention "Character Studio directly in-engine", so some character tooling survives under the Runtime brand.
Source: https://inworld.ai/blog/new-ai-infrastructure-scaling-games-media-characters ; https://docs.inworld.ai/guides/runtime-character ; https://docs.inworld.ai/models ; https://fish.audio/vs/pricing/inworld-ai/ ; https://arcanumrpgs.com/blog/inworld-ai/

### 7. Character.AI minors ban and Setzer settlement - confirmed
Bloomberg/TechCrunch (29 Oct 2025): open-ended chats for under-18s to end by 25 Nov 2025; interim cap "starts at two hours per day and goes down over the following weeks"; age assurance via an in-house behavioural tool plus Persona; teens redirected to prompt-based story/visual creation. JURIST and wire reports (early Jan 2026; one outlet says 14 Jan): Google and Character.AI agreed to settle the Florida (Garcia/Setzer) case plus Colorado, New York and Texas suits; terms undisclosed; M.D. Fla. dismissed with 90 days to finalize or reopen; Google's exposure comes from its $2.7B 2024 licensing deal and rehiring of the founders.
Source: https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots ; https://www.jurist.org/news/2026/01/google-and-character-ai-agree-to-settle-lawsuit-linked-to-teen-suicide

### 8. SAG-AFTRA NLRB charge - confirmed; no outcome found
SAG-AFTRA announced on 19 May 2025 an NLRB unfair labor practice charge against Llama Productions LLC (Epic-owned) for launching the AI Vader "without providing any notice of their intent to do this and without bargaining with us over appropriate terms"; the James Earl Jones family had approved the use. No disposition appeared in results; the charge copy carried no docket number. Next step: NLRB public case search.
Source: https://news.bloomberglaw.com/tech-and-telecom-law/actors-union-files-labor-charge-over-ai-darth-vader-in-fortnite ; https://esports.gg/news/fortnite/sag-aftra-files-unfair-labor-charge-against-fortnite-ai-darth-vader

### 9. Steam disclosures and Quantic Foundry - corrected
Steam half confirmed: Totally Human Media (Ichiro Lambe), as of 13 Jul 2025: 7,818 of ~114,126 games (~7%) disclose gen-AI; ~20% of 2025 releases; ~800% up on a ~1,000-title 2024 baseline (Apr 2024 study: 1.1%); ~60% of disclosed uses are visual assets; disclosure counts are a floor. TechRaptor separately: 18% of the top 100 2025 releases.
Quantic Foundry half corrected: the 18 Dec 2025 post reports an optional survey of **1,799 respondents** (Oct-Dec 2025): 85% below neutral, 63% (62.7%) chose the most negative option. The ">1.75M gamers" figure repeated by secondary outlets is an error (it is the size of Quantic Foundry's cumulative profile dataset). Segmentation: women/non-binary, younger and story-focused gamers more negative; older and power-progression-motivated gamers more favourable.
Source: https://quanticfoundry.com/2025/12/18/gen-ai/ ; https://www.videogameschronicle.com/news/steam-games-disclosing-generative-ai-use-are-up-800-this-year/ ; https://insider-gaming.com/nearly-20-of-new-steam-games-in-2025-use-generative-ai/

## Additional findings for a successor world
1. Ozimals' pre-shutdown giveaway of food-independent (sterile) items is a proven end-of-life escape hatch: a "perma-pet" conversion that trades reproduction for server independence should be designed in from day one. The 2017 claimant was a creditor asserting IP ownership over a dead vendor's code, a distinct failure mode from vendor-vs-vendor DMCA fights.
2. Second Life density keeps falling slowly: peak concurrency ~49.8k (Mar 2025) to ~43.9k (Sep 2026); regions 27,729 (Nov 2024) to 27,192 (Jun 2026). Concurrency includes bots. A Dec 2024 VentureBeat interview summary attributes ~$650M annual revenue to Linden's owner (unverified); mid-2010s MAU was 900k per then-CEO Altberg.
3. Quantic Foundry segmentation: hostility to gen-AI is strongest among exactly the social/story-motivated players a persistent social world would target, so disclosure posture must be strongest there.
4. Project Sid runs lasted 4 wall-clock hours; the authors call results preliminary. A 2026 arXiv literature on long-horizon agent societies now exists and the brief misses it: Agentopia (2606.07513), OpenLife (2606.31046), Emergence World (2606.08367), Interaction Theater (2602.20059), Superminds Test (2604.22452), Moltbook socialization case study (2602.14299).
5. Inworld's TTS-1 pricing ($5/M) is already superseded by TTS-1.5; vendor prices turn over within a year, so NPC cost models should be parameterised. WishRoll's "one million users in 19 days with over 20x cost reduction" is a vendor testimonial.
6. Character.AI's minors design (prompt-based co-creation instead of open chat, behavioural age inference plus Persona) is a concrete pattern; the sealed settlement sets no liability precedent, but Google's $2.7B licensing deal shows that licensing a companion model carries litigation exposure.
7. The Fortnite Vader NLRB charge has no reported disposition; check the NLRB case search for Llama Productions LLC (May 2025).
8. VGC reports Valve has "significantly" rewritten Steam's AI disclosure rules (date not captured); any Steam plan for a live-LLM world should re-read the current text.
