# 02 · World structure and places

Design document 02 of 10. Author: world-structure lead. Date: 2026-10-09. Status: draft for engineering review. Canonical names and numbers come from [the design spine](00-design-spine.md) (C.2, D.6); requirements R1-R30 come from [the failure taxonomy](../research/failure-taxonomy.md). Values the spine does not set are marked "(this document)". No web search was used.

## Summary

nolife's world is sized to its population. Every account gets a free, instanced **Hearth**. Anyone who wants persistent land rents a **Holding** (Plot S, Plot M, Cell or Domain), priced on Scene Weight and bytes and never on visitors. A Holding sits on an island or on one of two contiguous **Reaches**, and a Reach grows in 64-cell blocks only once it is 80% rented. A Charter makes one Holding its **Hall**. **Estates** add whitelists, seat caps, ranks, meters and damage parcels. Public life gathers in language-tagged, four-cell **Wards**, which open at 2,000 attached MAU and go fallow below 500. Six open at launch, one a **Night Ward** for verified adults. The **Ephemeral Ward**, event instances and Event Mode handle crowds; Landing halls and **Campus** are entry realms. Density is an SLO (about 130 avatars in a Ward's hub cells at peak; a newcomer sees a median of ten). Discovery ranks by returning humans; nothing is deleted for non-payment.

---

## The Ward Plan at a glance

The Ward Plan rests on one rule: **public land exists only where people already are, and private land is plentiful and may be empty.** Second Life spreads about 49,000 peak avatars over about 27,000 regions, roughly 1.2 per region, and its residents call the result "so beautiful, so empty" ([source](https://danielvoyager.wordpress.com/2025/08/11/second-life-statistics-august-2025-update/); [source](https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/)). Horizon Worlds had no land at all, yet only 9% of its worlds ever had 50 visitors ([source](https://www.cnbc.com/2022/10/15/meta-horizon-worlds-metaverse-losing-users-falling-short-of-goals.html)). The fault was never land. It was public space opened before there were people to fill it.

### Place types

| Place | Instanced? | Held by | Size | Price | Rating ceiling | On non-payment |
|---|---|---|---|---|---|---|
| Hearth | Yes | Every account | 1 room, 8 guests, 1,000 Weight | Free | Moderate (Adult with check) | Never lapses |
| Hearth+ | Yes | Resident subscriber | 4 rooms, 25 guests, 4,000 Weight | In Resident | As Hearth | Extra rooms: lapse rule |
| Plot S / Plot M | No | Individual or Charter | ¼ / ½ cell, Reach only | US$19 / US$35 | Moderate | Lapse rule |
| Cell / Domain | No | Individual or Charter | 1 / 4 cells | US$69 / US$249 | Any (island); Moderate (Reach) | Lapse rule |
| Hall | No | Charter | Any Holding | As Holding | Charter's fixed rating | Lapse rule; deputy notified |
| Estate | No | Charter | Island Cell or Domain | As Holding + 10% of tickets/priority | Charter's fixed rating | Lapse rule |
| Ward / Night Ward | No | Platform; council from L+6 | 4 cells | Commons plot US$8 | Moderate / Adult | Fallow rule |
| Ephemeral Ward | No | Platform; built by Charters | 16 cells in 2029 (this document) | Free to builders | Moderate | Erased by design |
| Event instance | Yes | Event owner | ~100 avatars | Free; Event Mode at cost | Host place's | Ends with event |
| Landing hall | Yes | Platform | ≤20 newcomers + Host | Free | General | n/a |
| Campus | Separate realm | Institution | Class Cells | US$34.50 | General, hard | Lapse rule |

### Capacity envelope (spine D.5)

- **Cells** simulate 150 avatars with voice; Jolt runs at 30 Hz.
- **Places** hold 1,000 presence, updated at 10 Hz within 30 m and 5 Hz beyond.
- **Event Mode** goes up to 5,000 per place: validated at 2,000 by September 2029, at 5,000 by L+23.
- **Event instances** hold about 100 each.

A Domain therefore simulates up to 600 avatars. In a 1,000-person crowd on a Domain, the remaining 400 are presence-only: pose, look, chat and voice.

---

## Hearths

A Hearth is a home that costs a document, not a server. It is a private instance with no map position and no neighbours. It loads into a shared Hearth-host process only while someone is inside, so every account can keep one for life without adding an empty plot to any map.

- **Free Hearth.** 1 room, 8 guests and 1,000 Weight, plus 2,000 inventory items and 1 GB of storage. It is created and furnished in the Landing's first ten minutes, from the free kit library and the **Starter Catalogue**. Each equipped Starter item counts as a purchaser for its creator's Pool weight for 90 days (document 04).
- **Hearth+.** 4 rooms, 25 guests, 4,000 Weight and 20 GB, included in Resident (US$9.99 a month or US$99 a year).
- **Address and doors.** The address is `hearth://<username>/<room>`. Door policy is `invite` (the default), `friends`, `charter:<id>` or `open`. Hearths never appear in discovery.
- **Sky and rating.** The owner sets the sky, time and weather (spine B.4, item 11). The rating is General or Moderate. Adult is allowed only if the owner, and every guest the door admits, has passed the Night Ward check.
- **Lapse.** A free Hearth never lapses. When Resident lapses, rooms 2-4 enter the lapse rule. Room 1 keeps 1,000 Weight of objects, chosen by the owner; by default, the most recently edited.

**Rejected.** A map-placed homes continent in the style of Linden Homes. Linden-owned land grew on Bellisseria homes from 2019 to 2024 and shrank in 2025 as first-generation home continents were retired ([source](https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/)). Placed homes mean empty streets whenever their owners are offline. Also rejected: the sociologist's paid Hearth tier and its 150,000-payer plan, because that payer share is not credible (spine B.3).

---

## Holdings, Halls and Reaches

### The price list (spine D.3)

| Holding | Area | Scene Weight | Storage | Per month | US$ per 1,000 Weight |
|---|---|---|---|---|---|
| Commons plot | 2,048 m² | 900 | Holder's own | US$8 | 8.89 |
| Plot S | ¼ cell (16,384 m²) | 4,000 | 4 GB | US$19 | 4.75 |
| Plot M | ½ cell (32,768 m²) | 10,000 | 10 GB | US$35 | 3.50 |
| Cell | 256 m × 256 m | 30,000 | 30 GB | US$69 | 2.30 |
| Domain | 4 contiguous cells | 120,000 | 120 GB (this document) | US$249 | 2.08 |

- Extra storage is US$1 per 10 GB-month.
- Non-profit and education rates are 50% off, so a Class Cell is US$34.50.
- There is no setup fee.
- A rise needs 12 months' notice and grandfathers existing holders.
- The price per unit of Weight falls with size on purpose. Small plots carry more fixed operations cost per unit of Weight, and the Commons premium pays for the lottery and the public fabric.

**Scene Weight** replaces Land Impact. The Foundry computes it per object across tiers (document 05). An SL full region carries 22,500 Land Impact and 100 avatars ([source](https://wiki.secondlife.com/wiki/Land)) and costs US$199 a month plus US$349 setup from 15 June 2026 ([source](https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/)). A nolife Cell costs 35% of that monthly price, with no setup fee. Kitely's 2015 tiers were US$14.95-39.95 ([source](https://www.kitely.com/virtual-world-news/2015/06/01/60-off-large-worlds-and-dedicated-memory-guarantee/)). nolife sits between the two because rent carries the platform (spine B.4, item 3).

### Cost basis and hibernation

The Fee Page prints the Cell's cost basis as US$14:

| Line | US$ | Basis |
|---|---|---|
| Compute | 10 | ~70 awake hours a month on 2 vCPU |
| Storage and escrow | 2 | |
| Operations | 2 | |

Hosting has converged at US$0.055-0.07 per vCPU-hour ([source](https://aws.amazon.com/gamelift/servers/pricing/); [source](https://edgegap.com/blog/announcement-offering-changes-for-2025)), so 70 × 2 × 0.069 ≈ US$9.66.

**Hibernation** keeps that figure true. A Cell sleeps after 10 minutes empty and wakes within 8 s at p95. This is Kitely's suspend-and-reload pattern ([source](https://www.hypergridbusiness.com/2015/06/kitely-cuts-prices-60-for-large-regions)).

A Cell awake all month (730 h) would cost about US$100 in compute, more than its rent. That cost is never passed to the owner, because traffic is free. The compute of occupied cells sits in the platform's US$0.025 per CCU-hour infrastructure line and is funded by all revenue. In short: rent pays for keeping a place, and the platform pays for the people in it.

While a Cell sleeps (this document; the protocol is in document 06):
- objects stay in the Entity Store;
- scripts are suspended, and on wake they receive `on_wake(elapsed_s)` with timers coalesced;
- vendors keep selling, settling in the Ledger and delivering from Vault without waking the Cell;
- Keepalive objects run in the Keepalive service;
- inbound HTTP or a teleport arrival wakes the Cell, and the client shows cached terrain and impostors during the wake.

### Islands and Reaches

**An island** is a standalone Cell or Domain, reached by teleport or by a Reach harbour link. It may carry any rating, and it is the only place Estate tools are available. This is SL's private-region pattern. SL's serious communities live on estates because mainland lacks estate-owner controls ([source](https://community.secondlife.com/forums/topic/472286-difference-between-mainland-region-and-private-region/)).

**A Reach** is contiguous mainland with platform-built roads and water. It hosts Plot S, Plot M, Cell and Domain (2 × 2) parcels; Plots S and M exist only on Reaches. Reach Holdings get parcel access and ban lists, but no whole-cell whitelist, seat cap or damage. The rating ceiling is Moderate. It serves residents who want neighbours, roads and vehicles.

**Growth rule (spine D.6).**
- There are two Reaches at L.
- A Reach opens a new **64-cell block** (8 × 8 cells, 2,048 m a side) only once it is **at least 80% rented**, measured daily.
- In this document, a block reserves 8 cells for roads, water and an arrival point, and offers 56 rentable cell-equivalents. The 80% test is measured over those.
- New blocks attach at the frontier, next to the fullest block, and each opening gets a Chronicle entry.
- A Reach never shrinks. A lapsed parcel is packed into a NAR, cleared to terrain and relisted, never left standing as an abandoned build.

### Halls

A Charter flags one Holding as its **Hall**. Any size qualifies. The Hall appears on the Charter profile, the Call Board and in the Chronicle.

- **Charter Import** (document 10) creates the Hall in the same transaction as roles, members, ban list, rating and calendar, then restores the community's NAR or OAR into it.
- **Deputy and succession.** A land-owning Charter must name a deputy and a succession rule.
- **Rent.** It can be paid from the treasury. Lapse notices go to the owner and the deputy together, and the succession rule decides who may cure a lapse.
- **Founding Charter terms.** A first Cell, or a Domain above 500 members, is rent-free until L+6. After that it is 30% off list and frozen for 36 months: US$48.30 for a Cell, US$174.30 for a Domain. In return the Charter runs a weekly public event and names deputies.

### Sub-letting and disclosure

Sub-letting is allowed and uncapped (spine B.4, item 16). SL's first fortune was land arbitrage hidden behind opaque tier ([source](https://en.wikipedia.org/wiki/Anshe_Chung)). nolife does not ban the margin. Every sub-let listing prints the platform base rent beside the landlord's fee, so the margin is visibly a service margin.

```
SubletListing {
  holding_id, landlord: PassportId | CharterId,
  subparcel: { area_m2, weight_allowance, storage_gb },
  base_rent_usd    = list_price(holding) * weight_allowance / holding.weight   // Ledger-computed, read-only
  landlord_fee_usd = monthly_price - base_rent_usd
  services: [string]          // required if landlord_fee_usd > 0
  term_days, notice_days >= 30
}
```

Example: 3,000 Weight of a US$69 Cell let for US$15 reads **"Platform base US$6.90 · Landlord service US$8.10"**. The base is always shown at list price, even when the landlord pays a Founding or non-profit rate.

**Tenant protection (this document).** If the landlord lapses, each tenant's objects go to that tenant's own inventory, and tenants are notified when the Holding enters Frozen.

**Rejected.** A cap or ban on markups (ai-world-designer, open-web-architect). It would end the estate-manager livelihood, and disclosure fixes the information problem a cap was meant to fix.

---

## Estates

An Estate is an island Cell or Domain with **Estate tools** switched on. It is where roleplay, combat and care communities hold their own space. It copies FiveM roleplay: whitelists, seat caps and paid queue priority, with a Steam peak of 221,062 in May 2026 ([source](https://steamcharts.com/app/2676230)). It also copies Rockstar's rules: cosmetics and priority may be sold, pay-to-win and loot boxes may not ([source](https://www.gameserverkings.com/knowledge-base/fivem/server-monetisation/)).

```
EstateProfile {
  holding_id, charter_id, rating,                      // = Charter's fixed rating
  access: { mode: whitelist | application | open, application_form, ban_list_ref },
  seat_cap,                                            // <= 150 per cell (Cell 150, Domain 600)
  ranks: map<CharterRole, EstateRank>,
  queue: { tiers: [{ name, price_coin_month, order }], rules_url, change_notice_days: 30 },
  damage_parcels: [parcel_id],                         // damage is zero elsewhere
  meters: { stats: [{ name, min, max, regen_per_s }], authority: "cell" },
  keepers_enabled: false                               // Keepers 0% unless the Charter enables them
}
```

- **Queue.** Arrivals at the seat cap queue first-in, first-out within each published tier. Changes to tiers need 30 days' notice to ticket holders (this document). The platform takes 10% of tickets and priority.
- **Meter API.** Stats are held by the Cell, not a vendor's HUD server, so a meter never dies with its vendor.
- **No pay-to-win, enforced in code.** An item with the `meter.write` or `damage` capability cannot carry a Coin price in an Estate with damage parcels. The Ledger rejects the listing.
- **Rank.** Priority buys a seat, never discovery rank.
- **Target.** At least 50 whitelisted Estates with weekly events by L+12 (R17).

**Rejected.** Estates on Reaches. A whole-cell whitelist would cut roads and wall off neighbours.

---

## Wards and the Commons

A Ward is a public, language-tagged district of exactly four cells. The Civic Calendar happens there, and so does a newcomer's first crowd.

| Cell | Contents | Calendar role (Ward-local time) |
|---|---|---|
| Commons A, B | 64 lottery plots (32 per cell, a 4 × 8 grid of 64 m × 32 m) | Holders' own events |
| Stage | 168 bookable hours a week, 40 prime | Friday Open Stage; Charter slots |
| Market and Green | Market half: weekly stalls (48, this document); Green half: council ring, Call Board kiosk, Warden post | Saturday Market Day (0% on in-person sales); Sunday Assembly Day |

- **Quiet Day.** Wednesday has no first-party events, so Charters own it.
- **Hub cells.** The Stage and the Market and Green cell.
- **Posts.** Each Ward has 8 Warden and 12 Host Posts, paid from the Pool's 10% line.
- **Look.** The Ward owns its sky, time and weather.
- **Council.** From L+6 an elected five-seat Ward council writes ordinances, including any building code. The platform never writes one.

### Stage time

**Prime hours (this document).** The 40 prime hours are:
- 18:00-23:00 on Monday-Thursday, Saturday and Sunday (30 h);
- 13:00-18:00 on Saturday and Sunday (10 h).

Friday 18:00-23:00 is Open Stage, run as its own weekly lottery weighted by audience retention.

**The quarterly prime-hour lottery:**
- Only Charters may enter.
- A Charter can win at most 2 weekly prime hours per Ward per quarter, which guarantees at least 20 prime-time hosts.
- A Charter's weight is `1 + min(2, R/50)`, where R is the number of distinct returning humans at its events last quarter.

The other 128 hours are first-come, booked up to 14 days ahead, with at most 4 hours a week per Charter.

### Ward lifecycle

```
[Proposed] ── petition: ≥3 Charters of ≥50 members; language tag, IANA time zone, rating ──▶ [Pledging]
[Pledging] ── pledged attached MAU ≥ 2,000 ──▶ [Open]
[Open]     ── attached < 500 ──▶ [At risk]  (day counter published in Census) ── back ≥ 500 ──▶ [Open]
[At risk]  ── 90 consecutive days < 500 ──▶ [Fallow] ── re-petition (former plot holders weight 2) ──▶ [Pledging]
```

- **Attached MAU** counts residents whose home Ward is W and who were Census-active in the last 30 days (entered, moved and interacted with another human for at least five minutes).
- **Home Ward and pledges.** Each resident has exactly one home Ward and can change it every 30 days. They may also hold one **pledge** to an unopened Ward, which becomes their home Ward when it opens (this document).
- **Founding Wards.** Six open at L: English ×3 by time zone, Portuguese, Spanish and an English Night Ward. Founding Charter members count as attached.
- **Anchor time zones (this document):**
  - English-East: America/New_York
  - English-West: America/Los_Angeles
  - English-Europe: Europe/London
  - Portuguese: America/Sao_Paulo
  - Spanish: America/Bogota
  - Night Ward: America/New_York
- **Later Wards.** Japanese and German Wards follow at L+12.
- **Fallow** affects only Commons plots:
  - Holders are refunded their unused prepaid rent in full, and their contents go to a NAR in inventory.
  - The hub cells are archived.
  - The council's term ends with a Chronicle entry.
  - Residents move to the same-language Ward in the nearest time zone unless they choose another.
  - No Holding, Hearth or Estate is touched.

**Planning arithmetic (this document).** At 100K MAU (L+12) the ceiling is 50 Wards. If about 60% of MAU set a home Ward and Wards settle at 3,000-5,000 attached, expect 12-20 Wards and 768-1,280 Commons plots.

### The Commons lottery

The model is FFXIV's housing:
- the full plot price as the ticket;
- auto-demolition after 45 days, with warnings from day 30;
- an 80% refund;
- the timer suspended during the pandemic and the Ukraine war ([source](https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1); [source](https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily)).

Scarcity made those plots status objects and grew a venue scene nobody planned.

| Spine rule | Value |
|---|---|
| Plot | 2,048 m², 900 Weight, US$8 a month |
| Ticket | US$24 (3 months prepaid); losers refunded in full within 24 h |
| 45-day rule | Unused 45 days → back to the lottery; objects to inventory; 80% of unused prepaid rent refunded |
| Pause policy | Published (below) |
| Target | ≥70% occupancy at peak |

Mechanics (this document):

- **Cadence.** Each Ward draws monthly for vacant plots, with 5 days of entry and the draw on day 6. The random seed is committed to the Chronicle before entry and revealed at the draw. Win rates are published.
- **Eligibility.** One entry per Passport per draw, and at most one Commons plot per Passport world-wide. A Charter may enter as a Charter, up to two plots world-wide.
- **Weight.** Residents of the drawing Ward count ×2. Standing never weights the Commons, so newcomers keep a real chance.
- **"Used."** The holder or a named co-holder was on the plot for at least 10 minutes that day, or the plot hosted a listed event with at least 5 human attendees. Logging in is not enough.
- **Warnings** at days 30, 38 and 44.
- **Pause policy:**
  1. During declared platform incidents over 4 h, every timer stops and is extended by the incident's length plus a day.
  2. During declared regional emergencies, timers stop for the affected Wards.
  3. Each holder gets one personal pause of up to 45 days in any 12 months, with no evidence required.
- **Payment failure** on a plot follows the lapse rule. The 80% refund applies only to the 45-day return.

### Rejected alternatives

- **Closing a Ward after 30 quiet days** (economist), or letting it **"go to seed" after 14** (ai-world-designer).
- **Folding districts back into wilderness** (open-web) and **Wilds that decay at 30 days** (engine).

All of these evict quiet residents, and none has a precedent. The spine keeps 90 days below 500 and touches only Commons plots.

- **An Archipelago with no mainland** (ai-world-designer). It would drop SL's road-and-neighbour culture. The Reach's 80% rule keeps a mainland without the emptiness.

---

## Night Wards and ratings

### The rating model

- There are three ratings: General, Moderate and Adult.
- A Charter's rating is fixed when the Charter is created, as in SL groups ([source](https://wiki.secondlife.com/wiki/Group)).
- An individual's Holding may change rating once per 30 days, and each change is logged.
- Content never exceeds the ceiling of the place where it is displayed.
- Event instances inherit their host's rating.

| Place | General | Moderate | Adult |
|---|---|---|---|
| Landing halls, Campus | ✔ | — | — |
| Hearth / Hearth+ | ✔ | ✔ | Owner and every admitted guest Night-checked |
| Ward cells and Commons plots | ✔ | ✔ | — |
| Night Ward cells and plots | ✔ | ✔ | ✔ |
| Reach Holdings | ✔ | ✔ | — |
| Island Cell or Domain, Estates | ✔ | ✔ | ✔ (Night-checked owner and visitors; Night directory only) |
| Homestead Kit cells (L+12) | ✔ | ✔ | — |
| Ephemeral Ward | ✔ | ✔ | See Open questions |

### Night Wards

A **Night Ward** is an Adult-rated Ward with the standard layout. The English Night Ward is a Founding Ward, and an Adult ward exists from private alpha. Adult communities are never retrofitted, which is how SL ended up with Zindra in 2009: about 850 forced move tickets, and promoted Adult content confined by a deadline ([source](https://wiki.secondlife.com/wiki/Zindra)). In November 2009, 5.69% of SL's 29,409 regions were Adult-flagged ([source](https://wiki.secondlife.com/wiki/Adult_content)). That is the planning anchor for Adult capacity.

- **The gate.** The **Night Ward check** is the Age Module's strictest profile for the resident's region. In the UK that is Ofcom's "highly effective" standard, in force from 25 July 2025 ([source](https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/)). No ID image is stored. SL still relies on a self-declared birthday ([source](https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/)).
- **Commerce.** The same check unlocks Adult-tagged commerce. Adult goods need uploader verification, consent records and human pre-publication review, which are the controls Mastercard's AN 5196 expects ([source](https://verifymy.io/resources/regulation/card-brand-requirements)). Spend is maturity-tagged from day one, and the adult share is published.
- **Deindex-but-sell.** This switch drops Adult listings from discovery within hours while owned items keep working and direct sales continue. It is the model that kept itch.io creators paid in July 2025 ([source](https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/)).
- **Visibility.** Night Wards, Adult islands and Adult Estates appear only in the Night directory, and only to residents who have passed the check. Nothing Adult renders outside an Adult-rated place.

---

## The Ephemeral Ward and event instances

### The Ephemeral Ward

This is the one annual scarce ritual: a Ward that exists for a single week. Its precedents are:
- BURN2, which has burned its Man in SL since 2003 ([source](https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/));
- Habbo's rares, never reissued ([source](https://www.habbo.com/community/article/22292/update-state-habbo-economy));
- SL20B, whose 60 regions and 425+ performers show what a resident-built festival can reach ([source](https://lindenlab.com/press-release/original-metaverse-second-life-celebrates-20th-birthday)).

| Phase (first edition, L+11) | Dates | What happens |
|---|---|---|
| Call for builders | June 2029 | Charters apply; plots by lottery if oversubscribed |
| Event Mode rehearsal | By August 2029 | Validated at 2,000 presence |
| Build month | 1-31 August 2029 | Plot-holding Charters build; closed to the public |
| The week | Mon 10 - Sun 16 September 2029 (second full week) | Public instances; relics minted |
| Erasure | Sunday 16 September, closing | Erased on camera; Darkroom renders and Chronicle remain |

- **Size (this document).** 16 cells in 2029, growing toward 64 as Event Mode reaches 5,000.
- **Relics.** Never reissued, with a 0% resale fee and no resale royalty. Document 03 owns the relic rules.
- **What erasure removes.** The place is erased; nobody's property is. Builders' creations return to their own inventories under the persistence covenant. The layout, the place and the minting close forever, and the platform keeps no restorable NAR of the Ward itself.
- **Cost.** The Ward is a Civic Calendar event, so Event Mode is free.

### Event instances and Event Mode

The largest crowds never share one simulation. Fortnite reached audiences in the tens of millions in instances of about 100 ([source](https://musicbusinessworldwide.com/fortnites-remix-the-finale-concert-draws-over-14m-players-breaking-records)).

| Situation | Mechanism | Limit |
|---|---|---|
| Ordinary place | Cells under one Presence layer | 150 per cell; 1,000 per place |
| Full, no reservation | Overflow into **synchronised instances** with cross-instance chat and a shared performer feed | ~100 each |
| Declared crowd | **Event Mode**: impostors, pre-mixed audio | 5,000 per place |

- **Placement.** Cohorts, Charter members and friends stay together first, then language.
- **Split and merge (this document).** A new instance opens when one reaches 100. Two instances merge when both have held below 40 for 3 minutes and together hold no more than 80.
- **Price.** US$0.004 per reserved avatar-hour above 1,000 presence, waived for Civic Calendar events. Worked example: 3,000 presence for a 3-hour concert costs (3,000 − 1,000) × 3 × 0.004 = **US$24**. Below 1,000 presence it is free. This is the only metered activity, and it is charged at cost (spine B.4, item 3).

---

## Landing halls and Campus

### Landing halls

Every new account arrives in a **Landing hall** in its language: English, Portuguese and Spanish at L, with Japanese and German at L+12. A Landing hall is an instanced, General-rated room for one cohort. Document 03 owns the social script; the place rules are these:

- **Cadence.** A cohort starts every 15 minutes per launch language, 16:00-24:00 in the language's Founding Ward time zone. That is 32 cohorts a day per anchor.
- **Size.** Target 12, range 6-20 (this document for the handling):
  - fewer than 6 at start: held up to 15 minutes and merged into the next cohort;
  - more than 20: a parallel hall opens with a second Host.
- **Outside hours, and for the 10% holdout** (6 months): the self-guided Landing. From L+12 a Keeper Greeter may hold a hall until a human Host arrives, then hands over.
- **Two exits.** One leads to the newcomer's Hearth, furnished within ten minutes. The other is the **gate**, through which the Host walks the cohort to an event starting within 30 minutes.

### Campus

**Campus** is a separate realm and the only place for ages 13-17. Its rules:
- entry by institutional SSO, with bulk accounts, from L+6;
- General-rated, with no exceptions;
- no economy and no cash-out;
- scripted-only Keepers;
- no teleport, chat, friending or inventory transfer to or from the open world.

Adults enter only on staff accounts provisioned by their institution. Institutions rent **Class Cells** at US$34.50, with NAR export and the persistence covenant (R28).

SL's educators left when the 2010 discount removal doubled their costs. They went to grids with lower prices, more control and OAR backups ([source](https://hypergridbusiness.com/?p=35085)). Adult learners in the open world use ordinary Holdings at the 50% education rate. Target: at least 20 Campus institutions by L+18.

---

## Density, discovery and the empty-world rule

### The empty-world rule

1. **Public land opens only with population.** Wards need 2,000 attached MAU, and Reaches grow only at 80% rented.
2. **No newcomer is sent to an empty place.** They arrive in hosted cohorts and are routed to live events.
3. **Nothing is listed as live without humans.** Keepers and bots are counted separately.
4. **Private places may be empty.** Holdings, Hearths and Estates are never merged, closed, charged or ranked down for being quiet. Studio-exec's density manager drew the same line: estates are exempt.

### The density SLO

The SLO is **one avatar per 0.1 ha in Ward hub cells at weekly peak (~130).** The arithmetic:
- two hub cells cover 2 × 6.5536 ha = 13.1 ha;
- 13.1 ha ÷ 0.1 ha = 131 avatars;
- that is about 65 per cell, well inside the 150-avatar Cell SLO;
- it is roughly 40 times SL's grid-wide average.

```
D(W, week) = mean over the Ward's busiest local hour of humans in hub cells, sampled every 60 s
             (excluding Keepers, flagged bots, Nuisance-flagged accounts)
SLO_met(W) = D >= 131 in at least 3 of the last 4 weeks
V(session) = distinct humans within 64 m of the newcomer for >= 60 s cumulative
target     : median V over a week's first sessions >= 10, per Landing language
```

The 0.1 ha figure is a design target, not a measured constant. R12's test re-sets it with Census data at L+6.

### Routing and merging

```
route_cohort(cohort):
  E = events live or starting within 30 min, language in cohort.languages, rating <= Moderate,
      excluding first-party events on Quiet Day
  p10[e] = P(humans_present(e) >= 10)            # from the series' last 3 occurrences
  pick argmax p10; tie-break home-Ward match, then Call Board Charter, then distance
  if max p10 < 0.5: busiest same-language Ward hub cell
  if that hub has < 10 humans: a synchronised instance of the nearest live Open Stage or Market
```

**Twinning (this document).** A Ward that misses its SLO for 4 consecutive weeks is twinned with a same-language Ward. Their prime-hour Stage events are cross-listed and run as synchronised instances across both Stages. This merges the crowds without moving anyone's plot. The twin ends after 4 weeks at or above the SLO.

### Discovery

Discovery is calendar-first. Views come in this order:
1. **Now and Next:** events in the next two hours, in my languages and ratings, near my Charters.
2. The **Call Board**.
3. The **directory**.
4. The map.

Directory cards show live human occupancy, bot share and Keeper share, language, rating, the next three events and returning humans over 28 days (the open-web graft).

**Ranking is by returning humans, never by payment:**

```
H28(P) = Σ w(h) over distinct Passports h with ≥ 2 visit-days (≥ 5 min each) at P in the last 28 days
w(h)   = 1.0 verified 18+ at Trust New or above; 0.5 unverified (mirrors the Pool);
         0 for Keepers, flagged bots, Nuisance flags, the place's owner and Charter officers
rank(place) = H28(P)                       # filters by language, rating, Charter; never boosted
rank(event) = median humans at its last 3 occurrences (new series: 0.1 × host Charter's H28)
```

None of these affects rank: Holding size, Founding status, Estate priority, Pool earnings or any payment. A place with H28 below 5 can be found by name but is not listed by default.

**Rejected.** Studio-exec's sponsored row and the economist's new-creator shelf. Even a small paid slot breaks "rank by returning humans."

**Keepers** (L+12) count in no SLO, metric or ranking, and their share of occupants is published beside the bot share. A Ward council may vote its Ward quiet.

---

## Persistence and lapse handling

### Guarantees

- **Write budget.** 60 + 10 × avatars writes per minute per Cell, the Roblox DataStore pattern ([source](https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits)). It is split per owner, so one Holding's runaway script cannot starve a neighbour.
- **Snapshots and rollback.** Snapshots are hourly, and owners can roll back 30 days. Another resident's objects removed by a rollback return to that resident's inventory.
- **Escrow.** Nightly, to a second hosting provider.
- **Inventory loss.** At most 1 per 10 million operations, published monthly.
- **Export.** NAR export of any Holding or Hearth at any time. NAR is a strict superset of OAR/IAR and restores by hash from Vault.
- **Price covenant.** 12 months' notice plus grandfathering. This answers SL's 2008 Openspace rise from US$75 to US$125, imposed without grandfathering ([source](https://forums-archive.secondlife.com/356/24/291220/1.html)).
- **Nothing is deleted for non-payment.** OSgrid gave users "five weeks to save your stuff" before its 2025 wipe ([source](https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff)), and Spatial deleted creator worlds on 27 July 2026 ([source](https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/)).

### The lapse state machine (Holdings, Hearth+ rooms, Commons plots on payment failure)

```
[Active] ─payment fails─▶ [Due]: 7-day retry; owner and deputy notified            (this document)
[Due]    ─cured─▶ [Active]          ─not cured─▶ [Frozen]
[Frozen] 90 days: scripts stopped, no edits, owner/officers only, delisted, no rent accrues, tenants notified
[Frozen] ─one month's rent─▶ [Active] in place      ─day 90─▶ [Archived]
[Archived]: NAR to owner's inventory (tenants' objects to tenants); parcel cleared and relisted or island released
[Archived] ─any time, indefinitely─▶ [Restored] into any Holding with enough Weight
```

- **Archived NARs** do not count against inventory quota, cannot be rezzed until restored, and are kept indefinitely.
- **Charters.** For a Charter's Holding, the deputy and the succession heir can cure at every stage. A Hall that reaches Archived gets a Chronicle entry.
- **Sunset.** If the 12-month shutdown notice ever fires, escrowed source is released under Apache-2.0 and every resident exports NARs (document 08).

---

## Requirements addressed

| Req. | How |
|---|---|
| R1 | Places sized to 150 per Cell, 1,000 per place, Event Mode to 5,000; ~100-avatar synchronised instances |
| R6 | Rent from day one for Holdings, Hearth+ and storage; printed Cell cost basis; traffic free; Event Mode the only meter, at cost |
| R8 | Rank and the venue line reward returning humans; directory makes creator-run places visible |
| R11 | Landing halls per language, a cohort every 15 minutes, 10% holdout, routing to an event within 30 minutes |
| R12 | Hub-cell SLO ~130, median ≥10, instance split/merge, twinning, fallow, routing, re-set at L+6 |
| R13 | Live humans, bot and Keeper shares on every card; SLO and Ward counters in the Census |
| R15 | Stage prime-hour lottery, Ephemeral Ward, synchronised instances, Ward Host and Warden Posts |
| R16 | US$24 refundable ticket, 45-day rule, 80% refund, published pause policy, ≥70% occupancy; no demolition |
| R17 | Estate tools, pay-to-win blocked in the Ledger, ≥50 Estates by L+12 |
| R18 | Charter Import lands a Hall in one transaction; Founding rent terms |
| R19 | 12 months' notice and grandfathering; Ward councils write ordinances; Chronicle entries |
| R20 | NAR export any time, nightly escrow to a second provider, sunset release |
| R21 | Campus only for 13-17s; Night Ward check at the strictest regional profile, no stored IDs |
| R22 | Night Ward from private alpha; Adult commerce controls; deindex-but-sell; adult share published |
| R25 | Keepers outside every SLO and rank; 0% in Estates unless enabled; quiet Wards |
| R26 | Free Hearth furnished within ten minutes |
| R28 | Class Cell US$34.50, SSO at L+6, NAR export, persistence covenant |
| R29 | Language-tagged Wards and Landing halls (PT/ES at L, JA/DE at L+12) with anchor time zones |

---

## Open questions

1. **Commons geometry.** 64 × 2,048 m² = 131,072 m², exactly the two Commons cells, which leaves no public lanes. The spine's values are kept. This document proposes a 4 m frontage easement inside each plot; the alternative is to treat 2,048 m² as gross area.
2. **Always-awake Cells.** A Cell awake all month costs about US$100 in compute against US$69 in rent. The cross-subsidy is intended, but the distribution of awake hours is unmeasured. Alpha must publish it before the US$10 compute line is confirmed.
3. **Archived-NAR storage.** Keeping archived NARs indefinitely and outside quota is not in D.8's model.
4. **Domain storage.** The spine gives none. This document assumes 120 GB.
5. **Adult land beyond islands.** Is a Night Reach, or an Adult quarter of the Ephemeral Ward, needed by L+12?
6. **Anchor time zones.** Bogota or Madrid for the Spanish Ward. Is an English Asia-Pacific Ward needed before L+12?
7. **Fallow and Founding Wards.** Should Founding Wards be exempt from fallow until the L+12 Tripwire review? This document applies the rule from L.
8. **The Founding freeze.** This document reads the 36-month freeze as running L+6 to L+42 (April 2032). Document 09 should confirm.
9. **Ephemeral Ward size.** The 16 cells depend on the 2,000-presence Event Mode validation.

---

## Sources

- https://danielvoyager.wordpress.com/2025/08/11/second-life-statistics-august-2025-update/
- https://community.secondlife.com/forums/topic/526582-so-beautiful-so-empty/
- https://www.cnbc.com/2022/10/15/meta-horizon-worlds-metaverse-losing-users-falling-short-of-goals.html
- https://danielvoyager.wordpress.com/2025/11/04/second-life-region-statistics-early-november-2025-update/
- https://wiki.secondlife.com/wiki/Land
- https://modemworld.me/2026/06/08/ll-announces-second-life-fee-changes-reductions-increases/
- https://www.kitely.com/virtual-world-news/2015/06/01/60-off-large-worlds-and-dedicated-memory-guarantee/
- https://aws.amazon.com/gamelift/servers/pricing/
- https://edgegap.com/blog/announcement-offering-changes-for-2025
- https://www.hypergridbusiness.com/2015/06/kitely-cuts-prices-60-for-large-regions
- https://community.secondlife.com/forums/topic/472286-difference-between-mainland-region-and-private-region/
- https://en.wikipedia.org/wiki/Anshe_Chung
- https://steamcharts.com/app/2676230
- https://www.gameserverkings.com/knowledge-base/fivem/server-monetisation/
- https://www.inverse.com/gaming/final-fantasy-14-housing-updates-lottery-empyreum-patch-6-1
- https://techraptor.net/gaming/news/ffxiv-house-demolition-suspension-reinstated-temporarily
- https://wiki.secondlife.com/wiki/Group
- https://wiki.secondlife.com/wiki/Zindra
- https://wiki.secondlife.com/wiki/Adult_content
- https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/
- https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/
- https://verifymy.io/resources/regulation/card-brand-requirements
- https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/
- https://ryanschultz.com/2021/10/09/burn2-celebrate-burning-man-in-second-life-october-8th-to-17th-2021/
- https://www.habbo.com/community/article/22292/update-state-habbo-economy
- https://lindenlab.com/press-release/original-metaverse-second-life-celebrates-20th-birthday
- https://musicbusinessworldwide.com/fortnites-remix-the-finale-concert-draws-over-14m-players-breaking-records
- https://hypergridbusiness.com/?p=35085
- https://create.roblox.com/docs/cloud-services/data-stores/error-codes-and-limits
- https://forums-archive.secondlife.com/356/24/291220/1.html
- https://www.hypergridbusiness.com/2025/02/osgrid-wiping-its-database-on-march-21-you-have-five-weeks-to-save-your-stuff
- https://www.uploadvr.com/spatial-is-discontinuing-its-creator-platform-in-july/
