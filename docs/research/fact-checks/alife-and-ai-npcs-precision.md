# Precision check: "Artificial life in games and the AI-agent era"

Checked 2026-10-09 against /tmp/claude-0/-home-user-nolife/d4696900-d73b-5efa-ba36-41eadc9a535f/scratchpad/research/alife-and-ai-npcs.md

## Tooling status (read this first)

- **WebFetch**: every call failed with `getaddrinfo ENOTFOUND` (en.wikipedia.org, videogameschronicle.com, boingboing.net, danielvoyager.wordpress.com, arxiv.org, technologyreview.com, arcanumrpgs.com, abc7news.com, thewrap.com). This is the same DNS failure the researcher reported.
- **WebSearch**: all ten searches (one per claim) returned "web search budget is used up (200 per turn, shared by every agent)". None executed.
- Per instructions I did not work around this with curl, proxies, readers or archives.

**Consequence:** no claim below was checked against a fetched source. Every verdict is `unverifiable` for this run. The "Recollection" lines are the checker's prior knowledge, not evidence; they are given only to prioritise what a follow-up pass with working tools should look at first. Nothing is marked corrected or refuted, because no evidence was obtained.

## Claim-by-claim

### [0] The Sims Online: launch 17 Dec 2002, forecast up to 1M subscribers, Wired 97,000 actives at six months, EA-Land closed 1 Aug 2008
- Verdict: **unverifiable** (source not fetched)
- Recollection: launch date 17 Dec 2002 and EA-Land closure 1 Aug 2008 (announced 29 Apr 2008) match memory. The "97,000 active subscribers" figure attributed to Wired and the 125,000 retail copies also match memory of the Wikipedia article. The "up to 1M subscribers" forecast is the weakest element: memory is of EA pre-launch targets quoted variously as 40,000 at launch / 200,000 by end of the first year, with "one million" appearing as an aspirational figure in press. Re-check the exact wording of the Wikipedia reception section before using "internal forecasts of up to 1M".
- Source cited: https://en.wikipedia.org/wiki/The_Sims_Online

### [1] ACNH ~31.18M by 31 Dec 2020; outsold Switch hardware (27.3M) in calendar 2020
- Verdict: **unverifiable**
- Recollection: 31.18M lifetime as of 31 Dec 2020 is Nintendo's own Q3 FY2021 figure and matches memory. The Switch comparator is less certain: summing Nintendo's quarterly hardware shipments for calendar 2020 (3.29M + 5.68M + 6.86M + 11.57M) gives ~27.4M, consistent with 27.3M to rounding; but the VGC article may instead have compared against the April-December fiscal nine-month figure (~24.1M). Either way the headline ("game outsold console in 2020") holds. Confirm which Switch number VGC used before quoting 27.3M.
- Source cited: https://www.videogameschronicle.com/news/animal-crossing-new-horizons-even-outsold-nintendo-switch-in-2020

### [2] May 2017 legal threat closed volunteer-run Ozimals food server; all bunnies in permanent hibernation (DRM food only)
- Verdict: **unverifiable**
- Recollection: Boing Boing (Cory Doctorow, 20 May 2017) and New World Notes covered Ozimals shutting down its servers after an IP legal threat it said it could not afford to fight; bunnies that run out of server-validated food enter hibernation rather than dying. Two details to re-check: (a) "volunteer-run" and "Ozimals shut down in 2016" in the brief: memory is that the May 2017 announcement came from Ozimals itself (the operating entity), not a separate volunteer; (b) "permanent" hibernation is an inference (hibernation is reversible if a server returned). Treat the operator description as uncertain.
- Source cited: https://boingboing.net/2017/05/20/breedables-vs-drm.html

### [3] Second Life ~500,000 MAU (Oct 2024, via New World Notes); 12-month avg peak concurrency ~49,649; ~27,769 main-grid regions (early 2025)
- Verdict: **unverifiable**
- Recollection: Daniel Voyager's 30 Oct 2024 post with that title exists and relays Wagner James Au (New World Notes) reporting ~500K MAU from Linden Lab. The concurrency and region figures are plausible against Voyager/GridSurvey trackers (main grid in the 27K-region range in 2024-25) but the specific numbers 49,649 and 27,769 could not be checked and are likely from a different Voyager post than the one cited; the brief's own source list already flags this as medium confidence.
- Source cited: https://danielvoyager.wordpress.com/2024/10/30/second-life-has-500000-monthly-active-users/

### [4] Stanford "Generative Agent Simulations of 1,000 People" (arXiv 2411.10109, 15 Nov 2024): 1,052 people, ~2-hour interviews, GSS replication 85% as accurate as self-replication two weeks later
- Verdict: **unverifiable**
- Recollection: all specifics match memory of the abstract (Park, Zou, Shaw, Hill, Cai, Yang, Jin, Bernstein, Leskovec; submitted 15 Nov 2024; 1,052 participants; two-hour qualitative interviews; 85% of participants' own two-week test-retest accuracy on the GSS; reduced accuracy gaps across racial and ideological groups). Highest-confidence claim in the set.
- Source cited: https://arxiv.org/abs/2411.10109v1

### [5] Altera Project Sid: up to 1,000 agents in Minecraft (PIANO); company video claims 32% of all items, constitution vote, tax adjustments; unverified
- Verdict: **unverifiable**
- Recollection: matches memory of Altera's preprint "Project Sid: Many-agent simulations toward AI civilization" (arXiv 2411.00114, 31 Oct 2024) and the MIT Technology Review piece (27 Nov 2024). PIANO = Parallel Information Aggregation via Neural Orchestration. The 32%-of-items claim (vs ~6% for a single agent, i.e. ~5x) and the tax/constitution episodes are in the preprint as well as the video, so "in its own video" undersells the primary source: cite the arXiv preprint. "Unverified company claims" is a fair characterisation; the preprint is not peer-reviewed and there is no independent replication.
- Source cited: https://www.technologyreview.com/2024/11/27/1107377

### [6] Inworld AI ($500M valuation, 2023) pivoted Mar-Sep 2025 to voice/inference infrastructure, retired Character Studio, TTS at $5 per 1M characters
- Verdict: **unverifiable**
- Recollection: $500M valuation (Aug 2023, Lightspeed-led round) matches. Inworld launched a TTS model (TTS-1) around July 2025 at roughly $5 per million characters and "Inworld Runtime" on 13 Aug 2025; deprecation of the older Character Engine/Studio in 2025 is consistent with memory but the exact retirement date and the "March to September" window are the blog author's framing. The cited source is a third-party RPG blog, not Inworld; a follow-up should swap in Inworld's own announcements (inworld.ai blog, GlobeNewswire 13 Aug 2025).
- Source cited: https://arcanumrpgs.com/blog/inworld-ai/

### [7] Character.AI: Oct 2025 announcement of 2-hour daily cap for under-18s, open-ended chat ban for minors from 25 Nov 2025; Google/Character.AI settlement in principle with Setzer family, Jan 2026
- Verdict: **unverifiable**
- Recollection: matches memory. Announcement 29 Oct 2025; interim 2-hour/day limit, falling to zero by 25 Nov 2025; age-assurance rollout; AP reported settlements in principle on 7 Jan 2026 covering the Setzer (Garcia v. Character Technologies) case and related Colorado, New York and Texas suits, terms undisclosed. One nuance: the cap was explicitly described as a transition measure that ramps down, not a steady-state policy.
- Source cited: https://abc7news.com/post/characterai-is-banning-minors-interacting-chatbots/18090030/

### [8] SAG-AFTRA NLRB ULP charge filed 19 May 2025 against Llama Productions (Epic) over AI Darth Vader voice; unilateral change without bargaining
- Verdict: **unverifiable**
- Recollection: matches memory. Fortnite's AI Vader (built with Google Gemini and ElevenLabs, with the James Earl Jones estate's permission) launched 16 May 2025; SAG-AFTRA filed the charge on 19 May 2025 naming Llama Productions LLC, alleging the employer changed terms (replacing bargaining-unit work with AI voice) without notice or bargaining. Note the brief says the games strike had "no resolution found": see additional findings, the strike ended in mid-2025.
- Source cited: https://www.thewrap.com/sag-aftra-darth-vader-fortnite-ai-voice/

### [9] Steam: 7,818 of ~114,126 games (~7%) with gen-AI disclosure by 13 July 2025; ~20% of 2025 releases; up ~700-800% YoY; Quantic Foundry (Dec 2025, >1.75M gamers) 62.7% very negative
- Verdict: **unverifiable**
- Recollection: the Steam numbers match memory of Ichiro Lambe's (Totally Human Media) July 2025 analysis as reported by VGC and others (7,818 / 114,126 / ~7% / nearly 20% of 2025 releases / roughly 8x). The claim bundles two sources: the Quantic Foundry figure comes from a separate Quantic Foundry post (18 Dec 2025) that the brief cites elsewhere, not from the VGC article. The exact 62.7% and the ">1.75M gamers" sample description could not be confirmed; re-check against quanticfoundry.com directly.
- Sources cited: https://www.videogameschronicle.com/news/steam-games-disclosing-generative-ai-use-are-up-800-this-year/ ; https://quanticfoundry.com/2025/12/18/gen-ai/

## Summary table

| # | Claim | Verdict | Priority for re-check |
|---|-------|---------|------------------------|
| 0 | Sims Online numbers/dates | unverifiable | Medium: "up to 1M" forecast wording |
| 1 | ACNH 31.18M vs Switch 27.3M | unverifiable | Low: which Switch comparator VGC used |
| 2 | Ozimals 2017 shutdown | unverifiable | Medium: "volunteer-run" / "2016 shutdown" framing |
| 3 | SL 500K MAU, concurrency, regions | unverifiable | Medium: specific concurrency/region figures |
| 4 | Stanford 1,000-person agents | unverifiable | Low: matches abstract from memory |
| 5 | Project Sid | unverifiable | Low: cite arXiv 2411.00114 as primary |
| 6 | Inworld pivot | unverifiable | High: third-party blog, dates are author framing |
| 7 | Character.AI minors policy, settlement | unverifiable | Low |
| 8 | SAG-AFTRA NLRB charge | unverifiable | Low |
| 9 | Steam disclosure + Quantic Foundry | unverifiable | Medium: 62.7% exact figure, source bundling |

## Additional findings (from checker recollection; verify before use)

1. SAG-AFTRA's video game strike (begun 26 July 2024, not 16 July as the brief says) ended in 2025: a tentative Interactive Media Agreement was reached in June 2025 and ratified in July 2025, with AI provisions covering consent and compensation for digital replicas. The brief says "no resolution found"; the strike itself is resolved even if the Vader ULP charge may not be. Relevant to any successor world that uses synthetic voices for agents.
2. Project Sid's primary source is Altera's own preprint, arXiv 2411.00114 ("Project Sid: Many-agent simulations toward AI civilization"), which should replace the Technology Review secondary citation.
3. California SB 243 (companion chatbot safeguards: disclosure that the user is talking to AI, suicide/self-harm protocols, minors protections) was signed in Oct 2025 and took effect 1 Jan 2026; the FTC opened a 6(b) inquiry into AI companion chatbots and minors in Sept 2025 (Character.AI, Meta, OpenAI, Snap, xAI, Alphabet among recipients). Both directly shape the "age-gating from day one" design rule.
4. Steam's disclosure requirement dates from Valve's 10 Jan 2024 policy update (pre-release and live-generated AI content must be disclosed, live-generated content must have guardrails). A successor world with live LLM agents would fall under the "live-generated" category if distributed on Steam.
5. The Sims Online strike-through: the brief's strike start date "16 July 2024" should be 26 July 2024.
