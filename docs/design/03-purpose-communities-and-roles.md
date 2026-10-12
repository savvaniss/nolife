# 03 · Purpose, communities and roles

Design document 03 of 10. Author: civic-engine lead. Date: 2026-10-09. Status: draft for engineering review. Canonical names and numbers come from [the design spine](00-design-spine.md) (C.1, D.6, D.7). Requirements R1-R30 come from [the failure taxonomy](../research/failure-taxonomy.md). Values the spine does not set are marked "(this document)". No web search was used. External facts come from the research briefs and carry inline sources.

## Summary

nolife manufactures no purpose. It gives communities the machinery to supply it, and this document specifies that machinery.

- **Charters** are permanent institutions. One that owns land or a calendar names a deputy and a succession rule.
- **Posts** are badged roles with shifts and deputies. Those earning Standing or stipends are capped at one per eight active members, minimum three.
- **The Landing** starts a hosted cohort every 15 minutes per launch language, 16:00-24:00 local (target 12, range 6-20). It runs **First Light**, walks the cohort to a live event and hands each newcomer three **Call Board** invitations. A 10% holdout decides at L+6 whether it is kept.
- **The Civic Calendar** fixes a weekly rhythm and the annual **Ephemeral Ward**, whose relics are never reissued.
- **Standing** (Neighbour to Elder) is earned, never sold, and decays one rank per 12 months of absence.
- **The Chronicle** records it all, operator decisions included.

---

## Purpose comes from communities

### The finding we build on

Retention concentrates in users attached to a group with a recurring time and place, and Second Life supplied neither schedule nor roles (taxonomy 1.4). What lasted was built and staffed by residents:
- the Confederation of Democratic Simulators, running since 2004 ([source](https://wiki.secondlife.com/wiki/Confederation_of_Democratic_Simulators));
- Virtual Ability, with 1,300+ members ([source](https://virtualability.org/history/));
- SL9B, which volunteers built after Linden withdrew ([source](https://modemworld.me/2012/06/17/sl9b-let-the-festivities-begin/));
- the Anglican Cathedral, which outlived its founder because a team existed ([source](https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/)).

Unstaffed corporate builds were "a shop in the High Street filled with brochures but never having any staff" ([source](https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2)).

Three patterns from the community-purpose brief shape every mechanism here:
1. **People stay where they are needed.** Mentors, hosts, DJs and NoPixel's whitelisted characters show it ([source](https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide)).
2. **Scarcity creates value.** FFXIV's housing lottery spawned an unplanned venue scene ([source](https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1)), and Habbo ran on never-reissued rares ([source](https://www.habbo.com/community/article/22292/update-state-habbo-economy)).
3. **Rituals need a calendar and must be shareable.** BURN2 has burned its Man in SL since 2003 ([source](https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/)), and the Animal Crossing graduation spread because people could post it ([source](https://www.newsweek.com/animal-crossing-new-horizons-teacher-help-students-graduate-pandemic-1498760)).

### The design rule

The platform supplies institutions, roles, scarcity, a calendar and memory; communities supply the life. Every feature passes doc 01's test: does it give a community a tool, role, slot or record (pass), or fill time for the operator (reject)? There are no quests and no story. Keepers (doc 07) never hold Posts or Standing.

### What is a hypothesis and what is a commitment

The causal effect of group membership on retention has never been published; the Destiny clan study is correlational ([source](https://www.sciencedirect.com/science/article/pii/S1875952117301350)). So the Landing is an experiment with a kill rule. Charters, Posts, the Calendar, Standing and the Chronicle are **commitments**: SL's proven group substrate (2-10 roles, a ban list, land, a fixed rating) ([source](https://wiki.secondlife.com/wiki/Group)) plus what it lacked: a schedule, a deputy, a paying treasury and memory.

### Outcome targets (spine D.7, published in Census)

| Target | Value | Definition (this document unless noted) |
|---|---|---|
| Scheduled-event reach | **≥25% of MAU each month** | The share of Census-active humans present for at least 15 minutes at one or more Calendar-listed events during the event's scheduled window |
| Venue survival | **≥80% survive a leader's 90-day absence** | See [Charters](#charters), "Measuring survival" |
| First-session completion | ≥60% | Reached the Hearth and either the event or the Call Board |
| Organic retention | D7 25%, D30 15%, D90 10%; Founding Charter members D90 25% | Census-active in the day window (D30 window: days 28-34, this document) |
| Creator-run places | ≥40% of DAU-hours by L+12 | Charter, Estate and Holding places (R8) |

---

## Charters

A **Charter** is an institution: a permanent name, 2-20 roles, a ban list, a fixed rating, a calendar, a multi-signature Coin treasury and Holdings, one of which may be its **Hall**. A Charter that owns land or a calendar must name a **deputy** and a **succession rule**.

### Data model (pseudo-interface)

```
Charter {
  name                    // permanent, unique, never reissued
  rating: General|Moderate|Adult         // fixed at creation
  roles: Role[2..20]      // permission bundles; Posts bind to roles
  posts: Post[], ban_list: PassportRef[]
  calendar: SeriesRef[]   // publishes into the Civic Calendar
  treasury: { balance_coin, signers: PassportRef[], threshold_m, legal_entity? }
  holdings: HoldingRef[], hall?: HoldingRef
  owner: PassportRef, deputy: PassportRef          // deputy required if holdings or calendar non-empty
  succession: NamedDeputy | OfficerVote | MemberVote
  state: Draft|Active|Acting|Succession|Dormant|Dissolved
  founding_charter: bool  // Founding Programme participant (spine C.10)
}
```

### Rules

- **Founding.** Any resident at Trust Member (doc 08) may found a Charter. A Charter needs three members within 14 days of founding, or it returns to Draft (this document).
- **Treasury.** Default 2 of 3 signers (owner, deputy, Quartermaster), each with a second factor (doc 08). It receives the Charter's share of the Pool's 20% line (doc 09) and may pay Post stipends, always shown in fiat, since a stipend in a currency also sold for cash gets no gameplay-only carve-out ([source](https://www.twobirds.com/en/insights/2025/global/regulatory-spotlight-virtual-currency-vs-consumer-law-part-2)).
- **Rent.** The treasury pays Holding rent automatically while it can, so a Hall is not lost because a founder's card expired. Doc 02's lapse rule applies only once it is empty.
- **Self-rule.** Access, bans, codes and consent rules inside its own Holdings, within the World Charter (doc 08).
- **Optionality.** No feature requires Charter membership (spine B.4, item 9).

### Succession and the absence watch

Founder dependence killed more SL venues than anything else, so succession is a state machine and not a suggestion:

```
Active ──owner not Census-active 21 days──▶ Acting
   Acting: deputy holds calendar and Holding admin; treasury needs deputy + one other signer
Acting ──owner returns──▶ Active
Acting ──60 days of absence──▶ Succession
   Succession runs the Charter's rule:
     NamedDeputy (default): deputy becomes owner; must name a new deputy within 14 days
     OfficerVote: majority of current Post holders, 7-day poll
     MemberVote: members at Trust Member+, 7-day poll, one vote per Person
Succession ──complete──▶ Active   (returning founder gets the "Founder" role, not ownership)
Active ──no Census-active members for 90 days──▶ Dormant   (Holdings follow the doc 02 lapse rule)
Dormant ──24 months, or owner + deputy vote──▶ Dissolved   (name retired; treasury per dissolution rule,
                                                            default pro rata to last-12-month contributors)
```

Timers are planning values (this document); every transition is written to the Chronicle. With no deputy when Acting would begin, officers are notified and a MemberVote opens after 14 days.

### Measuring survival (the 80% target)

```
venue(C)    = Charter with a Holding and >= 1 public recurring series in the prior 90 days
absence(C)  = owner not Census-active for 90 consecutive days (starts day 1 of the absence)
survived(C) = in days 31-120 of the absence:
                events_held >= 0.5 × events_held in the 90 days before the absence
                AND Hall not lapsed
                AND >= 1 event had >= 5 humans who were not officers
target      : survived / venues with an absence >= 0.80, per quarter (Census)
```

### Founding Charters (spine C.10)

There are 50 Founding Charters, 25 by L. Each gets a migration engineer and a first Cell (or a Domain above 500 members) rent-free until L+6, then 30% off list frozen for 36 months, in return for **one weekly public event** and named deputies. Compliance (this document): a listed public event of at least 60 minutes in 3 of any 4 weeks, and a deputy at all times. After 8 non-compliant weeks the discount pauses for future months, on 30 days' notice, and resumes on compliance; nothing is repriced retroactively.

### Charter Import

Charter Import (doc 10) moves roles, opt-in members, ban list, rating, calendar and Holding in one transaction. SL roles carrying a recurring duty (Host, DJ, Greeter) may become Posts, up to the cap. SL status is not imported.

**Rejected:** ai-world-designer's crews of 3-12 with a mandatory Apprentice. It is a second institution type, and its Apprentice slot was meant for Keepers (B.3); a small Charter does the job.

---

## Posts and the deputy rule

A **Post** is a role with slots, a shift calendar, a badge, an optional stipend and a deputy: a readable statement that "someone is needed here at 20:00 on Thursdays".

```
Post {
  kind: Host|Mentor|DJ|Warden|Builder|Chronicler|Teacher|Healer|Quartermaster|Juror|Custom(name)
  scope: Charter(id) | Ward(id)        // Juror is drawn per case, not appointed
  role: RoleRef                        // abilities granted while holding the Post
  holder: PassportRef, deputy: PassportRef?
  slots: ShiftSlot[]                   // recurring; on the Civic Calendar
  badge: visible on avatar and profile
  stipend?: { source: CharterTreasury | Pool10, coin_per_shift_hour, fiat_shown: true }
  earns_standing: bool                 // true for every capped Post
  term_days: 90                        // renewable (this document)
}
```

### The base vocabulary

| Post | Typical abilities | Entry rule (this document unless noted) |
|---|---|---|
| Host | Admission, Stage controls, greeting cohort and guests | Trust Member; Landing Hosts: Trust Known, Standing Regular, Host training (Standing waived in the alpha) |
| Mentor | Apprentice pairing; build rights in a mentee's Hearth on invitation | Trust Known |
| DJ | Sets the parcel audio stream; Stage controls | Trust Member |
| Warden | Kick and lock (Safety Kit); files reports with evidence | Trust Known (doc 08); second factor |
| Builder | Build rights on the Charter's Holdings | Trust Member |
| Chronicler | Signs Chronicle entries for the Charter or Ward | Trust Member |
| Teacher | Presenter tools, class seating, Campus-style rosters | Trust Member |
| Healer | Peer support and care sessions in private rooms; not clinical | Trust Known; Safety Kit training |
| Quartermaster | Proposes treasury payments; inventory custody | Trust Known; second factor |
| Juror | Tribunal duty (doc 08) | Drawn by lot from Pillar+ |

Charters may define their own Posts. A live venue dies if it loses its stream URL, its host and DJ roles or its tip jar (census brief), so the DJ Post owns the stream setting and tips split automatically among the Post holders on shift.

### The cap (spine B.4, item 8)

Only Posts that earn Standing or public stipends are capped:

```
cap(C) = max(3, floor(A / 8))
A      = Charter members Census-active in the last 30 days, one per Person, Keepers excluded
```

| Active members | Capped Posts allowed |
|---|---|
| 10 | 3 |
| 40 | 5 |
| 200 | 25 |
| 1,300 (Virtual Ability scale) | 162 |

- **Outside the cap:** deputies (Standing only for shifts they work); **event crews**, uncapped for the event, expiring 24 hours after it, tagged "Crew" rather than badged, earning no Standing beyond attendance but named in the Chronicle; and unlimited **unbadged internal roles**.
- **Shrinking Charters.** No Post is revoked mid-term; at term end, excess Posts with the fewest worked shifts become unbadged roles (this document).
- **Ward Posts:** each Ward has **8 Warden and 12 Host Posts**, paid from the Pool's 10% line, appointed by the Ward council from L+6 (doc 08) and before that by the community team from Founding Charter nominations.

### The deputy rule

- The deputy field is mandatory for any Post whose role owns land or a calendar, and for every Ward Post. A Post without a deputy for 30 days stops accruing Standing (this document).
- **Handover.** After 3 missed shifts or 21 days without Census activity, the deputy acts; after 60 days the deputy becomes holder and names a new deputy within 14 days (this document). Both earn a succession credit.
- **Valid shifts.** The holder or deputy is present for 75% of the shift, and another human (not a Keeper, not a same-Person alt) for half of it, so Standing cannot be farmed in empty rooms.

### Public stipends (spine B.4, item 10)

Standing is the main reward. Public stipends go only to **Landing Hosts, Ward Wardens and Jurors**, from the Pool's 10% line:

```
P10_month = 0.10 × Pool_month
units     = Landing Host shift-hours + Ward Warden shift-hours + 3 × Tribunal cases decided   (weights: this document)
rate      = min(1,500 Coin, P10_month / units)          // cap per shift-hour from doc 09; the excess rolls forward
stipend   = rate × units worked, shown in local fiat
```

At Reference scale the 10% line is about US$1.0M a year (spine D.8). Stipends are honoraria, not wages.

**Rejected:** paying every role from the Pool (economist), which the judges called a payroll (B.4, item 10); capping every role (sociologist), which starves festivals and Estates (B.4, item 8); Keepers filling empty slots (ai-world-designer, B.3); selling Posts (Never List).

---

## The Landing and First Light

The Landing's promise: "a human host will say your name, walk you to a live event with at least ten other people and hand you three invitations to be needed." Doc 02 owns the hall; this section owns the script.

### Cadence, size and staffing (spine D.6)

- **Cadence:** a cohort every 15 minutes per launch language, 16:00-24:00 anchor-local: 32 a day per anchor, five anchors at L (English ×3, Portuguese, Spanish), Japanese and German at L+12.
- **Size:** target 12, range 6-20; under 6 merge into the next cohort, over 20 open a parallel hall (doc 02).
- **Staffing:** a Host leads a cohort for about 40 minutes, so about three are on shift per anchor. Doc 09 plans one paid host-hour per cohort: about 224 a week per anchor, about 58,000 a year at L. The anchor Ward's 12 Host Posts and their deputies (about 24 people) work about 9 hours a week each; staff community managers cover gaps unpaid by the Pool.
- **Alpha:** Hosts come from Founding Charters and are paid from the Founding Programme budget until L+1 (doc 09). From L+12 a Keeper Greeter may hold an unstaffed hall and hands over when a Host arrives (doc 07).

### The script

```
t+0     Account, private age band, language → Landing hall. Host greets each newcomer by display name.
t+0-10  Dress: Common Body with three Starter Catalogue outfits (each equipped item earns its
        creator Pool weight for 90 days). Pick 3 of ~20 interest tags. Choose and furnish a Hearth
        from the free kit (R26). The scripting panel is not in the consumer UI.
t+10-20 First Light (below).
t+20-30 The Host walks the cohort through the gate to an event starting within 30 minutes, chosen
        by doc 02's route_cohort (p10 = P(>=10 humans present)). The Host introduces the cohort to
        the event's own Host and hands over.
t+30-60 The event. The Host leaves at about t+40 for the next cohort.
end     The Call Board presents three invitations, at least one outside any Charter.
        Logout prompt: "Your next thing is <invitation 1>, <day> <time>."
```

**R11 success** ("met a person or joined a group") is five minutes of two-way interaction with a human outside the cohort, or an accepted Charter invitation.

### First Light

First Light is a ten-minute shared job that writes every name into the Chronicle. The shipping version, **the Lamp Line** (this document): each newcomer carries a flame from the hall's hearth along the path to the gate, and a lamp lights only when two newcomers hold their flames to it together, so the cohort must pair up and talk. When every lamp is lit, the gate opens. It needs coordination, not skill. In Reader each pair types a word instead, and the words form the cohort's line (R27). The Chronicle then writes:

```
ChronicleEntry{ type: FirstLight, hall: "Portuguese Landing", at: 2028-10-14T19:15-03:00,
                names: ["Ana", "Bo", ...], host: "Rui (Host)", line: "<cohort words>" }
```

Names are display names; a newcomer may choose "write me as *a newcomer*" (this document). Completing First Light raises Trust from Visitor to New (doc 08).

### The holdout and the keep rule

- **Randomisation.** 10% of accounts whose first login falls in hosted hours get the self-guided Landing, for 6 months from L, so time of day cannot confound the result. Out-of-hours arrivals are offered a seat in the next cohort and reported separately.
- **The holdout** gets the same avatar, Hearth, Starter Catalogue, Now and Next and the Call Board as a list, but no Host, cohort, First Light or handed invitations, isolating the hosted group. Analysis is intent-to-treat, pre-registered in the Chronicle.
- **Keep rule (spine D.7).** The Landing is kept if **treated D30 ≥ holdout D30 + 3 points and treated D30 ≥ 15%**, published at L+6. If it misses, it follows doc 01's lifecycle: RESCOPED (one retry against the same holdout), then CUT.
- **Series A gate (spine D.2).** Alpha Landing D30 must be at least 3 points above the holdout.

Detecting a 3-point lift at D30 near 15% (80% power, α = 0.05) needs about 2,000 holdout accounts (derived): weeks at L traffic, but not reachable in the alpha (Open questions).

**Host incentives.** Hosts are paid per valid shift-hour, **never by retention**, which would reward pressure and measure salesmanship rather than the group. A one-tap "my Host said my name" rating goes to the Ward council; persistent misses mean retraining, then non-renewal.

**Rejected:** a cohort every 10 minutes (economist), with about 50% more host-hours for cohorts too small to fill events; ai-world-designer's Tide with an ever-present Keeper guide; a 24-hour hosted Landing the 10% line cannot fund.

---

## The Call Board

The Call Board lists Charters recruiting this week and gives each newcomer three invitations. It is a kiosk on each Ward's Green (doc 02), a client panel and discovery's second view.

### Calls and invitations

```
Call {                       // posted by a Charter (or by a Ward for public needs)
  charter?: CharterRef       // absent for public Calls
  need: PostApprenticeship | EventRole | Membership | OpenActivity
  when: next occurrence within 7 days
  greeter: PassportRef       // a named human who will meet the newcomer
  seats: 1..20, language, rating: General|Moderate      // Night Ward Calls never appear (doc 08)
  expires: 7 days
}
Invitation { call: CallRef, newcomer: PassportRef, state: Offered|Accepted|Met|Lapsed }
```

- At most 3 open Calls per Charter per Ward per week (this document); posting is free and payment never affects placement. Greeters acknowledge an acceptance within 24 hours.
- **Public Calls** sit outside any Charter: a Commons build day, a Market Day stall, Open Stage sign-up, an open council session, a Darkroom photo walk.

### Choosing the three

```
score(call, n) = lang_match × rating_ok × time_fit(n.first_session_hour, call.when)
               × (0.5 + tag_overlap(n.tags, call.tags))
               × quality(call.charter)
quality        = 0.5 + 0.5 × min(1, H28 / 200) × greeter_response_rate × survival_flag
pick           : top-scoring Call from three different Charters or categories,
                 with slot 3 forced to the best public Call or an individual's Call (B.4, item 9)
fairness       : a Charter appears in at most 1 in 20 offered sets per day per Ward,
                 and 20% of slot-1/2 offers go to Charters under 90 days old
```

Values are planning values (this document); H28 is doc 02's returning-humans measure. Census publishes acceptance rate, met rate (greeter and newcomer co-present within 7 days) and D30 by outcome. A Charter whose met rate stays below 50% for 4 weeks is paused until a deputy confirms its greeters.

---

## The Civic Calendar

Three layers: a fixed weekly rhythm, a Charter-owned seasonal layer and one annual ritual. Entries export as iCal and ActivityPub feeds and are relayed to SL by the Bridge for 18 months.

### The weekly rhythm (each Ward's local time)

| Day | Name | What happens |
|---|---|---|
| Monday, Tuesday, Thursday | — | Charter events; Stage prime hours by quarterly lottery (doc 02) |
| **Wednesday** | **Quiet Day** | No first-party events. Charters own the day. Landing cohorts are routed only to Charter events. |
| **Friday** | **Open Stage** | 18:00-23:00. Slots by weekly lottery weighted by audience retention. |
| **Saturday** | **Market Day** | Market stalls. 0% commission on in-person sales: a human seller or Split member present in the cell (doc 09). |
| **Sunday** | **Assembly Day** | The Ward council sits (from L+6), the week's Chronicle is read aloud and signed, and the Assembly sits (from L+12). |

**The Open Stage lottery** (this document) has ten 30-minute slots per Ward per week:

```
eligible  : any resident at Trust Member, alone or for a Charter; one entry per Person per week
w(entrant)= 1 + min(2, R / 20)
R         = distinct humans who stayed >= 20 min of the entrant's last 3 Calendar sets
reserve   : 2 of 10 slots for entrants who have never played Open Stage (w = 1 among themselves)
```

Retention, not size, weights the draw: keeping 20 people a whole set beats briefly drawing 100.

### The seasonal layer

Charters own it: Fantasy Faire, Pride, the Burn. A Charter registers a season of up to 14 days a year per Ward, approved by the Ward council (by the platform before L+6) (this document). A registered season gets a Chronicle entry and reserved Stage time, and counts as a **Civic Calendar event**, so Event Mode above 1,000 is waived. Ordinary weekly events are listed but not waived.

### The Ephemeral Ward

The one annual scarce ritual. Doc 02 owns the place (16 cells in 2029, growing toward 64); this document owns the ritual and its relics.
- **Dates.** Built by Charters each August; runs in the **second full week of September from 2029**. First edition: Monday 10 to Sunday 16 September 2029 (L+11), after Event Mode is validated at 2,000. Builder applications open each June.
- **Crowds.** Synchronised instances of about 100 with cross-instance chat, the format of Fortnite's concerts ([source](https://musicbusinessworldwide.com/fortnites-remix-the-finale-concert-draws-over-14m-players-breaking-records)).
- **Erasure on camera** at Sunday's close, with Darkroom renders and a Chronicle entry. Builders' items return to inventory; the place is never restored.

It replaces the proposals' four named rituals with one (B.3).

---

## Scarcity, relics and status

### The four scarcities

The world is short of four things and generous with the rest: private land is abundant (the Reach grows once 80% rented) and nothing is demolished.

| Scarce good | Rule | Never |
|---|---|---|
| Public land | 64 Commons plots per Ward by lottery. The ticket is US$24 (3 months prepaid at US$8/month) and is refunded in full to losers within 24 h. A plot unused for 45 days returns to the lottery, with 80% of unused prepaid rent refunded and a published pause policy (doc 02). | Sold outright; weighted by Standing or spend |
| Prime time | 40 prime Stage hours a week by quarterly lottery; 10 Open Stage slots | A sponsored slot |
| Posts | One capped Post per eight active members, minimum three; 8 Warden and 12 Host Posts per Ward | Bought or transferred |
| Relics | Minted only during the Ephemeral Ward week, never reissued | Distributed by chance |

The Commons ticket is not a wager: losers are refunded in full and winners prepay rent. FFXIV shows that a losable plot becomes a status object, and that its timer must be suspendable ([source](https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily)).

### Relic rules

The spine fixes never-reissued relics at a 0% resale fee, minted only in the Ephemeral Ward; doc 02 adds no resale royalty. Detailed rules (this document):

1. **Two kinds.** A **Witness mark** is non-transferable, on the Passport and in the Chronicle, for at least 60 minutes' presence on 2 days of the week. A **relic** is a transferable object minted by a builder Charter.
2. **Editions.** Up to 3 designs per plot-holding Charter, each with an edition cap of at most 1,000 published before the week. Minting closes at the erasure.
3. **No chance, ever.** Relics are given by presence at a scheduled moment ("at the burn") or sold first-come at a fixed price, never by lottery or roll: a cash-out-able item plus chance is gambling somewhere (R9), as SL's 2007 ban shows ([source](https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/)).
4. **One per Person per design**, so alts and bots cannot corner editions.
5. **Fees.** Primary sales pay the Fee Page's 10%; resale is 0% with no royalty.
6. **Enforced.** At erasure each template hash goes to the Chronicle and the Foundry's fingerprint catalogue; any matching upload is rejected. Habbo's 2004 accidental rare re-sale crashed values and drove players away ([source](https://habboxforum.com/showthread.php?t=701469)).
7. **No power.** No `meter.write` or `damage` capability (doc 02).

### What confers status

Status is written, never bought: Post badges, opt-in Standing heraldry, the Chronicle, Witness marks and relics, a Commons address. Money spent, Holding size and Estate priority confer no status or rank (doc 02).

---

## Standing and Trust

Two ladders answer different questions. **Trust**: is it safe to let this person do X? It gates rights. **Standing**: has this person served this world? It qualifies for civic office. Neither can be bought, transferred or earned by a Keeper.

### Trust (doc 08 owns the rules)

Visitor, New, Member, Known and Trusted, plus a Nuisance flag, on VRChat's behaviour-earned model ([source](https://docs.vrchat.com/docs/vrchat-safety-and-trust-system)). Here: First Light moves Visitor to New; Member founds a Charter, enters the Commons lottery and votes (with 90 days' tenure and verified 18+); Known qualifies for Warden, Mentor, Healer, Quartermaster and Landing Host Posts; a Nuisance flag bars any Post.

### Standing

There are four ranks: **Neighbour, Regular, Pillar and Elder**. Standing is earned through Posts, shifts, events, members retained, Commons use and jury duty, measured as **civic credit (CC)**. All values below are planning values (this document).

| Act | CC | Validity and caps |
|---|---|---|
| First Light completed | 2 | Once |
| Calendar event attended (≥15 min) | 1 | ≤6 per month |
| Valid Post shift (holder or deputy) | 2 per shift-hour | ≤40 per month from shifts |
| Public event hosted (Calendar-listed, ≥5 distinct non-officer humans for ≥15 min) | 4 | ≤8 events per month |
| Member retained (a newcomer you greeted or mentored is Census-active at D90) | 3 | ≤10 per month |
| Commons plot in use (passes the 45-day rule) | 2 per month | One plot |
| Tribunal case decided | 6 | — |
| Council or Assembly term completed | 30 | Per term |
| Succession credit (handover completed; the Post or Charter continues for 90 days) | 20 | Both parties |

| Rank | Threshold | Gates |
|---|---|---|
| Neighbour | 6 CC | — (typically within two weeks) |
| Regular | 120 CC, credit in ≥4 distinct months, ≥1 valid shift or hosted event | Stand for Ward council; Landing Host |
| Pillar | 400 CC, credit in ≥9 distinct months, a Post held (holder or deputy) for ≥90 days | Juror; stand for the Assembly (plus 12 months' tenure) |
| Elder | 1,200 CC, credit in ≥24 distinct months, and a succession credit or a completed council or Assembly term | Honorific; listed as a Ward's Elders in the Chronicle |

A Host on 9 hours a week reaches Regular in about three months and Pillar in about ten; a pure attendee reaches Neighbour quickly and Regular only by taking a shift.

### Decay

Standing decays **one rank per 12 months of absence** (spine D.6):
- An absent month is a calendar month with zero CC.
- After 12 consecutive absent months the resident drops one rank and their CC is set to the lower rank's threshold. The counter then restarts.
- Neighbour does not decay (this document).
- The Chronicle keeps the highest rank ever held ("Pillar, 2029-2032"), so history is not erased even when eligibility lapses.

Decay keeps institutions turning over.

**Never:** Standing never weights the Commons or Stage lotteries, discovery, the Pool or prices (doc 02). Heraldry is **opt-in** (B.4, item 9). It is held per Person, so alts share one record and never validate each other's shifts.

**Rejected:** Standing-weighted lotteries (sociologist), which newcomers would never win; a "Citizen" subscription with priority (civic standing is never sold); one merged reputation score, which would make safety rights depend on civic activity.

---

## The Chronicle

The **Chronicle** is an append-only public record. Belonging needs memory: a ten-year resident's history becomes legible to a newcomer, and the operator's decisions sit in the same log as everyone else's.

### What is written

| Entry type | Written by | Signed by |
|---|---|---|
| Charter founded, succession, dormant, dissolved | System | Charter Chronicler or owner |
| Post appointed, handed over, lapsed | System | Charter or Ward Chronicler |
| First Light cohorts | System | Landing Host |
| Events, seasons, the Ephemeral Ward, relic hashes | System or organiser | Ward Chronicler |
| Elections, turnout, ordinances, Tribunal draw seeds | System | Ward Chronicler |
| **Operator decisions**: price notices, RFCs, Assembly answers (within 30 days), keep/cut transitions, Census releases | Operator | Operator key |

From L+12 a Chronicler Keeper may draft entries from event logs, but a human Chronicler signs every one (doc 07).

### Structure

```
ChronicleEntry {
  seq, prev_hash, hash              // hash chain; a daily root is published in Census and escrowed
  type, scope: World|Ward|Charter, at
  body                              // public text and references
  body_hash                         // kept even if body is redacted
  signer: PassportRef | OperatorKey
  supersedes?: seq                  // corrections append; nothing is edited
}
```

- **Corrections** append superseding entries.
- **Legal redaction** (privacy erasure, court order, child safety) leaves a tombstone with the reason class and keeps `body_hash` and the chain; redactions are counted in the quarterly T&S report. A departing resident may have their name replaced by "a resident" everywhere.
- **Open API.** Readable without an account; third parties can verify the chain.

**Rejected:** a private-by-default history (R19 unmet) and an editable wiki (the record becomes the operator's blog).

---

## The first year and optionality

### Two paths through year one

| Month | Joiner (illustrative) | Individualist (illustrative) |
|---|---|---|
| Day 1 | Landing, First Light, accepts a Charter invitation | Landing, First Light, accepts the public Call (a Commons build day) |
| 1 | Apprentice with a Mentor; Neighbour | Hearth decorated; Market Day stall; Neighbour |
| 2-3 | First Post (a Thursday door Host shift); Trust Member | Trust Member; first Commons lottery ticket; plays Open Stage |
| 4-6 | Deputy DJ; Regular; votes in the Ward council election (L+6) | Wins a Commons plot; sells as a Maker in the Bazaar; Regular only if they take a shift |
| 9 | Covers the DJ Post through a handover: succession credit | Joins a Charter's event crew for a season (no Standing, named in the Chronicle) |
| 11 | Builds on their Charter's plot in the Ephemeral Ward; Witness mark and a relic | Attends the Ephemeral Ward; Witness mark |
| 12 | Pillar; eligible as a juror; considers a council run | Still unaffiliated, and nothing is closed to them |

### Optionality guarantees (spine B.4, item 9)

- **No feature requires Charter membership.** That includes Hearths, Holdings, the Commons, Market Day, Open Stage, the Bazaar, voting and standing for council.
- **One of the three Call Board invitations is always outside any Charter.**
- **Standing heraldry is opt-in.**
- **Quiet Day has no first-party events.** A resident who wants none of the civic machinery can ignore it entirely.

### Measuring the ladder

From L+6, Census publishes D30 and D90 **by rung** each quarter (the ai-world-designer graft). The rungs are: holdout; treated cohort; Call Board accepters; Charter members; Post holders and deputies; Regular and above; and individualists (no Charter at day 30). These are correlations. Only the Landing holdout is causal, and Census says so beside the table.

---

## Requirements addressed

| R | How this document addresses it |
|---|---|
| R8 | The Pool's 20% line to Charter treasuries by returning members at events; the 10% line to Landing Hosts, Wardens and Jurors |
| R9 | Stipends always show fiat; relics are never distributed by chance; the Commons ticket is fully refundable |
| R11 | Landing every 15 min per language, 16:00-24:00, target 12 (6-20); "met a person or joined a group"; 10% holdout; kept if D30 ≥ holdout + 3 pts and ≥15% at L+6 |
| R12 | Cohorts routed to events with P(≥10 humans); a median of ≥10 people seen in the first session; Landing hall merge and split |
| R13 | Census: event reach, venue survival, D30/D90 by rung, Call Board met rates, Chronicle chain roots |
| R15 | Deputies and succession; Posts with slots, badges, stipends, deputies; weekly rhythm; Ephemeral Ward in ~100-avatar instances; ≥25% of MAU at events; ≥80% venue survival |
| R16 | Commons plots as one of four published scarcities; refundable tickets; 45-day rule; no demolition |
| R17 | Estate ranks are Charter roles; Estate staff are capped Posts; event crews are uncapped |
| R18 | Charter Import maps SL roles to Charter roles and recurring duties to Posts; the calendar is bridged for 18 months |
| R19 | Operator decisions and Assembly answers in the Chronicle; hash-chained and escrowed |
| R23 | Warden Posts need Trust Known and a second factor; a Nuisance flag bars any Post; Healer and Host training include the Safety Kit |
| R25 | Keepers hold no Post or Standing, never validate a shift, and draft but never sign Chronicle entries |
| R26 | Dressed Common Body and furnished Hearth within ten minutes; no scripting panel in the Landing |
| R27 | First Light and the Call Board work fully in Reader; Healer and Mentor Posts; Virtual Ability as a Founding Charter |
| R29 | Landings and Wards per language (PT/ES at L, JA/DE at L+12); Call Board language matching |

---

## Open questions

1. **Alpha holdout power.** A 3-point D30 lift needs about 2,000 holdout accounts; 10% of 5,000-10,000 alpha residents gives 500-1,000, so the Series A gate rests on a noisy point estimate. The spine value is kept; publish a confidence interval beside it. A larger alpha holdout would need a spine change.
2. **Host load and pay.** About 224 host-hours a week per anchor across about 24 people, at about US$3.80 an hour at Floor scale (doc 09). Should the Founding budget top up the 10% line until L+12?
3. **Absence for decay.** This document reads "absence" as months with zero civic credit, not months without login. Confirm.
4. **Tiny-Charter farming.** The minimum of three capped Posts lets a three-person Charter badge everyone. Should valid shifts require one human from outside the Charter?
5. **Night Ward recruitment.** Night Ward Calls never reach newcomers (doc 08). Does R22's first-class adult purpose need a verified-only Call Board?
6. **Time zones.** Three English anchors leave Asia-Pacific English speakers self-guided. Revisit before L?
7. **Relic speculation.** A 0% resale fee with no royalty invites flipping; review after the first edition.
8. **Erasure versus append-only.** Legal must confirm that a retained `body_hash` satisfies GDPR and LGPD erasure.

---

## Sources

- https://wiki.secondlife.com/wiki/Confederation_of_Democratic_Simulators
- https://virtualability.org/history/
- https://modemworld.me/2012/06/17/sl9b-let-the-festivities-begin/
- https://episcopal.cafe/transitions_at_the_anglican_cathedral_in_second_life/
- https://www.techradar.com/news/internet/whatever-happened-to-second-life-1030314/2
- https://www.sportskeeda.com/gta/how-join-nopixel-gta-5-rp-server-a-step-by-step-guide
- https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1
- https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily
- https://www.habbo.com/community/article/22292/update-state-habbo-economy
- https://habboxforum.com/showthread.php?t=701469
- https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/
- https://www.newsweek.com/animal-crossing-new-horizons-teacher-help-students-graduate-pandemic-1498760
- https://www.sciencedirect.com/science/article/pii/S1875952117301350
- https://wiki.secondlife.com/wiki/Group
- https://www.twobirds.com/en/insights/2025/global/regulatory-spotlight-virtual-currency-vs-consumer-law-part-2
- https://musicbusinessworldwide.com/fortnites-remix-the-finale-concert-draws-over-14m-players-breaking-records
- https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/
- https://docs.vrchat.com/docs/vrchat-safety-and-trust-system
