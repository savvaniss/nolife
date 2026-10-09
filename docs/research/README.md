# Research appendix

This directory holds the source material behind the analysis, design and plan documents. Everything here was produced on 2026-10-09 by web-searching analysts and independent fact-checkers; nothing was written from the product's own perspective.

## Layout

| Directory | Contents |
|---|---|
| `briefs/` | One research brief per topic (14 topics). Each has a method note stating how many live searches were run and which figures rest only on prior knowledge, inline `(Source: URL)` citations, patterns, design implications and open questions. |
| `fact-checks/` | Independent verification reports. `*-search.md` reports used live web search and are the authoritative verdicts. `*-refute.md` and `*-precision.md` reports were produced when the shared search budget was exhausted; they are internal-consistency and prior-knowledge reviews, not evidence, and say so at the top. |
| `critiques/` | Three critiques of the first draft of the failure taxonomy (completeness, steelman of Second Life, causal-reasoning review) that drove its revision. |
| `ledgers/` | Machine-readable claim ledgers (JSON). `ledger-<topic>.json` holds the brief's key claims with the no-search checkers' notes; `ledger-<topic>-searchverify.json` holds the search-backed verdicts; `ledger2-<topic>.json` supersedes `ledger-<topic>.json` where a brief was re-researched with live search. |

## Topics

| Topic | Brief | Search-backed check |
|---|---|---|
| Second Life history and technical stagnation | `briefs/sl-history-stagnation.md` | `fact-checks/sl-history-stagnation-search.md` |
| Second Life economy and creators | `briefs/sl-economy-creators.md` | `fact-checks/sl-economy-creators-search.md` |
| Second Life UX, onboarding, governance | `briefs/sl-ux-onboarding-governance.md` | `fact-checks/sl-ux-onboarding-governance-search.md` |
| First-wave successors (There, Blue Mars, PS Home, Sansar, High Fidelity...) | `briefs/successors-wave1.md` | `fact-checks/successors-wave1-search.md` |
| Metaverse wave (Horizon, Decentraland, Sandbox, VRChat, Rec Room...) | `briefs/successors-wave2-metaverse.md` | `fact-checks/successors-wave2-metaverse-search.md` |
| What the winners did right (Roblox, Fortnite, Minecraft, GTA RP, FFXIV...) | `briefs/winners-lessons.md` | `fact-checks/winners-lessons-search.md` |
| Artificial life, life-sims and the AI-agent era | `briefs/alife-and-ai-npcs.md` | `fact-checks/alife-and-ai-npcs-search.md` |
| Real-time graphics state of the art (2026) | `briefs/graphics-tech-2026.md` | `fact-checks/graphics-tech-2026-search.md` |
| Networking, persistence and scale | `briefs/networking-scale-tech.md` | `fact-checks/networking-scale-tech-search.md` |
| What gives virtual communities purpose | `briefs/community-purpose.md` | `fact-checks/community-purpose-search.md` |
| Safety, moderation, identity and regulation | `briefs/safety-regulation-identity.md` | `fact-checks/safety-regulation-identity-search.md` |
| Business models and unit economics | `briefs/business-models.md` | `fact-checks/business-models-search.md` |
| Legacy content, interoperability and audience | `briefs/legacy-interop.md` | `fact-checks/legacy-interop-search.md` |
| Smaller surviving worlds and new entrants | `briefs/alt-survivors.md` | `fact-checks/alt-survivors-search.md` |
| Gap: adult economy and payment rails | `briefs/gap-adult-economy-and-payment-rails.md` | `fact-checks/gap-adult-economy-and-payment-rails-search.md` |
| Gap: non-English communities and regional law | `briefs/gap-non-english-communities-and-regional-law.md` | `fact-checks/gap-non-english-communities-and-regional-law-search.md` |
| Gap: virtual currency, consumer law and tax | `briefs/gap-virtual-currency-consumer-law-and-tax.md` | `fact-checks/gap-virtual-currency-consumer-law-and-tax-search.md` |
| Gap: Second Life community census and migration needs | `briefs/gap-sl-community-census-and-migration-needs.md` | `fact-checks/gap-sl-community-census-and-migration-needs-search.md` |

## Synthesis

`failure-taxonomy.md` is the working synthesis of all briefs and fact-checks: root causes, the comparative table of successors, constraints, and the numbered requirements R1-R30 that the design documents trace to. The reader-facing versions of this material are in `docs/analysis/`.

## Evidence quality

- Web pages could not be fetched from the research environment, so every fact comes from search-engine extracts of the cited page rather than a full read. Treat single-sourced figures as provisional.
- Company-reported figures (Linden Lab, Meta, Roblox) are labelled as such in the briefs; independent measurements are labelled separately.
- Where a search-backed check corrected a figure, the corrected value is the one used in `docs/analysis/` and later documents.
