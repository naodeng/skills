# AGENTS.md

This file defines the maintenance rules for the `30-days-learning-plan-project-creator` skill. The skill is a Markdown documentation package, not an executable application.

## Scope and file map

Keep changes inside this directory unless the user explicitly requests a broader repository update.

| Path | Responsibility |
| --- | --- |
| `SKILL.md` | Canonical instructions, contracts, workflow, and validation checklist |
| `README.md` | Short orientation and quick-use summary; keep it aligned with `SKILL.md` |
| `references/project-structure.md` | Detailed repository, generator, site, and Pages contracts |
| `agents/openai.yaml` | Display metadata and default invocation prompt |

Do not add generated sites, course repositories, screenshots, caches, or temporary audit reports to this directory unless the user explicitly asks for an example or fixture.

## Editing rules

- Preserve the skill name `30-days-learning-plan-project-creator` and the directory name.
- Keep frontmatter valid YAML. The `description` must start with `Use when`, describe triggering conditions only, and stay concise; do not summarize the workflow there.
- Treat `SKILL.md` as the source of truth. When its contracts change, update `README.md` and `references/project-structure.md` in the same change.
- Keep the skill topic-agnostic. Use placeholders such as `TOPIC` only in reference examples, and require agents to replace them consistently in generated projects.
- Preserve technical names, commands, identifiers, paths, and URLs when describing localization behavior.
- Do not hard-code secrets, analytics tokens, private data, or a reference project's unrelated product names.
- Do not claim that a Pages deployment or public URL was verified unless it was checked remotely in the current task.
- Do not create a version number or changelog unless the repository adopts a versioning convention; document-only fixes do not require one here.

## Required behavior documented by the skill

Generated projects must have one canonical total plan, exactly 30 daily Markdown sources, a reproducible site builder, observable build tests, bilingual documentation, and a Pages workflow. Generated HTML belongs in `_site/` and must not be hand-edited or delivered as source.

When a reference project is supplied, reuse its responsibilities and recognizable interaction contract, but replace its topic-specific names and content. Branded icon assets and reference-only interactions are conditional on the selected project contract.

## Validation before delivery

From the repository root, run the checks that apply to the changed files:

```bash
python3 - <<'PY'
from pathlib import Path
import re

p = Path('30-days-learning-plan-project-creator/SKILL.md')
frontmatter = p.read_text().split('---', 2)[1]
description = re.search(r'^description:\s*(.+)$', frontmatter, re.M).group(1)
assert description.startswith('Use when ')
assert len(description) <= 500
print('skill metadata: PASS')
PY
git diff --check
```

Also verify that every relative Markdown link under this directory resolves and that `SKILL.md`, `README.md`, `agents/openai.yaml`, and `references/project-structure.md` remain present. If a repository-level Skill validator exists, run it as well. Static checks validate the package only; they do not prove that a generated course site renders correctly or that Pages deployment succeeded.

## Git safety

Inspect `git status --short` before and after editing. Stage or commit only this Skill's task-owned files when explicitly requested. Do not reset, delete, or overwrite unrelated user changes, and do not push without explicit permission.
