# What gives virtual communities purpose: sociology, rituals, governance, roles

Research brief for the design of "nolife", a successor to Second Life. Prepared 2026-10-09.

**Method note.** 24 web searches were run (extended mode for dated/niche facts). WebFetch could not resolve any host in this sandbox (DNS failure on every attempt: wikipedia, arxiv, eveonline.com, virtualability.org, Stanford HCI), so primary pages were read only through the excerpts the search engine returned from them. Where an excerpt came straight from an official page (CCP election posts, virtualability.org, Linden Lab press release, ADL press releases, the Stanford "Eternal September" paper) it is cited as such. Figures that originate from fan blogs, forum posts or vendor marketing are labelled. Numbers marked *derived* are my arithmetic on cited inputs.

---

## Findings

### 1. The "empty world" problem, quantified (Second Life as the baseline)

- Second Life's all-time concurrency peak was 88,220 simultaneous users on 29 March 2009 (Engadget reported 88,199 for the same period). Engadget tied the subsequent slide to Linden Lab's crackdown on traffic-inflating bots, i.e. part of the 2009 peak was never human. (Source: https://danielvoyager.wordpress.com/2024/09/25/second-life-maximum-daily-concurrency-peaks-january-2020-to-september-2020/ ; https://www.engadget.com/2009-12-25-second-life-user-concurrency-spends-year-in-slow-decline.html)
- The pandemic produced a secondary high of 60,068 in April 2020. The 2024 daily maximum was 53,016 (19 Feb 2024); 2025 peaks ran roughly 47,000-49,000 and were flat. (Source: https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/) These are fan-compiled from the community Grid Survey, not official Linden figures.
- The main grid crossed 28,000 regions in May-June 2024, then shrank: 26,785 regions in early November 2025 (17,589 private estates, 9,196 Linden-owned). Private estates fell by a net 270 (~1.5%) during 2024, attributed partly to rising costs, while Linden-owned regions grew by 211. Total land area sat at roughly 1,817-1,823 km² through 2024, so the decline was in region count, not acreage. (Source: https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/ ; https://danielvoyager.wordpress.com/2025/01/02/second-life-regions-2024-last-report/ ; https://danielvoyager.wordpress.com/2024/08/28/second-life-august-2024-statistics/)
- *Derived density:* ~1,820 km² of land against a ~49,000 peak concurrency gives about 3.7 hectares per logged-in avatar at the busiest moment of the day, or fewer than two avatars per 65,536 m² region on average. That is the arithmetic behind "it feels empty". At median hours the ratio is worse.
- TechRadar's retrospective: even at peak times only about 30,000-40,000 users were logged on; "build it and they will come" failed, and the most successful in-world venues were staffed, usually 24/7, versus unstaffed corporate builds compared to "a shop in the High Street filled with brochures but never having any staff". (Source: https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2)
- Funnel, 2009 (informal student analysis of Linden data, treat with caution): 16.8 million registered accounts, 941,000 logged in within 30 days, 522,000 within 7 days, i.e. roughly 3% monthly return on registrations. (Source: https://www.slideshare.net/slideshow/linden-lab/57701017) Linden's CEO at the time conceded "it wasn't easy to know what was happening, especially for new users" and cited ~16,000 new signups per day after streamlining registration. (Source: https://www.foxnews.com/tech/how-to-use-second-life.print)
- Berkeley's 2009 retrospective notes both gambling (2007) and banking were banned, which removed two of the few activity loops with built-in stakes. (Source: https://alumni.berkeley.edu/california-magazine/march-april-2008-mind-matters/will-second-life-survive)

### 2. Theory: what a "place" needs before people will stay

- **Oldenburg / third places.** Steinkuehler & Williams, *Journal of Computer-Mediated Communication* 11(4), 2006, argue MMOs function as virtual third places and are "especially suited to forming bridging social capital" (weak ties that expose people to other worldviews) rather than bonding capital; press coverage also notes their worry that heavy raiding becomes hierarchical and less bridging. (Source: https://news.illinois.edu/some-online-video-games-found-to-promote-sociability-researchers-say/ ; https://mackenty.org/images/uploads/social_space_games.pdf.pdf) Ducheneaut, Moore & Nickell (CSCW 2007) tested the idea on Star Wars Galaxies with months of ethnography plus logged data. (Source: https://dl.eusset.eu/items/f01f68ba-a365-40de-bd86-046477557db5) A 2009 AIS study of WoW concluded Oldenburg's framework "does not stretch to accommodate the peculiarities of virtual places". (Source: https://aisel.aisnet.org/mg2009/12) The common thread across these: regulars, neutral ground and a "home away from home" feeling transfer; physical accessibility and serendipity do not transfer automatically and have to be designed.
- **Bartle (1996).** "Hearts, Clubs, Diamonds, Spades" came out of a wizard debate on a UK commercial MUD running November 1989 to May 1990 on "What do people want out of a MUD?". Two axes (acting vs interacting; players vs world) give achievers, explorers, socialisers, killers, and the paper's second half is explicitly about population dynamics and "how to promote balance or equilibrium", explaining why worlds drift toward "social" or "gamelike". (Source: https://wikipedia.com/wiki/Bartle_Test ; https://aom.jku.at/archiv/cmc/text/bartle.90/mud.co.uk/richard/VWWPP.pdf) The Bartle Test questionnaire (Andreasen & Downey, 1999-2000) is widely criticised for its forced-choice format.
- **Yee / Quantic Foundry.** The Gamer Motivation Model is a factor-analytic model of 12 motivations in 6 clusters (action, social, mastery, achievement, immersion, creativity). Sample sizes cited by the company vary by date: 30,000 at launch (2015), 400,000+ in a GDC talk, "2M gamers" in the latest post, so quote the figure with its date. (Source: https://quanticfoundry.com/2015/07/20/how-we-developed-the-gamer-motivation-profile-v2/ ; https://gdcvault.com/play/1025742/contactUs ; https://quanticfoundry.com/?p=57788)
- **Castronova (2001).** From a 3,600-user survey plus eBay sales of EverQuest goods he computed a Norrath hourly wage of about $3.42, a platinum-piece exchange rate of $0.0107, and GNP per capita between Russia and Bulgaria; a later widely-repeated figure of $2,266 and "77th largest economy" is dated 2005 by Guinness, so the two are not the same measurement. His EverQuest II work on 314 million transactions saw inflation spike more than 50% in five months during a population surge. (Source: https://www.cesifo.org/DocDL/cesifo_wp618.pdf ; https://www.guinnessworldrecords.com/world-records/80675-largest-online-game-economy ; https://spectrum.ieee.org/virtual-economies-and-the-real-things)
- **McGonigal (2011).** *Reality Is Broken* names four things good games reliably supply: urgent optimism, social fabric, blissful productivity ("we are happier working hard if given the right work"), and epic meaning. Student reviewers consistently object that the feeling of achievement does not transfer out of the game. (Source: https://www.supersummary.com/reality-is-broken/summary/ ; https://gamescriticism.org/2023/07/19/gaming-for-better-life-a-review-of-jane-mcgonigals-reality-is-broken/)
- **Kraut & Resnick (MIT Press, 2012).** *Building Successful Online Communities* organises evidence-based "design claims" around five challenges: starting a community, attracting newcomers, encouraging commitment, encouraging contribution, regulating misbehaviour. Commitment claims are split by mechanism (identity-based vs bond-based attachment); newcomer claims by the specific newcomer problem (recruitment, selection, retention, socialisation, protection). (Source: https://mitpressbookstore.mit.edu/book/9780262528917 ; https://ds-infolib.hcltechsw.com/ldd/lcwiki.nsf/dx/Dealing_with_Newcomers_in_Online_Communities)

### 3. Growth, newcomers and the lifecycle

- Lin, Salehi, Yao, Chen & Bernstein, "Better When It Was Smaller?" (ICWSM 2017) analysed 45 million comments across 10 subreddits that were suddenly added to Reddit's default set. Communities did **not** become "generic Reddit": they kept their linguistic fingerprints, implying newcomers acculturate. Subreddits with high moderation activity (share of deleted comments) had significantly higher average scores and lower complaint levels after the shock, and members clustered activity around a smaller share of posts. A separate r/NoSleep study likewise found no major disruption from massive growth; other work finds spikes hurt small communities more than large ones. (Source: https://hci.stanford.edu/publications/2017/eternalseptember/eternalseptember.pdf ; https://news.ua.edu/2019/02/reddit-study-shows-how-growth-aging-affect-online-communities/)
- The "Eternal September" lifecycle (beginner surge, core burnout, rule crackdown) is an essay-level hypothesis, not a measured law. (Source: https://lcamtuf.substack.com/p/the-evolution-of-expert-communities)
- Discord: no peer-reviewed churn study surfaced. Vendor claims (unverified, sellers of retention tooling): most servers lose over half of new joiners within seven days; servers where under 40% of messages get a reply see worse churn; "83% of new servers never pass 100 members". Academic Discord work that does exist covers #vent channels and teen volunteer moderators. (Source: https://yellowworm.io/blog/discord-member-retention ; https://research.mental-momentum.ai/r/discord-community-growth-monetization-jbm6i2 ; https://arxiv.org/pdf/2502.06985)

### 4. Self-governance and gatekeeping

- EVE Online's Council of Stellar Management (CSM) is a player-elected advisory body. Votes cast: CSM5 39,433 (12.67% of eligible accounts), CSM6 49,096 (14.25%), CSM7 59,109 (16.63%, record), CSM10 36,984, CSM12 31,274, CSM13 29,417, CSM14 32,994, CSM15 36,120, CSM16 38,086, CSM17 30,814, CSM18 47,155, CSM19 35,701, CSM20 (2025) 49,870 from 55 candidates. Turnout is a reliable 12-17% of eligible accounts and has held for fifteen years. (Source: https://www.eveonline.com/news/view/csm-7-the-results ; https://www.eveonline.com/news/view/csm6-elections-the-results ; https://www.eveonline.com/news/view/csm5-election-the-results-are-in ; https://www.eveonline.com/news/view/heres-your-csm-20 ; https://tagn.wordpress.com/2025/11/15/introducing-your-csm20-representatives/)
- GTA RP / NoPixel: entry is by written application ("what is your definition of roleplay?" plus in-character scenarios), the whitelisted server held only 32 players at once per instance in 2021 guides, and a paid "donator whitelist" opens when standard applications close. GTA V was Twitch's most-watched category in 2021 at 2.1 billion hours, with xQc routinely drawing 150,000+ viewers inside NoPixel. Scarcity of slots plus curation is the product. (Source: https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide ; https://www.sportskeeda.com/gta/gta-5-ends-2021-watched-game-twitch ; https://businessinsider.nl/a-grand-theft-auto-v-roleplay-server-called-nopixel-continues-to-dominate-twitch-with-its-immersive-ecosystem/)
- SL roleplay systems: Bloodlines runs five themed regions with factions (vampire, lycan, angel, demon, mortal hub); a bite registers the victim's SL name as a "soul" in a database, feeding is mandatory, and it is the only one of the three major SL vampire systems that asks consent before biting. Its revenue came from HUDs and blood tanks sold to players. Gorean sims (City of Tentium, Isle of Nara, Torvaldsburg) describe themselves as "by the book" lore communities. (Source: https://go.secondlife.com/destination/bloodlines ; https://community.secondlife.com/forums/topic/415080-what-is-bloodlines/)

### 5. Rituals, calendars and scarcity

- SL20B (22 June-11 July 2023) used 60 regions: 24 for the largest-ever Shop & Hop and 36 for a community-built festival, with 425+ live performers across four stages, plus a sweepstakes (Chevy Bolt EV) that required visiting the region. No attendance figure was published. (Source: https://lindenlab.com/press-release/original-metaverse-second-life-celebrates-20th-birthday ; https://ryanschultz.com/2023/06/19/your-guide-to-sl20b-second-life-celebrates-its-20th-birthday-with-sixty-sims-june-22nd-july-11th-2023/)
- BURN2 has burned the Man in Second Life since 2003, is the only virtual event among 100+ sanctioned Burning Man regionals and the only regional allowed to burn the Man, holds a year-round region (Deep Hole), runs five main events a year, and claims "thousands" over its October week (self-reported). (Source: https://burningman.org/?p=7024 ; https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/)
- Habbo's economy ran on "rares": limited-time furniture never re-released. The marketplace had logged 4,373,036 trades worth 110,147,058 credits at one official update. Community lore records the 2004 "Palsternakka" incident (rares accidentally re-sold on a foreign catalogue page, crashing values, many players leaving), the 2006 4chan "Pool's Closed" raid, and the 2012 Channel 4 exposé on adult predators that led Sulake to mute chat across all hotels ("The Great Mute"). (Source: https://www.habbo.com/community/article/22292/update-state-habbo-economy ; https://habboxforum.com/showthread.php?t=701469 ; https://gurlworld.com/what-happened-to-habbo-habbo-hotel-turns-25/)
- Club Penguin: 12 million users when Disney bought it for up to $700 million in 2007; ~200 million registered by 2013 though visitors were already declining; shutdown announced 30 January 2017 and executed 30 March 2017. The fan server Club Penguin Rewritten (launched 12 February 2017) grew past 11 million users before City of London Police shut it on 13 April 2022 at Disney's request. (Source: https://techcrunch.com/2017/01/31/club-penguin-is-shutting-down/ ; https://en.wikipedia.org/wiki/Club_Penguin ; https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/)
- Animal Crossing: New Horizons (March 2020): a Texas teacher's in-game graduation clip drew 83,000 retweets and 231,000 likes; weddings ran hybrid (avatars plus video chat); Austin (2024, *Journal of Gaming & Virtual Worlds*) documents player-built memorials and funerals as "a space for ritualizing mourning practices"; Zhu (2021) reports reduced isolation and stress. The practices spread because players posted them to social media. (Source: https://www.newsweek.com/animal-crossing-new-horizons-teacher-help-students-graduate-pandemic-1498760 ; https://intellectdiscover.com/content/journals/10.1386/jgvw_00109_1 ; https://unfsoars.domains.unf.edu/2021/posters/the-consumer-experience-of-animal-crossing-new-horizons-players-during-covid-19-lockdowns/)
- FFXIV venues: players turned housing into nightclubs the designers never intended; builders charge up to ~50 million gil per venue and some build in out-of-bounds void space. Since Patch 6.1 (2022) all land goes by lottery with full price deposited; forum anecdotes report 75 consecutive losses and roughly 3% win odds, with ~3,500 bids on a batch of plots. Scarcity of place is extreme and the scene exists anyway. (Source: https://medium.com/@deirdre.darkk/beginners-guide-to-the-ffxiv-nightclub-scene-9efa7d823cfd ; https://ffxiv.consolegameswiki.com/wiki/Player_Housing ; https://forum.square-enix.com/ffxiv/threads/523854)

### 6. Affinity, care and identity communities (the ones that lasted)

- **Virtual Ability (SL).** Founded 2007 by three friends with disabilities who toured half a dozen worlds and chose SL for its "richer cultural environment"; as The Heron Sanctuary it brought 100+ people with disabilities in-world in eight months; 501(c)(3) status April 2008; Virtual Ability Island opened August 2008 with a self-guided skills course and mentors by appointment; won the first Linden Prize in 2009. Membership: 850+ (2014), 1,300+ across six continents (2025); about a quarter are "TABs" (temporarily able-bodied). A Loyola Marymount study reports statistically significant social-emotional outcomes. (Source: https://virtualability.org/history/ ; https://blog.virtualability.org/2014/ ; https://cdn.clinicaltrials.gov/large-docs/10/NCT02626910/Prot_SAP_005.pdf)
- **Helping Hands (VRChat).** Founded October 2018 by Papa Thelius; scheduled volunteer-taught sign classes in private instances; ASL dominant but KSL, JSL, LSF, BSL used; members receive name-signs; a learning wall plays sign videos. A 2022 study of disabled users' avatars found Deaf members invented "VR-ASL", simplifying signs the controllers cannot track, and deliberately omit hearing devices from avatars. (Source: https://vrchat-legends.fandom.com/wiki/Helping_Hands ; https://arxiv.org/pdf/2208.11170)
- **Grief and health.** Lubas & De Leo (2014) argue 3-D presence addresses facilitators' main objection to online grief groups; Rice et al. (2014) ran nine oncology nurses through five one-hour avatar sessions and found storytelling "helpful in making sense of" grief; AA and Cancer Caregiver groups meet in SL. (Source: https://pubmed.ncbi.nlm.nih.gov/24875703/ ; https://pubmed.ncbi.nlm.nih.gov/25598720/)
- **Religion.** The Anglican Cathedral on Epiphany Island runs live voice/chat services, a meditation garden, labyrinth and conference centre; founder Mark Brown stepped back after ~2.5 years and a leadership team carried on, a rare documented founder succession. (Source: https://slangcath.wordpress.com/about/ ; https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/)
- **Live music.** Cafe Musique has hosted 600+ performers since February 2015; venues typically pay a performer fee plus tips; a 2009 CNN profile recorded ~$18 in tips for an hour set; tip-jar vendors have operated since 2009. (Source: https://secondlife.com/destinations/music/livemusic ; https://www.cnn.com/2009/TECH/04/07/second.life.singer/index.html ; https://slummagazine.wordpress.com/2013/07/03/how-to-show-your-love-in-second-life/)
- **Clans.** A network analysis of ~3.5 million Destiny players found clan members had higher in-game performance and players with stronger social ties played longer and more often (correlational, Destiny 1). Claims of "40% retention lift" circulating on content farms cite no source. (Source: https://www.sciencedirect.com/science/article/pii/S1875952117301350)

### 7. What kills communities

- **Harassment.** ADL 2022: 86% of US adult online multiplayer gamers experienced harassment (~67 million people), severe harassment up from 71% to 77%; 66% of teens and 70% of pre-teens. ADL 2019: 19% stopped playing certain games entirely and 23% avoided games with hostile reputations; only 27% said harassment had no effect. (Source: https://www.adl.org/news/press-releases/two-thirds-of-us-online-gamers-have-experienced-severe-harassment-new-adl-study ; https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf)
- **Platform decisions.** Gambling/banking bans in SL (2007-08); Habbo's global mute (2012) and rare-value crashes; Disney closing Club Penguin (2017) and then prosecuting its 11-million-user fan revival (2022); SL private-estate loss tied to cost increases (2024-25). Each is a case of the operator removing the thing the community had organised itself around.
- **Founder dependence and drift.** Unstaffed venues die (TechRadar); the Cathedral survived a founder exit only because a team existed; Bartle's dynamics predict that unchecked killers drive out socialisers and that a world with no achievers loses its killers' prey and then its killers.

---

## Patterns / root causes

1. **Purpose is supplied by other people, not by the world.** Every durable example above (Virtual Ability, Helping Hands, Burn2, NoPixel, FFXIV venues, EVE's CSM) is a group with a reason to meet at a time and place. Second Life's failure mode was a 1,800 km² canvas with ~50,000 people on it at best, no default schedule, and a first hour spent alone.
2. **Scarcity creates value, abundance creates emptiness.** Habbo rares, FFXIV's 3% housing odds, NoPixel's 32 seats, and Burn2's single annual week all show that limited supply of place, roles or time is what gives presence meaning. SL sold unlimited land and got unlimited emptiness.
3. **Roles beat features.** Mentors (Virtual Ability), hosts and DJs (SL music), teachers (Helping Hands), elected representatives (CSM), whitelisted characters (NoPixel). People stay where they are needed.
4. **Rituals need a calendar and a story.** SL20B, Burn2, ACNH graduations and funerals, Habbo's rare drops. The important variable is recurrence plus shareability (the ACNH graduation went viral because it was postable).
5. **Growth does not destroy culture; absence of moderation does.** The Reddit defaulting evidence shows newcomers acculturate when norms are enforced; harassment, not crowding, is what makes 19% quit.
6. **Operators kill communities more often than members do.** The documented deaths were policy changes, shutdowns, cost hikes and lawsuits.

## Design implications for nolife

1. **Size the world to the population, not the ambition.** Target a peak-hour density of at least one avatar per ~0.1 ha in public zones (roughly 40x Second Life's grid-wide average) by instancing, shardless "districts" that open only when occupancy warrants, and letting empty land decay back to wilderness.
2. **First hour = first group.** Route every new account into a hosted, scheduled cohort (Virtual Ability's mentor model, Helping Hands' class model) rather than an empty Welcome Island; measure day-7 return as the primary KPI.
3. **Ship a civic calendar on day one.** A weekly rhythm (market day, open stage, assembly) and an annual ritual with real scarcity (a Burn2-style week with a region that exists only then), with built-in capture/share tools because rituals spread through screenshots and clips.
4. **Make roles first-class objects.** Host, mentor, DJ, moderator, judge, builder, performer: each with a schedule slot, a visible badge, a stipend from the venue or the platform, and succession rules so a group survives its founder.
5. **Scarcity by design.** Limited plots in prime districts allocated by lottery or by community vote, time-limited items that are never re-issued, and seat caps on curated RP servers, all stated as policy so the economy can plan.
6. **Constitutional self-governance.** An elected council with published turnout (EVE's 12-17% is the benchmark), district-level rule-setting by residents, and a platform charter that constrains the operator (no retroactive economy changes without council review), because operators are the leading cause of death.
7. **Moderation as infrastructure.** Consent mechanics for all avatar-to-avatar actions (Bloodlines' bite consent), moderator tooling with public deletion rates (the Reddit signal that predicted healthy growth), and fast human response to new members in their first week.
8. **Support bridging and bonding separately.** Public third places for weak ties (Steinkuehler & Williams) and private, persistent group homes for strong ties (clans, support groups), with easy movement between them.
9. **Fund the venues, not the brochures.** A revenue share or stipend for staffed venues with scheduled programming; unstaffed corporate builds should not get prime placement.
10. **Protect care communities explicitly.** Accessibility (text, voice, sign, screen-reader), low-cost tenancy for nonprofits, and a guarantee that disability, grief and faith spaces are not instanced away or repriced.

## Open questions

- No independent attendance data exists for SL20B, Burn2 or SL live music; Linden Lab does not publish daily active users. What is the real weekly population of SL's event-going core?
- Does the Reddit "newcomers acculturate" finding hold in embodied 3-D spaces where norms are spatial and voice-based rather than textual?
- What is the causal (not correlational) effect of clan or group membership on retention? Bungie, Square Enix and Linden hold the data; none has published it.
- What density threshold makes a space feel alive (the 0.1 ha/avatar figure above is a design target, not a measured constant)?
- Why have the EVE CSM's vote totals held at 30-60k for 15 years while turnout percentages are no longer published? Is the electorate shrinking?
- Discord's churn figures are vendor claims; a peer-reviewed study of small-server lifecycle is still missing.
- How much of SL's niche-community durability depends on the one thing nolife will not have on day one: twenty years of accumulated user content?
- The Second Life education exodus after the 2010 nonprofit discount removal and Habbo's post-2012 user decline could not be quantified within this search budget and should be checked.

## Sources

- https://danielvoyager.wordpress.com/2025/10/20/second-life-maximum-user-concurrency-through-2025-so-far/
- https://danielvoyager.wordpress.com/2024/09/25/second-life-maximum-daily-concurrency-peaks-january-2020-to-september-2020/
- https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/
- https://danielvoyager.wordpress.com/2025/01/02/second-life-regions-2024-last-report/
- https://danielvoyager.wordpress.com/2024/08/28/second-life-august-2024-statistics/
- https://www.engadget.com/2009-12-25-second-life-user-concurrency-spends-year-in-slow-decline.html
- https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2
- https://www.slideshare.net/slideshow/linden-lab/57701017
- https://www.foxnews.com/tech/how-to-use-second-life.print
- https://alumni.berkeley.edu/california-magazine/march-april-2008-mind-matters/will-second-life-survive
- https://news.illinois.edu/some-online-video-games-found-to-promote-sociability-researchers-say/
- https://mackenty.org/images/uploads/social_space_games.pdf.pdf
- https://dl.eusset.eu/items/f01f68ba-a365-40de-bd86-046477557db5
- https://aisel.aisnet.org/mg2009/12
- https://wikipedia.com/wiki/Bartle_Test
- https://aom.jku.at/archiv/cmc/text/bartle.90/mud.co.uk/richard/VWWPP.pdf
- https://quanticfoundry.com/2015/07/20/how-we-developed-the-gamer-motivation-profile-v2/
- https://gdcvault.com/play/1025742/contactUs
- https://quanticfoundry.com/?p=57788
- https://www.cesifo.org/DocDL/cesifo_wp618.pdf
- https://www.guinnessworldrecords.com/world-records/80675-largest-online-game-economy
- https://spectrum.ieee.org/virtual-economies-and-the-real-things
- https://www.supersummary.com/reality-is-broken/summary/
- https://gamescriticism.org/2023/07/19/gaming-for-better-life-a-review-of-jane-mcgonigals-reality-is-broken/
- https://mitpressbookstore.mit.edu/book/9780262528917
- https://ds-infolib.hcltechsw.com/ldd/lcwiki.nsf/dx/Dealing_with_Newcomers_in_Online_Communities
- https://hci.stanford.edu/publications/2017/eternalseptember/eternalseptember.pdf
- https://news.ua.edu/2019/02/reddit-study-shows-how-growth-aging-affect-online-communities/
- https://lcamtuf.substack.com/p/the-evolution-of-expert-communities
- https://yellowworm.io/blog/discord-member-retention
- https://research.mental-momentum.ai/r/discord-community-growth-monetization-jbm6i2
- https://arxiv.org/pdf/2502.06985
- https://www.eveonline.com/news/view/csm-7-the-results
- https://www.eveonline.com/news/view/csm6-elections-the-results
- https://www.eveonline.com/news/view/csm5-election-the-results-are-in
- https://www.eveonline.com/news/view/csm-x-voting-results
- https://www.eveonline.com/news/view/heres-your-csm-20
- https://tagn.wordpress.com/2025/11/15/introducing-your-csm20-representatives/
- https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide
- https://www.sportskeeda.com/gta/gta-5-ends-2021-watched-game-twitch
- https://businessinsider.nl/a-grand-theft-auto-v-roleplay-server-called-nopixel-continues-to-dominate-twitch-with-its-immersive-ecosystem/
- https://go.secondlife.com/destination/bloodlines
- https://community.secondlife.com/forums/topic/415080-what-is-bloodlines/
- https://lindenlab.com/press-release/original-metaverse-second-life-celebrates-20th-birthday
- https://ryanschultz.com/2023/06/19/your-guide-to-sl20b-second-life-celebrates-its-20th-birthday-with-sixty-sims-june-22nd-july-11th-2023/
- https://burningman.org/?p=7024
- https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/
- https://www.habbo.com/community/article/22292/update-state-habbo-economy
- https://habboxforum.com/showthread.php?t=701469
- https://gurlworld.com/what-happened-to-habbo-habbo-hotel-turns-25/
- https://techcrunch.com/2017/01/31/club-penguin-is-shutting-down/
- https://en.wikipedia.org/wiki/Club_Penguin
- https://www.vice.com/en/article/cops-arrest-3-people-for-running-club-penguin-rewritten-beloved-by-millions/
- https://www.newsweek.com/animal-crossing-new-horizons-teacher-help-students-graduate-pandemic-1498760
- https://intellectdiscover.com/content/journals/10.1386/jgvw_00109_1
- https://unfsoars.domains.unf.edu/2021/posters/the-consumer-experience-of-animal-crossing-new-horizons-players-during-covid-19-lockdowns/
- https://medium.com/@deirdre.darkk/beginners-guide-to-the-ffxiv-nightclub-scene-9efa7d823cfd
- https://ffxiv.consolegameswiki.com/wiki/Player_Housing
- https://forum.square-enix.com/ffxiv/threads/523854
- https://virtualability.org/history/
- https://blog.virtualability.org/2014/
- https://cdn.clinicaltrials.gov/large-docs/10/NCT02626910/Prot_SAP_005.pdf
- https://vrchat-legends.fandom.com/wiki/Helping_Hands
- https://arxiv.org/pdf/2208.11170
- https://pubmed.ncbi.nlm.nih.gov/24875703/
- https://pubmed.ncbi.nlm.nih.gov/25598720/
- https://slangcath.wordpress.com/about/
- https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/
- https://secondlife.com/destinations/music/livemusic
- https://www.cnn.com/2009/TECH/04/07/second.life.singer/index.html
- https://slummagazine.wordpress.com/2013/07/03/how-to-show-your-love-in-second-life/
- https://www.sciencedirect.com/science/article/pii/S1875952117301350
- https://www.adl.org/news/press-releases/two-thirds-of-us-online-gamers-have-experienced-severe-harassment-new-adl-study
- https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf
