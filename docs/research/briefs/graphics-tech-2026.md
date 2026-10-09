# State of real-time graphics for a UGC virtual world (as of 2026-10-09)

Research brief for the "nolife" series. Method: 22 web searches (budget then exhausted); only github.com resolved for full reads in this sandbox, so official GitHub release pages (gpuweb, NVIDIA RTXNTC/RTXGI/DLSS, AMD FidelityFX, Intel XeSS, three.js, Babylon.js, Godot, Epic PixelStreaming, XVERSE, aras-p) were read directly and vendor/news pages only via search excerpts. GitHub release pages omit years; years are inferred from ordering.

## Findings

### 1. Engines: what "best graphics of the era" actually means in 2026

**Unreal Engine 5.x is the reference bar, and 5.8 is the last planned UE5 release.** Epic shipped UE 5.6 in June 2025 (MetaHuman Creator embedded in-engine, MetaHuman Animator from a mono camera/webcam, Fast Geometry Streaming) (Source: https://www.unrealengine.com/news/unreal-engine-5-6-is-now-available; https://www.pugetsystems.com/blog/2025/06/19/unreal-engine-5-6-faster-open-worlds-smoother-animation-better-icvfx/). UE 5.7 (November 2025) brought Nanite Foliage (Experimental, with Nanite Assemblies and Nanite Skinning), moved Substrate materials to Production-Ready and MegaLights from Experimental to Beta (Source: https://www.unrealengine.com/news/unreal-engine-5-7-is-now-available; https://www.cgchannel.com/2025/11/unreal-engine-5-7-five-key-features-for-cg-artists/). (Puget notes Nanite Foliage was shown at the 5.6 keynote but shipped in 5.7.) UE 5.8 (June 2026, via search excerpts) adds **Lumen Lite**, a cut-down dynamic GI path aimed at 60 fps on Nintendo Switch 2 and low-end PCs; **MegaLights production-ready**; experimental **Mesh Terrain** (caves/overhangs), **Procedural Vegetation Editor**, **MetaHuman Collections** (crowds of "hundreds on mobile and thousands on higher-end platforms"), a Substrate-based Toon shader, production-ready Dataflow and Chaos Cloth, and an experimental MCP plugin. Epic says shader-compilation work cut Fortnite's shader count by 68% and calls 5.8 the final major UE5 release before UE6, reserving a 5.9 "if needed" (Source: https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available; https://www.unrealengine.com/news/state-of-unreal-2026-top-news-from-the-show; https://gamesbeat.com/epic-games-launches-unreal-engine-5-8/). A single secondary source claims UE6 merges UE5 with UEFN, Early Access late 2027; unverified (Source: https://tech-insider.org/unreal-engine-6-state-of-unreal-2026/).

**MetaHuman licensing opened in June 2025.** With 5.6, MetaHumans can be used in any engine or DCC (Unity, Godot, Blender) and sold; the cloud instance queue and session limits are gone; studios get Creator source code. A Medium guide cites free use under US$1M revenue, then US$1,850/seat, with no 5% royalty for non-Unreal games; the official EULA should be checked before relying on those numbers (Source: https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/; https://www.metahuman.com/news/metahuman-leaves-early-access-with-a-feature-packed-new-release; https://medium.com/@Jamesroha/a-beginners-guide-to-metahumans-in-unreal-engine-5-6-and-5-7-e9b14fadbf3d).

**Unity 6.3 LTS (late 2025)** is a stability release: Render Graph is now shared between URP and HDRP, a cross-platform ray-tracing shader API, xAtlas lightmap packing, no-code terrain shaders, and on-tile post-processing for tile-based XR GPUs such as Quest (Source: https://unity.com/blog/unity-6-3-lts-is-now-available; https://docs.unity3d.com/6000.5/Documentation/Manual/WhatsNewUnity63.html; https://gamefromscratch.com/unity-6-3-released/).

**Godot 4.6 (26 Jan 2026) and 4.7 (18 Jun 2026).** The GitHub releases page lists 4.6-stable on 26 Jan, 4.7-stable on 18 Jun and 4.7.2 on 18 Aug (years inferred) (Source: https://github.com/godotengine/godot/releases). 4.6 made Jolt the default 3D physics engine for new projects, made Direct3D 12 the Windows default renderer, overhauled screen-space reflections, added a modular IK framework, native OpenXR 1.1 and LibGodot for embedding (Source: https://www.phoronix.com/news/Godot-4.6-Released; https://www.gamingonlinux.com/2026/01/the-free-and-open-source-godot-engine-4-6-is-out-now-with-major-upgrades/). Godot has no Nanite/Lumen equivalent; it is a credible choice for a mid-fidelity client, not for the "UE5 look."

### 2. Scanned reality: Gaussian splatting (3DGS)

Plugin coverage is broad; production use is still "backdrop, not gameplay." For Unreal: NanoGS (free, March 2026) adds Nanite-style LOD/culling so "millions of splats" can be sorted and only visible ones drawn (Source: https://www.cgchannel.com/2026/03/free-plugin-nanogs-puts-nanite-style-gaussian-splatting-in-unreal-engine/); XVERSE XScene-UEPlugin (Apache-2.0, UE 5.0+, Niagara-based, hybrid rendering with native UE assets, dynamic LOD still on the roadmap) (Source: https://github.com/xverse-engine/XScene-UEPlugin); DazaiStudio SplatRenderer for UE 5.5+ (3D/4D splats, Sequencer, crop volumes) (Source: https://github.com/DazaiStudio/SplatRenderer-UEPlugin). For Unity, aras-p's reference renderer measured a 6.1M-splat "bicycle" scene at 6.8 ms (147 fps) on an RTX 3080 Ti using about 1.3 GB VRAM, versus 21.5 ms (46 fps) on an M1 Max; it needs ~48 bytes of GPU memory per splat, requires DX12/Vulkan/Metal (no OpenGL/WebGL), was untested on mobile/web, and the author stopped development in December 2023. Importantly, the original INRIA training code is non-commercial without a license (Source: https://github.com/aras-p/UnityGaussianSplatting). Babylon.js has had native Gaussian splat support with streaming compaction and IBL shadows on splats through its 9.2x releases in 2026 (Source: https://github.com/BabylonJS/Babylon.js/releases).

Vendor guides agree on the limits: splats are appearance, not geometry; no collision or relighting, fragile occlusion against meshes, and mobile budgets of roughly 200-500K splats at 30 fps. The common pattern is splat backdrop plus mesh gameplay layer (Source: https://www.polyvia3d.com/guides/gaussian-splatting-unity-unreal; https://www.kiriengine.app/blog/3d-gaussian-splatting-in-godot-workflows). Apple's visionOS 26 Personas are reported to be Gaussian-splat based, which is the most visible shipping consumer use (Source: https://www.uploadvr.com/meta-hologram-realistic-avatars-meta-vr-glasses-connect-2026/).

### 3. Neural rendering and path tracing

**Upscaling/frame generation is now three-vendor and ML-based.** NVIDIA's DLSS SDK moved the transformer model out of beta on 25 Jun 2025 (310.3.0), added Super Resolution presets L/M on 6 Jan 2026, 5x and 6x frame generation on 21 Apr 2026 (310.6.0) and a transformer Ray Reconstruction preset on 8 Sep 2026 (310.9.1) (years inferred from release order) (Source: https://github.com/NVIDIA/DLSS/releases). NVIDIA says DLSS 4 is in over 250 games (company claim) (Source: https://www.nvidia.com/en-us/geforce/news/dlss-4-rtx-path-tracing-game-announcements-ces-2026/). AMD's FidelityFX SDK v2.1.0 (10 Dec 2025) introduced "Redstone" (ML Frame Generation 4.0, Ray Regeneration 1.0, Radiance Caching listed as Preview); v2.3.0 (24 Jun 2026) shipped FSR Upscaling 4.1.1 with support extended to RX 7000 (RDNA 3) discrete GPUs, and Ray Regeneration 1.2 (Source: https://github.com/GPUOpen-LibrariesAndSDKs/FidelityFX-SDK/releases). AMD said Radiance Caching's production release was scheduled for 2026 and that a Fatshark title would be first to use it as a tech demo; third-party guides say it had not shipped in a game as of their writing (Source: https://gpuopen.com/learn/amd-fsr-redstone-developers-neural-rendering/; https://tech-insider.org/amd-fsr-redstone-setup-2026/). Intel's XeSS SDK 3.0.0 (9 Mar 2026) added 3x/4x multi-frame generation on Arc, and since 2.1.0 XeSS-FG runs on non-Intel GPUs with Shader Model 6.4 (Source: https://github.com/intel/xess/releases).

**Neural shaders / cooperative vectors are an API reality but not yet shippable on all vendors.** Microsoft introduced Cooperative Vectors in Shader Model 6.9 and showed DXR 2.0 and neural rendering at GDC 2026 (Source: https://developer.microsoft.com/en-us/games/articles/2026/03/gdc-2026-evolving-directx-for-ml-era-on-windows/; https://windowsreport.com/microsoft-showcases-neural-rendering-and-dxr-2-0-plans-for-directx-at-gdc-2026/). NVIDIA's RTX Neural Texture Compression SDK (v0.10.0 beta) claims ~5 bits/texel at BCn-comparable quality (40-50 dB PSNR); for a 2k x 2k five-map material it quotes 2.5 MB on disk versus 12 MB BCn, and 2.5 MB VRAM in "inference on sample" mode. But its DX12 path depends on the SM 6.10 LinAlg preview (Agility SDK 1.721.0-preview, Developer Mode, NVIDIA preview driver 620.12+) and is stamped "DO NOT SHIP ANY PRODUCTS USING IT"; it is incompatible with current AMD preview drivers; a DP4a/integer fallback runs on any SM6 GPU at lower speed; Cooperative Vector hardware gives 2-4x inference throughput on Ada/Blackwell (Source: https://github.com/NVIDIA-RTX/RTXNTC). No shipped 2026 game using NTC through DirectX cooperative vectors was found. Intel's cooperative-vector neural block compression paper reports up to 23x speedup over an FMA compute path, as research (Source: https://arxiv.org/pdf/2506.06040). NVIDIA's RTXGI 2.0 ships Neural Radiance Cache (experimental, Turing+ tensor cores, driver 555.85+) and SHaRC (any DXR GPU) (Source: https://github.com/NVIDIA-RTX/RTXGI).

**Path tracing viability:** the search budget ran out before independent midrange benchmarks could be gathered; NVIDIA's CES 2026 list of path-traced titles (007 First Light, Pragmata, etc.) is a company claim (Source: https://www.nvidia.com/en-us/geforce/news/dlss-4-rtx-path-tracing-game-announcements-ces-2026/). Treat full path tracing as a top-tier option only.

### 4. The browser: WebGPU, Three.js, Babylon.js

Per the gpuweb implementation-status wiki (last edited 2 Oct 2026): Chrome shipped WebGPU on Windows/macOS/ChromeOS in 113, Android 12+ (ARM/Qualcomm/Intel GPUs) in 121, Imagination GPUs on Android 16+ in 139, Linux Intel Gen12+ in 144 and NVIDIA-on-Wayland in 147; Samsung Xclipse and other Android GPUs are "TBD"; Windows ARM64 is behind a flag. Firefox shipped Windows in 141 (July 2025), macOS 26 in 145 and all macOS in 147; Linux is Nightly-only with a 2026 target; Android behind a flag. Safari shipped WebGPU in macOS Tahoe 26, iOS 26, iPadOS 26 and visionOS 26 (Source: https://github.com/gpuweb/gpuweb/wiki/Implementation-Status; https://mozillagfx.wordpress.com/2025/07/15/shipping-webgpu-on-windows-in-firefox-141/). "Baseline in every browser" claims from 2026 blogs are true of the API but not of every OS/GPU combination; a WebGL2 fallback is still required for Linux Firefox, Samsung Exynos phones and older Android (Source: https://vr.org/articles/webgpu-baseline-2026-three-js-webxr-default; https://app.cinevva.com/guides/webgpu-vs-webgl-games).

Three.js r186 (24 Sep 2026, year inferred) adds a WebGPU DirectRenderPipeline and MSAA for WebXR-on-WebGPU; r185 added WebXR support for WebGPU; r184 reported a 3.0x TSL compilation speedup. The releases do not declare WebGPURenderer the default (Source: https://github.com/mrdoob/three.js/releases). Babylon.js is at 9.30.0 (8 Oct 2026) with continuous WebGPU, Gaussian-splat and WebXR work (dynamic viewport scaling, depth sensing, persistent anchors) (Source: https://github.com/BabylonJS/Babylon.js/releases).

### 5. Cloud rendering and pixel streaming economics

No official Epic per-user price exists; cost is the rented GPU. Community/vendor datapoints: AWS g4dn.xlarge (T4) about US$0.71-1.12/hour on-demand (Nov 2024 list; Linux cheaper than Windows) with one Pixel Streaming session per instance in the default setup; a 2025 forum post quotes ~US$1/hour per session; an indie reports 1-3 EUR per user-hour on pay-as-you-go GPUs; managed hosts charge US$0.10/minute (~US$6/hour) above plan minutes (Eagle 3D) or EUR 99/month for 2 concurrent users (Streampixel) (Source: https://thegabmeister.com/p/unreal-pixel-stream-aws/; https://forums.unrealengine.com/t/pixel-streaming-cost/660659; https://www.eagle3dstreaming.com/pricing; https://www.streampixel.io/; https://learn.microsoft.com/sv-se/gaming/azure/reference-architectures/unreal-pixel-streaming-in-azure). Epic's PixelStreamingInfrastructure ships packages for UE 5.6/5.7/5.8 with SFU routing added mid-2026 (Source: https://github.com/EpicGames/PixelStreamingInfrastructure/releases).

Consumer cloud gaming sets the price ceiling: GeForce NOW Ultimate moved to RTX 5080-class servers in 2025 at an unchanged US$19.99/month (US$199.99/year), streaming up to 5K/120 fps or 1080p/360 fps, with a 100-hour monthly cap on paid tiers; Xbox Game Pass Ultimate is US$22.99/month after an April 21, 2026 cut from US$29.99, with cloud-hour caps (15/10/5 hours by tier) reportedly starting November 2026 (Source: https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now; https://www.howtogeek.com/nvidia-geforce-now-rtx-5080-ultimate/; https://tech-insider.org/xbox-cloud-gaming-hourly-limits-2026/). At ~US$1/user-hour raw cost, US$20/month cannot cover more than ~20 hours.

### 6. Avatars

The third-party avatar-platform layer collapsed in 2025-26. Netflix agreed to acquire Ready Player Me in late 2025 and shut the public creator, PlayerZero and developer APIs on 31 Jan 2026; previously exported GLBs still load, anything hosted or API-driven is dead (Source: https://variety.com/2025/digital/news/netflix-acquires-ready-player-me-games-avatar-creation-1236612915/; https://avatarsdk.com/blog/2026/01/15/switch-from-ready-player-me-to-avatar-sdk-fast-familiar-production-ready/; https://genies.com/blog/ready-player-me-discontinued-alternatives). Union Avatars has also closed (reports differ: mid-2025 confirmed by its CEO on LinkedIn vs. "offline July 2026") (Source: https://avatarsdk.com/blog/2026/07/07/union-avatars-shut-down/). Avaturn is listed as active in an August 2026 competitor roundup, unverified independently (Source: https://avatarsdk.com/blog/2026/08/31/avatar-platforms-2026-whos-alive-whos-gone/). Platform-owned realism is advancing: Apple's visionOS 26 Personas (June 2025) use volumetric rendering and on-device ML with full side profiles (Source: https://roadtovr.com/vision-pro-persona-avatar-upgrade-visionos-26/; https://techcrunch.com/2025/06/09/from-spatial-widgets-to-realistic-personas-all-the-visionos-updates-apple-announced-at-wwdc); Meta announced "Hologram," a productized Codec Avatar for calling that ships first in limited form on its VR glasses, with Horizon OS already carrying "Hologram Calling" frameworks, but Quest 3/3S lack eye and face tracking that Codec Avatars depend on, and Meta's research showed only 3 full-body Gaussian avatars running on a Quest 3 (Source: https://www.uploadvr.com/meta-hologram-realistic-avatars-meta-vr-glasses-connect-2026/; https://www.uploadvr.com/meta-squeezeme-mobile-ready-distillation-of-gaussian-full-body-avatars/; https://vr.org/articles/meta-hologram-calling-codec-avatars-horizon-os-framework-2026).

### 7. Hardware baseline

**PC (Steam Hardware Survey, September 2026):** the RTX 5070 is the single most common GPU at 5.86% (Valve's all-cards table shows 6.15%; the two Valve views differ), followed by RTX 5060 (4.20%), RTX 5060 Ti (3.87%), RTX 4060 (3.72%), RTX 3060 (3.54%); RTX 4060 Laptop 3.35%, RTX 4060 Ti 2.73%. 32 GB system RAM overtook 16 GB for the first time; Windows 11 was 70.97% in August (Source: https://store.steampowered.com/hwsurvey/Steam-Hardware-Software-Survey-Welcome-to-Steam; https://mixed-news.com/en/steam-september-2026-hardware-survey-rtx-5070-32gb-ram/; https://www.tech2geek.net/steam-hardware-survey-september-2026-32gb-ram-becomes-the-new-gaming-standard/). The modal Steam GPU is therefore an 8-12 GB xx60/xx70-class card; the long tail is far weaker and Steam over-represents gamers.

**VR:** only about 1.77% of Steam users had a headset connected in January 2026; Quest 2 (26.97%), Quest 3 (26.01%) and Quest 3S (11.50%) made up ~72% of connected headsets in August 2026 (Source: https://rec0ded88.com/statistics/vr-gaming-headset-ownership/; https://axis-intelligence.com/meta-quest-statistics/). IDC data via secondary reports: Meta held 74.6% of 2025 headset shipments with Quest units down 16% YoY through Q3 2025 (~1.7M units Q1-Q3); Apple Vision Pro shipped roughly 390K units in 2024 and ~45K in 2025 (one outlet prints 4,500 for Q4 2025; the figures are contested and IDC's release was not read) (Source: https://r2u.io/en/blog/meta-quest-vs-apple-vision-pro-market-share-2026/; https://www.forbes.com/sites/andrewwilliams/2026/01/05/meta-quest-series-future-looks-bleaker-as-shipments-decline/).

**Consoles/handheld:** Nintendo Switch 2 reached 23.68M units as of 30 June 2026 (3.82M in the April-June quarter; FY to March 2027 forecast 16.5M); it is the device Epic targets with Lumen Lite at 60 fps (Source: https://www.gematsu.com/2026/08/switch-2-worldwide-sales-top-23-68-million-switch-tops-156-59-million; https://gameinformer.com/2026/05/08/as-nintendo-switch-2-nears-20-million-units-sold-the-company-expects-sales-to-decline). PS5 cumulative sell-in was 95.3M at 30 June 2026; Sony does not break out PS5 Pro, estimates put US Pro sales around 2.7M, and Famitsu logged only 840 Pro units in Japan for the week ending 5 April 2026 after a price rise (Source: https://tech-insider.org/ps5-93-million-sony-record-profit-2026/; https://coopboardgames.com/statistics/ps5-vs-ps5-pro-sales-comparison/).

**Mobile:** no reliable GPU vendor-share figures were found; Android is roughly 68-73% of smartphones (Source: https://commandlinux.com/android/android-global-market-share-statistics/). Roblox's draw-distance floor (below) is the best proxy for low-end mobile.

### 8. How UGC worlds actually handle fidelity

**Roblox (RDC, September 2026):** minimum draw distance rises to 500 studs by late 2026 ("more than double today's 200" even on a quality-level-1 low-end Android device); a terrain rework with up to 64 custom materials; auto-generated collision geometry with a debug overlay; orthographic camera; UI blur/shadow/gradients inside the one engine; and "Roblox Reality," a video world-model layer that "AI-upsamples reality" on top of the structured engine, a press characterization with no independent visual verification. Lighting is still the 2020-era "Future Is Bright" pipeline (HDR, PBR BRDF since January 2020, per-light shadows in Future mode) (Source: https://devforum.roblox.com/t/rdc26-what-we-announced/4865880; https://gamesbeat.com/roblox-dives-into-the-details-on-its-rdc-engine-updates-roblox-wallet-and-offline-play-press-briefing/; https://roblox.fandom.com/wiki/Future_Is_Bright; https://create.roblox.com/docs/tutorials/use-case-tutorials/lighting/enhance-indoor-environments).

**Fortnite/UEFN:** creators get Lumen, Nanite (static meshes only) and Niagara, but with Fortnite's performance budgets, Lumen falling to reduced modes on low hardware, Verse-only scripting and no outbound HTTP; Fortnite Creative got Lumen/Nanite lighting via the Chapter 5 Time of Day Manager in v35.00 (2025) (Source: https://uefncentral.com/blog/uefn-vs-unreal-engine-5-differences; https://www.fortnite.com/news/fortnite-ecosystem-v35-00?team=personal).

**VRChat:** avatars are rated Excellent/Good/Medium/Poor/Very Poor on polygons, texture memory, bones, materials and skinned meshes; Quest shows Medium-and-above by default and never shows Very Poor (Quest Very Poor threshold raised to >20,000 triangles in 2021; Excellent <=7,500, Good <=10,000); PC shows everything by default with user-selectable minimums; creators report the PC Good/Very Poor cliff at ~70,000 triangles and VRAM-driven Very Poor ratings (Source: https://medium.com/vrchat/avatar-performance-stats-and-rank-blocking-1ae0feddc775; https://docs.vrchat.com/docs/vrchat-202115; https://feedback.vrchat.com/feature-requests/p/update-to-the-number-of-triangles-in-the-performance-ranks).

**Second Life:** PBR materials (glTF-style) arrived in late 2023; Mirrors, PBR Terrain and 2K textures went grid-wide on 10 June 2024 in viewer 7.1.8. Mirrors are reflection-probe based, only the one probe nearest the camera renders, they are planar only, and Linden warns of a performance drop "since everything is being rendered twice"; PBR terrain launched only on private regions; 6.x viewers cannot see PBR at all (Source: https://community.secondlife.com/news/featured-news/launching-mirrors-pbr-terrain-and-2k-textures-in-second-life-r1519/; https://releasenotes.secondlife.com/viewer/7.1.8.9375512768.html; https://wiki.secondlife.com/wiki/Mirrors; https://wiki.firestormviewer.org/pbr).

## Patterns / root causes

1. **Fidelity is a budgeting problem before it is a rendering problem.** Every successful UGC world enforces content budgets (VRChat ranks, Roblox quality levels, UEFN's Fortnite budgets). SL cannot budget 20 years of uploads, so mirrors "render everything twice" and PBR terrain is private-region only.
2. **The frontier moved to "lite" variants.** Epic's 2026 investments are Lumen Lite, MegaLights production-ready and 68% fewer Fortnite shaders, i.e. making the UE5 look run on Switch 2 and midrange PCs rather than pushing the ceiling. The modal Steam GPU is an xx60/xx70 with 8-12 GB.
3. **Neural rendering is a bifurcated story.** ML upscaling/frame-gen is universal and mature (DLSS transformer out of beta June 2025, FSR 4.1 on RDNA 3, XeSS 3 multi-frame). Neural shaders/NTC are API-level previews with "do not ship" warnings and vendor incompatibilities; they are a 2027-28 bet.
4. **Scanned reality (3DGS) is a backdrop technology.** Great for capturing real places, weak for collision, relighting, occlusion and mobile budgets; licensing of training code is non-commercial by default.
5. **The browser is finally a real tier, with a fallback obligation.** WebGPU is shipped in Chrome, Safari 26 and Firefox on desktop; Linux Firefox, Samsung Exynos and old Android still need WebGL2.
6. **Rented avatar platforms are a dependency risk.** RPM (acquired, shut 31 Jan 2026) and Union Avatars are gone; realism is being captured by platform owners (Apple Persona, Meta Hologram) and tied to their sensors.
7. **Cloud rendering is a premium tier, not a baseline.** ~US$1/user-hour raw GPU cost vs. US$19.99/month consumer expectations and 100-hour caps even at NVIDIA scale.
8. **VR is a minority input device.** ~1.8% of Steam users; Quest shipments down 16% YoY; Vision Pro in the tens of thousands. VR is an optional view of a flat-screen world, not the primary client.

## Design implications for nolife

- Adopt a **three-tier fidelity contract** enforced server-side: Tier A "Reference" (UE5-class: Nanite, Lumen/MegaLights, Substrate, optional path tracing, DLSS/FSR/XeSS; target RTX 4060/5060-class at 1080p-1440p with upscaling), Tier B "Lite" (Lumen Lite-class GI, baked/probe lighting, SSR; target Switch 2 / Quest 3 / M-series Mac / mid Android; also the WebGPU browser client), Tier C "Compat" (WebGL2 / low Android: no dynamic GI, 200-500 stud-equivalent draw distance, VRChat-Quest-style avatar caps).
- Make **every asset carry a per-tier budget and auto-generated fallback** (LODs, impostors, transcoded textures, capped avatar ranks). Hide, impostor or placeholder content that exceeds budget, as VRChat and Roblox do; never render-twice like SL mirrors.
- Build on an engine that already has the "lite" path. UE 5.8/UE6 (Lumen Lite, MegaLights, MetaHuman Collections crowds) is the best fit for Tier A/B; keep the content format engine-neutral (glTF 2.0 + PBR extensions, MetaHuman-compatible rigs now that the license allows any engine) so a Godot/Three.js/Babylon client can serve Tier B/C.
- Treat **3DGS as a first-class "place capture" format** for scanned real-world venues, rendered as backdrops with proxy collision meshes; set splat budgets per tier (<=500K mobile, millions on PC with NanoGS-style LOD); secure commercial training/licensing.
- Ship ML upscaling and frame generation from day one (DLSS/FSR/XeSS via Streamline-style abstraction); plan neural texture compression as a 2027 upgrade when SM 6.10 LinAlg leaves preview and AMD/Intel drivers support it, since its 4-5x on-disk texture savings directly attack a UGC world's biggest download problem.
- Own the avatar pipeline (no third-party avatar API dependency); support MetaHuman-class humans in Tier A, stylized lower-cost rigs in B/C, and treat Persona/Hologram-style volumetric avatars as a sensor-gated optional feature for Vision Pro / eye-tracked headsets.
- Offer cloud streaming as a paid premium path for Tier C devices to see Tier A worlds, priced with explicit hour caps (GeForce NOW's 100 hours, Xbox's 15 hours are the market precedents), not as the baseline.
- Make the browser (WebGPU with WebGL2 fallback) the zero-install entry for visiting and socializing; reserve native clients for building and Tier A.

## Open questions

- Independent frame-cost measurements of Lumen Lite and MegaLights on Switch 2 / RTX 4060 / Quest 3-class hardware; Epic's "60 fps" is a company target.
- When does DirectX LinAlg / SM 6.10 leave preview, and will AMD RDNA 4 and Intel Arc ship Cooperative Vector drivers in 2027? Without them NTC is NVIDIA-only.
- What is the real retail Steam share of GPUs below RTX 3060 / 8 GB VRAM (the Tier B/C PC population)? Only top-10 cards were captured.
- IDC's exact Vision Pro and Quest 2025 numbers (45K vs 4,500; Q4 vs full year) are contested in secondary reporting.
- Does Roblox's "Roblox Reality" AI video layer ship in 2026-27, and at what latency/cost?
- Pixel-streaming sessions-per-GPU on RTX 5080/L40S-class cards at acceptable quality, which drives whether cloud can be a mid tier rather than premium.
- Whether UE6 (reported late-2027 Early Access) merges UEFN and deprecates Blueprints.
- Path-tracing performance on midrange 2026 GPUs (not benchmarked here).

## Sources

- https://github.com/gpuweb/gpuweb/wiki/Implementation-Status
- https://github.com/NVIDIA-RTX/RTXNTC
- https://github.com/NVIDIA-RTX/RTXGI
- https://github.com/NVIDIA/DLSS/releases
- https://github.com/GPUOpen-LibrariesAndSDKs/FidelityFX-SDK/releases
- https://github.com/intel/xess/releases
- https://github.com/mrdoob/three.js/releases
- https://github.com/BabylonJS/Babylon.js/releases
- https://github.com/godotengine/godot/releases
- https://github.com/EpicGames/PixelStreamingInfrastructure/releases
- https://github.com/xverse-engine/XScene-UEPlugin
- https://github.com/DazaiStudio/SplatRenderer-UEPlugin
- https://github.com/aras-p/UnityGaussianSplatting
- https://www.unrealengine.com/news/unreal-engine-5-6-is-now-available
- https://www.unrealengine.com/news/unreal-engine-5-7-is-now-available
- https://www.unrealengine.com/news/unreal-engine-5-8-is-now-available
- https://www.unrealengine.com/news/state-of-unreal-2026-top-news-from-the-show
- https://www.pugetsystems.com/blog/2025/06/19/unreal-engine-5-6-faster-open-worlds-smoother-animation-better-icvfx/
- https://www.cgchannel.com/2025/11/unreal-engine-5-7-five-key-features-for-cg-artists/
- https://www.cgchannel.com/2025/06/you-can-now-sell-metahumans-or-use-them-in-unity-or-godot/
- https://www.cgchannel.com/2026/03/free-plugin-nanogs-puts-nanite-style-gaussian-splatting-in-unreal-engine/
- https://www.metahuman.com/news/metahuman-leaves-early-access-with-a-feature-packed-new-release
- https://medium.com/@Jamesroha/a-beginners-guide-to-metahumans-in-unreal-engine-5-6-and-5-7-e9b14fadbf3d
- https://gamesbeat.com/epic-games-launches-unreal-engine-5-8/
- https://tech-insider.org/unreal-engine-6-state-of-unreal-2026/
- https://unity.com/blog/unity-6-3-lts-is-now-available
- https://docs.unity3d.com/6000.5/Documentation/Manual/WhatsNewUnity63.html
- https://gamefromscratch.com/unity-6-3-released/
- https://www.phoronix.com/news/Godot-4.6-Released
- https://www.gamingonlinux.com/2026/01/the-free-and-open-source-godot-engine-4-6-is-out-now-with-major-upgrades/
- https://docs.godotengine.org/en/4.5/tutorials/physics/using_jolt_physics.html
- https://www.polyvia3d.com/guides/gaussian-splatting-unity-unreal
- https://www.kiriengine.app/blog/3d-gaussian-splatting-in-godot-workflows
- https://www.thefuture3d.com/blog/gaussian-splatting-virtual-production-workflow/
- https://www.nvidia.com/en-us/geforce/news/dlss-4-rtx-path-tracing-game-announcements-ces-2026/
- https://gpuopen.com/learn/amd-fsr-redstone-developers-neural-rendering/
- https://tech-insider.org/amd-fsr-redstone-setup-2026/
- https://developer.microsoft.com/en-us/games/articles/2026/03/gdc-2026-evolving-directx-for-ml-era-on-windows/
- https://windowsreport.com/microsoft-showcases-neural-rendering-and-dxr-2-0-plans-for-directx-at-gdc-2026/
- https://arxiv.org/pdf/2506.06040
- https://mozillagfx.wordpress.com/2025/07/15/shipping-webgpu-on-windows-in-firefox-141/
- https://vr.org/articles/webgpu-baseline-2026-three-js-webxr-default
- https://app.cinevva.com/guides/webgpu-vs-webgl-games
- https://thegabmeister.com/p/unreal-pixel-stream-aws/
- https://forums.unrealengine.com/t/pixel-streaming-cost/660659
- https://www.eagle3dstreaming.com/pricing
- https://www.streampixel.io/
- https://learn.microsoft.com/sv-se/gaming/azure/reference-architectures/unreal-pixel-streaming-in-azure
- https://nvidianews.nvidia.com/news/nvidia-blackwell-architecture-comes-to-geforce-now
- https://www.howtogeek.com/nvidia-geforce-now-rtx-5080-ultimate/
- https://tech-insider.org/xbox-cloud-gaming-hourly-limits-2026/
- https://variety.com/2025/digital/news/netflix-acquires-ready-player-me-games-avatar-creation-1236612915/
- https://avatarsdk.com/blog/2026/01/15/switch-from-ready-player-me-to-avatar-sdk-fast-familiar-production-ready/
- https://avatarsdk.com/blog/2026/07/07/union-avatars-shut-down/
- https://avatarsdk.com/blog/2026/08/31/avatar-platforms-2026-whos-alive-whos-gone/
- https://genies.com/blog/ready-player-me-discontinued-alternatives
- https://roadtovr.com/vision-pro-persona-avatar-upgrade-visionos-26/
- https://techcrunch.com/2025/06/09/from-spatial-widgets-to-realistic-personas-all-the-visionos-updates-apple-announced-at-wwdc
- https://www.uploadvr.com/meta-hologram-realistic-avatars-meta-vr-glasses-connect-2026/
- https://www.uploadvr.com/meta-squeezeme-mobile-ready-distillation-of-gaussian-full-body-avatars/
- https://vr.org/articles/meta-hologram-calling-codec-avatars-horizon-os-framework-2026
- https://store.steampowered.com/hwsurvey/Steam-Hardware-Software-Survey-Welcome-to-Steam
- https://mixed-news.com/en/steam-september-2026-hardware-survey-rtx-5070-32gb-ram/
- https://www.tech2geek.net/steam-hardware-survey-september-2026-32gb-ram-becomes-the-new-gaming-standard/
- https://rec0ded88.com/statistics/vr-gaming-headset-ownership/
- https://axis-intelligence.com/meta-quest-statistics/
- https://r2u.io/en/blog/meta-quest-vs-apple-vision-pro-market-share-2026/
- https://www.forbes.com/sites/andrewwilliams/2026/01/05/meta-quest-series-future-looks-bleaker-as-shipments-decline/
- https://www.gematsu.com/2026/08/switch-2-worldwide-sales-top-23-68-million-switch-tops-156-59-million
- https://gameinformer.com/2026/05/08/as-nintendo-switch-2-nears-20-million-units-sold-the-company-expects-sales-to-decline
- https://tech-insider.org/ps5-93-million-sony-record-profit-2026/
- https://coopboardgames.com/statistics/ps5-vs-ps5-pro-sales-comparison/
- https://commandlinux.com/android/android-global-market-share-statistics/
- https://straitsresearch.com/report/mobile-gpu-market
- https://devforum.roblox.com/t/rdc26-what-we-announced/4865880
- https://gamesbeat.com/roblox-dives-into-the-details-on-its-rdc-engine-updates-roblox-wallet-and-offline-play-press-briefing/
- https://roblox.fandom.com/wiki/Future_Is_Bright
- https://create.roblox.com/docs/tutorials/use-case-tutorials/lighting/enhance-indoor-environments
- https://uefncentral.com/blog/uefn-vs-unreal-engine-5-differences
- https://www.fortnite.com/news/fortnite-ecosystem-v35-00?team=personal
- https://medium.com/vrchat/avatar-performance-stats-and-rank-blocking-1ae0feddc775
- https://docs.vrchat.com/docs/vrchat-202115
- https://feedback.vrchat.com/feature-requests/p/update-to-the-number-of-triangles-in-the-performance-ranks
- https://community.secondlife.com/news/featured-news/launching-mirrors-pbr-terrain-and-2k-textures-in-second-life-r1519/
- https://releasenotes.secondlife.com/viewer/7.1.8.9375512768.html
- https://wiki.secondlife.com/wiki/Mirrors
- https://wiki.firestormviewer.org/pbr
