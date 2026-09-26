# AI QA Weekly

`ai-qa-weekly` is a lightweight Agent Skill for discovering and writing a
source-backed bilingual weekly digest of meaningful developments across AI ×
software testing and quality engineering.

## What it covers

- AI Testing
- Agent Testing
- LLM Quality
- Test Automation
- Quality Engineering
- Performance & Reliability
- Tools & Projects
- Research & Trends

## What it produces

Each normal issue contains exactly 10 candidates selected from one unified
pool of Chinese/Chinese-language and international developments. The output
has a complete Chinese edition followed by a complete English edition. Both
editions contain the same 10 items in the same order, with descriptions longer
than 200 characters and matching facts, categories, dates, sources, and links.

## How it works

The Skill searches current Chinese/Chinese-language and international official,
GitHub, research, engineering, media, and community sources; verifies
freshness and the AI × QA intersection; scores all passing candidates
together; removes duplicates; and formats two equivalent Markdown editions.
Read the focused references when running it:

- [topics.md](references/topics.md) — taxonomy and query vocabulary;
- [sources.md](references/sources.md) — source hierarchy and evidence rules;
- [search-strategy.md](references/search-strategy.md) — bilingual discovery,
  unified scoring, and filtering;
- [output-template.md](references/output-template.md) — two-edition issue
  format; and
- [relevance.md](evals/relevance.md) — manual relevance cases.

## Current-source and discovery boundaries

Weekly claims must be supported by pages opened and verified during the current
run. Model memory, prior issues, prompt-supplied claims, and search snippets
are not evidence. If current external retrieval is unavailable, return no
publishable items and mark unsupported candidates `INSUFFICIENT_EVIDENCE`.

This repository is a source catalog, not itself a Codex runtime discovery
root. For local Codex use, install or link the Skill into a supported user
Skill directory, then restart Codex if needed:

```bash
mkdir -p ~/.agents/skills
ln -sfn /absolute/path/to/skills/ai-qa-weekly ~/.agents/skills/ai-qa-weekly
```

Verify discovery with an explicit `$ai-qa-weekly` invocation or the runtime's
Skill list. A GitHub push of this source directory does not by itself prove
runtime discovery.

## Schedule and boundaries

For a Monday report, the default coverage is the previous Monday through
Sunday in the user's local timezone. A manual request uses the most recent
completed seven-day period unless another range is specified.

This package intentionally has no backend, crawler, database, RSS collector,
vector database, web UI, or scheduler. Use an external scheduler to trigger a
weekly run; the Skill remains responsible for discovery and content quality.

## Example requests

```text
Generate this week's AI QA Weekly.
Generate the AI QA Weekly for 2026-09-21 through 2026-09-27.
Generate a 10-item AI QA digest with separate Chinese and English editions,
each with verified original sources and descriptions longer than 200
characters.
```

Version: 1.0.2

Last Verified: 2026-09-26
