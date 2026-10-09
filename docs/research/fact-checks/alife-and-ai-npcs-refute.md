# Adversarial fact-check: "A-life in games and the AI-agent era"

Checked 2026-10-09 against the brief at `scratchpad/research/alife-and-ai-npcs.md`.

**Method and limitation (important).** Every WebFetch to a primary source (Wikipedia, VGC, Boing Boing, Daniel Voyager, arXiv, MIT Technology Review, Arcanum, ABC7, TheWrap, Quantic Foundry) failed with `getaddrinfo ENOTFOUND`, and the shared per-turn WebSearch budget (200 calls) was already used up by other agents before this checker's first query. No live evidence could be gathered, and the instructions forbid curl/proxy workarounds. Verdicts below are therefore graded from the checker's own knowledge (training cutoff June 2026), with confidence stated per claim and the primary source named for a later live re-check. Where the checker's recall is not strong enough to confirm a specific number, the verdict is "unverifiable" even if the gist is plausible.

| # | Claim (short) | Verdict | Checker confidence |
|---|---|---|---|
| 0 | Sims Online: 17 Dec 2002 launch, 1M forecast, 97k subs at six months, EA-Land closed 1 Aug 2008 | confirmed (dates); 97k figure not re-checked | high on dates, medium on 97k |
| 1 | ACNH 31.18M by 31 Dec 2020 vs Switch 27.3M in CY2020 | confirmed (Switch CY2020 sums to ~27.4M from Nintendo quarterlies) | high |
| 2 | May 2017 legal threat closed Ozimals food server; bunnies in permanent hibernation | confirmed, with a caveat on "volunteer-run" | medium-high |
| 3 | SL ~500k MAU (Oct 2024), 12-mo avg peak concurrency ~49,649, ~27,769 regions | unverifiable (plausible; numbers are blogger compilations) | medium |
| 4 | Stanford 1,052-person generative agents, 85% of self-replication on GSS | confirmed | high |
| 5 | Project Sid: 1,000 agents, 32% of items, constitution, taxes; "video-only, unverified" | corrected: there is an arXiv paper (2411.00114, 31 Oct 2024); still not independently replicated | high |
| 6 | Inworld $500M valuation 2023; 2025 pivot; Character Studio retired; TTS $5/M chars | confirmed on valuation, Runtime (13 Aug 2025) and TTS price; retirement window unverifiable | medium |
| 7 | Character.AI minors cap/ban (25 Nov 2025); Google/C.AI settlement in principle Jan 2026 | confirmed | high |
| 8 | SAG-AFTRA NLRB charge 19 May 2025 vs Llama Productions over AI Vader | confirmed | high |
| 9 | Steam: 7,818 of ~114,126 (~7%), ~20% of 2025 releases, +700-800% YoY; Quantic Foundry 62.7% very negative | confirmed on Steam figures; Quantic Foundry figure unverifiable and the ">1.75M" sample is likely misattributed | medium |

## Claim-by-claim

### [0] The Sims Online
- **Verdict: confirmed (dates and forecast); the 97,000 figure could not be re-read.**
- Launch 17 December 2002 and EA-Land shutdown on 1 August 2008 (closure announced 29 April 2008) match the record. EA's public hope of roughly one million subscribers was widely reported at launch. Wired's 2003 coverage reported subscriber counts in the ~80-105k band; the brief's "97,000 active subscribers at six months" is consistent with Wikipedia's summary of that reporting but was not re-read here.
- Adversarial note: the ~55k/35k later figures in the brief body come from a fan-forum compilation and should not be promoted to a claim. Separately, the brief's "~$20M budget" is a press estimate, not an EA filing.
- Re-check against: https://en.wikipedia.org/wiki/The_Sims_Online and the Wired piece it cites.

### [1] Animal Crossing: New Horizons vs Switch, 2020
- **Verdict: confirmed.**
- Nintendo's Q3 FY2021 results (published 1 Feb 2021) list ACNH lifetime sell-through at 31.18M as of 31 Dec 2020; since the game launched 20 March 2020, all of it is calendar-2020. Switch hardware by Nintendo quarter: Jan-Mar 2020 ~3.29M, Apr-Jun ~5.68M, Jul-Sep ~6.86M, Oct-Dec ~11.57M, total ~27.4M. The VGC headline figure of 27.3M is within rounding. The claim holds.
- Re-check against: Nintendo IR "Consolidated Sales Transition by Region" / Q3 FY3/2021 earnings release.

### [2] Ozimals shutdown, May 2017
- **Verdict: confirmed, with a caveat.**
- Ozimals announced in May 2017 that its bunny and Puffling products were closing (servers off mid-May 2017) after a legal demand asserting ownership of the underlying code; because the pets required server-validated food, un-fed bunnies entered hibernation and, with no server, could not be revived. Cory Doctorow's Boing Boing post ("Breedables vs DRM", 20 May 2017) is the popular write-up.
- Caveat: the brief's narrative ("Ozimals shut down in 2016; a volunteer kept the food server alive until May 2017") may conflate two things. The checker's recollection is that the Ozimals operation itself, by then run at essentially no profit, was what received the legal threat and closed in May 2017; whether the server in its final year is fairly described as "volunteer-run" could not be re-verified. The design lesson (vendor-hosted DRM life-support = single point of failure) stands either way.
- Re-check against: the Boing Boing post and Ozimals' May 2017 closure notice (archived).

### [3] Second Life population and grid size
- **Verdict: unverifiable (plausible).**
- The ~500,000 MAU figure originates with New World Notes (Wagner James Au) reporting a Linden Lab statement in October 2024, relayed by Daniel Voyager's blog; the concurrency and region figures (~49.6k 12-month average peak concurrency; ~27.8k main-grid regions) are Voyager's compilations of Linden's public concurrency feed and Tyche Shepherd-style grid surveys. The checker cannot re-read these, and no Linden Lab filing publishes MAU. Treat as blogger-sourced with medium confidence.
- Adversarial context the brief misses: Linden Lab publicly cited roughly 900,000 MAU around 2020, so if ~500k in 2024 is right, the trend is a material decline, which strengthens the brief's density argument. Also, Linden's concurrency feed counts every logged-in agent, including scripted bots, so the "humans per region" arithmetic in the brief is an upper bound on humans, not a lower bound.
- Re-check against: https://nwn.blogs.com (Oct 2024), https://danielvoyager.wordpress.com (30 Oct 2024; 5 Jan 2025).

### [4] Generative Agent Simulations of 1,000 People
- **Verdict: confirmed.**
- Park, Zou, Shaw, Hill, Cai, Jurafsky, Pennebaker, Bernstein et al., arXiv:2411.10109, submitted 15 Nov 2024. 1,052 participants, ~2-hour AI-conducted qualitative interviews; generative agents replicate participants' General Social Survey responses 85% as accurately as participants replicate their own answers two weeks later (normalized accuracy 0.85), with reduced accuracy gaps across racial and ideological groups relative to demographic-prompted agents. The claim is accurate.
- Caveat for designers: 85% is relative to human test-retest, on survey items and classic economic games; it is not evidence that an interview-seeded "twin" behaves credibly in open-ended social interaction over weeks.
- Re-check against: https://arxiv.org/abs/2411.10109

### [5] Altera Project Sid
- **Verdict: corrected.**
- What holds: Altera reported 1,000+ concurrent agents in Minecraft under the PIANO architecture (Parallel Information Aggregation via Neural Orchestration); agents collected roughly 32% of all items in the Minecraft tech tree (reported as ~5x single-agent baselines), formed trading hubs, voted on constitutional amendments and tax rates, and spread a Pastafarian-themed religion. MIT Technology Review covered it on 27 Nov 2024. None of it has been independently replicated.
- What is wrong: the results are not "claimed in its own video" only. Altera published a paper, "Project Sid: Many-agent simulations toward AI civilization" (arXiv:2411.00114, 31 Oct 2024), which gives the methods and figures. It is still a self-reported, non-peer-reviewed company result, but the brief should cite the paper, not a video, and should say "self-reported" rather than imply there is no written methodology.
- Re-check against: https://arxiv.org/abs/2411.00114 ; https://www.technologyreview.com/2024/11/27/1107377/

### [6] Inworld AI pivot
- **Verdict: confirmed on the checkable parts; retirement window unverifiable.**
- Inworld raised a $50M+ round in August 2023 at a reported $500M valuation (correct). In 2025 it released Inworld TTS priced at $5 per million characters, marketed as ~20x cheaper than incumbents (correct), and launched Inworld Runtime on 13 Aug 2025 (GlobeNewswire). The strategic shift from a character/NPC product to voice and inference infrastructure is real.
- The specific claim that Character Studio was retired "between March and September 2025" could not be re-verified; the only source cited is a third-party RPG blog, not an Inworld announcement. Keep as medium confidence until an Inworld blog post or docs deprecation notice is read.
- Re-check against: https://inworld.ai/blog ; the 13 Aug 2025 GlobeNewswire release.

### [7] Character.AI minors policy and settlement
- **Verdict: confirmed.**
- On 29 Oct 2025 Character.AI announced it would remove open-ended chat for users under 18 by 25 Nov 2025, with an interim daily limit starting at two hours and decreasing until the cutoff, plus age-assurance rollout. On 7 Jan 2026 court filings showed Google and Character.AI had reached settlements in principle with Megan Garcia (mother of Sewell Setzer III) and with families in related Colorado, New York and Texas cases; terms undisclosed.
- Re-check against: Character.AI blog (29 Oct 2025); AP/Reuters 7 Jan 2026.

### [8] SAG-AFTRA NLRB charge over AI Darth Vader
- **Verdict: confirmed.**
- On 19 May 2025 SAG-AFTRA filed an unfair labor practice charge with the NLRB against Llama Productions LLC (an Epic Games entity) over the Fortnite AI Darth Vader (James Earl Jones' voice recreated with estate consent, using Google Gemini 2.0 Flash and ElevenLabs Flash v2.5), alleging the employer made a unilateral change to terms of employment without notice or bargaining.
- Correction to the brief body (not to claim 8 itself): the SAG-AFTRA video game strike began 26 July 2024, not 16 July 2024. It ended with a tentative Interactive Media Agreement on 9 June 2025, ratified 9 July 2025, with AI consent and compensation terms for digital replicas. The brief's "no resolution found" for the NLRB charge is still fair as far as the checker knows.
- Re-check against: https://www.sagaftra.org (press releases), TheWrap 19 May 2025.

### [9] Steam disclosures and Quantic Foundry
- **Verdict: confirmed on Steam figures; Quantic Foundry figure unverifiable and sample size likely misattributed.**
- Steam: Ichiro Lambe (Totally Human Media) published an analysis in July 2025 counting 7,818 Steam titles with a generative-AI disclosure, ~7% of ~114,000 titles, roughly 7-8x the count from a year earlier, with close to 20% of 2025 releases disclosing. Valve's disclosure requirement dates from 10 Jan 2024. These match the brief.
- Quantic Foundry: the checker cannot confirm a December 2025 post reporting 62.7% "very negatively". Adversarial flag: ">1.75M gamers" is the size of Quantic Foundry's cumulative Gamer Motivation Profile dataset; any single survey question on generative AI would have been answered by a much smaller subset. The brief should not present 1.75M as the sample for the 62.7% figure. Also note GDC's 2026 State of the Industry figures in the brief body (52% say gen-AI is hurting the industry) are cited only via a secondary blog.
- Re-check against: https://quanticfoundry.com/2025/12/18/gen-ai/ ; Totally Human Media / VGC July 2025.

## Additional findings the brief missed (relevant to designing a successor world)

1. **Project Sid has a paper** (arXiv:2411.00114) with the PIANO architecture description; cite it, and note Altera's own paper reports that agents' specialisation and social behaviour degrade without the "social awareness" and coherence modules, which is a useful design hint for agent legibility.
2. **Disclosure will soon be a legal requirement, not a courtesy.** EU AI Act Article 50 transparency duties (users must be told they are interacting with an AI system; synthetic content must be marked) apply from 2 Aug 2026. California SB 243 (signed 13 Oct 2025, effective 1 Jan 2026) regulates "companion chatbots": clear AI disclosure, suicide/self-harm protocols, and for minors periodic reminders and content limits. The US FTC opened a 6(b) inquiry into companion chatbots (Alphabet, Character.AI, Meta, OpenAI, Snap, xAI and others) in Sept 2025. A world with AI inhabitants must build disclosure, age assurance and crisis routing into the platform layer, which the brief recommends but frames as reputational rather than statutory.
3. **The SAG-AFTRA video game strike (26 Jul 2024 to 9 Jul 2025 ratification) ended in an Interactive Media Agreement with AI consent/compensation terms for digital replicas.** A successor world that lets creators sell synthetic voices needs a provenance and consent registry compatible with those terms; "union-safe voices" now has a concrete contract to point at.
4. **Second Life's decline is steeper than the brief implies.** Linden Lab's public figure around 2020 was ~900k MAU; ~500k in 2024 would be a ~45% fall in four years, while region count stayed roughly flat. Density per region therefore worsened faster than the brief's static snapshot suggests, and the concurrency feed counts bots, so the human number is lower still.
5. **End-of-life preservation matters to communities.** The Sims Online was revived by fans as FreeSO (2016 onward) by reverse engineering after EA's shutdown; Second Life residents have no equivalent exit. A successor should commit up front to a source or data release / self-hosting path at end of life, which also directly answers the Ozimals single-point-of-failure problem.
6. **The 85% result is survey-level fidelity, not behavioural fidelity.** The Stanford study measured GSS answers, Big Five and economic games; it does not show that an interview-seeded twin would act plausibly as a shopkeeper for weeks. Treat "digital twin of an absent resident" as a hypothesis to test, not a validated capability.
7. **Generative Agents (Park et al., UIST 2023) ablations**, which the brief could not read, showed that removing any of observation, reflection or planning measurably reduced believability ratings, with reflection and planning the largest drops. That supports the brief's "memory as retention hook" design implication.
