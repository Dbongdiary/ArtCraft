# What will work if the original repositories disappear?

Verified on 18 October 2026. All archived repository restoration, application builds and application tests ran on GitHub-hosted runners. No original repositories were cloned or models/application build outputs saved on the owner's Mac. Local inventory/workflow helper files from the earlier archive setup were removed after their GitHub counterparts were saved.

**The backup restores independently, and 13 desktop editors passed concrete sample workflows from that restored source. This does not establish that every feature of every repository works.** The captured public inventory contains 66 repositories: 65 with source and one empty repository, AniCraft. All 65 nonempty Git bundles passed checksum verification, Git integrity checks and checkout of their recorded commits. The two archived LFS objects and seven available external submodule references were also restored and verified.

Source snapshot: `1a39bbe21255a55128c503906888e9fb437b2c29`. Main sample/build evidence: [run 39071510854](https://github.com/Dbongdiary/ArtCraft/actions/runs/39071510854). ArtCraft package follow-up: [run 39074477664](https://github.com/Dbongdiary/ArtCraft/actions/runs/39074477664). [All 66 records](README.md), [machine summary](summary.json), [detailed missing requirements and source citations](REQUIREMENTS.md).

## Editors with a working sample from the backup

All 13 compiled their binaries and remained running for 15 seconds under a Linux virtual display. Each also passed the operation below; generated files were decoded, inspected or rendered to check meaningful output. For multi-page PDFs, page counts were inspected and only the first page was rendered for the nonblank-preview check. These are targeted checks, not an interactive GUI or complete feature certification.

| App | Verified operation | Broader-test limit |
|---|---|---|
| [CADCraft](cadcraft.json) | Created sample bracket DXF and converted it to a nonblank 2400 x 1600 PNG. | Workspace test command passed. |
| [GridCraft](gridcraft.json) | XLOOKUP returned 2; budget XLSX passed ZIP/XML checks; a two-page PDF had a nonblank first-page preview. | Workspace test command passed. |
| [FigCraft](figcraft.json) | Created a Dashboard document and exported a one-page PDF with a nonblank first-page preview. | Workspace test command reached the 15-minute limit. Collaboration was not tested. |
| [DeckCraft](deckcraft.json) | Exported an eight-page sample presentation PDF with a nonblank first-page preview. | One font-replacement dialog UI test failed. |
| [DesignCraft](designcraft.json) | Exported a four-page sample publication PDF with a nonblank first-page preview. | Workspace test command reached the 15-minute limit. |
| [EffectCraft](effectcraft.json) | Rendered a nonblank 320 x 180 demo frame. | Workspace test command reached the 15-minute limit. |
| [FilmCraft](filmcraft.json) | Rendered a nonblank 480 x 270 demo frame. | Workspace test command reached the 15-minute limit; video encoding was not certified. |
| [LightCraft](lightcraft.json) | Applied exposure to a 32 x 32 image; measured increased brightness against a baseline. | Workspace test command reached the 15-minute limit; sample used CPU mode. |
| [PDFCraft](pdfcraft.json) | Extracted text, rotated a page, changed its title, preserved text and rendered the edited PDF. | Workspace test command reached the 15-minute limit; OCR was not tested. |
| [PhotoCraft](photocraft.json) | Created a 40 x 30 image and verified a green painted stroke in its exported PNG. | Workspace test command reached the 15-minute limit. |
| [SoundCraft](soundcraft.json) | Bounced two seconds of non-silent stereo, 48 kHz, 24-bit audio to WAV. | Two unsaved-work recovery tests failed. |
| [VectorCraft](vectorcraft.json) | Exported the saved ribbons document to a one-page PDF with a nonblank first-page preview. | Workspace test command reached the 15-minute limit. |
| [WordCraft](wordcraft.json) | Saved and inspected DOCX, checked ZIP/XML, and exported a two-page PDF with a nonblank first-page preview. | Two font tests failed with the newer font set supplied by the verifier; PDF inspection also emitted a metadata warning. |

Eight test commands timed out; this is an inconclusive full-suite result, not proof of a broken app. Compilation is included in those time limits. A process remaining alive for 15 seconds does not prove every window or control is usable. Mac/Windows packaging, audio devices, GPU behavior and exhaustive format compatibility were not tested.

**WordCraft clarification:** its release workflow pins craft-fonts at `8dcdacd5153e64560d109541a47d806f26f048c0`, while this audit supplied the newer saved font snapshot, which contains Thai. The two tests explicitly expect Thai fallback to be absent. The correct root directory was supplied; this does not demonstrate a missing Thai font or a Thai-rendering defect. The pinned-font test configuration has not been rerun. The PDF tools reported “Suspects object is wrong type (boolean)” while still rendering the sample; strict PDF conformance is not certified.

**Practical conclusion:** deletion of the original Storytold repositories would not remove the saved source needed for these demonstrated operations. Rebuilding still uses external package registries, toolchains and system packages, which are not fully archived here.

## Other applications and tools

| Repository | What passed | What remains unresolved |
|---|---|---|
| [ArtCraft](artcraft.json) | Frontend production build; separate Rust builds of artcraft and artcraft_native; primary process remained alive for 15 seconds under a virtual display. | The earlier workspace-wide failure came from combining incompatible dialog backends. The separate builds passed. Tests were not rerun in the follow-up; packaged GUI behavior and authenticated AI operations remain unverified. |
| [ArtCraftX](artcraftx.json) | Frontend production build and Rust binary build. | A test needs absent `test_data/image/juno.jpg`; it was also absent from the pinned original source. Hosted AI operations were not tested. |
| [artcraft-services](artcraft-services.json) | Rust binary build and frontend package installation. | Database tests need MySQL; the runner had no server at `/tmp/mysql.sock`. The frontend had installation only, not a tested build. Production services/data are not backed up by Git. |
| [storyteller-bevy](storyteller-bevy.json) | Rust tests and binary build. | Frontend npm authentication failed (E401); the source also requires private FontAwesome Pro access. The combined app is not verified. |
| [Spark](spark.json) | WASM generation, npm installation, tests and production build. | Browser rendering and interaction were not tested. |
| [craft-repo-status-app](craft-repo-status-app.json) | npm typecheck/tests/build and Rust tests/binary build. | Authenticated GitHub/dashboard operation was not tested. |
| [craft-launcher](craft-launcher.json) | Rust tests and binary build. | Installer/update feeds still reference original release hosting; saved source does not preserve those installers. |
| [irsa-manager](irsa-manager.json) | Documented test target with its Kubernetes test environment. | No live AWS/Kubernetes deployment was exercised. |
| craft-fonts, craft-libs, craft-ai-integrations, bevy-mocap, point-generator, xsens-packet-send | Recorded Rust checks passed; see each record in the index. | Library tests do not prove real AI-provider access, hardware streaming or a complete end-user application. |

## Restored but not runtime-tested

| Group | Repositories | Coverage |
|---|---|---|
| Unreal projects/plugins | ActorSpawningPlugin, AnimationTest, CloudCamPlugin, EventCenterPlugin, HyperJail, RuntimeAudioImporter, RuntimeFilesDownloader, StreamTwo, UE4-OSC, UnrealZeroMQ | Source restoration only; no engine integration or execution. |
| Unity | Azure-Kinect-Sample-for-Unity | Source restoration only; no Unity/Kinect execution. |
| ML projects | cloud-worker, FineTrainers-Conditioning, storyteller-ml, torchscript-models, vits-finetuning | Source restore and Python syntax inspection; no training or inference. |
| Infrastructure | craft-common-actions, terraform-aws-observability-accelerator | Source restore and Python syntax inspection; Actions/Terraform/deployment behavior untested. |
| Other projects/assets | craft-contrib, craft-launcher-assets, crafthub, github-media, hanashi-graphics-demo, html_test, LiveScan3D, motion-capture-data, photocraft-corpus, redirect-vocodes | Source restored; no supported root execution workflow was exercised. |

“Syntax checked” does not mean syntax-clean or runtime-ready. The JSON records include parser findings; storyteller-ml has four, including notebook-style files and a BOM-related finding.

## Confirmed missing pieces and build blockers

| Affected area | Evidence and consequence |
|---|---|
| storyteller-ml: `3d_generation/moonTripoSR` | Missing submodule revision `33006d32ed28447f67f48a0b229b27fb2f313e65`; no source URL was recorded. No active caller was found in the inspected Python/deployment files. Separate TripoSRmoon implementation source is retained, but its equivalence and inference are unverified; it still downloads a model. This does not establish that all 3D generation is broken. |
| torchscript-models: Glow-TTS multispeaker | Missing `glow-tts-jaywalnut-multispeaker/glow-tts-multispeaker` at `23177d29a09015a4f40fce0b81b315392064f9d7`. The wrapper imports it directly, so this legacy multispeaker speech-model conversion path cannot run unchanged. Its checkpoint, dictionary and downstream vocoder are also needed. |
| cloudcam | Required local sibling `../kinect.rs` is absent. This blocks its current build. |
| realtime-voice-conversion | Required author-local `/home/bt/dev/world-sys` source is absent. This blocks its current build. |
| placeholder-artcraft | Its upstream snapshot omitted referenced workspace source directories (31 missing path entries in the audit). It is not a complete buildable copy of the application. |
| AniCraft / crafthub / html_test | AniCraft was empty; crafthub is a placeholder; html_test references a missing compiled JavaScript asset. These are not verified working applications. |
| fakeyou-recast | Old torch-sys could not acquire its external libtorch 1.13 SDK (HTTP redirect), then compilation lacked Torch headers. Matching Torch/CUDA and model files are needed. |
| discord-vocodes / voder-proxy | Older OpenSSL/socket2 dependencies failed with the current runner's toolchain. Their source is restored, but compatible dependencies/toolchains or code repairs are required. |
| k4a-sys-temp | Generated binding tests were rejected by current Rust for null-pointer dereferences. SDK/toolchain/hardware validation remains needed. |
| winit / winprint.rs | Linux could not validate macOS AppKit documentation examples or Windows bindings. Matching platform checks are still required. Their `--bins` build commands matched no binary targets and are not counted as successful builds. |
| indd-utils | Binary build passed, but a deeply nested group test aborted with stack overflow. |

The two unavailable ML submodules are **not prerequisites for the 13 successfully tested editor operations**. They affect specific ML paths. Seven other saved references were materialized successfully: ControlNet, ebsynth and gmflow in two locations each, plus Apex. The two LFS objects were restored and hash-verified: 1,146,432,909 bytes in total. Model inference was not executed.

## What a source archive does not preserve

1. **Model weights and datasets.** Python source is not the trained model. PDFCraft OCR needs two external .rten models. cloud-worker documents approximately 246 GB of MiniMax-H3 weights plus separate ComfyUI components. Other ML/training projects need their checkpoints, datasets, Python/Torch/CUDA environments and GPU capacity. The two LFS objects do not cover every model reference.
2. **Hosted backends, accounts and data.** ArtCraft/ArtCraftX use Storyteller/FakeYou APIs and external AI providers. Backend code is saved, but databases, object storage, workers, user accounts/credits and provider credentials are not. If only GitHub source repositories are deleted, those services may continue; if the services also close, hosted features need replacement infrastructure and configuration/code changes.
3. **Collaboration and release feeds.** FigCraft includes server source and can be configured for a separately hosted server; existing shared documents/data are not in its Git backup. CraftLauncher's original installer/update feed needs preserved release assets or retargeting/rebuilding. Original releases, installer binaries, issues, PR conversations and deployments were not captured by Git bundles.
4. **Third-party supply chain.** npm/Cargo/Python packages, external Git forks, container images, compilers and native SDKs are not comprehensively mirrored. The nine archived-dependency references were explicit submodule paths, not a complete inventory of every software dependency. Projects without lockfiles can resolve different versions later.
5. **Platform engines and hardware.** Unreal/Unity projects need compatible licensed editors/engines, plugins and often Kinect/Xsens hardware. Those environments were not provisioned. Private FontAwesome Pro access is also needed for storyteller-bevy's frontend.

[REQUIREMENTS.md](REQUIREMENTS.md) gives precise source locations, model hashes, service configuration details and the distinction between the two unavailable ML paths.

## Highest-priority remaining preservation work

- Preserve original installers/releases and the required model checkpoints, OCR models and external Git revisions where available and permitted.
- Obtain or replace the two unavailable ML submodules and the missing kinect.rs/world-sys source where those particular applications are needed.
- Record reproducible dependency/toolchain/SDK environments and run platform-specific checks; repeat inconclusive suites with appropriate resources and WordCraft's pinned font version.
- For independently operated online features, provision backend services and back up the actual databases/object storage; source alone cannot recover existing user data.

## How to read and reproduce the evidence

The [verification workflow](../../.github/workflows/verify-backup.yml) restores from this repository's release assets, verifies SHA-256 values and Git objects, and checks out the archived commits. Archived Storytold Git URLs are redirected to verified mirrors on the GitHub runner; fallback original Storytold Git URLs are made unavailable. Other public package registries and third-party sources remained online, so this is not a fully offline test.

Use Actions → Verify backup usability → Run workflow to repeat selected repository checks on GitHub. The JSON records preserve exact commands, exit codes, output tails, limitations and their original verification-run links. Publisher interpretation reconciles mixed JavaScript/Rust results and identifies no-op builds without changing the original test evidence. A green audit workflow means evidence collection completed, not that every application passed.

The committed report/JSON files are durable repository content. Full logs and generated sample outputs are Actions artifacts with a 30-day retention setting. The source/dependency backups are separate release assets, not those temporary test artifacts. No original application source was modified by this audit; runner-only setup changes and generated fixtures were disposable.
