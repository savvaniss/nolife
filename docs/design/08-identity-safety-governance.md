# 08: Identity, safety and governance

Design document 08 of 10. Status: draft for build, 2026-10-09. It implements spine section C.8 and must agree with spine sections D.2, D.5, D.6 and D.7. Names and numbers taken from `00-design-spine.md` are canonical. Values marked *planning value* are new to this document and may be tuned without a spine change.

## Summary

nolife is 18+ by default. One pseudonymous **Passport** carries each person, backed by a private age band from on-device estimation or a wallet credential; no ID image is ever stored. The **Age Module** ships five regional profiles at L (UK, EU, Brazil, Indonesia, Texas). Ages 13-17 exist only in **Campus**: institutional SSO, no economy, isolated. **Night Wards** and Adult-tagged commerce sit behind an Ofcom-grade check with card-scheme controls built in. The **Safety Kit** is always on, and **Trust** ranks gate upload, voice and proximity. Moderation runs on US$1.50 per DAU-month with a US$1.5M yearly floor and targets a median time-to-action under 24 hours. Appeals run Charter Warden, then **Tribunal** (72 h), then **Trust Desk** (7 days). Charters, 5-seat **Ward councils** (L+6) and a 9-seat advisory **Assembly** (L+12) govern under a **World Charter** requiring 12 months' notice for price rises and shutdown. **Census** publishes the numbers.

## Passport

### What it is

A Passport is the one persistent self. Identity is pseudonymous with a privately held age band, the settlement every surviving platform reached. Meta's 2020 requirement that Oculus users hold a Facebook account was reversed by 2022 ([source](https://androidcentral.com/gaming/virtual-reality/meta-finally-kills-the-oculus-quest-2-facebook-account-requirement)), and Roblox, VRChat and Discord all bind a private age band to a pseudonymous account ([source](https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat)). nolife never requires a real name.

### Data model

The design separates the **Person**, who is private and verified, from the **Passport**, which is public and pseudonymous. Votes, Pool weight, jury eligibility, bans for serious harm and alt limits all count per Person. What other residents see is the Passport.

```
Person {                      // never exposed outside the Trust Desk boundary
  person_id
  assurance: AgeClaim         // held in the Age Vault (see Age Module); services see booleans only
  kyc_ref?: RailKycId         // set by the licensed rail partner on Merchant onboarding
  passports: PassportId[]     // max 10 (planning value): alts allowed, linked privately
  sanctions: PersonSanction[] // S0/S1 bans and terminations apply to every Passport
}
Passport {
  username                    // permanent, unique, pseudonymous
  display_name                // changeable once per 7 days; the last 3 are visible to Wardens on a report
  home_ward                   // one per resident, changeable every 30 days
  trust: Visitor|New|Member|Known|Trusted, nuisance_until?
  standing: Neighbour|Regular|Pillar|Elder   // civic; see doc 03
  licences: SignedLicence[]   // readable off-platform (the "Content Passport")
  inventory_root: VaultRef
  creator_claims: SLClaim[]   // Ferry creator claim (doc 10)
}
```

### Rules

- **P1. Sign-in.** Sign-in uses passkeys (WebAuthn). A second factor is mandatory for Merchants, Charter treasury signers and every Warden Post.
- **P2. Alts.** Alts are allowed and private. The link between a Passport and its Person is visible only to the Trust Desk. A block applies to a Person by default, so blocking one Passport blocks all of that Person's alts.
- **P3. KYC.** KYC happens only at cash-out. Makers sell and spend without KYC. Merchants are verified by the rail partner and have tax data on file (W-9/W-8 and DAC7) before their first payout, because DAC7 has no floor for services ([source](https://www.fonoa.com/blog/dac7overview)).
- **P4. Biometrics.** Eye, face and hand tracking are processed on the device. Only abstracted animation data leaves it. Tracking requires explicit consent, the retention policy is published, and biometrics are never sold (Never List). Meta's eye-tracking notice shows that "abstracted gaze data" can still reach servers ([source](https://www.meta.com/legal/quest/eye-tracking-privacy-notice/)). Illinois BIPA and Colorado HB 24-1130 treat biometrics as consent-only ([source](https://fpf.org/blog/old-laws-new-tech-as-courts-wrestle-with-tough-questions-under-us-biometric-laws-immersive-tech-raises-new-challenges/)).
- **P5. Likeness consent registry.** The Foundry's likeness check blocks any asset that depicts a real person until it is linked to a consent record. That covers photo textures, scans, MetaHuman faces matched to a real person and voice clones. The record is signed by the depicted person's Passport or attached as a verified off-platform consent. A notice and counter-notice flow handles disputes. The design is ready for the NO FAKES Act, which advanced in June 2026 but has not passed ([source](https://www.govtrack.us/congress/bills/119/s4591)), and for the TAKE IT DOWN Act's removal duties, which are already in force ([source](https://www.sagaftra.org/take-it-down-act-notice-and-removal-obligations-now-effective)).
- **P6. Provenance.** Every asset carries a signed, C2PA-style manifest: creator, time, pipeline version and AI-assist flags. AI-generated likenesses also carry a visible in-world label, because under Article 50 of the AI Act a mark buried in metadata does not meet the deployer's labelling duty ([source](https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content)).
- **P7. Not imported.** SL status, age claims and SL Trust are not imported (doc 10). Members who arrive through Charter Import start at Trust New, skipping Visitor, because they land in their Hall rather than at a Landing.

**Rejected:** a federated home-shard Passport (open-web; federation is rejected in B.3); real names; unlinked alts, which break one-person-one-vote and Pool anti-farming.

## The Age Module and regional profiles

### Assurance levels

A self-declared birth date is no longer age assurance; the EU guidelines treat it as unreliable ([source](https://www.hlc.com/en/publications/the-longawaited-eu-guidelines-on-article-281-dsa-what-online-platforms-must-know)). Second Life still runs a self-declared Adult gate ([source](https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/)). For that reason the open world has no "declared only" tier.

| Level | How it is obtained | What it unlocks |
|---|---|---|
| **AA: Assured 18+** | On-device facial age estimation that clears the profile's challenge age (planning value: 25), or any accepted credential | Account creation and the open world (General and Moderate) |
| **AV: Verified 18+** | A method the profile rates "highly effective": an EU age credential or wallet proof, estimation with liveness that clears the challenge age where the profile accepts it, or an accepted second-method check | Night Wards, Adult-tagged commerce, voting, jury service, Merchant onboarding (plus rail KYC), and Pool weight 1.0 (AA counts 0.5) |
| **Campus** | Institutional SSO attestation of a birth year in the 13-17 range | Campus only (see next section) |

An estimate between 18 and the challenge age moves to a credential path. An estimate under 18 is refused an open-world account and pointed to Campus if an institution applies. Nobody under 13 is admitted anywhere.

### What is stored

The **Age Vault** is a store separate from the Passport, keyed by `person_id`. Nothing else touches it.

```
AgeClaim { level: AA|AV|CAMPUS, band: "18+"|"13-17", method_class: estimation|wallet|os_signal|sso,
           vendor_attestation_id, profile: "UK"|"EU"|"BR"|"ID"|"US-TX"|..., checked_at }
service API: is_open_world_eligible(), is_adult_verified(), campus_only(), profile()
```

No ID image is ever stored: estimation runs on the device and the vendor attests deletion of frames. Discord's appeals vendor exposed about 70,000 government-ID images ([source](https://cyberinsider.com/discord-confirms-70000-government-ids-exposed-in-third-party-breach/)), so appealing an estimate means retrying with another method, usually a credential, never uploading a document to a human. Any document check a profile ever required would be vendor-automated, never human-reviewed, with deletion attested in the Chronicle.

A person is checked again only when there is a reason:
- a "possible minor" signal (from a report or a classifier), which restricts the account to text with its friends until a credential check;
- an account recovery or change of ownership;
- a change to the profile's rules.

### Regional profiles

The jurisdiction is the strictest of three signals: billing country, IP geolocation and declared residence. A profile is configuration, not code.

```yaml
profile: BR
open_world_min_age: 18
accepted_av_methods: [wallet_credential, estimation_liveness, os_signal_18plus]
self_declaration: rejected
age_data_reuse: forbidden          # ECA Digital
campus: {enabled: true, guardian_surface: required}
loot_box_mode: n/a                 # Never List: no loot boxes anywhere
regulator_contact: ANPD
```

| Profile (at L unless noted) | Legal driver | nolife configuration |
|---|---|---|
| **UK** | Online Safety Act: "highly effective" checks since 25 July 2025, fines up to £18M or 10% of turnover, applies to user-to-user services ([source](https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/); [source](https://www.computerweekly.com/feature/The-UKs-Online-Safety-Act-explained-what-you-need-to-know)) | AV for the Night Ward uses only Ofcom-accepted methods; an information-request pack is pre-built |
| **EU** | DSA Article 28 guidelines: self-declaration unreliable, minors private by default, annual risk review; the Commission's age-verification app ([source](https://ec.europa.eu/commission/presscorner/detail/en/ip_25_1820); [source](https://cms.law/en/fra/news-information/protecting-minors-in-the-digital-space)) | Wallet credential preferred for AV; Campus private by default; annual risk review published with Census |
| **Brazil** | ECA Digital, in force 17 March 2026: any service "likely to be accessed by minors", no self-declaration, parental tools, no reuse of age data, fines up to R$50M ([source](https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/); [source](https://www.mayerbrown.com/en/insights/publications/2026/04/enforcement-of-brazils-eca-digital-introduces-new-obligations-for-companies)) | Age data used only for age gating; guardian surface required in Campus; Portuguese T&S staff at L |
| **Indonesia** | PP Tunas, enforceable March 2026: minimum age 16, unverified accounts lose communication ([source](https://avpassociation.com/indonesia/)) | No chat before AA; Campus disabled until counsel clears it |
| **Texas** | App Store Accountability Act in force pending appeal; developers receive age ranges, not birth dates ([source](https://www.pearlcohen.com/fifth-circuit-stays-injunctions-against-texas-app-store-accountability-act/); [source](https://developer.apple.com/forums/thread/810754)) | App-store age-range signal read where present; a minor signal is a hard block |
| California (2027) | AB 1043: age-bracket signal from the operating system ([source](https://www.alstonprivacy.com/california-enacts-digital-age-verification-law/)) | OS signal read by Lantern, and by the mobile clients from L+9 |
| Germany (before L+12) | JuSchG §24a precautions; KJM-approved verification for adult content ([source](https://law.ungovr.org/age/de)) | Profile signed off before the German Wards open; Night Ward AV limited to KJM-accepted methods |
| Japan (L+12) | No statutory mandate ([source](https://dl.digra.org/index.php/dl/article/download/2766/2750/2810)) | Default 18+ AA/AV rules apply |

Framing is a legal lever: Australia's under-16 ban excludes services whose primary purpose is gaming, and its list "is not static" ([source](https://www.esafety.gov.au/about-us/industry-regulation/social-media-age-restrictions/faqs)). nolife declares creation and play as its primary purpose.

**Rejected (B.3):** six world-wide Roblox-style bands and a 16-17 Scholar band in General Wards, which would bring ECA Digital, PP Tunas and children's codes into a cash-out economy. Adjacent-band logic survives only inside Campus.

## Campus and minors

Campus is the only place where anyone aged 13-17 can be. It ships at L+6 with SSO, and the target is at least 20 institutions by L+18.

**Rules:**
- **C1. Provisioning.** Accounts are created only through institutional SSO (SAML or LTI) as bulk accounts. The institution is the account holder of record and attests that each student is 13-17 under its own consent process. The SSO bridge rejects any birth year under 13.
- **C2. Isolation.** Campus cells are General-rated and cannot be reached by open-world teleport, search, map or Calendar. Campus residents cannot leave Campus.
- **C3. Adults.** The only adults in Campus are staff accounts that are both institution-attested and AV. They wear a staff badge. Adult-to-student direct messages are off. Staff talk to students only in class channels and spatial chat, and both are logged.
- **C4. No economy.** There is no Coin, Bazaar, cash-out, tips or Pool weight. Inventory exists. Own-created work exports as NAR.
- **C5. Defaults.** Profiles are private, there are no stranger contacts, geolocation is off and there are no engagement notifications, as the DSA Article 28 guidelines ask ([source](https://www.hlc.com/en/publications/the-longawaited-eu-guidelines-on-article-281-dsa-what-online-platforms-must-know)). Students can voice-chat only within their class or year group. This is adjacent-band chat inside Campus.
- **C6. Keepers.** Keepers in Campus are scripted only. There are no LLM conversations and no companion loops, because Character.AI banned open-ended chat for under-18s ([source](https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots)).
- **C7. Parental surface.** Guardians get a read-only summary of time in Campus, classes and reports filed, delivered through the institution. Brazil's profile makes this mandatory.
- **C8. Safety.** The Safety Kit applies at its strictest defaults. Any report goes straight to the platform's child-safety queue (S0/S1), never to a Charter Warden.
- **C9. Graduation.** At 18 a student completes AA in the normal way and creates an open-world Passport. They carry over their own-created NAR. Campus history is not linked to the new Passport unless the person chooses to link it.
- **C10. Price.** A Class Cell costs US$34.50 a month (50% off the Cell rate). The persistence covenant and NAR export apply as for any Holding.

**Minors found in the open world** are restricted pending a credential check. If confirmed, the account closes with an export of own-created content and a Campus referral where possible, and its contacts are reviewed under S0 rules.

## Night Wards and adult commerce

Adult content is a measured, controlled, first-class purpose. At L there is one English **Night Ward** among the six Founding Wards, and Adult Estates live in Night Wards. A Night Ward ran in private alpha first. There is no precedent to copy: VRChat verifies 18+ through Persona and bans pornography platform-wide ([source](https://wiki.vrchat.com/wiki/Age_Assurance)).

### Entry

1. A resident who is AV opts in to "Adult places and goods". Being AV alone does not opt anyone in.
2. Night Ward places, Calendar events and Bazaar listings become visible to that resident. They never appear in the Landing, in newcomer routing, on the Call Board or in Campus.
3. A Passport flagged Nuisance for sexual misconduct loses Night Ward access while the flag lasts.

### Adult-tagged goods pipeline

Mastercard's AN 5196 requires verification of uploaders and everyone depicted plus pre-publication review; Visa's VIRP makes adult content Tier 1 under MCC 5967 ([source](https://verifymy.io/resources/regulation/card-brand-requirements); [source](https://www.legitscript.com/regulatory-and-card-brand-compliance/adult-escort-and-dating-merchants-are-your-practices-in-line-with-virp-updates/)). nolife builds those controls before anyone asks for them.

```
Draft --(uploader is AV + rail KYC "Adult Seller")--> Verified
Verified --(consent records for every depicted real person; synthetic attestation otherwise)--> Consented
Consented --(Foundry: CSAM hash, likeness, fingerprint, script checks)--> Screened
Screened --(human pre-publication review, 72 h target, planning value)--> Listed[Adult]
Listed[Adult] <--> Deindexed            // deindex-but-sell switch
Listed[Adult] --> Removed               // report, consent withdrawal or reviewer reversal
```

An Adult listing is visible only to opted-in AV residents. Every Ledger entry carries the maturity tag (G, M or A) of its item and place from day one. Census publishes the adult share of spend and of cash-out each quarter. Purchases of Coin are coded as stored value held by the licensed partner, never under an adult MCC. That is plausibly why SL and Tilia were not named in the 2025 processor campaign that hit Steam, itch.io and DLsite ([source](https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story)).

### The switch ladder

| Level | Trigger | Effect | Authority | Target |
|---|---|---|---|---|
| 0 Normal | None | Adult goods are indexed for opted-in AV residents | — | — |
| 1 Deindex-but-sell | Scheme or processor signal, legal advice, or regulator contact | Adult listings leave search, Directory and Calendar. Direct links, in-world vendors and existing sales keep working | Head of T&S and CFO | Within 4 hours (planning value; spine: "within hours") |
| 2 Cash-out contingency | A **written processor demand** only | Adult-tagged proceeds are settled through the pre-qualified adult-specialist acquirer, or held | CEO, after written notice to Merchants | Within the processor's deadline |

Every change of level is entered in the Chronicle. Level 1 follows itch.io's model, which kept creators' income ([source](https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/)).

**Rejected:** a blanket exit (Tumblr lost about 29% of page views in three months ([source](https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/)); OnlyFans reversed its ban within a week once scheme controls were agreed ([source](https://www.cbc.ca/lite/story/1.6148524))); a separate adult rail by default (untested, and it raises fees for everyone); Stripe, which prohibits adult content ([source](https://conductatlas.com/platform/stripe/stripe-restricted-businesses-list/adult-content-prohibition-and-restriction/)).

## The Safety Kit

In 2024 UK police judged a virtual assault not viable to charge ([source](https://lbc.co.uk/news/police-investigate-rape-metaverse)), and ADL found 19% of harassed players quit games entirely ([source](https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf)). Platform controls are the only layer, so they are always on in Lantern, Ember and Reader, and certified third-party clients (L+24) must implement them.

| Primitive | Default | Detail |
|---|---|---|
| **Personal boundary** | On for anyone who is not a Friend | Default radius 0.6 m, which follows Meta's 2022 2-ft-radius cylinder ([source](https://ispr.info/2022/02/08/meta-establishes-four-foot-personal-boundary-to-deter-vr-groping/)). The user can set 0-3 m. Other avatars stop at the edge. |
| **Mute / block / vanish** | One gesture each | Mute silences voice and chat. Block makes both sides invisible to each other and removes IM, at the level of the Person. Vanish teleports you to your Hearth and hides your presence from that place for 10 minutes. |
| **Warden kick and lock** | Available to Warden Posts | Kick removes someone from the place for 15 minutes to 24 hours. Lock closes an instance or Holding to new entrants. Every use logs a reason code. |
| **Evidence buffer** | Rolling 60 seconds on the client | It holds positions and poses within 30 m, chat, the voice the reporter heard and object IDs. It is encrypted on the device and uploaded only when a report is filed. |
| **Consent prompts** | On | Animations, sits, attachments or scripted effects aimed at another avatar need an explicit grant, scoped to that avatar, object and session and revocable with one gesture. LSL permission requests go through the same prompt. Bloodlines, the SL vampire system that asked before biting, is the pattern ([source](https://community.secondlife.com/forums/topic/415080-what-is-bloodlines/)). |
| **Trust gating** | On | Upload, voice and proximity rights follow Trust rank (next section). |

**Accessibility.** In Reader every primitive is reachable by keyboard and announced through text-to-speech. A report can be filed by keyboard, and it attaches the text log plus whatever buffer data the client holds.

**Keepers** never moderate. Their logs may be attached as witness evidence (doc 07).

## Trust ranks and moderation operations

### Trust ranks

Trust follows VRChat's ladder of Visitor, New, Member, Known and Trusted, plus a visible Nuisance flag. It is earned through behaviour and cannot be raised by idling or mass-friending ([source](https://docs.vrchat.com/docs/vrchat-safety-and-trust-system)).

| Rank | Entry rule (planning values) | Upload | Voice | Other rights |
|---|---|---|---|---|
| Visitor | Account with AA | None | Landing cohort and Hosts only | Text chat with co-present people; build only in own Hearth |
| New | Completed the Landing or First Light, or 2 active hours | 10 items/day | Spatial voice in public places | IM people met in the last 7 days; scripts in own Hearth and Holdings |
| Member | 14 days' tenure, 10 active days, 5 distinct Member+ interlocutors, no confirmed report in 14 days | 100/day | Full | Maker selling; Commons lottery; found a Charter; vote (with 90 days' tenure and AV) |
| Known | 60 days' tenure, 30 active days, plus a Post shift, 3 events hosted or 10 accepted uploads | 1,000/day | Full | Scripts in public places; eligible for Warden Posts |
| Trusted | 180 days' tenure and 90 days at Known | Bulk | Full | Faster report triage; can reserve Event Mode |

**Trust score.** It is computed weekly and only rank thresholds are shown.

```
TS_week = Σ_days min(human_copresent_active_minutes, 120)/60
        + 2 × distinct_new_Member+_interlocutors (cap 10, same-Person alts excluded)
        + 5 × completed_post_shifts + min(accepted_uploads, 10)
        − 20 × confirmed_reports − 50 × nuisance_flags
```

Minutes count only with input and another human present; friend count is never an input. A confirmed violation drops one rank.

**Nuisance flag.** The flag is set when confirmed reports come from 3 distinct Persons in 30 days, or when a Warden or the Trust Desk sets it. It is visible to everyone, it blocks proximity to strangers and any Post, and it expires after 30 days with no new confirmed report.

### Severity classes and who acts

| Class | Examples | Who acts | Target |
|---|---|---|---|
| **S0** | CSAM, grooming, sextortion, credible threat to life | Platform only, immediate; legal hold; NCMEC or national authority report; Person-level termination | Action within 1 h (planning value) |
| **S1** | Non-consensual intimate imagery, likeness without consent, IP notices, court orders, terrorism | Platform only (Trust Desk) | Statutory windows; notice and counter-notice |
| **S2** | Harassment, hate, embodied abuse, scams, spam, ban evasion | Vendor first line, then Trust Desk; Ward Wardens in public places | Median under 24 h |
| **S3** | Charter or Ward rules (dress codes, building codes, roleplay rules) | Charter or Ward Wardens | Set by the community |

The spine's time-to-action target, a median under 24 hours, covers all classes together. Time-to-action runs from receipt of the report to the first decision, and "no action" counts as a decision.

**Sanctions ladder:** warning; mute in a place; kick; ban from a place (Charter Holding or Ward, up to 30 days from a Ward Warden); Nuisance flag; feature suspension (voice or upload); account suspension for 1, 7 or 30 days; termination of the Passport or the Person. Every action carries a reason code and the hashes of its evidence.

### The pipeline

1. **Proactive layer (AI as tooling).**
   - The Foundry checks every upload: CSAM hash-matching, likeness, fingerprinting and script analysis.
   - Classifiers run on public-place text and on speech-to-text of public voice.
   - Private Hearths and Holdings get hash-matching and report-driven review only.
   - The precedent: Roblox's open-sourced Sentinel caught 35% of detected grooming cases before any user report ([source](https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection)).
2. **Vendor first line.** A 24/7 queue in English, Portuguese and Spanish at L, adding Japanese and German at L+12. It handles S2 and escalates S0 and S1.
3. **Trust Desk.** Staff who handle policy, S0 and S1, quality audits of vendor decisions (2% sample, planning value) and final appeals.
4. **Community layer.** Charter Wardens, and the 8 Warden Posts in each Ward, paid from the Pool's 10% line.

### Team and budget

Trust and safety, policy, community and localisation is a team of 10 at L. It includes 4 Portuguese and Spanish community managers who also own localisation. The other six are planning values: a Head of T&S, a child-safety and law-enforcement liaison, a policy and regulatory lead, two Trust Desk analysts and an English community lead. Vendors cover first-line moderation and age assurance.

The vendor-and-tooling line is **US$1.50 per DAU-month, with a floor of US$1.5M a year**. Staff are counted separately.

| Scale (D.8) | DAU | 1.50 × DAU × 12 | Budget |
|---|---|---|---|
| Floor, 100K MAU | 25K | US$0.45M | **US$1.5M** (floor binds) |
| Break-even, 350K MAU | 87.5K | US$1.58M | **US$1.6M** |
| Reference, 600K MAU | 150K | US$2.7M | **US$2.7M** |

The floor binds until about 83K DAU (roughly 333K MAU), so launch-era spend per DAU is higher while norms are set.

Allocation of the floor (planning values):
- vendor first line, 24/7 in three languages: US$0.75M;
- age assurance: US$0.30M;
- classifiers, hash lists and tooling: US$0.20M;
- evidence storage, legal process and information requests: US$0.15M;
- Adult pre-publication review and external audit: US$0.10M.

For comparison, Roblox's combined infrastructure and T&S line was US$1,153.5M in 2025 ([source](https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm)).

### Evidence, logs and information requests

Ofcom has paired every substantive fine with a second fine for failing to answer information requests ([source](https://xident.io/blog/age-assurance-evidence-ofcom-information-request-second-fine-2026/)), so evidence is a product requirement:
- **Audit log.** Every enforcement action goes into an append-only log: actor, reason code, evidence hashes and timestamps.
- **Retention (planning values).** Report evidence is kept 90 days after a case closes. Cases under legal hold are kept indefinitely. Public-place chat logs are kept 30 days.
- **Information requests.** Regulators get an answer within 10 business days (planning value), from a pre-built pack covering age-assurance method and completion rate, risk review and KPI definitions.

## Appeals and Tribunals

### Path

```
Charter Warden action ──appeal (14 days)──> Tribunal (72 h SLA) ──appeal──> Trust Desk (7-day SLA, final)
Ward Warden action    ──appeal──────────────> Tribunal ─────────────────────> Trust Desk
Platform S2 action    ──appeal──────────────────────────────────────────────> Trust Desk (second human)
S0 / S1 action        ── platform-only, immediate; no community appeal; legal remedies only
```

Tribunals start at L+6 together with Ward councils. From L to L+6, appeals of Warden actions go straight to the Trust Desk under the same 7-day SLA. A Charter's ban from its **own** Holdings is freedom of association and cannot be appealed on its merits. A Tribunal may review it only when the ban had a public effect: an Estate ticket forfeited without refund, a Nuisance flag, or a report escalated to the platform.

### The Tribunal

- **Composition.** Three jurors are drawn by lot from residents with Pillar Standing or above who opted in to jury service. Each must be AV, Trust Known or above, and free of a Nuisance flag for 12 months.
- **Conflicts.** A juror may not share a Charter with either party or with the acting Warden, may not have a block relationship with either party, and may not be the Warden. Same language as the case where possible, otherwise the case is translated.
- **The draw.** It uses a published seed recorded in the Chronicle, so anyone can audit it.
- **Procedure.**
  - Jurors see the evidence with uninvolved third parties redacted.
  - Each party submits one written statement of up to 500 words.
  - The decision is by majority, with a written reason code: uphold, modify or overturn.
- **Pay and Standing.** Jurors receive a stipend from the Pool's 10% line, and jury duty earns Standing. The precedent is the Confederation of Democratic Simulators, whose Scientific Council has adjudicated since 2004 ([source](https://wiki.secondlife.com/wiki/Confederation_of_Democratic_Simulators)).
- **SLA breach.** If no decision comes within 72 hours, the case goes up to the Trust Desk automatically.

### Case state machine

```
Filed → Triaged(S0..S3) → Decided(action|no_action) → AppealWindow(14 d)
  → [Tribunal: Drawn → Deliberating → Ruled] → [TrustDesk: Reviewing → Final] → Closed
S0/S1: Filed → Escalated → Actioned+LegalHold → Reported(authority) → Closed
```

**Published each quarter:** appeal volumes, median times, reversal rates at each level, and the rate at which the Trust Desk overturns Tribunals.

**Rejected:** platform review first with an advisory resident panel (economist) and a jury only from month 18 (studio-exec); both put the community layer too late for a world built on self-rule.

## Charters, Ward councils and the Assembly

Three tiers hold real but bounded power. Decree, outcry and retreat is how Linden lost trust (Openspace 2008, the education discount 2010, the 2013 ToS) ([source](https://forums-archive.secondlife.com/356/24/291220/1.html); [source](https://thejournal.com/Articles/2010/11/03/Linden-Lab-To-End-Second-Life-Educational-Discounts.aspx); [source](https://www.hypergridbusiness.com/2013/09/outrage-grows-over-new-second-life-terms)).

### Charters

Charters rule their own Holdings within the World Charter:
- access lists and ban lists (imported intact by Charter Import);
- a fixed maturity rating;
- roles as ranks and dress or building codes;
- consent rules for their roleplay systems;
- Charter Wardens.

A Charter that owns land or a calendar must name a deputy and a succession rule (doc 03). No feature requires Charter membership.

### Ward councils

| Item | Rule |
|---|---|
| Seats and term | **5 seats, annual**, from **L+6** (six Founding Wards, so six councils) |
| Electorate | Residents whose home Ward has been this Ward for at least 60 days before polling day (planning value; it stops brigading through the 30-day home-Ward change), who hold Trust Member, have 90 days' tenure and are verified 18+ (AV). One vote per Person. |
| Candidates | Standing Regular or above |
| Method | Single transferable vote; turnout published |
| Ordinances | The Ward's rating (General or Moderate; Adult only by platform designation as a Night Ward), the building code for Ward public cells, Stage prime-hour lottery rules, Commons allocation rules within the 45-day and 80%-refund bounds, voting the Ward quiet of Keepers, and appointments to the 8 Warden and 12 Host Posts |
| Process | Draft, 7-day public comment, vote (3 of 5), then platform review within 14 days, which may refuse only on legal, safety or World Charter grounds with a written reason in the Chronicle. Then in force. |
| Limits | No ordinance may weaken the Safety Kit, the Age Module, the Never List or prices. |

Deletion rates are published per Ward; better-moderated subreddits coped better with sudden growth ([source](https://hci.stanford.edu/publications/2017/eternalseptember/eternalseptember.pdf)).

### The Assembly

| Item | Rule |
|---|---|
| Seats and term | **9 seats, annual**. The first election is at **L+12**. |
| Electorate | The same eligibility as Ward councils, across the whole world |
| Candidates | Pillar Standing plus 12 months' tenure |
| Powers | Advisory. Any published Assembly vote must be **answered in writing within 30 days**. The Assembly can demand **public review of any change that affects clients**. It receives the quarterly Census and T&S report and sits on Assembly Day (Sunday). |
| Benchmark | EVE's CSM turnout has held at 12-17% for fifteen years ([source](https://www.eveonline.com/news/view/csm-7-the-results)) |

**Public change review.** A client-affecting change is anything that touches the protocol, the Fidelity Contract, permissions, rendering of existing content or the removal of a feature. For such changes:
1. The change is published as an RFC 30 days before release (planning value).
2. If the Assembly demands a review, the RFC stays open 30 days for comment.
3. The operator answers in writing before shipping.

Security fixes may ship at once, with a review afterwards. VRChat's EAC update, which skipped this step, drew 22,000 votes in 24 hours ([source](https://www.dazeddigital.com/science-tech/article/56662/1/why-thousands-of-users-are-abandoning-the-worlds-most-popular-vr-game)).

**Rejected:** a binding council (no world has shipped one; it would put legal duties on volunteers); a Foundation board with shard-operator seats (open-web, goes with federation); a 15-seat Assembly (economist), harder to fill from the Pillar pool at L+12.

## The World Charter and Never List

The World Charter is the operator's constitution. The draft is published in March 2027 and the final text before private alpha.

| Clause | Commitment |
|---|---|
| WC1 Price notice | Any price rise, including persistence prices, needs **12 months' notice and grandfathering**. No retroactive repricing. |
| WC2 Persistence | Nothing is deleted for non-payment. A lapsed Holding is frozen for 90 days, then stored as a NAR in inventory and can be restored indefinitely. |
| WC3 Sunset covenant | Shutdown needs **12 months' notice**, then escrow release (server source under Apache-2.0) and NAR export of everything. |
| WC4 Content licence | Limited to operating the service. Any other use requires a defined affirmative opt-in. |
| WC5 Formats | Retiring a format requires a converter and 24 months' notice. |
| WC6 Voice of residents | The Assembly is answered in writing within 30 days, and public change review applies. |
| WC7 Transparency | The Census cadence, the Fee Page with its required margin, an annual audit of effective take, and the Chronicle record of operator decisions. |
| WC8 Regulation watch | When the Digital Fairness Act is published it is reviewed within 90 days, and the decision is entered in the Chronicle. |
| WC9 Human Primacy | The Human Primacy Charter (doc 07) is incorporated. |
| WC10 Amendment | Amendments need 12 months' notice and Assembly review. WC1, WC3 and the Never List are entrenched: they can be strengthened, never weakened. |

**The Never List:**
- **No crypto or NFTs.** Steam has banned blockchain games since 2021 ([source](https://www.techradar.com/news/steam-is-now-banning-all-games-that-engage-in-cryptocurrency-or-nft-trading)), and NeosVR split over crypto ([source](https://en.wikipedia.org/wiki/NeosVR)).
- **No loot boxes.** Any chance mechanic paying out something cash-out-able is gambling somewhere: SL banned wagering in 2007 and Belgium ruled loot boxes illegal ([source](https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/); [source](https://blog.promise.legal/loot-box-laws-game-developers/)).
- **No retroactive repricing.**
- **No sale of Standing or Posts.**
- **No undisclosed AI.**
- **No sale of biometrics.**
- **No sibling product.**

## Census

Census is the public metrics page and API. Second Life never published an official MAU series ([source](https://www.engadget.com/2010-07-10-the-virtual-whirl-a-brief-history-of-second-life-2009.html)), and Decentraland's 38 wallets a day against a self-reported 8,000 shows what opacity costs ([source](https://www.nasdaq.com/articles/the-final-word-on-decentralands-numbers)).

**"Active"** means a person entered, moved, and interacted with another human for at least five minutes in the period. Interaction means co-presence within 30 m with chat, voice or a shared activity. Keepers and bots never count as the other human, and alts of the same Person count as one person.

| Metric | Cadence |
|---|---|
| First-session completion; D7, D30, D90; DAU/MAU; peak and average CCU; bot share and Keeper share of occupants; retention by ladder rung | Quarterly |
| T&S KPIs: reports per 1,000 user-hours (all reports ÷ human user-hours × 1,000), median and p90 time-to-action, NCMEC reports, deletion rates per Ward, appeal reversal rates | Quarterly |
| Age-assurance completion rate by profile; adult share of spend and cash-out | Quarterly |
| Election turnout; Assembly votes and written answers | Per event |
| p95 frame time per reference device; inventory loss | Monthly |
| Revenue mix; effective-take audit | Annual |

The API (`/census/v1/{metric}?period=&ward=&language=`) returns the aggregates and their definitions. Concurrency comes with a public sampling endpoint so that third parties can reproduce it within 5%. Small cells are suppressed: no Ward or language figure is shown below 50 people (planning value). Census launches at L.

## Requirements addressed

| R | How this document addresses it |
|---|---|
| R9 | Never List (no loot boxes, crypto or NFTs); WC8 reviews the DFA within 90 days |
| R10 | Rail KYC only at cash-out; Adult Seller verification; adult-specialist acquirer for Level 2 |
| R13 | Census: documented "active", quarterly cadence, API reproducible within 5%, bot and Keeper shares |
| R15 | Warden and Host Posts per Ward; jury duty earns Standing; deputies for Charters with land or a calendar |
| R18 | Charter Import carries ban lists; imported members start at Trust New; SL status not imported |
| R19 | World Charter (12 months' notice and grandfathering, entrenched clauses), Assembly answered within 30 days, public change review, Chronicle |
| R20 | WC3 sunset covenant: 12 months' notice, escrow release under Apache-2.0, NAR export |
| R21 | Age Module: AA and AV levels, Age Vault with no stored ID images, five profiles at L plus California, Germany and Japan, feature gating, Campus-only minors, OS signals, completion rate published |
| R22 | Night Ward opt-in for AV residents; Adult goods pipeline (uploader verification, consent records, human pre-publication review); stored-value coding; switch ladder; adult share published |
| R23 | Safety Kit; Trust ranks and score; severity classes; median time-to-action under 24 h; quarterly KPIs; audit logs; information-request pack |
| R25 | Keepers never moderate and serve only as witnesses; scripted-only in Campus; excluded from "active" |
| R27 | Safety Kit fully usable by keyboard and text-to-speech in Reader |
| R28 | Campus: SSO at L+6, bulk accounts, General rating, isolation, Class Cell US$34.50, NAR export |
| R29 | Profiles for Brazil and Indonesia; vendor queues in PT/ES at L and JA/DE at L+12; Portuguese and Spanish CMs on the T&S team |
| R30 | No sibling product (Never List); T&S floor sized for the 100K MAU Floor Plan |

## Open questions

1. **The challenge age.** Does facial estimation meet Ofcom's "highly effective" bar at 18, and what buffer is accepted? The challenge age of 25 is a planning value pending vendor error data. Ofcom said in July 2026 that "tougher action is needed" ([source](https://www.lewissilkin.com/insights/2026/07/16/ofcom-warns-that-tougher-action-is-needed-on-age-assurance-following-publication-102nc4m)).
2. **Coding under VIRP.** Visa's February 2026 VIRP update requires MCC 5967 for all adult content and treats miscoding as an enforcement matter ([source](https://www.legitscript.com/regulatory-and-card-brand-compliance/adult-escort-and-dating-merchants-are-your-practices-in-line-with-virp-updates/)). Does coding Coin purchases as stored value stay defensible once Adult-tagged spend is measurable? The spine decision stands, but the rail contract signed in December 2027 must answer this in writing.
3. **Brazil and Pool weighting.** ECA Digital forbids reuse of age-verification data. Is weighting the Pool by AV status (the 0.5 for unverified accounts) a reuse? The proposed answer is that the Pool reads only the boolean, and counsel has to confirm it.
4. **The T&S budget.** The spine's US$1.50 per DAU-month sits at the bottom of the taxonomy's US$1.5-3 range, and studio-exec planned US$2. The floor covers this until about 333K MAU. If Census shows time-to-action above 24 hours at Reference scale, the per-DAU rate needs revisiting. The spine value is kept.
5. **The juror pool at L+6.** Pillar Standing may be thin outside the Founding Charters. If a Ward cannot seat three conflict-free jurors, the fallback is to draw from Pillars world-wide who speak the same language.
6. **Entrenchment of the Assembly.** "Pillar plus 12 months" at L+12 confines candidacy to alpha-era residents. This needs watching for capture by the Founding Charters.
7. **Recording voice.** Does the 60-second voice buffer comply with all-party recording-consent laws? Notice and consent at sign-up are assumed, and counsel review is needed.
8. **External uncertainty.**
   - Australia may designate social worlds.
   - The KIDS Act and KOSA may pass and pre-empt state law ([source](https://www.crowell.com/en/insights/client-alerts/house-advances-bipartisan-kids-online-safety-bill-but-senate-showdown-looms)).
   - NO FAKES may change takedown duties for avatars that resemble real people.
   - Indonesia's position on Campus is open.

## Sources

- https://about.roblox.com/newsroom/2025/08/open-sourcing-roblox-sentinel-preemptive-risk-detection
- https://about.roblox.com/newsroom/2026/01/roblox-age-checks-required-to-chat
- https://androidcentral.com/gaming/virtual-reality/meta-finally-kills-the-oculus-quest-2-facebook-account-requirement
- https://avpassociation.com/indonesia/
- https://blog.promise.legal/loot-box-laws-game-developers/
- https://cms.law/en/fra/news-information/protecting-minors-in-the-digital-space
- https://community.secondlife.com/forums/topic/415080-what-is-bloodlines/
- https://community.secondlife.com/forums/topic/533810-age-verification-in-2026/
- https://conductatlas.com/platform/stripe/stripe-restricted-businesses-list/adult-content-prohibition-and-restriction/
- https://cyberinsider.com/discord-confirms-70000-government-ids-exposed-in-third-party-breach/
- https://developer.apple.com/forums/thread/810754
- https://dl.digra.org/index.php/dl/article/download/2766/2750/2810
- https://docs.vrchat.com/docs/vrchat-safety-and-trust-system
- https://ec.europa.eu/commission/presscorner/detail/en/ip_25_1820
- https://en.wikipedia.org/wiki/NeosVR
- https://extremismterms.adl.org/sites/default/files/pdfs/2022-12/Free%20to%20Play%2007242019.pdf
- https://forums-archive.secondlife.com/356/24/291220/1.html
- https://fpf.org/blog/old-laws-new-tech-as-courts-wrestle-with-tough-questions-under-us-biometric-laws-immersive-tech-raises-new-challenges/
- https://hci.stanford.edu/publications/2017/eternalseptember/eternalseptember.pdf
- https://ispr.info/2022/02/08/meta-establishes-four-foot-personal-boundary-to-deter-vr-groping/
- https://inforrm.org/2026/03/11/ofcom-steps-up-online-safety-act-enforcement-with-two-further-age-assurance-fines-for-pornographic-platforms-alexandros-antoniou/
- https://law.ungovr.org/age/de
- https://lbc.co.uk/news/police-investigate-rape-metaverse
- https://techcrunch.com/2007/07/25/second-life-bans-gambling-following-fbi-investigation/
- https://techcrunch.com/2025/08/03/mastercard-denies-pressuring-game-platforms-valve-tells-a-different-story
- https://thejournal.com/Articles/2010/11/03/Linden-Lab-To-End-Second-Life-Educational-Discounts.aspx
- https://thenextweb.com/insider/2019/03/14/tumblr-traffic-dropped-by-nearly-100m-the-month-after-it-banned-porn/
- https://verifymy.io/resources/regulation/card-brand-requirements
- https://wiki.secondlife.com/wiki/Confederation_of_Democratic_Simulators
- https://wiki.vrchat.com/wiki/Age_Assurance
- https://www.alstonprivacy.com/california-enacts-digital-age-verification-law/
- https://www.bloomberg.com/news/articles/2025-10-29/character-ai-to-ban-children-under-18-from-talking-to-its-chatbots
- https://www.cbc.ca/lite/story/1.6148524
- https://www.computerweekly.com/feature/The-UKs-Online-Safety-Act-explained-what-you-need-to-know
- https://www.crowell.com/en/insights/client-alerts/house-advances-bipartisan-kids-online-safety-bill-but-senate-showdown-looms
- https://www.dazeddigital.com/science-tech/article/56662/1/why-thousands-of-users-are-abandoning-the-worlds-most-popular-vr-game
- https://www.demarest.com.br/en/eca-digital-entrada-em-vigor-em-17-de-marco-de-2026/
- https://www.engadget.com/2010-07-10-the-virtual-whirl-a-brief-history-of-second-life-2009.html
- https://www.esafety.gov.au/about-us/industry-regulation/social-media-age-restrictions/faqs
- https://www.eveonline.com/news/view/csm-7-the-results
- https://www.fonoa.com/blog/dac7overview
- https://www.govtrack.us/congress/bills/119/s4591
- https://www.hlc.com/en/publications/the-longawaited-eu-guidelines-on-article-281-dsa-what-online-platforms-must-know
- https://www.hypergridbusiness.com/2013/09/outrage-grows-over-new-second-life-terms
- https://www.legitscript.com/regulatory-and-card-brand-compliance/adult-escort-and-dating-merchants-are-your-practices-in-line-with-virp-updates/
- https://www.lewissilkin.com/insights/2026/07/16/ofcom-warns-that-tougher-action-is-needed-on-age-assurance-following-publication-102nc4m
- https://www.mayerbrown.com/en/insights/publications/2026/04/enforcement-of-brazils-eca-digital-introduces-new-obligations-for-companies
- https://www.meta.com/legal/quest/eye-tracking-privacy-notice/
- https://www.nasdaq.com/articles/the-final-word-on-decentralands-numbers
- https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content
- https://www.pearlcohen.com/fifth-circuit-stays-injunctions-against-texas-app-store-accountability-act/
- https://www.sagaftra.org/take-it-down-act-notice-and-removal-obligations-now-effective
- https://www.sec.gov/Archives/edgar/data/1315098/000131509826000024/rblx-20251231.htm
- https://www.techradar.com/news/steam-is-now-banning-all-games-that-engage-in-cryptocurrency-or-nft-trading
- https://www.thesixthaxis.com/2025/07/24/itch-io-delists-all-adult-nsfw-content-due-to-pressure-from-payment-processors-and-collective-shout/
- https://xident.io/blog/age-assurance-evidence-ofcom-information-request-second-fine-2026/
