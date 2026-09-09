---
name: dual-repository-release
description: Use when a version must be released or verified in both a fork/project repository and an upstream repository, especially when tags, GitHub Releases, CI, or branch targets may differ.
---

# Dual Repository Release

Use this for coordinated releases across two repositories. The release is a set of independently verified facts, not an assumption based on a local tag or one successful command.

## Before changing remote state

1. Inspect local status and remotes. Preserve unrelated changes.
2. Resolve which remote is the project/fork and which is upstream from repository metadata. Do not infer this from a remote name alone. If they are not related, treat them as two independent repositories and say so.
3. Identify the intended version, release commit, and required branch. Check that existing tags and Releases do not already use the version for a different iteration.
4. Verify each remote's target branch and release commit. Do not default the target branch to `main`; derive it from the project's release rule or explicit user direction. If the two branches do not resolve to the intended same commit, stop and report the divergence.
5. Run the project's release-relevant local validation. Separate a missing environment from a failed test; neither is a pass.

## Delivery boundary

Create commits, push, tag, publish packages, or create Releases only when the user has authorized those actions. A request to inspect readiness is read-only.

For an authorized delivery, prefer an annotated tag at the verified commit. Create and verify each repository independently. When using GitHub CLI, pass `--repo` explicitly for each Release and use `--target <verified-sha>` when creating a Release. Do not use a positional SHA as a substitute for `--target`. A readiness-only review should prefer checks that leave no worktree artifacts; disclose any local command that may generate output.

## Completion evidence

Report a compact per-repository matrix:

| Check | Project/fork | Upstream |
| --- | --- | --- |
| target branch SHA | value or gap | value or gap |
| annotated tag exists; peeled tag ref resolves to target commit | value or gap | value or gap |
| formal Release | URL/state or gap | URL/state or gap |
| required CI | run/result or gap | run/result or gap |

A Release is complete only when an annotated tag exists and its peeled tag ref resolves to the intended commit, is non-draft and non-prerelease if that was requested, and the repository-specific evidence is present. The annotated tag object SHA is tag metadata, not the release commit SHA. State package-registry publication separately because it is not proved by a GitHub Release.

## Common failure modes

- A CLI defaults to upstream: pass `--repo` and re-read the returned URL.
- A later version was assigned to the wrong iteration: inspect prior tags, releases, changelog, and version metadata before changing anything.
- Only one remote was updated: compare both remote branch and peeled-tag SHAs after delivery.
- A local gate cannot run: report the missing dependency or permission; do not reuse old CI as current proof.
