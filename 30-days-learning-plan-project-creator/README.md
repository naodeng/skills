# 30 Days Learning Plan Project Creator

Create a reproducible, Markdown-first 30-day learning-plan repository with
bilingual documentation, daily lessons, a generated static site, tests, and
GitHub Pages deployment.

## When to use this Skill

Use this Skill when you want to:

- create a new 30-day learning plan for a specific topic;
- restructure an existing learning-plan repository;
- produce bilingual `README.md` and `README_EN.md` files;
- generate a static course website from Markdown; or
- prepare a GitHub Pages deployment workflow.

## Expected project structure

The resulting project normally includes:

- one topic-specific total plan;
- exactly 30 daily Markdown lessons in a topic plan directory;
- `scripts/build_site.py` and generated `_site/` pages;
- shared assets under `site/assets/`;
- `tests/test_build_site.py`;
- bilingual README and deployment documentation;
- `.github/workflows/pages.yml`; and
- `AGENTS.md`, `LICENSE`, and `.gitignore`.

The exact topic name, directory prefix, and lesson slugs should match the
requested project. Technical names, commands, identifiers, paths, and URLs
should remain unchanged when content is localized.

## Workflow

1. Inspect the target repository, local instructions, Git status, and any
   reference project.
2. Define the 30-day curriculum arc and its practical deliverables.
3. Write the total plan and daily lesson sources.
4. Build the static site from the canonical Markdown sources.
5. Add bilingual documentation and the Pages workflow.
6. Run the repository checks and inspect the final Git diff.

## Validation

Run the project's established checks, typically:

```bash
python3 -m py_compile scripts/build_site.py
python3 scripts/build_site.py
python3 tests/test_build_site.py
git diff --check
```

Before delivery, confirm that there are 30 daily source files, 31 generated
HTML pages, working lesson links and navigation, no generated artifacts or
cache files in the change, and no unverified deployment claims.

For the complete operating instructions, see [SKILL.md](SKILL.md).
