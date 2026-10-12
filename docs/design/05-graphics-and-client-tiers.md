# 05 · Graphics and client tiers

Design document 05 of the nolife set, written 2026-10-09 against the design spine (`00-design-spine.md`: C.3, C.5, B.4 items 4 and 11, D.4) and the failure taxonomy (R1-R30). No web search was used. External facts carry the URL cited in the research briefs or panel proposals, and "(unsearched)" marks prior knowledge. Values marked *(spine)* are canonical. Values marked *(this doc)* are new detail proposed for the March 2027 Fidelity Contract draft.

## Summary

nolife must look like a 2026 Unreal title on the most common gaming PC, run in a browser on a school laptop, and keep doing both as uploads accumulate. Second Life failed at the last part: no asset carried a budget, so the hardware floor rose with the catalogue. The **Fidelity Contract** specified here stops that.

Every upload passes through the **Foundry**, which builds Reference, Lite and Compat versions, an impostor, a Scene Weight and a Fidelity Rank. Clients enforce line-item frame budgets and degrade over-budget scenes in a published order, never hiding them.

Three first-party clients ship at launch:
- **Lantern**, native, on Unreal 5.8;
- **Ember**, in the browser, on Babylon.js;
- **Reader**, text only.

Mobile follows at L+9 and an optional VR view at L+30. Unreal only renders. Its licence is gated on 30 September 2027, and the cost of leaving it is US$16M over 21 months.

## The Fidelity Contract

The Fidelity Contract is a published, versioned document backed by server-enforced rules. For every asset on every device it answers two questions: what will this look like, and what will it cost?

It answers the one Second Life root cause with no counter-example in the corpus. Land Impact was last changed in November 2016 ([source](https://modemworld.me/2016/11/03/lab-reveals-li-prim-allowance-changes-in-second-life-in-full)) and no asset carries a per-tier budget. By January 2025 about half of Linden's users lacked high-end machines ([source](https://modemworld.me/2025/01/02/)), and in 2014 its CEO had named "high client performance requirements" a second-login blocker ([source](https://modemworld.me/2014/06/29/ebbe-altberg-on-user-retention-now-and-in-the-future/)). The UGC worlds that work all set budgets: VRChat ranks avatars ([source](https://docs.vrchat.com/docs/vrchat-202115)), Roblox sets quality levels ([source](https://devforum.roblox.com/t/rdc26-what-we-announced/4865880)), and UEFN imposes Fortnite's budgets ([source](https://uefncentral.com/blog/uefn-vs-unreal-engine-5-differences)).

| # | Clause | Enforced by |
|---|---|---|
| FC-1 | Every asset has a package per tier. Clients receive only the Foundry's package for their tier, never a source asset. | Foundry, Vault |
| FC-2 | Reference is a ceiling, not a floor *(spine)*. Creators author once; the Foundry generates the Lite and Compat versions. A creator may supply a hand-made override, which must pass the same checks. | Foundry |
| FC-3 | Budgets are checked at upload (per-asset limits), at placement (the Holding's Weight allowance) and at render (per-view caps and the frame governor). | Foundry, Grid, clients |
| FC-4 | Over budget means degrade, never hide. Content is hidden only for safety reasons: block, mute, a failed check or a rating gate. | Clients |
| FC-5 | The owner is shown the cause of any degradation *(spine)*. | Clients, Workshop |
| FC-6 | A buyer always sees their own item in its tier version *(spine)*. | Clients, Bazaar |
| FC-7 | The hardware floor never rises *(spine)*. No content change can tighten Compat budgets or the Compat device list, and every accepted asset keeps a valid package on every tier. | Foundry, change control |
| FC-8 | The p95 frame time on each reference device is published monthly in Census *(spine)*. | Census |

**Change control.** The draft is published in March 2027 *(spine)* and v1 freezes at alpha (January 2028). Client-affecting changes are posted in the Chronicle 30 days ahead, and the Assembly can demand public review (C.8). Weight and Rank are frozen per asset version by the pipeline that accepted it. A new formula applies only to new uploads, and a Holding whose total would rise keeps its old one: the Never List's "no retroactive repricing", applied to builds.

## Tiers and reference devices

| Tier | Device classes *(spine)* | Client | Rendering | Lighting |
|---|---|---|---|---|
| **Reference** | RTX 4060/5060 class, 8 GB | Lantern (Windows, macOS) | Nanite, Substrate, virtual shadow maps, MegaLights, DLSS/FSR/XeSS | Lumen GI and reflections |
| **Lite** | Steam Deck and Switch 2-class GPUs, M1 Macs, Snapdragon 8 Gen 2/A16 phones, desktop WebGPU; performance classes only, no console port | Lantern (desktop at L; iOS and Android at L+9); Ember on WebGPU | LOD chains (no Nanite), metallic-roughness PBR, SSR | Lumen Lite on Lantern desktop; Foundry bake sets plus probes elsewhere |
| **Compat** | WebGL2, low-end Android, integrated GPUs | Ember | Forward renderer, atlased materials, 256 m draw distance | Baked; one cascaded shadow |
| **Stream** | Compat devices; a capped funnel, not a tier | Lantern on a cloud GPU | As Reference | As Reference |

The anchors follow the market. The most common Steam GPUs are the RTX 5070, then the 5060 (4.20%), 5060 Ti and 4060 (3.72%) ([source](https://store.steampowered.com/hwsurvey/Steam-Hardware-Software-Survey-Welcome-to-Steam); [source](https://mixed-news.com/en/steam-september-2026-hardware-survey-rtx-5070-32gb-ram/)), so an 8 GB xx60 card meets the Reference ceiling. Epic's Lumen Lite targets 60 fps on Switch 2 ([source](https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available)). WebGPU is still missing on Linux Firefox, Samsung Xclipse and older Android ([source](https://github.com/gpuweb/gpuweb/wiki/Implementation-Status)), hence Compat.

Lantern installs only at Lite or above, and anything below goes to Ember Compat, so QA covers four client-tier pairs. **Compat is never cut** *(spine, B.4 item 4)*, and in the spend sequence it comes before Reference polish.

**Reference device lab *(this doc)*.** These devices are behind the monthly p95 publication.

| Tier | Devices |
|---|---|
| Reference | RTX 4060 desktop; RTX 5060 desktop; RTX 4060 Laptop; Radeon RX 7600 |
| Lite | Steam Deck OLED; MacBook Air M1 8 GB (Lantern; Ember in Safari); Snapdragon 8 Gen 2 phone and iPhone 15 (A16) (Ember at L, Lantern at L+9); RTX 3050 laptop (Ember in Chrome) |
| Compat | Intel UHD 620 laptop (Chrome, WebGL2); Linux Firefox on an AMD integrated GPU; mid-range Samsung Exynos phone; a Campus Chromebook |

**Tier assignment.**

```
PROBE (Lantern: D3D12/Metal SM6; Ember: navigator.gpu?) ──> CALIBRATE
CALIBRATE: Landing hall with 40 avatars (Lantern 20 s, Ember 8 s);
           pick the highest tier where p95 <= 0.9 x budget ──> ASSIGNED(tier)
ASSIGNED ──(user override, either direction)──> ASSIGNED(tier')
ASSIGNED ──(governor held at D5 for 5 min)──> OFFER_STEP_DOWN (never forced)
ASSIGNED ──(driver, OS or browser update)──> PROBE
```

## Frame budgets

The D.4 tables are reproduced below unchanged *(spine)*.

| Tier | Output | Frame budget | Full avatars | Lighting |
|---|---|---|---|---|
| Reference | 1440p from 960p internal (DLSS/FSR/XeSS Quality), 8 GB RTX 4060/5060 | 16.7 ms (60 fps) | 100 | Lumen GI and reflections, MegaLights, virtual shadow maps, Substrate |
| Lite | 1080p | 16.7 ms (60 fps) | 40 + 60 impostors | Lumen Lite or lightmaps + probes; SSR |
| Compat | 720p, 256 m draw distance | 33.3 ms (30 fps) | 20 + 2D impostors | Baked; one cascaded shadow |
| VR view (L+30) | Quest 3 / OpenXR | 13.9 ms (72 Hz) | 40 | Lite settings |

**Reference GPU (ms):**

| Nanite visibility + base | Lumen GI | Lumen reflections | VSM | MegaLights (≤32 shadowed lights) | 100 avatars | Translucency + Niagara | Post + upscale | UI | Total |
|---|---|---|---|---|---|---|---|---|---|
| 3.5 | 3.0 | 1.2 | 2.0 | 1.5 | 3.0 | 1.0 | 1.3 | 0.2 | 16.7 |

**Reference VRAM (8 GB):** textures 2.5 GB, Nanite 1 GB, avatars 1.5 GB, caches and targets 1.5 GB, headroom 1.5 GB.

**Lite (ms):** base 5.0, lighting 3.0, shadows 1.5, avatars 4.0, translucency 1.0, post and UI 1.2, headroom 1.0.

**Compat (ms):** forward 12, shadow 4, avatars 8, post 3, headroom 6.

**Reference per-view caps:** 20M visible source triangles, a 2.5 GB streaming pool, 32 shadowed lights and 300 skinned meshes.

Caps for the lower tiers:

| *(this doc)* | Lite | Compat |
|---|---|---|
| GPU memory | 3 GB (textures 1.0, avatars 1.0, meshes 0.5, targets 0.3, headroom 0.2) | 1 GB (textures 0.4, avatars 0.16, meshes 0.15, targets 0.1, headroom 0.19) |
| Visible triangles after LOD | 4M | 1M |
| Shadowed lights | 8 | 1 (the sun) |
| Skinned meshes | 120 | 40 |

The VR planning split, from the engine-architect proposal, is: base 4.0, shadows 1.5, 40 avatars 4.0, translucency 1.0, post 1.5 and headroom 1.9, for 13.9 ms. It stands until measured.

Upscaling sits behind one abstraction over DLSS, whose transformer model left beta in June 2025 ([source](https://github.com/NVIDIA/DLSS/releases)), FSR 4.1 on RDNA 3 ([source](https://github.com/GPUOpen-LibrariesAndSDKs/FidelityFX-SDK/releases)) and XeSS ([source](https://github.com/intel/xess/releases)). Frame generation is a user option, and the published fps count only rendered frames.

### The frame governor and the degrade order

Each client runs a governor. It measures GPU time with timestamp queries and moves through the spine's degrade order one level at a time.

| Level | Action *(spine order)* | Detail *(this doc)* |
|---|---|---|
| D0 | Nominal | Avatars in the "focus ring" (within 10 m; up to 10 on Reference, 5 on Lite, 2 on Compat) may show worn attachments above the tier budget, paid for from the headroom line |
| D1 | Distant avatars become impostors | The full-avatar cap falls farthest first, in steps of 10, 5 or 2 by tier, down to a floor of 10, 8 or 6 |
| D2 | Fewer shadowed lights | Reference 32 → 16 → 8; Lite 8 → 4 → 2 |
| D3 | Lower off-focus LODs | LOD bias +1 beyond 15 m and outside the central 30° |
| D4 | Fewer translucency effects | Particle budget halved, then quartered; volumetric fog off |
| D5 | Over-budget attachments switch to their tier version | Focus-ring avatars switch to their budgeted Outfit Bake |

Impostors start at 30 m at every level *(spine)*.

**Stepping rules.** The governor steps down when the rolling p95 over 120 frames runs more than 5% over budget for 2 s. It steps up after 10 s below 85% of budget, and changes at most one level every 2 s. It also attributes cost to the Holdings and avatars in view. A Holding that pushes visitors to D2 or beyond for more than 5% of visitor-minutes in a week gets a **Fidelity Report** in Workshop, which names the assets responsible.

**Publication.** Census publishes the p95 for each lab device in three canonical scenes every month: the Landing hall with 40 avatars, a Friday Open Stage at 100 presence, and a Cell at full Weight. R2's test, at least 60 fps on Lite at 100 presence, is the Open Stage scene run on the Lite lab devices.

## Asset budgets, Scene Weight and Fidelity Rank

**Avatar budgets *(spine)*:**

| Tier | Triangles | Materials | Bones | Texture memory | Attachments |
|---|---|---|---|---|---|
| Reference | 120,000 | 12 | 300 | 80 MB | 24 |
| Lite | 35,000 | 6 | 120 | 24 MB | 12 |
| Compat | 20,000 | 2 (atlased) | 75 | 8 MB | 6 |

Compat's 20,000 triangles match VRChat's Quest "Very Poor" threshold ([source](https://docs.vrchat.com/docs/vrchat-202115)). Avatars over a tier's cap get that tier's version; they are never hidden.

**Per-asset hard limits *(this doc)*:**
- static mesh source: 2M triangles (the Nanite source);
- skinned mesh source: 240,000 triangles (2× the Reference avatar budget);
- texture maps: 4096² source, with Lite packages capped at 2048² and Compat at 1024²;
- lights: 8 per object.

### Scene Weight

Scene Weight replaces Land Impact *(spine)*. It is measured on the **Lite** packages, because Lite is the tier that constrains the most devices. Extra Reference detail costs no Weight; it is paid for in bytes, through the Holding's storage quota (rent on bytes kept). Weight bounds what every tier must draw, and bytes bound what Reference may carry on top.

```
Weight(object) = ceil( T/250 + X/64KiB + 10·M + 250·Ls + 20·Lu + 10·Pd + 100·E )
  T  = Lite LOD0 triangles     X  = unique Lite texture bytes (deduplicated by Vault hash per Holding)
  M  = unique materials        Ls / Lu = shadowed / unshadowed lights
  Pd = dynamic physics bodies  E  = particle or translucent emitters
```

The coefficients are calibrated *(this doc)* so that a full-Weight Cell, viewed from its centre on the Lite lab devices with 40 avatars present, fits the Lite base, lighting and shadow lines (9.5 ms). They are re-fitted only under change control.

A worked example of a full Cell:

| Component | Quantity | Weight |
|---|---|---|
| Triangles | 1.5M | 6,000 |
| Textures | 600 MB | 9,600 |
| Materials | 300 | 3,000 |
| Shadowed lights | 8 | 2,000 |
| Unshadowed lights | 100 | 2,000 |
| Dynamic bodies | 200 | 2,000 |
| Emitters | 20 | 2,000 |
| **Total** | | **28,600 of 30,000** |

Allowances *(spine)*:

| | Hearth | Hearth+ | Commons plot | Plot S | Plot M | Cell | Domain |
|---|---|---|---|---|---|---|---|
| Weight | 1,000 | 4,000 | 900 | 4,000 | 10,000 | 30,000 | 120,000 |

Script and physics budgets live in documents 04 and 06.

### Fidelity Rank

| Rank *(spine)* | Rule *(this doc)* |
|---|---|
| Excellent | Fits the Lite budget as authored |
| Good | Fits the Reference budget, and the Lite and Compat versions are within the perceptual threshold (silhouette error ≤2 px at 10 m, 1080p) |
| Fair | Fits the Reference budget, but a derived version shows visible loss |
| Heavy | Exceeds the Reference budget on at least one axis, or one object takes more than 5% of a Holding's Weight. Reference viewers see the reduced version unless they set "show Heavy" |

Rank appears in three places: on Bazaar listings, next to Foundry previews of the item on all three tiers (FC-6); on the Workshop's live meter; and in an avatar's inspect panel. A viewer can set a "full detail up to rank" filter, and avatars above it show their tier version.

Rank is **not** a discovery signal; discovery ranks places by distinct returning humans (C.2). The platform sets no minimum rank. Charters and councils may put a rank in their building codes (B.4 item 11).

## The Foundry pipeline

Every upload, import and Blocks edit passes through the Foundry *(spine, C.3)*:

| # | Stage | Output | Failure |
|---|---|---|---|
| 1 | Normalise glTF 2.0, VRM 1.0, OpenUSD, MetaHuman and Ferry formats to 1 unit = 1 m, metallic-roughness PBR | Canonical source | Reject with a reason code |
| 2 | Fingerprint against the catalogue (CopyBot defence) | Attribution record | Hold for IP review |
| 3 | Safety: CSAM hashing, the likeness consent registry, script static analysis, human pre-publication review of Adult-tagged items | Clearance | Quarantine (platform only) or hold |
| 4 | Four-level LOD chain and octahedral impostor | LOD0-3 and an impostor atlas | Reject if degenerate |
| 5 | Collision by automatic convex decomposition, or a hull the creator supplies | Physics shapes | Box hull and a warning |
| 6 | Transcode to BC7, ASTC, ETC2 and KTX2/Basis (Ember) | Texture sets per tier | |
| 7 | Bakes-on-Mesh atlasing | Tier atlases | |
| 8 | Lite and Compat bakes: Substrate mapped to metallic-roughness, lightmap bake sets per Holding | Tier packages | |
| 9-10 | Scene Weight and Fidelity Rank | Frozen values | |
| 11 | Licensed engine stage: Nanite cook (without the licence, Reference uses the LOD chain) | Derived cache | Retry; LOD0 served meanwhile |
| 12 | Sign the manifest and publish to Vault, content-addressed | Manifest hash | |

The LOD chain *(this doc)* is LOD0 = source; LOD1 = 25% (Lite near); LOD2 = 6.25% (Lite far, Compat near); LOD3 = 1.5% (Compat far). The impostor beyond that has 8×8 views in a 1024² atlas, or 512² on Compat.

```
RECEIVED → NORMALISED → SCREENED ─┬→ BUILT → MEASURED → PUBLISHED ⇢ NANITE_READY
                                  ├→ HELD (IP or Adult review) → SCREENED
                                  ├→ QUARANTINED (CSAM or legal; platform only)
                                  └→ REJECTED (reason code to the uploader)

AssetManifest { source_hash, pipeline_version, creator_passport, provenance_c2pa,
  ai_assist, export_bit, maturity, tiers{reference,lite,compat: Pkg}, impostor_hash,
  collision_hash, scene_weight, fidelity_rank, nanite_hash? /* derived, never source */ }
```

**Latency.** Targets at p95 *(this doc)*: 90 s for a prop, 5 min for a wearable, and 15 min for a Holding bake set once its debounce ends. Until stage 3 has passed, only the uploader sees a client-side provisional preview.

**Cost.** The Foundry costs US$0.01 per asset *(spine)*. Engine-architect estimated US$0.005-0.02 at spot compute of about US$0.07 per vCPU-hour ([source](https://edgegap.com/pricing)), and US$0.02-0.05 per plot bake. A Holding is rebaked at most hourly, and only if its Weight changes by more than 1% or a light moves.

**Format policy (R3).** Runtime formats are glTF 2.0 and VRM 1.0, and scenes use OpenUSD, which has a standards path through AOUSD's 2026 Core Spec ([source](https://www.linuxfoundation.org/press/aousd_prmarch2026)). The platform funds conversion, and retiring a format requires a converter and 24 months' notice *(spine)*.

Two technologies are absent at L:
- neural texture compression, whose SDK is stamped "DO NOT SHIP" ([source](https://github.com/NVIDIA-RTX/RTXNTC));
- Gaussian splats, which carry appearance only, with no collision or relighting ([source](https://www.polyvia3d.com/guides/gaussian-splatting-unity-unreal)), and whose reference training code is non-commercial ([source](https://github.com/aras-p/UnityGaussianSplatting)).

Both are reviewed at L+12.

## Lighting, skies and keeping UGC beautiful

**The lighting decision *(spine, B.4 item 11)*:**

| Who | Owns | Rule |
|---|---|---|
| Ward council | Sky, time of day and weather | Fixed time, Ward local time, or a cycle |
| Holding owner | Their own sky | Applies inside the Holding, blended over 16 m at the boundary |
| Any resident | Personal photo sky | Visible only to the person who sets it |
| Creators | Full-bright | Survives as a capped Unlit/Emissive material |
| Legacy content | Its appearance | Displays as imported; Relight is opt-in |
| Charters and councils | Building codes for their own land | The platform sets none |

**Sky resolution.** The sky follows the camera's position. A personal photo sky wins over the Holding sky, which wins over the Ward sky. This is EEP's model, minus the per-parcel presets that fought each other inside a single place.

A Sky is a USD asset: sun and moon, sky model, clouds, fog, an exposure range and a grading LUT. Ferry exports EEP and Windlight settings to the same asset (C.9).

**Bake sets *(this doc)*.** Each sky a Holding uses gets four keyframes (dawn, noon, dusk and night) with baked indirect light and probes. Lite and Compat blend between keyframes while the sun stays dynamic. A personal photo sky snaps to its nearest keyframe on Lite and Compat, and renders in full on Reference and in Darkroom.

**Full-bright *(this doc)*.** Full-bright survives as two capped modes:

| Mode | Behaviour | Cap |
|---|---|---|
| **Unlit** | Base colour shown relative to the current exposure, so it reads the same at noon and at night | ≤1.0 of exposure-relative white; no bloom |
| **Emissive** | Physical luminance; feeds Lumen on Reference, and the bakes when static | 5,000 cd/m²; bloom allowed |

Club neon and signage survive; the halo that blows out a whole scene does not.

**Legacy display.** Ferry rebuilds prims, sculpts and llmesh exactly (C.9), and legacy materials map as follows:

| Second Life | nolife |
|---|---|
| Diffuse and tint | Base colour |
| Legacy normal map | Normal |
| Specular map, glossiness, environment | A "Legacy" model: Substrate specular on Reference; an F0 and roughness approximation on Lite and Compat |
| Full-bright / Glow | Unlit / Emissive (capped) |
| Alpha blend, mask, emissive mask | glTF alpha modes |
| SL PBR (glTF) | Native |

**Relight** is opt-in. It infers roughness and metalness, bakes ambient occlusion and can request a Nanite cook. The owner compares the result side by side before accepting it, and can always revert, because Vault keeps the original. Second Life made PBR grid-wide only in November 2023 ([source](https://modemworld.me/2023/11/28/)), and its Mirrors render only the probe nearest the camera ([source](https://wiki.secondlife.com/wiki/Mirrors)).

**Beauty by defaults, not mandates:** one scale (1 unit = 1 m, Blocks snap to 5 cm, imports flagged); PBR validation that warns rather than rejects; a free kit library of Reference-grade materials, props, foliage and light rigs; Blocks compiled to Nanite-cooked meshes; a live rank meter and three-tier preview in Workshop; Ward-owned skies; and Darkroom.

## Avatars: Common Body, atlasing, impostors

The **Common Body** is open-licensed and first-party, with realistic and stylised variants, on a VRM 1.0 skeleton with a MetaHuman-compatible face rig and a published Bento table *(spine)*. The avatar pipeline is owned because the rented layer collapsed: Ready Player Me's APIs closed on 31 January 2026 ([source](https://variety.com/2025/digital/news/netflix-acquires-ready-player-me-games-avatar-creation-1236612915/)). MetaHuman output can be imported because its licence opened to any engine in June 2025 ([source](https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/)).

**Specification *(this doc)*.** Body and head use 45,000 / 14,000 / 7,000 triangles (Reference / Lite / Compat), leaving the rest of each budget for clothing. Height runs 1.55-1.95 m via morphs, and a published fitting cage lets clothing follow the shape sliders. Skeletons: Reference 300 bones with the face driven by MetaHuman-style control curves (webcam capture on-device); Lite 120 (VRM humanoid plus springs, face on morphs); Compat 75. Bento (133 bones, unsearched) maps through the published table, `nolife-bento` keeps the wing, tail and face bones VRM lacks, and VRM 0.x is migrated ([source](https://vrm.dev/vrm1/)).

**Outfit Bake (server-side Bakes-on-Mesh).** Every outfit change triggers a bake that composites skin, tattoo, clothing and alpha layers into per-tier atlases, merges rigid attachments into one skinned mesh where they exceed the cap, prunes bones, and emits a look descriptor and a crowd proxy. Bakes are cached by outfit hash, so identical outfits share one. The targets are p95 ≤20 s, at most 60 bakes per account per hour, and ≤US$0.002 per bake *(this doc)*. The wearer sees a client-side composite immediately; everyone else sees the previous bake until the new one lands.

| Tier *(this doc)* | Body and head atlas | Attachments | Total |
|---|---|---|---|
| Reference | 2 × 2048² × 3 maps, BC7 (≈34 MB) | ≈46 MB | 80 MB |
| Lite | 2048² × 2 maps, ASTC 6×6 (≈5 MB) | ≈19 MB | 24 MB |
| Compat | 1024² base colour + normal, ETC2/EAC (≈2.8 MB) = material 1 | 1024² atlas (≈2.8 MB) = material 2 | ≈5.6 of 8 MB |

**Impostors.**

| Form | When | Content |
|---|---|---|
| Full avatar | Within 30 m and inside the tier cap (100 / 40 / 20) | Tier package |
| Crowd proxy (Reference, Lite) | Beyond 30 m or over the cap | A 2,000-triangle decimation of the *actual* outfit: 256² atlas, 24 bones, vertex-animation clips for walk, sit, idle and dance |
| 2D impostor (Compat) | Beyond 30 m or over the cap | Cards rendered from the proxy at 8 angles, 128² each |

Impostors keep outfit colour, silhouette and role badge *(spine)*, so a DJ, Host or Warden reads across a plaza. Keepers keep their "artificial" badge in every form (C.7), which carries the EU AI Act Article 50 disclosure to any distance ([source](https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/)).

Full-render priority: people you are interacting with (voice, IM, consent action), then friends and Charter members, then Hosts and Wardens on shift, then the nearest. The look descriptor is sent only when an outfit changes. Pose travels at 10 Hz within 30 m and 5 Hz beyond (D.5), inside the 200 kbps cap.

```
LookDescriptor (≤64 B) { outfit_hash:16B; palette: 4×RGB565; height_cm, width_cm: u16;
  badges: 2×u16; flags: keeper|stand_in|rating; anim_set: u8; reserved }
```

## Clients: Lantern, Ember, Reader, mobile, VR, Stream

| Client | Engine | Platforms | Tiers | Building | Launch team |
|---|---|---|---|---|---|
| **Lantern** | UE 5.8, rendering only | Windows and macOS at L; iOS and Android at L+9 | Reference, Lite | Full Workshop | 12 |
| **Ember** | Babylon.js; WebGPU with WebGL2 fallback | Browsers | Lite, Compat | None at L; full economy | 5 |
| **Reader** | No renderer | Desktop, with screen readers | n/a | None | 2 |
| **Stream** | Lantern on a cloud GPU | Compat devices | Reference image | None | Lantern and Grid |

**Lantern** defaults to the consumer interface, with Workshop as a separate mode (R26). Reference uses Substrate (production-ready since 5.7) and MegaLights (production-ready in 5.8) ([source](https://www.unrealengine.com/news/unreal-engine-5-7-is-now-available); [source](https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available)), and Lite desktops run Lumen Lite. In the mobile builds at L+9 *(spine)*, the governor runs before any thermal fallback, and a 30 fps battery mode is only ever the user's choice.

**Ember** is the zero-install Landing entry, and calendar links (iCal, ActivityPub) open it straight into an event. It loads Compat packages first and upgrades to Lite, targeting *(this doc)* an interactive Landing hall in ≤30 s on 25 Mbps from ≤60 MB. Babylon.js (9.30.0 on 8 October 2026 ([source](https://github.com/BabylonJS/Babylon.js/releases))) is pinned and upgraded quarterly. Safari 26 brings WebGPU to iOS ([source](https://github.com/gpuweb/gpuweb/wiki/Implementation-Status)), so phones reach Lite in the browser before L+9.

**Reader** succeeds Radegast, which has had no release since February 2022 ([source](https://modemworld.me/2022/10/18/2022-viewer-release-summaries-week-41/)). It offers chat, IM, inventory, teleport, an object list, voiced GPS, speech-to-text, text-to-speech and keyboard-only use. Object descriptions are drafted by the Foundry, editable by the creator and tagged as AI-assisted (C.7 tooling). It ships with an XAG 119/GAG checklist ([source](https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119)) and a funded maintainer, for communities such as Virtual Ability's 1,000-1,300 members ([source](https://virtualability.org/about-us)).

**Look parity.** Ember Lite and Lantern Lite use the same packages, bake sets, tonemapping LUT and exposure model. Each release renders 40 golden scenes on both, and CI fails if they differ by more than a published perceptual threshold. This answers the feasibility panel's concern about consistency between the two renderers.

**VR view (L+30, optional).** OpenXR on desktop Lantern, with Quest 3 at 72 Hz tethered to a PC and no native Quest port (B.3). It uses Lite settings, 40 full avatars, and seated, snap-turn and vignette options. Eye and face tracking stay on the device ([source](https://www.meta.com/legal/quest/eye-tracking-privacy-notice/)). It is never required for identity or inventory; only 1.77% of Steam users had a headset connected in January 2026 ([source](https://rec0ded88.com/statistics/vr-gaming-headset-ownership/)).

**Stream.** Stream is a capped funnel *(spine)*. Each new account on a Compat device gets 2 free hours, at a published cost of US$1.75 per hour, and total spend is capped at 5% of infrastructure. The hourly figure is an unsearched extract on Project Zero ([source](https://modemworld.me/tag/project-zero/)). Raw GPU cost runs about US$1 per user-hour ([source](https://thegabmeister.com/p/unreal-pixel-stream-aws/)), against GeForce NOW's US$19.99 a month with a 100-hour cap ([source](https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now)).

```
monthly_stream_hours = 0.05 × monthly_infrastructure_budget ÷ 1.75
  Floor (US$0.9M/yr):      0.05 × 75,000 ÷ 1.75  ≈ 2,143 h (~1,070 newcomers)
  Break-even (US$3.1M/yr): 0.05 × 258,333 ÷ 1.75 ≈ 7,381 h
```

An exhausted pool pauses the offer until next month, and hours are never sold (B.3). Census publishes cost per retained user (D30 of streamed against non-streamed Compat newcomers). Two providers are contracted, because Firestorm Zero closed after a provider-forced migration ([source](https://modemworld.me/2025/06/27/)); Epic's Pixel Streaming infrastructure supports 5.8 ([source](https://github.com/EpicGames/PixelStreamingInfrastructure/releases)).

**Third-party clients.** The protocol is documented at L, and certification opens at L+24 *(spine)*; Firestorm, not Linden's viewer, carried SL ([source](https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/)). A certified client receives only tier packages, honours the Export bit, renders Keeper badges and implements the Safety Kit.

The newcomer team owns first-session completion (≥60%). Landing halls use ≤50% of their Weight allowance, so they hold 60 fps on Lite and 30 fps on Compat.

## Engine, licence and exit

| Boundary | Rule | Protects |
|---|---|---|
| Format | The engine never sees a creator .uasset. The source of truth is glTF, VRM or USD in Vault; Nanite data is a derived cache | Content survives an engine change |
| Simulation | Cells are headless C++/Rust with Jolt and Luau, and clients predict with the same Jolt build (C.6) | Server costs stay off Epic's terms |
| Second renderer | Ember is in production from L | Losing Unreal costs Reference, not the world (B.4 item 4) |
| Protocol | Documented at L | Any renderer can be a client |

**Licence.** nolife needs a custom platform licence, budgeted at **3% of gross** *(spine)*: US$0.3M, 0.7M and 1.3M a year at the D.8 scales. Engine-architect reports the standard terms as 5% of gross above US$1M (unsearched), which is the wrong shape for a business that lives on rent. The licence must cover:
1. headless cloud cooking of user uploads, which the feasibility panel flagged;
2. shipping an in-world editor;
3. royalty terms that exclude rent and subscriptions, or charge them a flat rate;
4. MetaHuman-compatible rigs.

**Gate.**

```
30 Sep 2027 ─┬─ signed ──> Lantern ships Reference + Lite at L; Foundry stage 11 on
             └─ unsigned ─> FALLBACK: Lantern ships Lite on the web stack (Babylon in a
                            native shell); Reference waits; stage 11 stays off (LOD
                            chains already serve Reference); the 12-person Lantern team
                            moves to shell and parity work; negotiation reviewed quarterly
```

The fallback loses Nanite, Lumen, MegaLights and Substrate. It keeps every asset, every budget, Ember, Reader and the launch date.

**Exit.** Leaving Unreal costs **US$16M over 21 months** *(spine; a planning value)*, while Ember carries the world. An indicative breakdown *(this doc)*:

| Line | US$M |
|---|---|
| Renderer team: 30 FTE × 21 months at US$150K loaded | 7.9 |
| Rendering middleware and contractors | 4.0 |
| Device lab, QA, certification | 1.6 |
| Running both Lantern stacks during the overlap | 2.5 |
| **Total** | **16.0** |

**Fallback renderer.** The fallback is Godot 4.x, which uses Jolt by default but has no Nanite or Lumen equivalent ([source](https://www.phoronix.com/news/Godot-4.6-Released)), or an in-house renderer. Unity 6.3 was rejected as the primary engine for the same missing features ([source](https://unity.com/blog/unity-6-3-lts-is-now-available)). Meta's Horizon Engine switch shows how an engine change strands content ([source](https://developers.meta.com/horizon/blog/meta-horizon-engine-at-a-glance)).

**UE6.** Epic calls 5.8 the final major UE5 release ([source](https://gamesbeat.com/epic-games-launches-unreal-engine-5-8/)). One unverified report puts UE6 Early Access in late 2027 ([source](https://tech-insider.org/unreal-engine-6-state-of-unreal-2026/)). The UE6 decision is documented at L+12 *(spine)*, and it is a renderer migration behind the format boundary, not a content migration.

## Darkroom

Darkroom is the world-owned photo mode. It farm-renders any public place *(spine)*, so the image of nolife that circulates is always its best.

**Flow.**
1. The resident places a camera and submits a request.
2. Darkroom validates it: the place is public or the requester's own, the rating gate is passed, and quota remains.
3. It snapshots the place's objects and sky from the Entity Store.
4. It renders with Lantern Reference at offline settings: 4× supersampling, high-quality Lumen, up to 8K.
5. It attaches the manifest and credits.
6. It delivers the image to inventory, with a share link.

**Rules.**
- **Price.** 10 free renders a month, then 10 Coin each *(spine)*. A render takes about 60 GPU-seconds, roughly US$0.02 at about US$1 per GPU-hour ([source](https://thegabmeister.com/p/unreal-pixel-stream-aws/)).
- **Avatars.** Excluded by default. The requester may appear; others appear only after a consent prompt (the Safety Kit pattern). Blocked users never appear, and Keepers keep their badge.
- **Sky.** Ward, Holding or the requester's personal photo sky.
- **Credits and provenance.** A sidecar credits the creators of every item covering more than 0.5% of the frame, with Bazaar links (SL's photo-credit custom), and a C2PA-style manifest doubles as a machine-readable mark ([source](https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content)).
- **Rating.** Night Ward renders need the Night Ward check, are tagged Adult and never become General directory images.
- **Uses.** Monthly directory images and the Ephemeral Ward's on-camera erasure. Civic Calendar events get queue priority; delivery is p95 ≤10 minutes. Under the licence fallback, renders use the Babylon stack with supersampling.

## Alternatives rejected

- **Path-traced A+ tier, strand hair, console and native Quest ports**: a scope sink and platform-holder risk (B.3).
- **Platform-owned lighting, a full-bright ban, fidelity minimums, forced legacy re-make**: they alienate photographers, clubs and builders (B.4 item 11).
- **Cutting Compat, or mobile at month 18**: reopens root cause 1.1 and breaches R14.
- **Selling streamed hours, or streaming as the baseline**: about US$1 per user-hour against a US$19.99 monthly ceiling.
- **Hiding over-budget avatars** (VRChat on Quest): breaks FC-4 and FC-6.
- **One mid-fidelity tier**: cheaper QA, but it gives up the 2026 look.

## Requirements addressed

| R | How |
|---|---|
| R1 | Impostors from 30 m, crowd proxies and a ≤64-byte look descriptor keep 100 presence and Event Mode crowds within frame and bandwidth budgets |
| R2 | Clauses FC-1 to FC-8, per-tier budgets, Foundry fallbacks, the degrade order, and ≥60 fps on Lite at 100 presence published monthly |
| R3 | glTF 2.0 and VRM 1.0 at runtime, OpenUSD for scenes, funded conversion, and a converter plus 24 months' notice before any retirement |
| R4 | Lantern, Ember and Reader under a named newcomer team; protocol at L; certification at L+24 |
| R13 | Monthly p95 for each device and canonical scene; Stream cost per retained user |
| R14 | Lantern and Ember at L; mobile at L+9; VR optional at L+30; Stream capped at 2 h with the US$1.75/h cost published |
| R18 | Exact legacy rebuilds displayed as imported; the legacy shading map; EEP skies as USD; the Bento table and `nolife-bento` |
| R20 | Format and simulation boundaries, Ember as a live second renderer, the Sep 2027 gate, the US$16M / 21-month exit, two Stream providers |
| R22, R23 | Foundry safety stage and Adult pre-publication review; Darkroom consent and rating gates |
| R25 | Keeper badges carried into every impostor form |
| R26 | A dressed Common Body on every tier; Workshop separate from the consumer interface |
| R27 | Reader with the XAG 119/GAG checklist, Foundry object descriptions and a funded maintainer |
| R28, R29 | Ember Compat on Campus Chromebooks; VRM import; zero-install entry for non-US markets |
| R30 | Licence at 3% of gross; Compat before Reference polish; a fallback that keeps the launch date |

## Open questions

1. **M1 at Lite.** An 8 GB M1 with Lumen Lite and 40 × 24 MB avatars may exceed the 3 GB Lite budget; if so, M1 uses bake sets. The spine's device list is unchanged.
2. **Unverified budgets.** Lumen Lite and MegaLights figures are Epic's targets, so D.4 is a planning value until the lab measures it.
3. **Quest 3.** "Quest 3 at 72 Hz" with no Quest port is read as PC-tethered OpenXR; the spine should confirm.
4. **Exit funding.** The US$16M exit is outside the US$45M envelope; document 09 should say how it is funded after L.
5. **Fallback shell.** The native Babylon shell needs a feasibility spike by June 2027.
6. **The hardware floor.** "Never rises" must cope with WebGL2 devices their vendors abandon. Proposal: retire them only under the format-retirement rule and Assembly review.
7. **Dynamic resolution.** Should it become a degrade step? The spine's order holds until measured.
8. **Face bones.** Are 300 Reference bones enough for MetaHuman-grade faces?
9. **Darkroom path tracing.** Is it an offline render, or the A+ tier B.3 rejected? The lead designer should rule.
10. **Compat far field.** A baked skyline beyond 256 m for the Reaches? Roblox is raising its low-end floor to 500 studs ([source](https://devforum.roblox.com/t/rdc26-what-we-announced/4865880)).
11. **Building in Ember.** No date yet.
12. **Common Body licence.** CC BY 4.0 or CC0.

## Sources

- https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available
- https://www.unrealengine.com/news/unreal-engine-5-7-is-now-available
- https://gamesbeat.com/epic-games-launches-unreal-engine-5-8/
- https://tech-insider.org/unreal-engine-6-state-of-unreal-2026/
- https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/
- https://store.steampowered.com/hwsurvey/Steam-Hardware-Software-Survey-Welcome-to-Steam
- https://mixed-news.com/en/steam-september-2026-hardware-survey-rtx-5070-32gb-ram/
- https://github.com/gpuweb/gpuweb/wiki/Implementation-Status
- https://github.com/BabylonJS/Babylon.js/releases
- https://github.com/NVIDIA/DLSS/releases
- https://github.com/GPUOpen-LibrariesAndSDKs/FidelityFX-SDK/releases
- https://github.com/intel/xess/releases
- https://github.com/NVIDIA-RTX/RTXNTC
- https://www.polyvia3d.com/guides/gaussian-splatting-unity-unreal
- https://github.com/aras-p/UnityGaussianSplatting
- https://docs.vrchat.com/docs/vrchat-202115
- https://devforum.roblox.com/t/rdc26-what-we-announced/4865880
- https://uefncentral.com/blog/uefn-vs-unreal-engine-5-differences
- https://modemworld.me/2016/11/03/lab-reveals-li-prim-allowance-changes-in-second-life-in-full
- https://modemworld.me/2025/01/02/
- https://modemworld.me/2014/06/29/ebbe-altberg-on-user-retention-now-and-in-the-future/
- https://modemworld.me/2023/11/28/
- https://wiki.secondlife.com/wiki/Mirrors
- https://www.linuxfoundation.org/press/aousd_prmarch2026
- https://vrm.dev/vrm1/
- https://variety.com/2025/digital/news/netflix-acquires-ready-player-me-games-avatar-creation-1236612915/
- https://www.stephensonharwood.com/post/102nfqh/eu-ai-act-update-european-commission-adopts-guidelines-on-article-50-transparency-obligations/
- https://www.paulweiss.com/insights/client-memos/eu-finalises-transparency-rules-for-ai-generated-content
- https://www.meta.com/legal/quest/eye-tracking-privacy-notice/
- https://rec0ded88.com/statistics/vr-gaming-headset-ownership/
- https://thegabmeister.com/p/unreal-pixel-stream-aws/
- https://modemworld.me/tag/project-zero/
- https://modemworld.me/2025/06/27/
- https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now
- https://github.com/EpicGames/PixelStreamingInfrastructure/releases
- https://www.hypergridbusiness.com/2015/04/firestorm-by-far-most-popular-on-hypergrid/
- https://modemworld.me/2022/10/18/2022-viewer-release-summaries-week-41/
- https://learn.microsoft.com/en-us/gaming/accessibility/xbox-accessibility-guidelines/119
- https://virtualability.org/about-us
- https://www.phoronix.com/news/Godot-4.6-Released
- https://unity.com/blog/unity-6-3-lts-is-now-available
- https://developers.meta.com/horizon/blog/meta-horizon-engine-at-a-glance
- https://edgegap.com/pricing
