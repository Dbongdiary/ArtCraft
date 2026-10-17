# ArtCraft

Independent source archive of **66 public repositories** from [storytold](https://github.com/storytold), stored in the Dbongdiary account.

**Backup status: 66/66 source repositories complete.** See [.archive/status.json](.archive/status.json) and [repository manifests](.archive/repositories) for exact capture times, checksums, exclusions and remaining issues. The inventory is frozen at 2026-10-17T20:04:16Z; rerunning resumes incomplete entries.

**Dependency archive status:** 7/9 pinned root references independently archived and materialized. See [.archive/dependencies/status.json](.archive/dependencies/status.json).

Each named folder contains that repository's default-branch source tree. Files larger than 100 MiB are omitted from the browsable folder and listed with exact paths and SHA-256 hashes in its manifest; their contents remain in the full Git bundle. Git LFS pointer files remain unchanged, and available LFS payloads are saved separately. Original licenses and notices are preserved.

[Download the independent Git history and LFS archives](https://github.com/Dbongdiary/ArtCraft/releases/tag/storytold-source-backup). These release assets belong to this repository and do not require the source organization to remain available. Git bundles retain all advertised refs, branches, tags and reachable objects. An empty repository is represented by an explanatory file and manifest.

## Restore one repository

Download its bundle assets from the release. For a split bundle, concatenate the exact asset names listed in its manifest, in part order: `cat PART1 PART2 > NAME.bundle`. For a single bundle, rename the downloaded content-addressed asset to `NAME.bundle`. Verify the whole-file SHA-256 against the manifest, then run `GIT_LFS_SKIP_SMUDGE=1 git clone --branch DEFAULT_BRANCH NAME.bundle NAME` using the manifest default branch.

For LFS, concatenate numbered tar parts if present, verify the checksum, and extract `NAME.lfs.tar` inside the cloned repository's `.git` directory. Then run `git lfs checkout` in that repository. The archive contains `lfs/objects/...` paths.

## Scope and limitations

This is a source and Git-history snapshot. Original submodule references remain in the source Git bundles. Available exact pinned dependency trees are now materialized in the browsable parent folders; unresolved dependencies remain recorded in the separate dependency report. Original issue discussions, pull-request conversations, release assets, deployments and private/deleted repositories unavailable at capture time are outside this backup. The upstream listing currently exposes 66 public repositories; this archive makes no claim about any additional inaccessible repositories.

No source repository is cloned onto the user's Mac. Cloning, inspection and transfer happen only on an ephemeral GitHub Actions runner. The archival workflows do not execute source code, hooks or build scripts; the separate verification workflow executes builds and tests only on GitHub runners.


<!-- dependency-backup:start -->
## External dependency archive

**7/9 original pinned dependency references complete.** Available dependencies are stored under `dependencies/OWNER/REPO/COMMIT` and copied into the original parent submodule paths. Nested dependencies are recursively archived at their exact pinned commits; unresolved sources remain explicitly incomplete. The dependency archival workflow does not execute source code or hooks.

[Dependency history and LFS release assets](https://github.com/Dbongdiary/ArtCraft/releases/tag/storytold-dependency-backup) are independent of the original authors. [.archive/dependencies/status.json](.archive/dependencies/status.json) records every root reference and remaining error; individual manifests include checksums, exact commits, tree verification and large-file exclusions. Files over100MiB remain in full Git bundles where GitHub cannot store them as ordinary browsable files. Original source backup status and original release assets are preserved.

History scope limits after an integrity check rejected a historical submodule URL. Each successful replacement archive passed the same unchanged Git integrity checks:

- `NVIDIA/apex` at `37cdaf4ad57ab4e7dd9ef13dbed7b29aa939d061`: GitHub pull-request refs and other non-branch/tag refs excluded.

Unresolved references:

- `storytold/storyteller-ml/3d_generation/moonTripoSR`: No source URL is recorded for this gitlink; no substitute repository was guessed
- `storytold/torchscript-models/glow-tts-jaywalnut-multispeaker/glow-tts-multispeaker`: Git clone failed (exit 128). Source repository is inaccessible with the available authentication.

To restore an exact dependency: concatenate any bundle parts in manifest order, verify SHA-256, then run `GIT_LFS_SKIP_SMUDGE=1 git clone NAME.bundle NAME`. In that clone run `GIT_LFS_SKIP_SMUDGE=1 git checkout --detach PINNED_COMMIT`. If LFS payloads exist, extract their verified tar into `.git` and run `git lfs checkout`. Original submodule configurations remain preserved for provenance; the browsable parent copies contain materialized source folders.
<!-- dependency-backup:end -->

## Backup usability verification

See [.archive/verification/FINDINGS.md](.archive/verification/FINDINGS.md) for the conclusions, [.archive/verification/README.md](.archive/verification/README.md) for all 66 result records, and [.archive/verification/REQUIREMENTS.md](.archive/verification/REQUIREMENTS.md) for missing runtime requirements. A source backup is not a guarantee that every app or hosted feature works. Backup workflows do not execute source; the separately requested verification workflow runs builds/tests on ephemeral GitHub runners.
