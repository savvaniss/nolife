# Research appendix

This directory holds the source material behind the analysis, design and plan documents. Everything here was produced on 2026-10-09 by web-searching analysts and independent fact-checkers; nothing was written from the product's own perspective.

## Layout

| Directory | Contents |
|---|---|
| `briefs/` | One research brief per topic (14 topics). Each has a method note stating how many live searches were run and which figures rest only on prior knowledge, inline `(Source: URL)` citations, patterns, design implications and open questions. |
| `fact-checks/` | Independent verification reports. `*-search.md` reports used live web search and are the authoritative verdicts. `*-refute.md` and `*-precision.md` reports were produced when the shared search budget was exhausted; they are internal-consistency and prior-knowledge reviews, not evidence, and say so at the top. |
| `ledgers/` | Machine-readable claim ledgers (JSON). `ledger-<topic>.json` holds the brief's key claims with the no-search checkers' notes; `ledger-<topic>-searchverify.json` holds the search-backed verdicts; `ledger2-<topic>.json` supersedes `ledger-<topic>.json` where a brief was re-researched with live search. |

## Topics

| Topic | Brief | Search-backed check |
|---|---|---|
| Second Life history and technical stagnation | `briefs/sl-history-stagnation.md` | `fact-checks/sl-history-stagnation-search.md` |
| Second Life economy and creators | `briefs/sl-economy-creators.md` | `fact-checks/sl-economy-creators-search.md` |
| Second Life UX, onboarding, governance | `briefs/sl-ux-onboarding-governance.md` | see ledgers (verified in the synthesis pass) |
| First-wave successors (There, Blue Mars, PS Home, Sansar, High Fidelity...) | `briefs/successors-wave1.md` | `fact-checks/successors-wave1-search.md` |
| Metaverse wave (Horizon, Decentraland, Sandbox, VRChat, Rec Room...) | `briefs/successors-wave2-metaverse.md` | `fact-checks/successors-wave2-metaverse-search.md` |
| What the winners did right (Roblox, Fortnite, Minecraft, GTA RP, FFXIV...) | `briefs/winners-lessons.md` | see ledgers (verified in the synthesis pass) |
| Artificial life, life-sims and the AI-agent era | `briefs/alife-and-ai-npcs.md` | `fact-checks/alife-and-ai-npcs-search.md` |
| Real-time graphics state of the art (2026) | `briefs/graphics-tech-2026.md` | `fact-checks/graphics-tech-2026-search.md` |
| Networking, persistence and scale | `briefs/networking-scale-tech.md` | see ledgers (verified in the synthesis pass) |
| What gives virtual communities purpose | `briefs/community-purpose.md` | see ledgers (verified in the synthesis pass) |
| Safety, moderation, identity and regulation | `briefs/safety-regulation-identity.md` | `fact-checks/safety-regulation-identity-search.md` |
| Business models and unit economics | `briefs/business-models.md` | see ledgers (verified in the synthesis pass) |
| Legacy content, interoperability and audience | `briefs/legacy-interop.md` | `fact-checks/legacy-interop-search.md` |
| Smaller surviving worlds and new entrants | `briefs/alt-survivors.md` | `fact-checks/alt-survivors-search.md` |

## Evidence quality

- Web pages could not be fetched from the research environment, so every fact comes from search-engine extracts of the cited page rather than a full read. Treat single-sourced figures as provisional.
- Company-reported figures (Linden Lab, Meta, Roblox) are labelled as such in the briefs; independent measurements are labelled separately.
- Where a search-backed check corrected a figure, the corrected value is the one used in `docs/analysis/` and later documents.
