# Backup usability verification

GitHub-hosted audit run: https://github.com/Dbongdiary/ArtCraft/actions/runs/39069519709

Source snapshot: 1a39bbe21255a55128c503906888e9fb437b2c29. All restoration, downloads, builds and tests ran on ephemeral GitHub runners. No repository was cloned or built on the owner's Mac.

## Meaning of the results

A verified restore proves the saved Git bundle can be checked out independently of the original repository. Git URLs for archived Storytold dependencies are redirected to checksum-verified local mirrors on the runner. Other package registries and third-party sources remain available; this is not a fully offline or feature-complete certification.

Passing library tests/builds is narrower than working interactive editing, exports, AI inference, hardware capture or hosted integrations. Python syntax checks are not execution tests. Missing models and service domains are evidence to review, not a claim every occurrence is required.

## Repository results

| Repository | Restore | Check result | Details |
|---|---|---|---|
| ActorSpawningPlugin | verified | source_restored_runtime_unverified | [unreal](ActorSpawningPlugin.json) |
| AniCraft | not verified / empty | empty_repository | [details](AniCraft.json) |
| AnimationTest | verified | source_restored_runtime_unverified | [unreal](AnimationTest.json) |
| artcraft | verified | audit_blocked | [rust](artcraft.json) |
| artcraft-services | verified | build_or_tests_blocked | [rust](artcraft-services.json) |
| artcraftx | verified | build_or_tests_blocked | [rust](artcraftx.json) |
| Azure-Kinect-Sample-for-Unity | verified | source_restored_runtime_unverified | [unity](Azure-Kinect-Sample-for-Unity.json) |
| bevy-mocap | verified | build_or_tests_blocked | [rust](bevy-mocap.json) |
| cadcraft | verified | build_and_tests_passed | [rust](cadcraft.json) |
| cloud-worker | verified | syntax_checked_runtime_unverified | [python](cloud-worker.json) |
| cloudcam | verified | build_or_tests_blocked | [rust](cloudcam.json) |
| CloudCamPlugin | verified | source_restored_runtime_unverified | [unreal](CloudCamPlugin.json) |
| craft-ai-integrations | verified | build_and_tests_passed | [rust](craft-ai-integrations.json) |
| craft-common-actions | verified | syntax_checked_runtime_unverified | [python](craft-common-actions.json) |
| craft-contrib | verified | source_restored_runtime_unverified | [other_or_assets](craft-contrib.json) |
| craft-fonts | verified | build_and_tests_passed | [rust](craft-fonts.json) |
| craft-launcher | verified | build_and_tests_passed | [rust](craft-launcher.json) |
| craft-launcher-assets | verified | source_restored_runtime_unverified | [other_or_assets](craft-launcher-assets.json) |
| craft-libs | verified | build_and_tests_passed | [rust](craft-libs.json) |
| craft-repo-status-app | verified | build_or_tests_blocked | [rust](craft-repo-status-app.json) |
| crafthub | verified | source_restored_runtime_unverified | [other_or_assets](crafthub.json) |
| deckcraft | verified | build_or_tests_blocked | [rust](deckcraft.json) |
| designcraft | verified | build_and_tests_passed | [rust](designcraft.json) |
| discord-vocodes | verified | build_or_tests_blocked | [rust](discord-vocodes.json) |
| effectcraft | verified | build_or_tests_blocked | [rust](effectcraft.json) |
| EventCenterPlugin | verified | source_restored_runtime_unverified | [unreal](EventCenterPlugin.json) |
| fakeyou-recast | verified | audit_blocked | [rust](fakeyou-recast.json) |
| filmcraft | verified | build_and_tests_passed | [rust](filmcraft.json) |
| FineTrainers-Conditioning | verified | syntax_checked_runtime_unverified | [python](FineTrainers-Conditioning.json) |
| github-media | verified | source_restored_runtime_unverified | [other_or_assets](github-media.json) |
| gridcraft | verified | build_and_tests_passed | [rust](gridcraft.json) |
| hanashi-graphics-demo | verified | source_restored_runtime_unverified | [other_or_assets](hanashi-graphics-demo.json) |
| html_test | verified | source_restored_runtime_unverified | [other_or_assets](html_test.json) |
| HyperJail | verified | source_restored_runtime_unverified | [unreal](HyperJail.json) |
| indd-utils | verified | build_or_tests_blocked | [rust](indd-utils.json) |
| irsa-manager | verified | tests_blocked | [go](irsa-manager.json) |
| k4a-sys-temp | verified | build_or_tests_blocked | [rust](k4a-sys-temp.json) |
| LiveScan3D | verified | source_restored_runtime_unverified | [other_or_assets](LiveScan3D.json) |
| motion-capture-data | verified | source_restored_runtime_unverified | [other_or_assets](motion-capture-data.json) |
| photocraft-corpus | verified | source_restored_runtime_unverified | [other_or_assets](photocraft-corpus.json) |
| placeholder-artcraft | verified | manifest_or_source_dependency_blocked | [rust](placeholder-artcraft.json) |
| point-generator | verified | build_or_tests_blocked | [rust](point-generator.json) |
| realtime-voice-conversion | verified | build_or_tests_blocked | [rust](realtime-voice-conversion.json) |
| redirect-vocodes | verified | source_restored_runtime_unverified | [other_or_assets](redirect-vocodes.json) |
| RuntimeAudioImporter | verified | source_restored_runtime_unverified | [unreal](RuntimeAudioImporter.json) |
| RuntimeFilesDownloader | verified | source_restored_runtime_unverified | [unreal](RuntimeFilesDownloader.json) |
| spark | verified | package_checks_blocked | [javascript](spark.json) |
| storyteller-bevy | verified | build_and_tests_passed | [rust](storyteller-bevy.json) |
| storyteller-ml | verified | audit_blocked | [details](storyteller-ml.json) |
| StreamTwo | verified | source_restored_runtime_unverified | [unreal](StreamTwo.json) |
| terraform-aws-observability-accelerator | verified | syntax_checked_runtime_unverified | [python](terraform-aws-observability-accelerator.json) |
| torchscript-models | verified | syntax_checked_runtime_unverified | [python](torchscript-models.json) |
| UE4-OSC | verified | source_restored_runtime_unverified | [unreal](UE4-OSC.json) |
| UnrealZeroMQ | verified | source_restored_runtime_unverified | [unreal](UnrealZeroMQ.json) |
| vits-finetuning | verified | syntax_checked_runtime_unverified | [python](vits-finetuning.json) |
| voder-proxy | verified | build_or_tests_blocked | [rust](voder-proxy.json) |
| winit | verified | build_or_tests_blocked | [rust](winit.json) |
| winprint.rs | verified | build_or_tests_blocked | [rust](winprint.rs.json) |
| xsens-packet-send | verified | build_or_tests_blocked | [rust](xsens-packet-send.json) |

## Coverage

{"audit_blocked": 3, "build_and_tests_passed": 9, "build_or_tests_blocked": 16, "empty_repository": 1, "manifest_or_source_dependency_blocked": 1, "package_checks_blocked": 1, "source_restored_runtime_unverified": 21, "syntax_checked_runtime_unverified": 6, "tests_blocked": 1}

59 repository result files received. Any omitted repository is unverified.

## Concrete missing source paths

- artcraft-services: Cargo.toml -> crates/lib/shared_service_components
- artcraft-services: crates/lib/deprecated/machine_learning/ml_models/Cargo.toml -> ../image_algorithms
- artcraft-services: crates/vendor/candle/candle-examples/Cargo.toml -> examples/lcm/debug_test.rs
- cloudcam: Cargo.toml -> ../kinect.rs
- designcraft: Cargo.toml -> crates/testkit
- placeholder-artcraft: Cargo.toml -> crates/api_clients/artcraft_api_defs
- placeholder-artcraft: Cargo.toml -> crates/lib/build_metadata
- placeholder-artcraft: Cargo.toml -> crates/api_clients/cloud_storage
- placeholder-artcraft: Cargo.toml -> crates/lib/cloudflare_errors
- placeholder-artcraft: Cargo.toml -> crates/service/plugins/component_traits
- placeholder-artcraft: Cargo.toml -> crates/lib/cookie_store
- placeholder-artcraft: Cargo.toml -> crates/lib/data/crockford
- placeholder-artcraft: Cargo.toml -> crates/schema/public/enums
- placeholder-artcraft: Cargo.toml -> crates/schema/public/enums_public
- placeholder-artcraft: Cargo.toml -> crates/lib/errors
- placeholder-artcraft: Cargo.toml -> crates/api_clients/fal_client
- placeholder-artcraft: Cargo.toml -> crates/lib/files/file_to_base64_url
- placeholder-artcraft: Cargo.toml -> crates/lib/files/filesys
- placeholder-artcraft: Cargo.toml -> crates/lib/idempotency
- placeholder-artcraft: Cargo.toml -> crates/lib/files/images
- placeholder-artcraft: Cargo.toml -> crates/lib/jwt_light
- placeholder-artcraft: Cargo.toml -> crates/lib/caching/memory_caching
- placeholder-artcraft: Cargo.toml -> crates/lib/caching/memory_store
- placeholder-artcraft: Cargo.toml -> crates/api_clients/midjourney_client
- placeholder-artcraft: Cargo.toml -> crates/lib/files/mimetypes
- placeholder-artcraft: Cargo.toml -> crates/api_clients/openai_sora_client
- placeholder-artcraft: Cargo.toml -> crates/lib/data/primitives
- placeholder-artcraft: Cargo.toml -> crates/lib/shared_service_components
- placeholder-artcraft: Cargo.toml -> crates/schema/database/sqlite_tasks
- placeholder-artcraft: Cargo.toml -> crates/api_clients/storyteller_client
- placeholder-artcraft: Cargo.toml -> crates/lib/subprocess_common
- placeholder-artcraft: Cargo.toml -> crates/lib/test_data
- placeholder-artcraft: Cargo.toml -> crates/lib/testing
- placeholder-artcraft: Cargo.toml -> crates/schema/public/tokens
- placeholder-artcraft: Cargo.toml -> crates/lib/data/web_base64
- placeholder-artcraft: crates/vendor/candle/candle-examples/Cargo.toml -> examples/lcm/debug_test.rs
- realtime-voice-conversion: Cargo.toml -> /home/bt/dev/world-sys

## Original Git references and service/model requirements

Each repository JSON records pinned Git dependencies, missing Cargo paths, model filename references, service domains, exact commands, exit codes and limitations. Logs are retained in this run's GitHub Actions artifacts. Original releases/installers, hosted databases, API credentials, paid plugins and external model downloads are not automatically preserved by a source archive.

The previously unavailable moonTripoSR and glow-tts-multispeaker references remain unresolved. See ../dependencies/status.json.
