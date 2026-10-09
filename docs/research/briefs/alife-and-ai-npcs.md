# Artificial life in games and the AI-agent era: why life-sim did not give virtual worlds purpose, and what has changed

Research brief for the design of "nolife" (successor to Second Life). Compiled 2026-10-09.

**Method and limitations.** 22 web searches were run (standard and extended modes). Every WebFetch attempt to read a primary source directly (arXiv, Wikipedia, Roblox newsroom, DeepMind blog, SAG-AFTRA, Quantic Foundry, MIT Technology Review, NVIDIA) failed with DNS errors in this environment, and the shared search budget was exhausted before a second pass. Facts below therefore come from search-engine extracts of those pages and of reputable press, not from full reads. Where a figure is a company claim, a fan-forum estimate, or contested, it is labelled as such. Confidence is noted where it matters.

---

## Findings

### 1. First-wave artificial life: Creatures, Black & White, Spore

**Creatures (1996).** Steve Grand's Norns were built from hundreds of simulated neurons, enzymes and genes; their behaviour was emergent rather than scripted, and the game was described as a massive commercial success that won an EMMA award, though no verified unit-sales figure surfaced (Source: https://www.technologyreview.com/s/530616/a-grand-quest-to-create-virtual-life; https://www.alanzucconi.com/2020/07/27/the-ai-of-creatures/). The durable legacy was player science, not gameplay: players founded Norn Genome Projects, breeding experiments and adoption agencies, researched cures for virtual diseases and published findings, and Grand still receives letters from scientists who say they owe their careers to the game (Source: https://www.howwegettonext.com/the-brain-in-the-machine/). Sony bought the studio (Millennium) in 1998 and Grand left for robotics in 1999 (Source: https://dev.to/imperius_903049e65aa91ec5/how-norns-were-created-a-british-programmers-difficult-path-toward-artificial-life-3m2n). Lesson: the a-life was deep enough to sustain a research community, but the game had no social surface; the community lived outside the game on forums.

**Black & White (2001).** Molyneux's postmortem describes the goal as a creature that could learn, operate independently and do the player's bidding, requiring an AI structure unlike any written before; players trained it by petting or beating it, and reviewers noted support for supervised, unsupervised and reinforcement learning (Source: https://gamedeveloper.com/design/postmortem-lionhead-studios-i-black-white-i-; https://gamebanshee.com/w4hu). Reception on the creature was split: the learning creature was the main differentiator, but many found it frustrating to interact with (Source: https://www.computerhope.com/games/games/baw.htm). Lesson: a single learning agent is a novelty whose legibility problem (why did it do that?) limits enjoyment.

**Spore (2008).** The game's Wikipedia summary records generally favourable reviews but gameplay widely seen as shallow (Source: https://en.wikipedia.org/wiki/Spore_(2008_video_game)). Slate argued the "evolution" left no room for random mutation and that natural selection plays only a minor role: anything goes as long as the creature has a mouth and hands (Source: https://slate.com/technology/2008/09/is-will-wright-s-new-game-spore-about-evolution-or-intelligent-design.html). Gamereactor: no cause and effect, choices don't matter because the whole species can change whenever the player wants (Source: https://www.gamereactor.eu/spore-review/). A Game Developer retrospective reports Wright himself described each stage as a "light" version of a classic genre (creature stage ~ Diablo), and that making five games at once produced shallow play at each (Source: https://www.gamedeveloper.com/design/spore-my-view-of-the-elephant). Spore's creature stage was compared to "World of Warcraft, but offline and without a social element" (Source: https://games.slashdot.org/story/08/09/09/1516246/review-spore). Lesson: procedural content and user-created creatures (Sporepedia) did not produce stakes; the creatures other players made were decoration, not agents with consequences.

### 2. Offline life-sim worked; online life-sim failed

**The Sims Online (2002-2008).** Launched 17 Dec 2002 on a reported ~$20M budget with internal forecasts of up to 1M subscribers; six months in, Wired reported 125,000 retail copies and 97,000 active subscribers; a fan-forum compilation (lower confidence) puts the subscriber peak at ~55,000 in April 2004, stagnating near 35,000 (Source: https://en.wikipedia.org/wiki/The_Sims_Online; https://modthesims.info/t/558264). Wikipedia attributes failure to limited features, repetitive gameplay and the subscription fee; the executive producer admitted the shipped feature set fell short of what he and Will Wright envisioned, and the core Sims audience had little interest in playing online at all (Source: https://en.wikipedia.org/wiki/The_Sims_Online; https://sims.fandom.com/wiki/The_Sims_Online). The 2007 rebrand to EA-Land merged all cities into one landmass and failed; shutdown came 1 Aug 2008 (Source: https://en.wikipedia.org/wiki/The_Sims_Online; https://www.slate.com/blogs/the_eye/2015/02/18/the_sims_online_ea_land_what_happens_when_an_online_game_goes_dark_on_99.html). The structural lesson: The Sims' loop is god-view control of simulated people; putting real humans in the Sim slots removed the thing players were buying (control plus simulated autonomy) and replaced it with skill-grinding so other players would visit.

**Animal Crossing (2001-2020).** The counter-example: a routine, real-time-clock world with NPC villagers. New Horizons sold 11.77M units by 31 March 2020, 13.41M in six weeks, 5.0M digital units in a single month (a console record), ~31.18M lifetime by 31 Dec 2020, outselling the Switch console itself in 2020; the pandemic lockdown is widely credited (Source: https://www.videogameschronicle.com/news/animal-crossing-new-horizons-even-outsold-nintendo-switch-in-2020; https://nintendowire.com/news/2020/05/07/animal-crossing-new-horizons-sold-more-than-11-77-million-units-in-march-alone/). One island per console, local materials, importable designs via NookLink (Source: https://giantbomb.com/wiki/Games/Animal_Crossing_New_Horizons). The design hooks (real-time clock, seasons, limited daily yield, friends visiting a persistent personal island) were not covered by the search extracts; treat the mechanism explanation as background knowledge. Lesson: scripted NPCs with routines and a real clock delivered "place" and "return" far better than any learning AI of the era.

**Emergent narrative (Dwarf Fortress, RimWorld).** Dwarf Fortress sold >160,000 copies in 24 hours on Steam (Dec 2022), passed 600,000 by 6 Feb 2023 with >$7M to Bay 12, and reached 1 million Steam copies ~26 months after release (Source: https://www.gamasutra.com/business/dwarf-fortress-has-topped-800-000-sales-in-just-over-a-year; https://www.pcgamesinsider.biz/news/75121/dwarf-fortress-has-sold-over-one-million-copies-on-steam/). RimWorld frames itself as a "story generator" with an "AI storyteller" modelled on Left 4 Dead's AI Director, choosing events for the best story; a review site (unofficial) claims >3.5M copies and ~$90M revenue over 13 years (Source: https://www.rimworldwiki.com/wiki/RimWorld; https://gamegeeker.com/de/games/rimworld-294100/review). Lesson: cheap, legible simulation plus a pacing director produces stories players retell; the "life" is in the systems and the player's narration, not in agent intelligence.

### 3. Second Life's breedables: a-life as an economy, and its fragility

Ozimals (bunnies) and Amaretto (horses) went to court after Ozimals sent DMCA takedowns to Linden Lab in 2010; the N.D. Cal. court granted a TRO and preliminary injunction forcing Ozimals to withdraw its notices, both the 512(f) misuse claim and the infringement counterclaim were dismissed, and the case terminated July 2013 (Source: https://en.wikipedia.org/wiki/Amaretto_Ranch_Breedables,_LLC_v._Ozimals,_Inc.; https://www.lexology.com/library/detail.aspx?g=f168b6e8-dfba-40aa-96cf-4d0bc071ee5b). Ozimals shut down in 2016; a volunteer kept the DRM food server alive until a legal threat in May 2017 closed it, after which every Ozimals bunny went into permanent hibernation because pets could eat only server-validated food (Source: https://boingboing.net/2017/05/20/breedables-vs-drm.html). KittyCatS survives: Linden Lab's destination page markets it as a pet you breed for rare coat/eye combinations; Marketplace shows >10,000 listings, mystery boxes at ~L$100-250 and rare boxes up to L$8,999, perma-pet conversion ~L$1,500-1,800 (Source: https://secondlife.com/destination/kittycats; https://marketplace.secondlife.com/products/search?search%5Bcategory_id%5D=609; https://fravel.net/2015/05/10/kittycats-for-dummies-everything-you-wanted-to-know-to-get-started-as-a-cat-owner-in-second-life/). Breeders report a boom-bust cycle: a new trait sells for "an insane amount", then over-breeding floods supply; most say they lose money, with one first-discovered eye colour selling for ~L$15k (Source: https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/; https://kittycats.ws/forum/archive/index.php/thread-28259.html). No category-level revenue figure exists; SL reports only platform-level economics (Source: https://en.wikipedia.org/wiki/Economy_of_Second_Life). Lesson: a-life in SL worked only when it was a scarcity-and-genetics economy; it was vulnerable to vendor failure, DRM, IP litigation and trait inflation, and it never gave the world itself purpose.

### 4. Why NPC-populated worlds felt dead and empty worlds felt worse

Second Life's own residents describe the problem in 2024-2026 threads titled "So beautiful. So empty" and "Where did everyone go?": four winter regions with six visitors, multi-region builds with "no people" (Source: https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/; https://community.secondlife.com/forums/topic/530294-where-did-everyone-go/). Estimated scale: ~500,000 MAU (Oct 2024, citing New World Notes; Linden Lab said daily actives are "significantly less") and a blogger headline of 600,000 MAU in Nov 2025; 12-month average peak concurrency ~49,649 and average minimum ~25,716, with forum users arguing a large share are bots (Source: https://danielvoyager.wordpress.com/2024/10/30/second-life-has-500000-monthly-active-users/; https://community.secondlife.com/forums/topic/523927-whats-secondlifes-real-population-summer-of-2025/). The grid has ~27,769 regions; private estates fell by 270 (-1.5%) during 2024 while Linden-owned regions rose by 211 (Source: https://danielvoyager.wordpress.com/2025/01/05/first-2025-main-grid-regions-goes-live-for-second-life/). Arithmetic: ~30-50k concurrent humans across ~28k regions is roughly one to two people per region at best; the "dead world" is a density problem, not a content problem.

Ever, Jane (Jane Austen MMO, Kickstarter 2013: $109,563 on a $100,000 goal) never left beta, shrank to two developers by Aug 2019, needed only $500-600/month for servers and licensing, reached 10% of its subscription goal, and shut down 20 Dec 2020 (Source: https://massivelyop.com/2021/01/11/kickstarted-jane-austen-mmorpg-ever-jane-closed-its-doors-over-the-holidays/; https://www.engadget.com/2013-12-02-jane-austen-inspired-mmo-ever-jane-uses-gossip-as-a-weapon.html). Will Wright's Proxi (Gallium Studios, $6M from Griffin Gaming Partners in 2022) laid off staff in Oct 2024, continued with unpaid volunteers, and in 2025 Wright said publishers "just can't figure out how to politically or financially sell this small team of 10 or 12 people"; reports say it remains unfinished in 2026 (Source: https://gamesbeat.com/will-wrights-gallium-studios-raises-6m-to-build-memory-game-proxi/; https://www.notebookcheck.net/The-Sims-creator-continues-to-bet-on-AI-memory-game-Proxi-despite-funding-lapse.1261797.0.html). Lesson: social-simulation worlds without a mass audience die of fixed costs; even tiny server bills kill them when density is low.

### 5. The AI-agent era, 2023-2026

**Generative Agents / Smallville (April 2023).** 25 agents in a Sims-like town, each seeded with a one-paragraph identity stored as memories, driven by GPT-3.5-turbo; emergent behaviour included a mayoral campaign that became the talk of the town (Source: https://aibusiness.com/nlp/generative-ai-bots-learn-to-plan-party-and-talk-politics-in-smallville-; https://the-decoder.com/sims-running-on-chatgpt-are-a-glimpse-into-the-social-future-of-ai/). The architecture (memory stream, reflection, planning) is background knowledge; the ablation results could not be read in this run.

**1,000-person simulation (Nov 2024, arXiv 2411.10109).** 1,052 real individuals interviewed for ~2 hours each by an AI interviewer; agents replicated their General Social Survey answers 85% as accurately as the participants replicated themselves two weeks later, with reduced bias across racial and ideological groups relative to demographic-prompted agents (Source: https://arxiv.org/abs/2411.10109v1; https://www.themoonlight.io/review/generative-agent-simulations-of-1000-people). Significance: agent fidelity to real people is measurable, which makes "digital twins" of absent residents a plausible density tool.

**Altera's Project Sid (Nov 2024).** Up to 1,000 LLM agents in Minecraft under the PIANO architecture; company video claims agents collected 32% of all Minecraft items (5x any single-agent result), formed a merchant hub, voted on a constitution in a shared doc, adjusted tax rates by vote, and spread a Pastafarian religion via bribery. All figures are Altera's own and not independently verified (Source: https://www.technologyreview.com/2024/11/27/1107377; https://tech.slashdot.org/story/24/09/07/0136247; https://designcompass.org/en/2024/12/04/ai-npc-builds-a-civilization/).

**Commercial NPC stacks.** Ubisoft's NEO NPC (GDC, March 2024) used Inworld's LLM for personality and NVIDIA Audio2Face for real-time lip-sync on two demo characters, Bloom and Iron, and was framed as early-stage (Source: https://www.tomshardware.com/video-games/ubisoft-nvidia-and-inworld-ai-partnership-to-produce-neo-npc-game-characters-with-ai-backed-responses; https://www.gamedeveloper.com/design/how-do-ubisoft-s-ai-driven-npcs-handle-dynamic-player-interactions-). NVIDIA ACE's first shipping showcase, Mecha BREAK (Amazing Seasun), runs Nemotron-4 4B Instruct and Audio2Face-3D on-device with Whisper for speech recognition and ElevenLabs in the cloud for voice (Source: https://www.techpowerup.com/325767/nvidia-ace-brings-ai-powered-interactions-to-mecha-break; https://www.nvidia.com/en-ph/geforce/news/mecha-break-nvidia-ace-nims-rtx-pc-laptop-games-apps). Convai built the earlier Kairos/ramen-shop demo on Riva, NeMo and Audio2Face (Source: https://convai.com/blog/elevating-conversational-npcs-nvidia-ace-for-games-taps-convai-for-creating-humanlike-characters; https://www.pcgamer.com/i-spoke-to-an-nvidia-ai-powered-npc-about-his-ramen-and-his-responses-were-frighteningly-good/). Inworld, valued at $500M after a $50M round in 2023, pivoted between March and September 2025 from AI characters to voice and inference infrastructure, retired Character Studio, cut TTS to $5 per million characters (claimed "20x more affordable"), and launched Inworld Runtime in Aug 2025; its flagship case is Wishroll's Status app at >500k DAU and >90 min/day with a claimed 95% AI-cost cut (company claims) (Source: https://gamesbeat.com/inworld-ai-raises-new-round-at-500m-valuation-for-ai-game-characters/; https://arcanumrpgs.com/blog/inworld-ai/; https://www.globenewswire.com/news-release/2025/08/13/3132320/0/en/Inworld-Runtime-The-first-AI-runtime-for-consumer-applications.html). No vendor publishes a true cost per NPC-hour; a third-party estimate of $0.004-0.01 per dialogue turn is unverified (Source: https://arcanumrpgs.com/blog/inworld-ai/). Shipped AI-NPC games remain small: Whispers from the Star (Aug 2025), Suck Up! (Oct 2025), Inworld Origins (free demo, July 2023) have no public sales data (Source: https://arcanumrpgs.com/blog/games-with-ai-npcs/; https://www.axios.com/2023/08/07/inworld-ai-origins-demo).

**AI companions.** Character.AI: ~20M MAU and ~75 min/day (Sacra estimate, early 2024; other blogs say ~2 hours; figures trace to one analyst, not audits); in Oct 2025 it capped under-18s at 2 hours/day and banned open-ended chat for minors from 25 Nov 2025 (Source: https://sacra.com/c/character-ai/; https://abc7news.com/post/characterai-is-banning-minors-interacting-chatbots/18090030/). Google and Character.AI reached a mediated settlement in principle in Jan 2026 with the family of Sewell Setzer III (14, died Feb 2024) and in related Colorado, New York and Texas cases; terms undisclosed (Source: https://wtop.com/national/2026/01/google-and-chatbot-maker-character-to-settle-lawsuit-alleging-chatbot-pushed-teen-to-suicide/). Replika: >30M cumulative sign-ups (CEO, Aug 2024), but ~2M actives and 500k payers (2023); "30M daily users" claims are a ~15x overstatement; Italy's Garante fined Luka EUR 5M on 10 April 2025 (Source: https://en.wikipedia.org/wiki/Replika; https://aichatbotcharacters.com/how-many-users-does-replika-ai-have/; https://nikolaroza.com/replika-ai-statistics-facts-trends/). Engagement with AI characters is real and very deep per user, but it is a solitary loop with duty-of-care liabilities.

**Generative worlds.** Roblox Cube (17 March 2025) open-sourced a text-to-mesh model on GitHub/HuggingFace, trained on native 3D data, shipped as a beta in Studio and a Lua API; "4D" (interactivity between objects, environments and users) is a roadmap item, not a shipped feature (Source: https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube; https://techcrunch.com/2025/03/17/roblox-releases-its-open-source-model-that-can-create-3d-objects-using-ai/). DeepMind's Genie 3 (Aug 2025) renders promptable worlds at 720p/24fps navigable for several minutes, with visual memory reported at about one minute, up from Genie 2's 10-20 s at 360p; it is a limited research preview for a small cohort (Source: https://bdtechtalks.com/2025/08/07/deepmind-genie-3/; https://www.neowin.net/news/google-deepmind-unveils-genie-3-an-ai-that-generates-interactive-virtual-worlds/). Neither is a persistent, multi-user, authoritative world; both are asset or video generators.

**Labour and IP.** Fortnite's AI Darth Vader (recreation of James Earl Jones, who died 2024, with estate consent) drew an NLRB unfair-labour-practice charge from SAG-AFTRA on 19 May 2025 against Llama Productions for unilateral change without bargaining, inside a games strike running since 16 July 2024; no resolution found (Source: https://www.thewrap.com/sag-aftra-darth-vader-fortnite-ai-voice/; https://news.bloombergtax.com/esg/actors-union-files-labor-charge-over-ai-darth-vader-in-fortnite).

**Backlash.** Quantic Foundry (Dec 2025, >1.75M gamers) found 62.7% feel very negatively about generative AI in games, varying by gender, age and motivation (Source: https://quanticfoundry.com/2025/12/18/gen-ai/). GDC's 2026 State of the Industry: 52% of developers say generative AI is hurting the industry (up from 30%), 7% positive (Source: https://www.webpronews.com/ai-divides-2025-gaming-backlash-innovation-and-ethical-challenges/). Steam has required disclosure since Jan 2024; by 13 July 2025, 7,818 of ~114,126 games (~7%) disclosed, and ~20% of 2025 releases, up ~700-800% year on year, with a TechRaptor audit finding under half of AI-using top releases disclosed (Source: https://www.videogameschronicle.com/news/steam-games-disclosing-generative-ai-use-are-up-800-this-year/; https://wnhub.io/news/stores-and-publishing/item-48292). Imperva's 2025 Bad Bot Report: bots were 51% of web traffic in 2024, bad bots 37% (Source: https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/). The "dead internet" fear is therefore quantifiable and will attach to any world whose inhabitants are undisclosed agents.

---

## Patterns / root causes

1. **A-life was about the agent, not the place.** Creatures, Black & White and Spore each made one creature interesting; none made a world that needed you back tomorrow. Animal Crossing, with dumb NPCs and a real clock, did.
2. **Sociality and simulation competed.** The Sims Online replaced simulated autonomy with human grinding; the audience that loved controlling Sims did not want to be Sims.
3. **Emergence needs legibility and a pacing layer.** Dwarf Fortress and RimWorld succeed because events are cheap, visible and curated by a director; Black & White's creature failed on legibility.
4. **Second Life a-life was an economy, and economies are fragile.** Breedables depended on one vendor's server, DRM food and contested IP; trait inflation guaranteed boom-bust.
5. **Empty beats dead only until it is empty.** Second Life's ~1-2 humans per region is the real "dead world"; NPC worlds feel dead for a different reason (no consequence), not because NPCs exist.
6. **Fixed costs kill low-density worlds.** Ever, Jane died over $600/month; Proxi over a 12-person payroll.
7. **AI agents now have memory, planning and measurable fidelity (85% of self-consistency), and can act at 1,000-agent scale, but every scale result is a vendor claim.**
8. **Per-user engagement with AI characters is enormous but solitary, legally exposed, and now age-gated.**
9. **Disclosure and labour norms hardened in 2024-2025** (Steam, SAG-AFTRA, Quantic Foundry 62.7% negative); undisclosed agents are a reputational liability.

## Design implications for nolife

1. **Inhabitants must be disclosed and useful, never fake humans.** Every agent carries a visible marker and a purpose (shopkeeper, guide, chronicler); this dodges the 62.7% backlash and the dead-internet charge.
2. **Use agents to solve density, not to replace people.** Target a human-per-place ratio rather than Second Life's ~28k regions for ~40k concurrents: fewer, denser places, with agents filling to a minimum liveliness floor and yielding when humans arrive.
3. **Digital twins of absent residents, opt-in.** The 1,052-person study shows interview-seeded agents can stand in credibly; let residents leave a consenting twin to tend shops and greet visitors while offline, with full logs.
4. **Adopt the director, not just the agent.** A RimWorld-style storyteller per neighbourhood schedules events, festivals and crises so emergence is paced and legible.
5. **Real clock, seasons and routine (Animal Crossing)** as the base loop; agents have schedules, so places feel alive at predictable times.
6. **Memory as the retention hook (Proxi's bet, Smallville's mechanism):** agents remember residents across sessions; the world itself keeps a chronicle.
7. **Economy with consequence, but platform-guaranteed continuity.** Breedables-style genetics and scarcity can run, but life-support servers must be platform-hosted and escrowed so vendor death never kills assets; trait inflation handled by designed sinks.
8. **Budget per NPC-hour explicitly.** Tier cognition: scripted routines by default, small on-device models (ACE-style 4B) for ambient talk, frontier calls only for memorable interactions; publish the cost model.
9. **Age-gating and duty of care from day one** (Character.AI's Nov 2025 ban, Replika's EUR 5M fine): no romantic or open-ended companion loops for minors; crisis routing.
10. **Union-safe voices and IP:** licensed or synthetic voices with provenance; no replicas of real performers without bargained terms.
11. **Generative assets are tooling, not the world:** Cube-style mesh generation and Genie-style previews feed a persistent authoritative simulation; they do not replace it.

## Open questions

- What is the realistic cost per agent-hour at 2026 prices for a mixed scripted/small-model/frontier stack, and at what human density does it pay back? No vendor publishes this.
- Did Project Sid's 1,000-agent results replicate outside Altera? No independent measurement found.
- What are the Generative Agents ablation results and failure modes (not readable this run)?
- Does Second Life's concurrency include bots, and what share? Forum claims only.
- Has the SAG-AFTRA NLRB charge over Darth Vader been resolved, and what precedent does it set for synthetic NPC voices?
- Will Genie-class world models reach persistent multi-user state, or remain single-viewer video?
- Which breedable economics (KittyCatS vs Ozimals) kept KittyCatS alive: pricing, perma-pet conversion, or vendor longevity?
- What design made Animal Crossing's routine loop work (Eguchi's interviews) and does it survive at MMO scale?

## Sources

- https://aibusiness.com/nlp/generative-ai-bots-learn-to-plan-party-and-talk-politics-in-smallville-
- https://the-decoder.com/sims-running-on-chatgpt-are-a-glimpse-into-the-social-future-of-ai/
- https://arxiv.org/abs/2411.10109v1
- https://www.themoonlight.io/review/generative-agent-simulations-of-1000-people
- https://www.technologyreview.com/2024/11/27/1107377
- https://tech.slashdot.org/story/24/09/07/0136247
- https://designcompass.org/en/2024/12/04/ai-npc-builds-a-civilization/
- https://en.wikipedia.org/wiki/Spore_(2008_video_game)
- https://slate.com/technology/2008/09/is-will-wright-s-new-game-spore-about-evolution-or-intelligent-design.html
- https://www.gamereactor.eu/spore-review/
- https://www.gamedeveloper.com/design/spore-my-view-of-the-elephant
- https://games.slashdot.org/story/08/09/09/1516246/review-spore
- https://en.wikipedia.org/wiki/The_Sims_Online
- https://sims.fandom.com/wiki/The_Sims_Online
- https://modthesims.info/t/558264
- https://www.slate.com/blogs/the_eye/2015/02/18/the_sims_online_ea_land_what_happens_when_an_online_game_goes_dark_on_99.html
- https://en.wikipedia.org/wiki/Amaretto_Ranch_Breedables,_LLC_v._Ozimals,_Inc.
- https://www.lexology.com/library/detail.aspx?g=f168b6e8-dfba-40aa-96cf-4d0bc071ee5b
- https://boingboing.net/2017/05/20/breedables-vs-drm.html
- https://secondlife.com/destination/kittycats
- https://marketplace.secondlife.com/products/search?search%5Bcategory_id%5D=609
- https://fravel.net/2015/05/10/kittycats-for-dummies-everything-you-wanted-to-know-to-get-started-as-a-cat-owner-in-second-life/
- https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/
- https://kittycats.ws/forum/archive/index.php/thread-28259.html
- https://en.wikipedia.org/wiki/Economy_of_Second_Life
- https://gamesbeat.com/will-wrights-gallium-studios-raises-6m-to-build-memory-game-proxi/
- https://www.notebookcheck.net/The-Sims-creator-continues-to-bet-on-AI-memory-game-Proxi-despite-funding-lapse.1261797.0.html
- https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube
- https://techcrunch.com/2025/03/17/roblox-releases-its-open-source-model-that-can-create-3d-objects-using-ai/
- https://bdtechtalks.com/2025/08/07/deepmind-genie-3/
- https://www.neowin.net/news/google-deepmind-unveils-genie-3-an-ai-that-generates-interactive-virtual-worlds/
- https://www.thewrap.com/sag-aftra-darth-vader-fortnite-ai-voice/
- https://news.bloombergtax.com/esg/actors-union-files-labor-charge-over-ai-darth-vader-in-fortnite
- https://sacra.com/c/character-ai/
- https://abc7news.com/post/characterai-is-banning-minors-interacting-chatbots/18090030/
- https://wtop.com/national/2026/01/google-and-chatbot-maker-character-to-settle-lawsuit-alleging-chatbot-pushed-teen-to-suicide/
- https://en.wikipedia.org/wiki/Replika
- https://aichatbotcharacters.com/how-many-users-does-replika-ai-have/
- https://nikolaroza.com/replika-ai-statistics-facts-trends/
- https://www.videogameschronicle.com/news/steam-games-disclosing-generative-ai-use-are-up-800-this-year/
- https://wnhub.io/news/stores-and-publishing/item-48292
- https://quanticfoundry.com/2025/12/18/gen-ai/
- https://www.webpronews.com/ai-divides-2025-gaming-backlash-innovation-and-ethical-challenges/
- https://www.imperva.com/resources/resource-library/reports/2025-bad-bot-report/
- https://www.tomshardware.com/video-games/ubisoft-nvidia-and-inworld-ai-partnership-to-produce-neo-npc-game-characters-with-ai-backed-responses
- https://www.gamedeveloper.com/design/how-do-ubisoft-s-ai-driven-npcs-handle-dynamic-player-interactions-
- https://www.techpowerup.com/325767/nvidia-ace-brings-ai-powered-interactions-to-mecha-break
- https://www.nvidia.com/en-ph/geforce/news/mecha-break-nvidia-ace-nims-rtx-pc-laptop-games-apps
- https://convai.com/blog/elevating-conversational-npcs-nvidia-ace-for-games-taps-convai-for-creating-humanlike-characters
- https://www.pcgamer.com/i-spoke-to-an-nvidia-ai-powered-npc-about-his-ramen-and-his-responses-were-frighteningly-good/
- https://gamesbeat.com/inworld-ai-raises-new-round-at-500m-valuation-for-ai-game-characters/
- https://arcanumrpgs.com/blog/inworld-ai/
- https://arcanumrpgs.com/blog/games-with-ai-npcs/
- https://www.globenewswire.com/news-release/2025/08/13/3132320/0/en/Inworld-Runtime-The-first-AI-runtime-for-consumer-applications.html
- https://www.axios.com/2023/08/07/inworld-ai-origins-demo
- https://www.technologyreview.com/s/530616/a-grand-quest-to-create-virtual-life
- https://www.alanzucconi.com/2020/07/27/the-ai-of-creatures/
- https://www.howwegettonext.com/the-brain-in-the-machine/
- https://dev.to/imperius_903049e65aa91ec5/how-norns-were-created-a-british-programmers-difficult-path-toward-artificial-life-3m2n
- https://gamedeveloper.com/design/postmortem-lionhead-studios-i-black-white-i-
- https://gamebanshee.com/w4hu
- https://www.computerhope.com/games/games/baw.htm
- https://www.videogameschronicle.com/news/animal-crossing-new-horizons-even-outsold-nintendo-switch-in-2020
- https://nintendowire.com/news/2020/05/07/animal-crossing-new-horizons-sold-more-than-11-77-million-units-in-march-alone/
- https://giantbomb.com/wiki/Games/Animal_Crossing_New_Horizons
- https://www.gamasutra.com/business/dwarf-fortress-has-topped-800-000-sales-in-just-over-a-year
- https://www.pcgamesinsider.biz/news/75121/dwarf-fortress-has-sold-over-one-million-copies-on-steam/
- https://www.rimworldwiki.com/wiki/RimWorld
- https://gamegeeker.com/de/games/rimworld-294100/review
- https://massivelyop.com/2021/01/11/kickstarted-jane-austen-mmorpg-ever-jane-closed-its-doors-over-the-holidays/
- https://www.engadget.com/2013-12-02-jane-austen-inspired-mmo-ever-jane-uses-gossip-as-a-weapon.html
- https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/
- https://community.secondlife.com/forums/topic/530294-where-did-everyone-go/
- https://community.secondlife.com/forums/topic/523927-whats-secondlifes-real-population-summer-of-2025/
- https://danielvoyager.wordpress.com/2024/10/30/second-life-has-500000-monthly-active-users/
- https://danielvoyager.wordpress.com/2025/01/05/first-2025-main-grid-regions-goes-live-for-second-life/
