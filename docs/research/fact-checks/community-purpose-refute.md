# Adversarial fact-check: "What gives virtual communities purpose"

Brief checked: `scratchpad/research/community-purpose.md`. Date: 2026-10-09.

## Verification limits (read first)

- **WebFetch**: every call failed with `getaddrinfo ENOTFOUND` for all 11 primary hosts (danielvoyager.wordpress.com, eveonline.com, hci.stanford.edu, virtualability.org, adl.org, techcrunch.com, burningman.org, ryanschultz.com, cesifo.org). Same DNS failure the researcher reported.
- **WebSearch**: the shared per-turn budget (200 calls) was already consumed by other agents before this checker ran; all 15 queries were refused.
- The task forbids working around this with curl, proxies, readers or archives, so no live independent evidence was obtained.
- Verdicts below are therefore based on the checker's prior knowledge of the cited sources. "confirmed" is used only where that knowledge is strong and specific; "unverifiable" is the default wherever a precise number or date could not be independently recalled. Treat every "confirmed" as "consistent with well-established reporting, not re-fetched today".

## Claim-by-claim

### [0] SL concurrency: 88,220 peak on 29 Mar 2009; 53,016 on 19 Feb 2024; 2025 peaks ~47-49k
**Verdict: unverifiable (historical part consistent).**
The ~88,200 peak in late March 2009 matches contemporaneous reporting (Tateru Nino / Engadget, Dec 2009, gave 88,199 for the same window; the ~20-user gap is the two sources sampling at different instants). The 2024 and 2025 figures are Daniel Voyager's own daily sampling of the login-page concurrency number, not a Linden Lab publication; nothing independent could be fetched to confirm 53,016 / 19 Feb 2024 or the 47-49k 2025 band. Note the researcher already flags that the 2009 peak was inflated by traffic bots.
Sources (not fetched): danielvoyager.wordpress.com 2025/10/20; engadget.com 2009-12-25 concurrency article.

### [1] Main grid 26,785 regions early Nov 2025 (17,589 private / 9,196 Linden); >28,000 mid-2024; private estates -270 (~1.5%) in 2024
**Verdict: unverifiable (internally consistent).**
17,589 + 9,196 = 26,785, so the split is arithmetically sound. 270 / ~17,860 = 1.5%, also consistent. Direction (private-estate decline after Linden Lab's 2024 region price rise, Linden-owned growth via Linden Homes / Bellisseria) matches what is known of 2024-25 grid trends. The specific counts are fan-compiled (Voyager's monthly region census, successor to Tyche Shepherd's Grid Survey) and could not be re-fetched.
Sources (not fetched): danielvoyager.wordpress.com 2025/11/04 and 2025/01/02.

### [2] EVE CSM: CSM7 59,109 votes / 16.63% record; CSM20 (2025) 49,870 votes, 55 candidates, second-highest ever
**Verdict: confirmed for CSM7; unverifiable for CSM20.**
CSM7 (2012) at 59,109 votes and ~16.6% of eligible accounts is the well-known record and matches recall. CSM20's 49,870 could not be fetched; it is consistent with the brief's own series (above CSM6's 49,096, below CSM7), which is what makes "second-highest ever" arithmetically true if the number is right. Two caveats the brief under-states: votes are per *account* (Omega accounts older than 30 days), so multi-account players vote several times and vote counts are not a head-count of players; and CCP stopped publishing a turnout percentage years ago, so the "12-17% for fifteen years" framing in the brief extrapolates from the early elections only. The CSM is advisory and NDA-bound, not a governing body.
Sources (not fetched): eveonline.com/news/view/csm-7-the-results; eveonline.com/news/view/heres-your-csm-20.

### [3] Lin et al. ICWSM 2017: 45M comments, 10 subreddits made default; linguistic fingerprints kept; high-moderation subreddits had higher scores and fewer complaints
**Verdict: confirmed (bibliographic details and main finding), moderation detail plausible but not re-verified.**
"Better When It Was Smaller? Community Content and Behavior After Massive Growth" (Lin, Salehi, Yao, Chen, Bernstein; ICWSM 2017) does analyse ~45 million comments from subreddits added to Reddit's default set in May 2014 and finds language and behaviour stayed stable after the growth shock. The secondary finding that subreddits with more comment removals had higher average scores and fewer "this sub has gone downhill" complaints matches recall of the paper's discussion but could not be re-read. Caveats for a 3-D world: the growth was passive exposure (defaulting), the communities were text-only, and the moderation result is correlational.
Source (not fetched): hci.stanford.edu/publications/2017/eternalseptember/eternalseptember.pdf.

### [4] Virtual Ability: founded 2007; 501(c)(3) April 2008; VAI opened Aug 2008; first Linden Prize 2009; 850+ members 2014; 1,300+ in 2025
**Verdict: confirmed on the year-level milestones; month-level dates and membership counts unverifiable.**
Virtual Ability, Inc. (Alice Krueger / "Gentle Heron") was founded in 2007, incorporated as a Colorado 501(c)(3) in 2008, opened Virtual Ability Island in 2008, and won the inaugural US$10,000 Linden Prize in 2009. These are consistent with the organisation's own history page and press from the period. The April/August 2008 months and the 850+ / 1,300+ figures are self-reported and could not be fetched.
Source (not fetched): virtualability.org/history.

### [5] ADL 2022: 86% of US adult online multiplayer gamers harassed; severe 77% (up from 71%); ADL 2019: 19% stopped playing certain games
**Verdict: confirmed, with a source-attribution correction.**
ADL's *Hate Is No Game* 2022 report gives 86% any harassment and 77% severe (up from 71% in 2021), ~67 million adults. ADL's 2019 *Free to Play?* report gives 74% any / 65% severe, and 19% stopped playing certain games, 23% avoided games because of reputation. The numbers match recall. However, the URL cited for the 2022 figures ("two-thirds-of-us-online-gamers-have-experienced-severe-harassment") is the **2019** press release (65% ≈ two-thirds); the 2022 figures belong to the 2022 report/press release. The brief should cite the 2022 report directly.
Sources (not fetched): adl.org press release (2019); adl.org *Hate Is No Game* (2022); Free to Play PDF (2019).

### [6] Club Penguin: 12M users at 2007 Disney purchase (up to $700M); ~200M registered by 2013; shut 30 Mar 2017; CPR 11M+ users, police shutdown 13 Apr 2022
**Verdict: confirmed.**
Disney bought Club Penguin in August 2007 for US$350M plus up to $350M in earn-outs (hence "up to $700M"); it had ~12M registered users (~700k paying) at the time; Disney cited 200M+ registered accounts by 2013; shutdown was announced 30 Jan 2017 and executed 30 Mar 2017 (Disney replaced it with the mobile *Club Penguin Island*). Club Penguin Rewritten was taken down 13 Apr 2022 by the City of London Police's PIPCU at Disney's request, three people arrested; press reported ~11M registered users. All consistent with recall.
Source (not fetched): techcrunch.com 2017/01/31; vice.com CPR arrests story.

### [7] BURN2 since 2003; only virtual Burning Man regional among 100+; year-round region Deep Hole; five main events a year
**Verdict: corrected.**
The Man has been burned in Second Life since 2003, but from 2003 to 2009 the event was **Burning Life**, run by Linden Lab itself. **BURN2** is the community-run successor that became an officially sanctioned Burning Man regional in **2010**. "BURN2 ... since 2003" conflates the two. Burning Man's regional network page has historically described BURN2 as its only virtual regional, and BURN2 does keep a year-round region (Deep Hole). The "five main events a year" count is BURN2 self-description and could not be verified (Octoburn, Burnal Equinox, Conception and others exist; the exact number varies by year).
Sources (not fetched): burningman.org/?p=7024; ryanschultz.com 2021/10/09.

### [8] SL20B 22 Jun-11 Jul 2023: 60 regions (24 Shop & Hop, 36 community festival), 425+ performers, four stages
**Verdict: unverifiable.**
SL20B did run from 22 June 2023 (SL's birthday is 23 June) into July across roughly sixty regions, per Ryan Schultz's guide title and Linden Lab's press release. The 24/36 split, the 425+ performer count and "four stages" could not be re-fetched and the checker cannot confirm them from memory; treat as blog-sourced. No attendance figure was ever published, as the brief says.
Sources (not fetched): ryanschultz.com 2023/06/19; lindenlab.com press release.

### [9] Castronova 2001: 3,600-user survey + eBay sales; Norrath hourly wage $3.42; GNP per capita between Russia and Bulgaria; platinum piece $0.0107
**Verdict: confirmed (survey n = 3,619, rounded).**
"Virtual Worlds: A First-Hand Account of Market and Society on the Cyberian Frontier", CESifo Working Paper 618 (Dec 2001): survey of 3,619 EverQuest players; mean hourly wage ≈ US$3.42; per-capita GNP ≈ US$2,266, 77th in the world, between Russia and Bulgaria; platinum piece ≈ US$0.0107. **Important correction to the brief's body text (not the key claim):** the $2,266 / "77th richest" figures are from this same 2001 paper, not a separate 2005 Guinness measurement. Guinness merely repeated Castronova's numbers. The brief's statement that "the two are not the same measurement" is wrong.
Source (not fetched): cesifo.org/DocDL/cesifo_wp618.pdf.

## Summary table

| # | Claim | Verdict |
|---|-------|---------|
| 0 | SL concurrency peaks | unverifiable (2009 peak consistent) |
| 1 | SL region counts Nov 2025 | unverifiable (arithmetic consistent) |
| 2 | EVE CSM7 / CSM20 votes | confirmed (CSM7) / unverifiable (CSM20); caveats on per-account voting |
| 3 | Lin et al. 2017 Reddit study | confirmed (main), moderation detail plausible |
| 4 | Virtual Ability milestones | confirmed (years); months/counts unverifiable |
| 5 | ADL 2022 / 2019 harassment | confirmed; URL cited is the 2019 release, not 2022 |
| 6 | Club Penguin / CPR | confirmed |
| 7 | BURN2 since 2003 | corrected: Burning Life 2003-09 (Linden-run), BURN2 regional from 2010 |
| 8 | SL20B region/performer split | unverifiable |
| 9 | Castronova 2001 | confirmed; brief wrongly separates the $2,266 figure from the 2001 paper |

## Additional findings the researcher missed (relevant to designing a successor)

1. **The same company already built and lost a "successor to Second Life".** Linden Lab launched Sansar (2017) as its VR-first successor, could not attract SL's creator base (no in-world building, separate economy, VR hardware barrier), and sold it to Wookey in 2020; Linden Lab itself was sold to an investor group (Oberwager/Randall) in 2020. Philip Rosedale's High Fidelity likewise abandoned its social-VR world in 2019-20. Any "nolife" plan must explain why it will not repeat Sansar's failure: community does not transfer, content does not transfer, and a VR requirement shrinks the audience.
2. **Disney's official Club Penguin successor failed where the fan clone thrived.** Club Penguin Island (March 2017) closed 20 Dec 2018, under two years, while the unlicensed Club Penguin Rewritten reached ~11M users by preserving the *original* world for free. Lesson: continuity of place, content and ritual beat a redesigned product; and IP ownership let the operator kill the community twice.
3. **SL's economy runs on a regulated money transmitter.** Linden Lab created Tilia (registered money services business, licensed in US states) in 2019 to process L$ cash-outs; a successor with a convertible currency inherits that compliance burden from day one. Castronova's numbers came from grey-market eBay trading precisely because EverQuest had no sanctioned exchange.
4. **EVE's CSM is advisory, NDA-bound, elected by STV on a per-account franchise.** The brief holds it up as the governance benchmark but does not say it has no binding power, that CCP has overruled or ignored it, and that account-based voting lets multi-boxers vote repeatedly. A "constitutional" council for nolife needs one-person-one-vote identity and a defined scope of binding authority, which no existing virtual world has shipped.
5. **The Reddit acculturation result comes from passive, text-only growth.** Default-subreddit growth is exposure, not migration of a hostile population; voice and spatial harassment (the ADL figures) are the failure mode in embodied worlds, so the "growth does not destroy culture" pattern should not be generalised without 3-D evidence.
6. **Source hygiene.** Three of the ten key claims rest on a single fan blog (Daniel Voyager), one cites the wrong ADL release, one conflates Burning Life with BURN2, and the Castronova/Guinness distinction in the body is wrong. None of these overturn the brief's conclusions, but they should be fixed before the figures are reused in a plan.
