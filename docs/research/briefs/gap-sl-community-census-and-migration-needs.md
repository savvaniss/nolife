# Gap research: census of Second Life's communities and what each needs to migrate

Date: 2026-10-09. Author: research subagent (nolife postmortem). Status: first pass; figures are best-available and uneven.

## Method note

Fourteen WebSearch calls (the hard cap) were used; page fetching is blocked in this sandbox, so every figure comes from quoted search extracts, not from reading pages. Unsearched statements are marked **[prior knowledge, unverified]**. Virtual Ability membership, Cafe Musique and breedables are covered in `community-purpose.md`, `legacy-interop.md` and `alife-and-ai-npcs.md`; national/language communities in `gap-non-english-communities-and-regional-law.md`. Public headcounts for roleplay, furry, combat and religious communities do not exist: Linden Lab publishes no per-community statistics, and the SL blogs report events, not populations. Treat every count as an order-of-magnitude anchor.

## Findings

### 1. Census: who the durable communities are and what we can actually count

| Community | Best-available size / footprint | Infrastructure and calendar | Confidence |
|---|---|---|---|
| **Education (VWBPE)** | VWBPE 2026 ran 19-21 March 2026 in SL with a Philip Rosedale keynote and interviews with Linden executives; organisers claimed "over 2,000 educational professionals" a year in 2022 and reported "over 1,200 people from 30 countries" for the March 2022 edition (Source: https://secondlife.com/destination/vwbpe; https://ryanschultz.com/2023/02/21/; https://modemworld.me/page/352/?wref=bif) | Annual 3-day conference on donated/sponsored regions; year-round educator groups; parallel OpenSim track | Medium |
| **Disability (Virtual Ability Inc.)** | 1,000-1,300 members on six continents; ~25% are carers, clinicians or researchers (see community-purpose.md). Sub-community Cape Able (run by Gabrielli Rossini) serves deaf/HoH residents inside the Virtual Ability estate (Source: https://lists.aoir.org/archives/list/air-l@lists.aoir.org/thread/IY67LPKZMS37Q4O6NF6VZTIMITQAANSL/) | Own estate (Virtual Ability Island, Cape Able), mentors by appointment, annual Mental Health Symposium and International Disability Rights Affirmation Conference **[prior knowledge for the two conferences]** | High for membership, medium for calendar |
| **Live music** | No count exists. Linden's own blog says "hundreds, if not thousands" of venues (promotional); Cafe Musique alone has hosted 600+ performers since 2015 (legacy-interop.md). SL22B (20 June-20 July 2025) ran open performer applications 27 March-19 May 2025 with slots "scheduled in the order applied" (Source: https://modemworld.me/2025/03/27/sl22b-performer-applications-open/; https://community.secondlife.com/blogs/entry/9829-david-venter-a-new-electronic-music-project-in-second-life/) | Venues are parcels with a streaming-audio URL; weekly calendars per venue; charity marathons such as AISM 2025 (16-30 May) for MS research (Source: https://go.secondlife.com/destination/aism) | Low |
| **Charity/fashion events** | Fantasy Faire (Relay for Life) had raised US$358,000 for the American Cancer Society by end-2019; the 2025 edition ran 17 April-4 May with roleplay, LitFest, auctions, a fourth Film Festival and a new Theatre Festival (Source: https://modemworld.me/2020/04/25/fantasy-faire-2020-three-reasons-to-relay/; https://modemworld.me/2025/04/17/fantasy-faire-2025-your-almost-complete-unofficial-guide/). Collabor88 (monthly designer event, 8th of each month) returned no search results; its format is **[prior knowledge]** | Multi-region temporary builds; sponsor shops; a published seasonal calendar (Fantasy Faire April/May, SLB June/July, Pride June) | Medium |
| **LGBTQ+ (Second Pride)** | Destination page says "20 years of service to the LGBTQ+ community"; main event 20-29 June on three stages, fundraising for It Gets Better; a Community Resource Centre for newcomers existed in 2023. No trans-specific group was surfaced; Garbo's (est. July 2021) is a trans-friendly music venue (Source: https://secondlife.com/destination/second-pride; https://modemworld.me/2023/06/11/) | Annual festival regions, year-round clubs | Medium |
| **Furry** | No population figure. Luskwood (avatar maker since 2003) self-reported ~30,000 customers in 2010 and 40,000+ by 2013; Furscience reports ~40% of furries interact on sites "such as Second Life or IMVU" (Source: https://marketplace.secondlife.com/p/Luskwood-Tundra-Kellashee-Avatar-Male-Complete-Furry-Avatar/2359366?page=1; https://furscience.com/research-findings/fandom-participation/2-12-social-interaction/) | Hub sims (Luskwood), avatar vendors, dance clubs | Low |
| **Roleplay by genre** | Historical: the 1920s Berlin Project passed its 10th anniversary in 2019, "100+ tenants", weekly period events (Source: https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/; https://www.killscreen.com/you-can-visit-a-historically-accurate-1920s-berlin-in-second-life/). Urban noir: The Crack Den spans three sims (Crack Den, Backwaters, Columtreal University) and is text-only roleplay (Source: https://thecrackden.com/roleplay/). Gor: a "world within a world" with rules "so mind-numbingly elaborate they put off casual visitors" (2007) (Source: https://www.theregister.com/2007/04/18/role_play_in_sl/?page=4) | Private estates with dress codes, application forms, HUD-based meters; events weekly | Low |
| **Combat/military** | **[prior knowledge, unverified]**: the SL Military Community (SLMC) groups such as Alliance Navy, Ordo Imperialis and Merczateers run damage-enabled regions with scripted weapon/meter systems; no public counts | Damage-enabled parcels, scripted combat meters, group-based factions | Low |
| **Religious** | First UCC Second Life was the first virtual congregation in a US mainline denomination to receive full standing; the UU Congregation of SL notes that worship "occurs in text", which "makes it accessible to the deaf, and to people whose English isn't very good" (Source: https://www.ucc.org/virtual_church_meets_needs_of_marginalized_through_extravagant_welcome/; https://www.uua.org/node/31164; https://auc.edu.au/2012/10/sacred-space-and-religious-ritual-in-the-virtual-world/) | Single parcels or regions; weekly services; text-first | Medium (dated 2008-2013) |
| **Breedables / non-English** | See alife-and-ai-npcs.md and gap-non-english-communities-and-regional-law.md | Vendor life-support servers; language hub sims | Medium |

### 2. Load-bearing platform features per community

Second Life's group system is the common substrate: a group needs at least two residents, has a moderated group chat, two to ten roles with assignable abilities, can own land and objects, and any resident can join up to 42 groups; ban lists hold up to 500 avatars and are managed by an explicit "Manage ban list" ability; each group carries a maturity rating set at creation and the name can never be changed (Source: https://wiki.secondlife.com/wiki/Group; https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.7.14.292630; https://community.secondlife.com/English-Knowledge-Base/Managing-your-group-memberships/ta-p/700117). Estate owners and managers additionally script access and ban lists via llManageEstateAccess (throttled to 30 calls per 30 seconds) (Source: https://wiki.secondlife.com/wiki/LlManageEstateAccess).

- **Education**: instructor/student roles, estate access lists for private classes, text chat logs, General maturity rating; voice is secondary.
- **Disability**: text parity with voice (Cape Able and UU worship run in text), a text-mode client (section 3), group notices as the event bus, mentors with rez rights.
- **Live music**: parcel-level stream URL, owner control of who sets it, DJ/host roles, L$ tip jars, event listings. Losing any one ends a venue.
- **Roleplay**: estate access/ban lists, roles as in-fiction ranks, attachment and animation systems (HUD meters, dress codes), ranged text chat and emotes, Moderate/Adult ratings.
- **Combat**: damage-enabled parcels, physics push, scripted projectiles, faction groups **[prior knowledge]**.
- **Fashion/charity events**: temporary multi-region estates, vendor rights by group, L$ with charity splits.
- **LGBTQ+ and religious**: safe-space access lists, moderated group chat, ratings that let Adult venues and General congregations coexist.
- **Breedables**: scripted objects phoning home to vendor servers; guaranteed script execution and persistence.

### 3. Blind and deaf residents today, and what guidelines would demand

Blind residents overwhelmingly use **Radegast**, a text-based client that Latif Khalifa built for IM when the full viewer could not run; he only later learned it was screen-reader friendly and that blind users were logging in with it. Its text menus, text inventory and text object list are what make it workable (Source: https://applevis.com/comment/73862; https://www.disabled-world.com/entertainment/games/radegast.php). Virtual Ability's 2021 blog describes a blind member who "relies on Radegast", and a Voices of VR interview says "most blind people working in this space" use it (Source: https://blog.virtualability.org/2021/06/the-most-common-questions-asked-by.html; https://voicesofvr.com/934-accessibility-in-virtual-worlds-lessons-from-second-life-with-donna-davis/). The maintenance picture is fragile: Khalifa stepped back in 2014 for health reasons and later died; Cinder Roxley maintained it for about six years; the last formal release was 2.39 in February 2022, the radegast.life site has been dead since April 2022, development moved to github.com/cinderblocks/radegast, the MEGAbolt fork was started partly over "concerns about Radegast's state", and the SL third-party viewer directory still points at the dead site (Source: https://modemworld.me/2022/10/18/2022-viewer-release-summaries-week-41/; https://www.sourceforge.net/mirror/radegast; https://wiki.secondlife.com/wiki/Third_Party_Viewer_Directory/Radegast). Academic predecessors (TextSL, IBM's 2009 navigation study) showed that voiced GPS, self-voicing TTS, key remapping and keyboard-only navigation are what blind and motor-impaired players need in a 3D world (Source: https://a11y-paradise.onrender.com/reviews/69c2d08e8f65accc3c0ac0a0; https://research.ibm.com/publications/exploring-visual-and-motor-accessibility-in-navigating-a-virtual-world). Deaf residents rely on text chat parity: the Cape Able sim and text-based worship are both built on it.

What the guidelines would require: the **Xbox Accessibility Guidelines** (v3.2, June 2023, explicitly advisory) chat guideline XAG 119 asks for real-time speech-to-text transcription of voice chat for d/Deaf players, text-to-speech chat for non-verbal players with no action required by listeners, screen-narration previews of canned messages, and per-game override of platform defaults (Source: https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119; https://devdocs.xbox.com/build/game-principles/accessibility/xag-deep-dives/xag-119-chat.md). The **Game Accessibility Guidelines** add "voiced GPS" (a spoken overview of nearby objects) for blind navigation of 3D environments, an appropriate default field of view, and the rule that no essential information be conveyed by audio alone (Source: https://gameaccessibilityguidelines.com/?p=263; https://www.webbie.org.uk/blog/?p=115). Second Life meets none of these natively; it meets them only through a third-party client with no release since 2022.

### 4. Educators: what they need and why they left for OpenSim

Linden Lab removed the education/non-profit land discount in autumn 2010, which "resulted in a near-immediate doubling in server costs" for those users, and contributed to a gradual migration to OpenSim as contracts expired: grids "typically offered much lower prices, more security, and more control", plus "full region and inventory backups" (OAR/IAR) and hypergrid avatar portability (Source: https://hypergridbusiness.com/?p=35085; https://hypergridbusiness.com/2013/07/second-life-restores-half-off-discount-to-educators; https://er.educause.edu/articles/2011/4/second-life-is-dead-long-live-second-life). Linden restored a 50% discount in July 2013 (region setup ~US$1,000 to ~$500; monthly ~$300 to ~$150) for accredited institutions and 501(c)(3)s, but commentators judged it "too late" and noted "a good degree of bad feeling" (Source: https://hypergridbusiness.com/?p=43975; https://modemworld.me/2013/03/14/). A 2014 study of 34 university educators found cost and *persistence* (will the world still exist next semester) were the deciding factors (Source: https://www.scitepress.org/Papers/2014/49578/). OpenSim today still reports roughly 900,000-1,000,000 region equivalents (late 2025), with OSgrid and Kitely (~18,000-19,000 regions) the largest grids (Source: https://www.hypergridbusiness.com/statistics/; https://hypergridbusiness.com/?p=73088).

Current needs **[prior knowledge, unverified by search]**: private or institution-hosted grids (FERPA/GDPR student-data control, no public search of minors), SSO via institutional identity (SAML/LTI into Canvas/Moodle), bulk account provisioning with no email verification per student, export of builds (OAR) at end of grant, an 18+/13+ split that is auditable, and a price per class-sized region in the tens of dollars a month, not hundreds. Linden's own Registration API exists but is enterprise-gated (Source: https://wiki.secondlife.com/wiki/Registration_API_Reference).

### 5. Leaders, venue owners, and what past migrations cost

Institution-holders identified: Gentle Heron (Alice Krueger) and Virtual Ability's board; Gabrielli Rossini (Cape Able); Jo Yardley (1920s Berlin) **[name prior knowledge]**; the Crack Den collective; Second Pride's board; Fantasy Faire's RFL team; the VWBPE committee; Luskwood's founders; the First UCC SL and UUCSL minister teams. Each rents regions, runs a group with roles and a published calendar; several are 501(c)(3)s.

Costs of previous migrations:
- **OpenSim (2010-2013)**: lost L$ economy and Marketplace, lost audience (OpenSim's active users are a fraction of SL's: one undated Hypergrid report put *all* OpenSim actives at ~35,500), fragmentation across grids, and the need to self-host; gained backups, control and ~10x lower land cost (Source: https://www.hypergridbusiness.com/?p=34624; https://hypergridbusiness.com/?p=35085).
- **Sansar (2017-2020)**: Linden stopped funding it in February 2020, laid off 20+ staff, and sold it to Wookey in March 2020; it then went offline without explanation in December 2021 with only a Discord note from management, and the community openly asked "is it time to give up on Sansar and leave?" in April 2021 (Source: https://uploadvr.com/sansar-offline-without-explanation/; https://modemworld.me/2020/02/21/lab-seeking-a-plan-b-to-secure-sansars-future/; https://roadtovr.com/sansar-spin-off-linden-lab-refocus-second-life/; https://ryanschultz.com/2021/04/12/). Creators who moved rebuilt content in a different asset pipeline and lost it when the operator went silent. Its eventual closure is **[prior knowledge, unverified in this run]**.
- **VRChat**: no evidence surfaced of whole SL communities moving; what moved were individuals (furry and music scenes overlap). VRChat has no land, no group-owned persistent economy and no text-first client, so the disability, education and roleplay-estate communities had nowhere to land **[inference]**.

What moves a whole community rather than individuals: (a) the institution survives intact: group, roles, ban lists, land, calendar and treasury migrate as one object, not 1,300 sign-ups; (b) the assets the community *is* (venues, HUDs, meters, worship spaces, avatars) import or are rebuilt at platform cost; (c) the audience can be reached from SL during a long dual-presence window; (d) a credible persistence guarantee, the first question leaders ask (2014 educator study; Sansar outage); (e) text/screen-reader parity on day one, or Virtual Ability cannot come.

## Design implications for nolife

1. **Migrate groups, not people.** A "community charter import" creates group name, roles/abilities, opt-in member list, ban list, maturity rating, calendar and land allocation in one transaction with the leader as owner. This operationalises R33.
2. **Ship a first-party text client (Radegast successor) before launch**: chat, IMs, notices, inventory, teleport, object list, voiced GPS, speech-to-text captions on voice, TTS of typed chat. Target GAG and XAG 119 conformance and fund maintenance rather than relying on a volunteer.
3. **Streaming audio and tip rails are venue infrastructure.** Parcel-level stream URL, host/DJ roles, and micropayment splitting (including charity splits for RFL/AISM-style marathons) are the minimum for live music to come.
4. **Education tier**: institutional SSO (SAML/LTI), bulk student accounts without email, private grid or region isolation with export (OAR-equivalent), General-rated-only enforcement, and a published price for a class region under US$50/month, with a written persistence/escrow commitment.
5. **Roleplay and combat need estate-grade tools**: access/ban lists at region and parcel level, attachment and animation systems rich enough for HUD meters, damage-enabled parcels, and Moderate/Adult ratings with age assurance so Gor, noir and Pride venues can all exist.
6. **Platform-hosted life-support for scripted economies** (breedables) so vendor death never kills assets.
7. **Dual-presence window**: bridge chat/events with SL for 12-24 months so venues keep their audience while building a new one.
8. **Named-leader outreach list**: Virtual Ability, VWBPE committee, Second Pride board, Fantasy Faire/RFL, 1920s Berlin, Crack Den, Luskwood, Cafe Musique, First UCC SL/UUCSL; each is a single decision-maker who can bring hundreds to thousands.

## Sources

- https://secondlife.com/destination/vwbpe
- https://ryanschultz.com/2023/02/21/
- https://modemworld.me/page/352/?wref=bif
- https://community.secondlife.com/t5/Featured-News/Virtual-Worlds-Best-Practices-in-Education-Starts-March-18th/ba-p/2914664
- https://lists.aoir.org/archives/list/air-l@lists.aoir.org/thread/IY67LPKZMS37Q4O6NF6VZTIMITQAANSL/
- https://modemworld.me/2025/03/27/sl22b-performer-applications-open/
- https://community.secondlife.com/blogs/entry/9829-david-venter-a-new-electronic-music-project-in-second-life/
- https://go.secondlife.com/destination/aism
- https://modemworld.me/2020/04/25/fantasy-faire-2020-three-reasons-to-relay/
- https://modemworld.me/2025/04/17/fantasy-faire-2025-your-almost-complete-unofficial-guide/
- https://secondlife.com/destination/second-pride
- https://modemworld.me/2023/06/11/
- https://marketplace.secondlife.com/p/Luskwood-Tundra-Kellashee-Avatar-Male-Complete-Furry-Avatar/2359366?page=1
- https://furscience.com/research-findings/fandom-participation/2-12-social-interaction/
- https://ryanschultz.com/2019/05/30/the-1920s-berlin-project-celebrates-its-10th-anniversary-in-second-life/
- https://www.killscreen.com/you-can-visit-a-historically-accurate-1920s-berlin-in-second-life/
- https://thecrackden.com/roleplay/
- https://www.theregister.com/2007/04/18/role_play_in_sl/?page=4
- https://www.ucc.org/virtual_church_meets_needs_of_marginalized_through_extravagant_welcome/
- https://www.uua.org/node/31164
- https://auc.edu.au/2012/10/sacred-space-and-religious-ritual-in-the-virtual-world/
- https://wiki.secondlife.com/wiki/Group
- https://wiki.secondlife.com/wiki/Release_Notes/Second_Life_Release/3.7.14.292630
- https://community.secondlife.com/English-Knowledge-Base/Managing-your-group-memberships/ta-p/700117
- https://wiki.secondlife.com/wiki/LlManageEstateAccess
- https://wiki.secondlife.com/wiki/Registration_API_Reference
- https://applevis.com/comment/73862
- https://www.disabled-world.com/entertainment/games/radegast.php
- https://blog.virtualability.org/2021/06/the-most-common-questions-asked-by.html
- https://voicesofvr.com/934-accessibility-in-virtual-worlds-lessons-from-second-life-with-donna-davis/
- https://modemworld.me/2022/10/18/2022-viewer-release-summaries-week-41/
- https://www.sourceforge.net/mirror/radegast
- https://wiki.secondlife.com/wiki/Third_Party_Viewer_Directory/Radegast
- https://a11y-paradise.onrender.com/reviews/69c2d08e8f65accc3c0ac0a0
- https://research.ibm.com/publications/exploring-visual-and-motor-accessibility-in-navigating-a-virtual-world
- https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119
- https://devdocs.xbox.com/build/game-principles/accessibility/xag-deep-dives/xag-119-chat.md
- https://gameaccessibilityguidelines.com/?p=263
- https://www.webbie.org.uk/blog/?p=115
- https://hypergridbusiness.com/?p=35085
- https://hypergridbusiness.com/2013/07/second-life-restores-half-off-discount-to-educators
- https://hypergridbusiness.com/?p=43975
- https://er.educause.edu/articles/2011/4/second-life-is-dead-long-live-second-life
- https://modemworld.me/2013/03/14/
- https://www.scitepress.org/Papers/2014/49578/
- https://www.hypergridbusiness.com/statistics/
- https://hypergridbusiness.com/?p=73088
- https://www.hypergridbusiness.com/?p=34624
- https://uploadvr.com/sansar-offline-without-explanation/
- https://modemworld.me/2020/02/21/lab-seeking-a-plan-b-to-secure-sansars-future/
- https://roadtovr.com/sansar-spin-off-linden-lab-refocus-second-life/
- https://ryanschultz.com/2021/04/12/
