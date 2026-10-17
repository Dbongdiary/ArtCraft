# ArtCraft

Independent source archive of **66 public repositories** from [storytold](https://github.com/storytold), stored in the Dbongdiary account.

**Backup status: 66/66 source repositories complete.** See [.archive/status.json](.archive/status.json) and [repository manifests](.archive/repositories) for exact capture times, checksums, exclusions and remaining issues. The inventory is frozen at 2026-10-17T20:04:16Z; rerunning resumes incomplete entries.

**Submodule dependencies are references only:** 9 linked commit references have been preserved, but linked repositories are not independently archived by this workflow.

Each named folder contains that repository's default-branch source tree. Files larger than 100 MiB are omitted from the browsable folder and listed with exact paths and SHA-256 hashes in its manifest; their contents remain in the full Git bundle. Git LFS pointer files remain unchanged, and available LFS payloads are saved separately. Original licenses and notices are preserved.

[Download the independent Git history and LFS archives](https://github.com/Dbongdiary/ArtCraft/releases/tag/storytold-source-backup). These release assets belong to this repository and do not require the source organization to remain available. Git bundles retain all advertised refs, branches, tags and reachable objects. An empty repository is represented by an explanatory file and manifest.

## Restore one repository

Download its bundle assets from the release. For a split bundle, concatenate the exact asset names listed in its manifest, in part order: `cat PART1 PART2 > NAME.bundle`. For a single bundle, rename the downloaded content-addressed asset to `NAME.bundle`. Verify the whole-file SHA-256 against the manifest, then run `GIT_LFS_SKIP_SMUDGE=1 git clone --branch DEFAULT_BRANCH NAME.bundle NAME` using the manifest default branch.

For LFS, concatenate numbered tar parts if present, verify the checksum, and extract `NAME.lfs.tar` inside the cloned repository's `.git` directory. Then run `git lfs checkout` in that repository. The archive contains `lfs/objects/...` paths.

## Scope and limitations

This is a source and Git-history snapshot. Submodule commit references and original `.gitmodules` files are preserved; linked submodule repositories are not recursively fetched, so external dependencies may disappear independently. Original issue discussions, pull-request conversations, release assets, deployments and private/deleted repositories unavailable at capture time are outside this backup. The upstream listing currently exposes 66 public repositories; this archive makes no claim about any additional inaccessible repositories.

No source repository is cloned onto the user's Mac. Cloning, inspection and transfer happen only on an ephemeral GitHub Actions runner. Source code, hooks, workflows and build scripts are never executed.
