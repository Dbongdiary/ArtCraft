# Additional requirements found in the backup

This is a source inspection report, not a claim that these applications passed runtime tests. Actual GitHub-hosted results are in [README.md](README.md) and the linked per-repository JSON files. Source snapshot: 1a39bbe21255a55128c503906888e9fb437b2c29.

## Confirmed missing source and other inputs

| Component | Evidence and impact |
|---|---|
| cloudcam | [Cargo.toml](../../cloudcam/Cargo.toml) requires sibling ../kinect.rs (local kinect 0.0.6). That repository is not in the 66-repository archive; its exact local revision is unknown. Blocks a fresh build. |
| realtime-voice-conversion | [Cargo.toml](../../realtime-voice-conversion/Cargo.toml) requires /home/bt/dev/world-sys. This author-local source folder is absent; blocks a fresh build. |
| storyteller-ml | Exact moonTripoSR gitlink remains unavailable. Separate TripoSRmoon source is present, but model weights/configuration and Python dependencies must still be supplied. |
| torchscript-models | Missing glow-tts-multispeaker source directly blocks its multi-speaker model exporter. Its checkpoint paths point into the author's local filesystem; code recovery alone does not supply the trained model. |
| cloud-worker | [WEIGHTS.md](../../cloud-worker/docs/WEIGHTS.md) documents 246 GB of MiniMax-H3 weights on a separate RunPod volume. ComfyUI and plugins are installed separately. GPU infrastructure, weights and configuration are outside the Git backup. |
| pdfcraft OCR | [ATTRIBUTION.toml](../../pdfcraft/ATTRIBUTION.toml) lists separately fetched text-detection.rten and text-recognition.rten. They are not committed source assets. The two documented SHA256 values are f15cfb56bd02c4bf478a20343986504a1f01e1665c2b3a0ad66340f054b1b5ca and e484866d4cce403175bd8d00b128feb08ab42e208de30e42cd9889d8f1735a6e. Core PDF editing and OCR must be tested separately. |
| fakeyou-recast | [README](../../fakeyou-recast/README.md) requires libtorch/CUDA and separately hosted acoustic/vocoder model files. |
| FineTrainers-Conditioning, vits-finetuning | Training/inference requires external pretrained weights, datasets, matching Python/Torch/CUDA environments and suitable GPU capacity. Python syntax success is not an inference test. |
| storyteller-bevy | npm dependencies include private FontAwesome Pro; requires legitimate registry access. Rust also uses external Git forks. |
| artcraft / artcraftx frontend | ccapture.js is fetched from an external GitHub branch aceslowman/ccapture.js#npm-fix. That dependency is outside the previously archived nine gitlinks. |
| spark | Build generates rust/spark-internal-rs/pkg using its Rust/WASM build before npm can resolve the local dependency. Example scene assets are separate downloads. |
| html_test | HTML snapshots reference absent /static/js/main.*.js resources and remote media; these are not a complete web application. |
| AniCraft, crafthub, placeholder-artcraft | AniCraft was empty; Crafthub is a placeholder; placeholder-artcraft is explicitly a partial snapshot. A preserved repository does not imply a complete app. |

## Source-hosted dependencies and releases

Most native editor apps still reference pinned original Storytold Git URLs, especially craft-libs. Some also require filmcraft, pdfcraft, indd-utils and winprint.rs. The verification workflow restores our saved Git bundles, verifies checksums/commits, and redirects these URLs on the runner. A normal fresh build needs equivalent restoration/configuration. Merely placing repository folders side by side does not satisfy a Cargo Git dependency.

Other external Git dependencies include skylartaylor/winit, kulkalkul/bevy_mod_billboard, rewin123/space_editor and felipenoris/hyper-reverse-proxy. Their availability is separate from deletion of Storytold, but they are not independently preserved by this archive. Package registries, toolchains and native SDKs are also not vendored.

Original GitHub release installers/binaries, signatures and update feeds were not included in the source/history backup. Craft Launcher downloads original release assets; its installation/update functions and screenshot URLs need independent release backups and URL changes if the original repositories are deleted. Reusable craft-common-actions references also require redirection.

## App-by-app runtime requirements

| Repositories | What still needs verification or provision |
|---|---|
| figcraft | Offline design editor; optional craft-fonts fallback to system fonts. Sharing defaults to collab.craftapps.dev; self-hosting the included server is a separate deployment. |
| gridcraft, wordcraft, vectorcraft, deckcraft, designcraft, cadcraft | Core document editing/import/export should be verified with fixture workflows after building. Exact shared-library revisions must resolve from backup; fonts and platform printing can affect results. |
| effectcraft, filmcraft, soundcraft | Timeline/audio/video output requires actual media fixture checks; hardware acceleration, audio devices and codecs are beyond compilation. |
| lightcraft | [README testing caveat](../../lightcraft/README.md) says some tests return success without exercising GPU/corpus/fonts/models when those resources are absent. Passing cargo tests cannot establish these features; inspect the xtask skip report. |
| photocraft, photocraft-corpus | Image/PSD operations and separately fetched compatibility corpora need fixture-based verification. |
| pdfcraft | Separate PDF view/edit/export, OCR model inference and Windows printing checks. |
| artcraft, artcraftx | AI operations rely on external providers/accounts and online APIs. A working desktop window does not prove generation works. |
| artcraft-services | Running backend requires migrated MySQL, Redis, Elasticsearch, object storage, worker configuration and provider credentials. No production database or deployment is captured in Git. |
| craft-ai-integrations | Core library tests do not exercise authenticated providers, OS keychains or local ComfyUI/model installations. |
| craft-repo-status-app | Node24+, Tauri and GitHub token; purpose depends on querying repositories. UI starts hidden in the tray; process survival is not a visual UI test. |
| discord-vocodes | Discord bot credentials and voice service endpoint, plus native dependencies. |
| voder-proxy | A router for separate TTS backend services; source does not include a running backend fleet. |
| cloudcam, k4a-sys-temp, Azure-Kinect-Sample-for-Unity, LiveScan3D | Compatible Kinect SDK, platform toolchain and physical sensors. Unity sample requires matching editor/license; LiveScan3D documents Visual Studio2019. |
| ActorSpawningPlugin, CloudCamPlugin, EventCenterPlugin, RuntimeAudioImporter, RuntimeFilesDownloader, UE4-OSC, UnrealZeroMQ | Unreal plugins require compatible engine and host projects. EventCenter also needs BlueprintWebSocket; CloudCam needs its producer/service. |
| AnimationTest, HyperJail, StreamTwo | Unreal project/plugin dependencies: LiveLinkMvnPlugin; HyperJail additionally Smartsuit; StreamTwo needs BlueprintWebSocket and VocodesPlugin. Licenses and hardware are not bundled source. |
| bevy-mocap, xsens-packet-send, point-generator | Library/streaming demos require compatible assets, local receiver or visualization consumer; hardware end-to-end coverage remains separate. |
| indd-utils | Build plus sample INDD conversion; larger test corpus is separately fetched and not redistributed. |
| irsa-manager | Kubernetes/AWS controller; unit tests do not prove a real cluster/AWS deployment. |
| terraform-aws-observability-accelerator | Infrastructure modules require AWS resources/configuration; verification must not apply resources or incur cloud costs. |
| redirect-vocodes | Hosting/domain configuration and reachable fakeyou.com destination. |
| hanashi-graphics-demo | Prebuilt browser/WASM demo; requires browser smoke of bundled assets. A reproducible source build route is not established. |
| winit, winprint.rs, craft-libs, craft-fonts | Supporting libraries/assets, not standalone apps. Native windowing/printing needs platform-specific tests; preserve font notices/licenses. |
| craft-launcher, craft-launcher-assets, github-media, craft-common-actions | Original release/asset/action references need independent destinations after deletion. |
| craft-contrib, motion-capture-data | Documentation/data; validate integrity and relevant consumers, not app startup. |

## Limits of this audit

The archive contains 66 repositories, not 66 complete products. Many newer apps describe themselves as alpha/pre-alpha. Build/test success, startup success and successful sample document export are different levels of evidence. Paid services, licensed engines, missing private code, production databases, physical devices and GPU model inference cannot be certified by a generic Linux runner. The report records those gaps explicitly and does not invent credentials, missing source or successful runtime results.
