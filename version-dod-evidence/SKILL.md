---
name: version-dod-evidence
description: Use when deciding whether a feature, iteration, or version is genuinely ready to close, release, or describe as complete, particularly when evidence comes from several kinds of validation.
---

# Version DoD Evidence

Use this skill to assess a version against its written acceptance criteria without inflating partial validation into completion.

## Establish the acceptance basis

Read the version specification, roadmap, issue, or user request first. Convert only explicit acceptance items into a matrix. Do not invent requirements merely because a repository has common tooling. If no acceptance basis is available, report the decision as incomplete or unable to determine; do not report complete.

Keep each item in one of these states: `verified`, `failed`, `not run`, `blocked`, or `not applicable`. A claim without an inspectable result is not verified. Use `blocked` for an environment, dependency, permission, or runner problem; use `failed` when the required behavior itself does not meet the criterion. Include the relevant error in the evidence.

## Keep evidence types separate

Use distinct rows or columns for:

- unit/integration tests and the exact command result;
- evals, fixtures, or adversarial cases;
- build, lint, formatting, and packaging checks;
- browser, device, or real integration execution when required;
- review/PR status and remote CI;
- release/tag/package state when delivery is in scope.

Passing a narrow test selection, static schema check, or small eval does not prove a broader lifecycle, browser path, external integration, or release state. A test executable that errors is unavailable evidence, not successful execution.

## Decision rule

Mark the version complete only when every applicable acceptance item is verified. If an item is `failed`, `not run`, or `blocked`, report the version as incomplete and name the smallest next action.

Use `release-ready with stated exclusions` only for a release decision when the user explicitly accepts each documented exclusion and none violates a non-negotiable acceptance item. It does not mean the version is complete: retain the incomplete DoD state and name the excluded evidence.

For a read-only review, do not modify source, issues, or remote state. For an implementation task, use the matrix to prioritize the remaining work, then re-run the relevant checks after changes.

## Report format

Start with the decision: `complete`, `incomplete`, or `release-ready with stated exclusions`. Then provide a compact matrix:

| Acceptance item | Evidence | State | Gap / next action |
| --- | --- | --- | --- |

Clearly distinguish current-turn evidence from historical records. Historical results can guide investigation but must not be presented as current verification for changed code or a new release.

## Common misstatements to avoid

- “All done” based only on passing unit tests.
- Treating a missing dependency, unavailable credentials, or skipped browser runner as a pass.
- Reporting a Release as proof of implementation quality, or tests as proof of delivery.
- Silently accepting a changed or incomplete acceptance scope.
