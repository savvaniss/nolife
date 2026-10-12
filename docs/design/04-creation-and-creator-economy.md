# 04 · Creation and creator economy

Design document 04, written 2026-10-09 against the spine (C.3, C.4, B.4, D.3, D.5) and the failure taxonomy (R1-R30). Owners: Foundry, Workshop and tools (7 at L) with Ledger, payments and compliance (4). No web search was used. Values marked *(spine)* are canonical. Values marked *(this doc)* are planning detail for the March 2027 drafts. Docs 05, 06, 08 and 09 own the renderer, the Grid, safety and the P&L.

## Summary

Creators are nolife's supply side, and most come from Second Life. SL paid them about US$78M a year, but behind its "90/10" marketing the all-in take was 20-31%. This document specifies the creator's whole path:
- **Workshop**, a creator interface kept separate from the consumer one;
- the **Foundry**, which checks every upload at US$0.01 per asset;
- Luau under per-owner budgets, with LSL running unchanged;
- licences that carry an Export bit and signed provenance;
- **Coin**, shown fiat first, with one Fee Page whose worked example is 12.5% all-in;
- the open-protocol **Bazaar**;
- **Splits** of up to 10 contributors and **Component Royalties** of up to 10%;
- the Maker, Merchant and Studio ladder, ending in cash-out on a licensed rail;
- the **Commons Pool** (25% of net revenue, split 70/20/10);
- **Keepalive** and **Lineage** for breedables, with no chance mechanic that pays cash;
- fingerprinting that catches CopyBot replays at upload.

## Two interfaces

R26 requires a consumer interface separate from the creator interface. In 2014 Linden's CEO named "the not very intuitive viewer interface" as the second-login blocker ([source](https://modemworld.me/2014/06/29/ebbe-altberg-on-user-retention-now-and-in-the-future/)). nolife ships two interfaces over one world and one inventory.

| | Consumer interface | **Workshop** |
|---|---|---|
| Does | Dress, furnish (**Arrange**: place owned items within Weight), attend, buy, tip, resell, claim Re-delivery | Build, script, import, publish, list, Splits, royalties, Pool forecast, payouts, tax forms |
| Scripts | Never visible; only object UIs and consent prompts | Luau editor, LSL upload, profiler |
| Clients at L | Lantern, Ember, Reader | Building on Lantern (Windows, macOS). Ember has no building at L *(spine)*. The commerce pane works on all three |

Rules *(this doc)*:
- The "Make" button is hidden in the first session. The Landing hands the newcomer a dressed **Common Body** and a furnished Hearth within ten minutes *(spine)*, from the kit library and the **Starter Catalogue**, and never opens Workshop.
- Building in one's own Hearth and Holdings needs Trust **New**; selling needs **Member** (doc 08).
- The commerce pane works fully in **Reader**, keyboard-only and with text-to-speech (R27). Mobile (L+9) gets Arrange and the commerce pane only.

Workshop's parts *(spine, C.3)* are **Blocks**, a PBR material and light editor with a live **Fidelity Rank** meter, a Luau editor, a free kit library, and import of glTF 2.0 and VRM 1.0 (runtime), OpenUSD (scenes) and MetaHuman output.

Generative assistants (text-to-mesh, texture synthesis, code completion) tag their output with provenance and never place content into the world on their own. Roblox Cube is the pattern: an asset generator, not world content ([source](https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube)).

## Blocks, import and the Foundry

### Blocks

**Blocks** are parametric building, compiled to meshes. In-world creation is first-class because maker cultures grew inside SL, Resonite and Dreams, while worlds that made Unity the real editor never grew an economy (alt-survivors brief). Rules *(this doc)*:
- **Shapes and parameters.** Box, cylinder, prism, sphere, torus, tube and ring, with SL's prim parameters: path cut, hollow, twist, taper, shear and skew. Ferry therefore rebuilds legacy prims exactly as Blocks.
- **Snapping and scale.** A 5 cm grid and 15° rotation, at 1 unit = 1 m.
- **Linksets.** Up to 256 Blocks; each linkset compiles to one mesh plus collision.
- **Compiling.** The client previews instantly. The Foundry compiles on commit, after 10 s without an edit, within doc 05's 90 s p95 prop latency.
- **Build rights.** These come from Holding ownership or a Charter role. Each Block keeps its author, so Workshop can propose a Split from the build log.
- **Rank.** The Foundry derives Block LODs analytically, so Blocks always rank Excellent or Good.

### Import and format policy (R3)

The import formats are:
- **glTF 2.0** (PBR metallic-roughness), the canonical runtime format;
- **VRM 1.0** for avatars; VRM 0.x is migrated on import ([source](https://vrm.dev/vrm1/));
- **OpenUSD** for scene interchange; AOUSD's 2026 Core Spec gives it a standards path ([source](https://www.linuxfoundation.org/press/aousd_prmarch2026));
- **MetaHuman** output, under the creator's own licence, now usable outside Unreal ([source](https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/));
- **Ferry formats** (NAR, Collada and llmesh, prims, sculpts, BVH, .anim), specified in doc 10.

The policy is canonical *(spine)*: the platform pays for conversion, and retiring a format needs a converter and 24 months' notice. SL never had such a policy. In July 2026 Linden was still asking creators what they wanted from glTF ([source](https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/)).

### The Foundry, from the creator's side

Every upload, import and Blocks commit passes through the Foundry *(spine)*, in this order:
1. normalise (1 unit = 1 m, PBR);
2. catalogue fingerprinting;
3. CSAM, likeness and script checks;
4. a four-level LOD chain and an octahedral impostor;
5. collision;
6. BC7/ASTC/ETC2/KTX2 transcoding;
7. Bakes-on-Mesh atlasing;
8. Lite and Compat bakes;
9. Scene Weight;
10. Fidelity Rank (Excellent, Good, Fair, Heavy);
11. a licensed Nanite cook, with LOD chains as the fallback.

Doc 05 specifies each stage. Workshop shows the states as follows *(this doc)*:

```
RECEIVED → NORMALISED → SCREENED ─┬→ BUILT → MEASURED → PUBLISHED
 (provisional preview, uploader   ├→ HELD        "In review: IP match" | "In review: Adult"
  only, until SCREENED)           ├→ QUARANTINED "Removed" (platform only, no detail)
                                  └→ REJECTED    reason code + fix hint, e.g. NON_MANIFOLD_LOD
```

At MEASURED, Workshop shows the tier previews side by side. It also shows the Scene Weight and the rank, with the axis that set the rank (for example, "Lite: 41,200 triangles, over the 35,000 budget"). Over-budget content is never hidden from its buyer; it shows its tier version *(spine)*.

**Cost.** The Foundry costs US$0.01 per asset *(spine)*, about US$10K a year per million assets. The engine-architect estimate is US$0.005-0.02 per asset at about US$0.07 per vCPU-hour ([source](https://edgegap.com/pricing)). Uploads carry **no fee** *(this doc)*: bytes are charged as rent and storage, and volume is bounded by Trust rank (10, 100 or 1,000 items a day, or bulk; doc 08).

## Luau, budgets and the LSL Runtime

### Per-owner budgets (R5)

Scripts run in a sandboxed Luau VM in each Cell. Luau is the language Roblox runs at scale and the base of Linden's SLua fork ([source](https://wiki.secondlife.com/wiki/Lua_Alpha)). Budgets are per owner, and doc 06 sets the defaults:

| Resource | Land scripts (per Holding) | Avatar attachments | Rule |
|---|---|---|---|
| CPU per tick | 18 ms per Cell, split by Scene Weight share (min 0.5 ms) | 0.05 ms × avatars present | Idle share can be borrowed |
| Memory | 64 MB per Cell-equivalent, pro rata; 64 KB per LSL-origin script | 2 MB per avatar | Hard limit |
| Network | 30 requests/min + 1 per 1,000 Weight | 5 requests/min per avatar | Token bucket |
| Durable writes | 60 + 10 × avatars per minute per Cell | Shared | Coalesce, queue, then error |

**Worst-offender throttle.** When demand exceeds the pool, the scheduler cuts back the owner with the highest usage-to-share ratio first. Owners within their share are never slowed. SL's rule was that scripts starve first. Workshop's profiler shows each owner, per script: p50 and p99 ms, memory, network tokens and throttle events. The R5 test is that script-caused overruns stay under 1% of cell-hours.

### Money in scripts *(this doc)*

```lua
nl.ledger.requestDebit(avatar, {max_per_tx=500, max_per_day=2000, expires="24h"}) -- consent prompt
nl.ledger.pay(grant, to_passport, amount_coin, memo)   -- tips, prizes, refunds
nl.bazaar.sell(listing_id, buyer)                      -- vendor sale; Fee Page applies
on_paid(buyer, amount_coin, listing_id)
nl.keepalive.get(obj, key) / nl.keepalive.set(obj, key, value)  -- value-bearing state
on_wake(elapsed_seconds)                               -- after hibernation (doc 06)
```

Rules:
- No script moves Coin without a consent record.
- Grants appear in the payer's Passport and can be revoked with one gesture. A grant above 2,000 Coin a day needs a fresh prompt.
- Any call with a Keeper as counterparty fails, because Keepers hold no Coin *(spine)*.

### The LSL Runtime

Residents upload LSL unchanged. Ferry compiles it transparently to Luau against an `ll` library, using OpenSimulator's BSD engine and its tests as the reference. Unsupported calls fail loudly *(spine, B.4 item 14)*. The target is that 90% of Founding Charter scripts run unmodified at L *(spine)*. Calls fall into four classes *(this doc)*:

| Class | Examples | Behaviour |
|---|---|---|
| Native | Events, states, timers, link messages, chat, sensors, prim params, HTTP | Compiled with the same semantics; `state` blocks become coroutine tables |
| Mapped | `llGiveMoney`, `llTransferLindenDollars`, `PERMISSION_DEBIT`, `money()` | Routed to `nl.ledger`, and disabled until the owner passes **Coin review** |
| Shimmed | Experience keys, agent data, region queries | Answered from Charter and Passport equivalents |
| Unsupported | SL-hosted services, Linden-only calls | A compile-time error with the line number, plus a runtime `NOT_SUPPORTED` event; never a silent no-op |

**Coin review.** LSL amounts are integers in L$, and L$ has traded at about 320 to the US dollar since 2023 ([source](https://exchangerate.guru/ld/usd/1/)), against 100 Coin = US$1.00 *(spine)*. Run blindly, a vendor priced at "250" would charge about three times its SL price. Workshop therefore lists every literal amount in an LSL-origin script with its L$ and fiat values and a proposed Coin price. The owner confirms each one before money calls are enabled.

## Ownership, licence, provenance and the Export bit

### The licence *(this doc)*

Creators own what they make. The content licence is one plain-language page:
- The platform may display, cache, transcode, back up and deliver content, only to run the service.
- Any other use, including marketing, sub-licensing and model training, needs a per-use affirmative opt-in.
- Any widening needs 12 months' notice, and the Assembly may demand public review.

This is written for people who remember August 2013, when a ToS change led Renderosity and CG Textures to ban their assets from SL until July 2014 ([source](https://www.hypergridbusiness.com/2013/09/outrage-grows-over-new-second-life-terms); [source](https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/)).

### Permissions and the Export bit

Licences carry SL's three bits and an **Export** bit:
- **Copy:** rez unlimited instances.
- **Modify:** edit the item, or use it in a derived work, with any Component Royalty attached.
- **Transfer:** give or resell at 0% platform fee.
- **Export:** take the item out of nolife as glTF, VRM or USD, inside its signed licence envelope.

Firestorm and OpenSim developers proposed the Export bit in 2012 so that creators could opt in to portability. SL never adopted it ([source](https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/)). In nolife:
- **Own-created content always exports** to its creator, minus any third-party parts that are not Export-flagged. This is Kokua's creator-only rule ([source](https://modemworld.me/2013/08/24/)).
- **Bought content exports only if the creator set Export.** Each listing shows the bit.
- **The server enforces it.** Clients receive only tier derivatives (doc 06). Full-resolution source leaves the Vault only through the export endpoint, which checks the bit and stamps the envelope. That is how "every client honours it" holds even against a modified client, and it is a certification condition for third-party clients at L+24.

### Provenance and likeness

Every asset carries a signed manifest in C2PA style *(spine)*. It records:
- the creator's Passport;
- the time;
- the pipeline version and Foundry hash;
- the permission bits and maturity tag;
- an `ai_assist` flag naming any assistant used.

The manifest doubles as the machine-readable mark that EU AI Act Article 50 requires from 2 August 2026 ([source](https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content)). Listings show "AI-assisted" whenever the flag is set. Licences are readable off-platform through Passport.

An asset depicting a real person needs a record in the likeness consent registry, or it is held at stage 3. If the person withdraws consent, the asset is delisted within 24 hours. Existing copies then render only for their owner, who is refunded from the seller's `earned` balance *(this doc)*.

## Coin and the Fee Page

### Coin (R9)

**Coin** is a display unit: 100 Coin = US$1.00, with local fiat shown first at a daily-fixed rate and no spread *(spine)*. Legally it is stored value held by the licensed partner. It is bought in exact amounts from US$1. There are no bundles, no second currency, and no chance mechanic paying anything cash-out-able. Coin moves between residents and leaves only through cash-out.

This follows the CPC Network's March 2025 Key Principles: fiat shown on every price, exact-amount purchase, one currency, and no gameplay-only carve-out for a stipend paid in a currency that is also sold ([source](https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr)). The 300 Coin Resident allowance is therefore shown in fiat. If the Digital Fairness Act restricts paid currencies, the display switches to fiat and the ledger is unchanged *(spine)*. Doc 09 specifies the wallet buckets, the spend order and the 14-day clearing hold on card-funded value.

### The Fee Page (R7)

The Fee Page is one versioned, signed page, published as HTML and as JSON for stores, auditors and the Census API. Its draft is due in March 2027 *(spine)*. Every line below is canonical *(spine, D.3)*:

| Line | Rate |
|---|---|
| Buying Coin on web or PC | 0%. The platform absorbs about 3% processing |
| App-store top-ups | Store fee shown as a separate line. Store-routed money-in ≤25% by L+12 |
| Primary commission | 10% on the Bazaar, in-world vendors and the API. Founding Merchants pay 5% for 12 months from L. Body and head vendors' Re-delivery editions pay 0% for 12 months |
| Resale, tips, in-person Market Day sales, off-platform-paid deliveries | 0%. Optional resale royalty up to 10% |
| Estate tickets and priority | 10% |
| Cash-out | 2.5% plus pass-through rail cost (US$0.25 ACH, EUR 0.50 SEPA, ~US$2 international). Minimum 2,500 Coin domestic, 10,000 international. Weekly |
| Darkroom | 10 free renders a month, then 10 Coin each |
| Re-delivery | 10 Coin per claim, paid to the creator; ≤US$5,000 per merchant; US$1.5M fund, L-6 to L+24 |
| Commons Pool | 25% of net: 70 creators / 20 Charters and venues / 10 public Posts |
| **Required margin (printed)** | 5% of gross |
| **Worked example** | A US$10 sale leaves 900 Coin. Cashed out within a US$100 payout, the all-in take is **12.5%** |

The same page prints the rent lines *(spine)*:
- **Free account:** a Hearth with 1,000 Weight, 2,000 items and 1 GB.
- **Resident:** US$9.99/month or US$99/year.
- **Extra storage:** US$1 per 10 GB-month.
- **Holdings:** Plot S US$19, Plot M US$35, Cell US$69 (cost basis US$14), Domain US$249, Commons plot US$8.
- **Non-profit and education:** 50% off.
- **Price rises:** each needs 12 months' notice and grandfathering.

A creator therefore pays rent on bytes kept plus a slice of sales, and nothing for visitors.

The worked example at other payout sizes (doc 09's derivation):

| Case | Creator nets from US$10 | All-in take |
|---|---|---|
| Domestic ACH, US$100 payout | US$8.75 | **12.5%** |
| Domestic ACH, US$25 minimum | US$8.69 | 13.2% |
| International, US$100 minimum | US$8.60 | 14.1% |
| Founding Merchant, US$100 ACH | US$9.24 | 7.6% |

Every case is inside R7's 15% ceiling. SL residents estimate their all-in take at 20-31% ([source](https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/)), after the Marketplace commission doubled to 10% in 2019 ([source](https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/)). VRChat pays creators about 50% of spend ([source](https://creators.vrchat.com/economy/payout)). Rec Room kept 30 cents of each UGC dollar after store fees, and closed ([source](https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue)). Each change is logged in the Chronicle, and an annual audit checks that the effective take is within 2 points of the published figure.

## The Bazaar and vendors

### One protocol

The **Bazaar** is the open-protocol marketplace. The web Bazaar, in-world vendors and outside stores (BOOTH, Gumroad, Kitely Market) all use the same API *(spine)*. This reverses Linden's 2009 purchase of Xstreet SL and OnRez, which made SL's marketplace a captive channel ([source](https://lindenlab.wordpress.com/2009/01/20/xstreet-sl-and-onrez-to-join-linden-lab/)). It is also how nolife reaches Japan's avatar trade, where BOOTH's 3D-model category passed 10 billion yen in 2025 ([source](https://realsound.jp/tech/2026/02/post-2303955.html)).

```
Listing  { id, creator, manifest_hash, price_coin, regional_prices?, perms{c,m,t,export},
           maturity, splits_id?, royalty_refs[], resale_royalty_bps?, kind: item|access|keepalive }
Purchase { listing_id, buyer, price_shown{coin, fiat, fx_date}, channel: bazaar|vendor|market_day|external }
Delivery { licence record → buyer Passport; bytes stay in Vault by hash }
Receipt  { store_id, external_order_ref, signature }      // external channel only
```

Rules *(this doc unless marked)*:
- **One price, one fee.** Every channel charges 10% on a primary sale *(spine)*, and no channel is cheaper because the platform owns it.
- **Off-platform-paid deliveries are 0%** *(spine)*. The store must be Bazaar-certified (KYC on the operator, a receipt-signing key and audit sampling). The resulting licence is owner-only and cannot be transferred unless the creator registers the item for transfer.
- **Delivery is a licence, not a copy.** This keeps inventory loss measurable against the spine's target of at most 1 per 10 million operations, and lets a NAR restore by hash.
- **Regional prices.** Creators set them, with purchasing-power defaults. Roblox's regional pricing lifted paying users 26% in Brazil and 52% in the Philippines ([source](https://about.roblox.com/newsroom/2025/04/roblox-launches-regional-pricing-for-in-experience-items)). Pix is live at L and konbini at L+12 *(spine)*.
- **What listings show:** fiat first; the Fidelity Rank and tier previews; the permission bits; the maturity tag; any AI-assisted flag; and, on sub-lets, the base rent.

### Discovery

Search ranks by **distinct returning purchasers**, never by payment *(spine)*. There are no promoted listings and no listing-enhancement fees. SL's decade-old catalogue calcified around incumbents (sl-economy-creators brief). To counter that, a free **New Makers** shelf *(this doc)* features a creator's first 20 listings for 90 days after their first sale. Slots rotate by a lottery weighted by the return rate of the creator's buyers.

### Vendors and Market Day

A vendor is any object that calls `nl.bazaar.sell`. Vendors in Halls, Estates and Reaches sell at 10%. **Market Day** is Saturday in Ward local time *(spine)*, and its 0% rate covers **in-person sales only**. A sale qualifies when all four tests hold (doc 09's definition, enforced here):
1. It happens at a Market stall in a Ward's Market cell. Doc 02 allocates the stalls.
2. The seller or a Split member is present as a human in the cell, with input in the last 5 minutes. A Stand-in or any other Keeper does not count.
3. The buyer is in the same cell.
4. It is a primary-sale item, not an access ticket.

A sale that fails any test settles at 10%, and the stall says so before payment. Market Day sales earn Pool weight like any other sale.

### Refunds

Delivery is immediate, so the EU 14-day withdrawal right is waived only with the buyer's express consent at checkout. Separately, an item that fails to deliver, or that renders materially differently from its Foundry preview, is refunded from the seller's `earned` balance within 7 days *(this doc)*.

## Splits, royalties and the creator ladder

### Splits and royalties

A **Split** divides a sale among up to **10 contributors** *(spine)*. Its rules *(this doc)*:
- It is a signed Ledger object. Every member signs to create it.
- Reducing a member's share needs that member's signature.
- A change applies only to sales made after it.
- A member may be a Charter treasury, which makes charity splits possible.

A **Component Royalty** of up to 10% *(spine)* attaches to an asset others may build on: a body, a rig, a texture set or a script module. It is paid from gross before the Split, and the platform takes nothing extra. This is how one body maker becomes a platform for a hundred clothing makers without SL's no-mod lock-in. Two further rules *(this doc)*:
- **Stacking cap.** Royalties stacked on one item are capped at 25% of gross and scaled pro rata above it. Workshop warns before publishing.
- **Automatic attachment.** When Foundry fingerprinting finds a Component-licensed asset inside an upload, it attaches the royalty.

The optional **resale royalty** of up to 10% applies to Transfer-enabled items *(spine)*.

```
G  = gross (Coin)
c  = rate × G                 // 0.10 | 0.05 Founding Merchant | 0 Re-delivery body/head
r  = Σ min(rate_i, 0.10) × G, scaled so r ≤ 0.25 × G
N  = G − c − r                // divided by Split bps; remainder to the largest share
journal: gross, fees withheld, payee account per seller          // the DAC7 fields
```

Doc 09 works one sale through. A 1,000 Coin sale with a 5% royalty and a 70/30 Split settles as 100 commission, 50 royalty, and 595 and 255 to the two Split members.

Charter treasuries are multi-signature and can be attached to a legal entity *(spine)*. A school or a non-profit is paid as an organisation, not through a volunteer.

### The creator ladder

| Rung *(spine)* | Who | Can | Onboarding *(this doc)* |
|---|---|---|---|
| **Maker** | Any adult Passport at Trust Member | Sell on every channel; earn; spend in-world; join Splits. **No cash-out** | One click. Above US$600 of sales in a trailing 12 months, Merchant verification is needed before the next listing |
| **Merchant** | Verified adult, tax data on file | Weekly cash-out; analytics; Keepalive products; Adult-tagged goods (with Adult Seller KYC) | Rail KYC, then W-9 or W-8BEN/W-8BEN-E, then the DAC7 set (name, address, date of birth, TIN, VAT number, payout account), all **before the first payout** |
| **Studio** | A legal entity with Merchant status | Team seats with roles (builder, scripter, lister, finance), Splits by role, an SLA on review and payout support | Entity verification |

Tax data comes before the first payout because DAC7 binds non-EU platform operators and has no floor for services ([source](https://www.fonoa.com/blog/dac7overview)). The US 1099-K trigger is back at more than US$20,000 and more than 200 transactions ([source](https://irs.gov/newsroom/irs-issues-faqs-on-form-1099-k-threshold-under-the-one-big-beautiful-bill-dollar-limit-reverts-to-20000)).

Census publishes retention **by ladder rung** *(spine)*. The baseline is SL's 2023 creator distribution: 21,152 earning creators, of whom 6,446 earned over US$1,000 and 139 over US$100,000 ([source](https://wnhub.io/news/other/item-46605)).

### Founding Merchants and Re-delivery

The first 1,000 verified creators become **Founding Merchants** *(spine)*. They get:
- 5% commission for 12 months from L;
- funded conversion of their catalogue;
- the Ferry **creator claim**, in which a one-time code in their SL profile signs their imported catalogue to their Passport;
- **Re-delivery**, which pays them 10 Coin each time a migrant proves an SL purchase and claims the nolife edition.

Body and head vendors' Re-delivery editions pay 0% commission for 12 months, because the avatar's look is the migrant's main switching cost. Kitely used the same principle to rescue stranded OSgrid buyers ([source](https://www.hypergridbusiness.com/?p=79686)).

**Example: an SL clothing maker's first month.**
1. **Day 0:** she places the Ferry code in her SL profile.
2. **Day 1:** she uploads 140 own-created Collada items. The Foundry ranks 118 Good and 22 Fair, naming the Lite budget each Fair item misses.
3. **Day 2:** she lists 120 items, Re-delivery-eligible, each with a 5% Component Royalty to the base mesh she licensed.
4. **Weeks 1-4:** 900 Re-delivery claims pay her 9,000 Coin (US$90), and each claimant becomes a purchaser for 90 days. 210 new buyers spend US$1,900, which cashes out weekly once cleared.
5. **L+1:** her first Pool payout counts every buyer who returned on 2 or more days.

## The Commons Pool

The **Commons Pool** is 25% of net revenue (gross less processing, refunds and taxes), paid monthly and split 70/20/10 *(spine)*. Two pieces of evidence shape it:
- Epic's November 2025 rewrite counts only purchasing players and pays a 75% bonus on new or lapsed ones ([source](https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items)).
- A pool taken from gross spend cannot be funded at Linden scale (taxonomy section 5).

```
Pool_m = 0.25 × (Gross_m − Processing_m − Refunds_m − Taxes_m)
Lines  = Creators 0.70 | Charters & venues 0.20 | Public Posts 0.10
RPU(u,m): ≥1 qualifying purchase in the 90 days to m-end AND visits on ≥2 distinct days in m
          AND a human Passport (no Keepers, no flagged bots)
w(u)   = (1.0 verified | 0.5 unverified) × 1.75 for 6 months if referred as new or lapsed
CreatorWeight(c) = Σ w(u) over distinct RPUs who bought c's goods, wherever sold
                   (Split members and Component Royalty holders included)
                 + w(recipient) per equipped Starter Catalogue item of c, for 90 days
Payout(c) = 0.70 × Pool_m × CreatorWeight(c) / Σ CreatorWeight
```

What this means for a creator:
- **Distinct buyers, not revenue.** Five hundred returning buyers of US$1 items earn the same weight as five hundred of US$50 items. Price is already rewarded by sales, and the Pool rewards breadth of returning customers, which protects the long tail that SL's market buried.
- **"Wherever sold"** includes Market Day, vendors and certified stores. Marketplace-only creators are therefore not starved (B.4 item 7).
- **Workshop's forecast** shows the month's RPU count, the verified share and the referral bonuses in force, with an estimate based on last month's rate.
- **Timing.** Payouts land on the 10th, starting at L+1. Census publishes the formula, the distribution and the **median** quarterly *(spine)*.

At Reference scale the Pool is US$10.0M a year, of which US$7.0M goes to creators *(spine, D.8)*. Doc 09 illustrates about US$560 a month for a creator with 500 verified returning buyers. The median will be much smaller, and it is the number that will be published.

**Anti-farming** *(spine; doc 09)*: purchasers only, unverified at 0.5; one Pool identity per verified person; no credit below 100 Coin or between accounts sharing a payout account, Split or device cluster; Keepers excluded; holds when the bot detector trips; external deliveries count only from existing RPUs.

### The Starter Catalogue

The Landing dresses and furnishes newcomers from the **Starter Catalogue**: creator goods given free, each equipped item counting as a purchaser for 90 days *(spine)*. The first thing a newcomer wears is a creator's product, and the Pool pays for it. Rules *(this doc)*:

| Rule | Value |
|---|---|
| Eligibility | Merchant; General-rated; Fidelity Rank Excellent or Good; fits the Common Body; Copy permission; no debit-grant scripts |
| Size per launch language | 240 items: 60 outfits, 60 hair and head items, 120 furnishings |
| Per-creator cap | 3 items, so at least 80 creators |
| Selection | Quarterly open call, judged against a published rubric by 5 Pillar-Standing residents and one Landing designer. 25% of slots go to first-time Starter creators |
| "Equipped" | Worn or placed in the Hearth on at least 2 distinct days that month |

## Keepalive and Lineage

### Why (R24)

Ozimals bunnies could eat only server-validated food. When a legal threat closed the volunteer-run food server in May 2017, every bunny went into permanent hibernation ([source](https://boingboing.net/2017/05/20/breedables-vs-drm.html)). KittyCatS survived, but its breeders describe a boom-bust driven by trait inflation ([source](https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/)). This section designs out both failures.

### Keepalive

**Keepalive** is escrowed life-support for value-bearing scripts, with a food-independent end state *(spine)*. Its rules *(this doc)*:
1. **Registration is mandatory** for any product whose function or value depends on state outside the object (breedables, pets, RP meters, vendor HUDs, licence servers). The Foundry flags validation-style HTTP calls, and the Bazaar refuses the listing until the product is registered.
2. **Value lives on the platform.** The vendor's server logic runs as a Luau *service script* under the creator's budgets, with state in the Entity Store. External HTTP may serve only features that carry no value.
3. **The end state is tested.** Each product ships an `on_retire()` handler converting objects to a food-independent "perma" form with traits kept; the Foundry runs it before listing.
4. **An escrow deposit** of 24 months' projected service cost (minimum 1,000 Coin per product line) sits in doc 09's Keepalive escrow account.

```
REGISTERED → LIVE ──exit trigger──→ NOTICE (90 days, owners told in-world)
              │                        ▼
              │                     SUSTAINED (platform runs the service script from escrow; no new sales)
              │                        │ escrow exhausted or 24 months
              └──creator retires───────┴──→ CONVERTED (on_retire for every object; no server needed)
Exit triggers: Merchant status lapsed 90 days; account closed or banned; declared exit;
health checks failing for 7 days.
```

**Price** *(this doc; see Open questions)*: the first 10,000 live objects per Merchant are included, then US$1 per 10,000 live objects a month, mirroring the storage price. The deposit is refunded on orderly retirement. None of this is a fee on sales, so the Fee Page take is unchanged.

### Lineage

**Lineage** is the registry for breedable genetics, with habitat caps *(spine)*. A species registers a trait schema (loci, alleles, dominance and mutation rate) and published rarity tables. Lineage holds each creature's genome, so the creature outlives its vendor.

**The Lineage rule** *(spine)* is that breeding outcomes are either previewed before commit, or random only for non-transferable offspring. A cash-out-able item combined with chance is gambling somewhere; SL banned wagering in 2007 ([source](https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/)). Breeding has two modes *(this doc)*:

| Mode | Mechanism | Offspring |
|---|---|---|
| **Preview** | The genome comes from a seed fixed when the pair forms. It is shown in full before any Coin or cooldown is spent. Declining locks the pair's seed for 7 days, so re-rolls cannot be bought | Transferable; sold under normal fees |
| **Surprise** | The genome is drawn at birth | **Bound**: never transferable or sellable, and every descendant is Bound too |

Bound inheritance closes the leak in which a chance-bred animal is bred once more in Preview mode and the result sold. **Habitat caps** *(this doc)* limit a Holding to Weight ÷ 150 live, breedable creatures: 200 on a Cell, 26 on Hearth+. The rest wait dormant in inventory. Lineage publishes live counts per trait every month, so trait inflation is visible as it happens.

## UGC moderation and fingerprinting

### Layers

Nothing is visible to anyone but its uploader until Foundry stage 3 passes. The checks:

| Layer | Mechanism | Outcome |
|---|---|---|
| Trust | Upload volume and publication rights by rank (doc 08) | Throttle |
| Illegal content | CSAM hash on every texture, bake and thumbnail | QUARANTINED, platform only and immediate; NCMEC report |
| Likeness | Match against the consent registry | HELD until consent is shown |
| Scripts | Static analysis: self-replication, grief patterns, obfuscation, credential prompts, undeclared value-bearing calls | REJECTED with a reason code, or Keepalive registration required |
| Adult-tagged goods | Uploader verification (AV plus Adult Seller KYC), consent records, **human pre-publication review**, maturity tag on every Ledger entry *(spine; pipeline in doc 08)* | Visible only to opted-in AV residents; subject to deindex-but-sell |
| IP | Fingerprinting, plus notice and counter-notice | HELD, attributed or delisted |

These are the controls Mastercard's AN 5196 and Visa's VIRP expect ([source](https://verifymy.io/resources/regulation/card-brand-requirements)). Coin purchases are coded as stored value, never under an adult MCC. That is plausibly why SL and Tilia escaped the July 2025 processor campaign that hit Steam, itch.io and DLsite ([source](https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story)). Deindex-but-sell copies itch.io's survivable middle path ([source](https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/)).

### Fingerprinting: the CopyBot defence

CopyBot (2006) showed that any viewer can replay the asset stream it receives, and Linden treated the problem as a ToS matter (legacy-interop brief; [source](https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/)). nolife makes it technical, at the Foundry *(spine)*.

The index *(this doc)* holds the source hash and the hash of **every derivative the Foundry has ever served**. Clients only ever receive derivatives, so any replay is by construction one of them.

| Signal | Computation | Threshold | Action |
|---|---|---|---|
| Exact replay | Hash of the quantised vertex buffer (1 mm) and the decoded texture, matched against derivative hashes | Any match | HELD and attributed to the original. A second replay within 12 months suspends uploads |
| Near-duplicate geometry | Rotation- and scale-normalised shape descriptor, robust to decimation | Similarity ≥0.95 | HELD for IP review |
| Near-duplicate texture | 64-bit perceptual hash per mip | Hamming distance ≤6 | HELD for IP review |
| Licensed reuse | A match with a Component-licensed or kit asset | Any | Published; royalty attached; kit items exempt |
| Trivial geometry | Under 200 triangles with no unique texture | n/a | Not fingerprinted |

Catalogues signed through the Ferry creator claim are indexed before their creators' storefronts open. A thief's later copy is held, not the original.

**IP process.** The review target is 72 hours *(this doc)*. Notices and counter-notices run on a published turnaround. Three upheld findings within 12 months remove Merchant status, and with it cash-out, for 12 months. Disputed earnings stay in `earned` until the decision. Appeals go to the Trust Desk (7 days); IP cases are legal matters, so Tribunals do not hear them.

**Published quarterly in Census** *(this doc)*: Foundry hold, reject and quarantine rates; fingerprint false positives found on appeal; IP review time; deletion rates per Ward *(spine)*; and the adult share of spend. Inventory loss is published monthly *(spine)*.

## Trade-offs and alternatives rejected

| Alternative | Source | Why rejected |
|---|---|---|
| 1.5% cash-out plus a 4% spread; a 3% top-up fee; a buy spread | engine, open-web, ai-world | Spreads are invisible at the point of sale, which is how "90/10" became 20-31% *(spine, B.3)* |
| Metered compute above a visitor allowance | economist | Charges places for success *(spine, B.3)* |
| Paid new-creator shelf or sponsored row | economist, studio | Breaks ranking by returning humans; the New Makers shelf is free |
| Pool weighted by revenue or play-hours | Roblox and Epic patterns | Pays incumbents twice, or rewards session length. Roblox's 2026 bookings miss followed a retention-favouring recommender change ([source](https://www.sec.gov/Archives/edgar/data/0001315098/000162828026051059/ex991-robloxq22026earnin.htm)) |
| A transpiler that rewrites creators' source; a separate legacy VM | open-web, economist | Creators keep their source; one scheduler keeps R5's per-owner guarantee |
| Chance breeding for cash-out-able value | ai-world | Gambling somewhere (R9); Preview or Bound instead |
| Export enforced by client trust | open-web | Fails against a modified client; the Vault enforces it instead |

**Trade-offs accepted.**
- **The commission is SL's 10%.** The edge comes from the 0% buy, resale and Market Day lines, a printed 12.5% round trip, and the Pool.
- **Distinct-buyer weighting invites small-ticket farming.** The 100-Coin floor and the device-cluster rules exist to contain it.
- **Mandatory Keepalive registration adds friction for makers of scripted products,** in exchange for a guarantee no other world offers.
- **Server-side export makes export depend on the endpoint being up.**

## Requirements addressed

| R | How |
|---|---|
| R3 | glTF 2.0/VRM 1.0 runtime, OpenUSD scenes; funded conversion; converter + 24 months' notice |
| R5 | Per-owner CPU, memory, network and write budgets; worst-offender throttle; LSL under the same scheduler; profiler |
| R6 | No upload fee; rent on bytes kept, never visitors; rent lines on the Fee Page |
| R7 | Signed Fee Page (HTML and JSON); 0% buy, 10% primary, 0% resale; 12.5% example; 5% margin printed; annual audit; stores ≤25% by L+12 |
| R8 | Pool 25% of net, 70/20/10; distinct returning purchasers; anti-farming; Starter weighting; median published |
| R9 | Coin fiat-first, exact amounts, no bundles or spread; Lineage Preview/Bound rule; DFA fallback |
| R10 | Merchant rung on a licensed rail; W-9/W-8 and DAC7 before the first payout |
| R13 | Pool distribution and median, retention by rung, moderation rates in Census |
| R18 | Creator claim, Re-delivery, Ferry formats through the Foundry, LSL unchanged |
| R22 | Adult-tagged pipeline with pre-publication review; maturity-tagged Ledger; deindex-but-sell |
| R23 | Trust-gated upload; review before visibility; published rates |
| R24 | Keepalive registration, escrow, SUSTAINED/CONVERTED; Lineage with habitat caps |
| R25 | Keepers excluded from wallets, debit grants, Market Day and Pool counts |
| R26 | Workshop separate from the consumer interface; the Landing never opens it |
| R29 | Bazaar open to BOOTH, Gumroad and Kitely Market; VRM; regional prices; Pix, then konbini |

## Open questions

1. **Keepalive price.** D.3 sets none, and doc 09 asks for one. This document proposes a 24-month escrow (minimum 1,000 Coin per product line) plus US$1 per 10,000 live objects a month above 10,000. It needs a Fee Page line before the Bazaar opens.
2. **Maker threshold.** The US$600 trigger is a planning value. Counsel must say whether Coin credited to a Maker who cannot cash out counts as "consideration" under DAC7. If it does, EU Makers need the DAC7 set at their first sale.
3. **The 25% stacking cap** on Component Royalties is new. It should be tested with body and clothing makers in alpha.
4. **Starter counting.** Doc 09's formula has no visit test for Starter items, and this document's "equipped" rule adds one. The two must be reconciled before the formula is published.
5. **Re-delivery bounty (spine value kept).** 10 Coin (US$0.10) per claim may not move the top mesh-body vendors. The 0% commission may carry the deal on its own. Measure alpha sign-ups before proposing any change to D.3.
6. **Ember building.** Without building in Ember at L, Chromebook-only educators cannot build. Should a Blocks-only Ember Workshop be scheduled for L+12?
7. **Coin review.** Should LSL prices convert at the live L$ rate, or at a fixed published rate?
8. **Fingerprint thresholds** are uncalibrated. Tune them on the alpha catalogue and publish the false-positive rate before L.

## Sources

- https://modemworld.me/2014/06/29/ebbe-altberg-on-user-retention-now-and-in-the-future/
- https://corp.roblox.com/newsroom/2025/03/introducing-roblox-cube
- https://vrm.dev/vrm1/
- https://www.linuxfoundation.org/press/aousd_prmarch2026
- https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/
- https://modemworld.me/2026/07/03/2026-week-27-sl-ccug-meeting-summary-updating-sl-mesh/
- https://edgegap.com/pricing
- https://wiki.secondlife.com/wiki/Lua_Alpha
- https://exchangerate.guru/ld/usd/1/
- https://www.hypergridbusiness.com/2013/09/outrage-grows-over-new-second-life-terms
- https://modemworld.me/2014/07/16/lab-updates-section-2-3-of-their-terms-of-service-will-it-calm-doubts/
- https://www.hypergridbusiness.com/2012/09/hypergrid-permissions-need-viewer-change/
- https://modemworld.me/2013/08/24/
- https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content
- https://techinsights.linklaters.com/post/102k6t4/game-changer-eu-introduces-consumer-protection-guidance-for-in-game-virtual-curr
- https://community.secondlife.com/forums/topic/519135-linden-claims-to-only-take-10-off-creators-but-they-really-take-20-by-the-time-you-pay-marketplace-fees-cash-out-fake-advertising-by-phil/
- https://ryanschultz.com/2019/11/25/editorial-second-life-users-are-less-than-happy-about-linden-lab-doubling-commission-rates-on-the-sl-marketplace-from-5-to-10/
- https://creators.vrchat.com/economy/payout
- https://blog.recroom.com/posts/2025/8/28/rec-room-finances-and-ugc-revenue
- https://lindenlab.wordpress.com/2009/01/20/xstreet-sl-and-onrez-to-join-linden-lab/
- https://realsound.jp/tech/2026/02/post-2303955.html
- https://about.roblox.com/newsroom/2025/04/roblox-launches-regional-pricing-for-in-experience-items
- https://www.fonoa.com/blog/dac7overview
- https://irs.gov/newsroom/irs-issues-faqs-on-form-1099-k-threshold-under-the-one-big-beautiful-bill-dollar-limit-reverts-to-20000
- https://wnhub.io/news/other/item-46605
- https://www.hypergridbusiness.com/?p=79686
- https://www.fortnite.com/news/fortnite-developers-will-soon-be-able-to-sell-in-game-items
- https://boingboing.net/2017/05/20/breedables-vs-drm.html
- https://community.secondlife.com/forums/topic/435130-how-much-have-you-made-via-kittycats-plantpets-dfs-other-breedables/
- https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/
- https://verifymy.io/resources/regulation/card-brand-requirements
- https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story
- https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/
- https://www.sec.gov/Archives/edgar/data/0001315098/000162828026051059/ex991-robloxq22026earnin.htm
