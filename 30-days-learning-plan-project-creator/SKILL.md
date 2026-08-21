---
name: 30-days-learning-plan-project-creator
description: Create Markdown-first 30-day learning plan repositories with bilingual docs, daily lessons, static sites, and GitHub Pages deployment.
---

# 30 Days Learning Plan Project Creator

Create or restructure a complete 30-day learning-plan repository for a user-specified topic. Use this skill when the user asks for a course project, learning-plan repository, bilingual README, static course website, or GitHub Pages workflow modeled on the reference project pattern.

## Required outcome

Produce a repository that is Markdown-first and reproducible:

- `TOPIC_qa_30_day_learning_plan.md` (or an equivalent topic-specific total plan)
- `topic-qa-30-day-plan/day-*.md` with exactly 30 daily source files
- `scripts/build_site.py` that generates `_site/` from the Markdown sources
- `site/assets/` for shared CSS and browser-side behavior
- `site/assets/site-icon.svg`, `favicon-32.png`, and `apple-touch-icon.png` when the reference site uses branded assets
- `tests/test_build_site.py` for observable build invariants
- `.github/workflows/pages.yml` for GitHub Pages deployment
- `README.md` and `README_EN.md`
- `DEPLOYMENT.md` and `DEPLOYMENT_EN.md`
- `AGENTS.md`, `LICENSE`, and `.gitignore`

The exact topic prefix and lesson slugs should be natural for the project. Keep the reference repository's separation of source files, generator, assets, tests, and generated output; do not collapse the project into a single HTML file. The canonical source directory and total-plan filename must use the requested topic, not the name of the reference project.

When a reference project is supplied, match its rendered-site contract as well as its repository contract. Port the shared page template, external stylesheet, frontend script, favicon/brand assets, header links, footer, print behavior, search/filter interactions, and lesson navigation. Replace the reference product's content and labels with the requested topic; do not substitute a separate visual system unless the user asks for a redesign.

Never leave transitional duplicates in the finished repository: do not keep root-level `day-*.md`, a second total-plan file, or `playwright-*` names in a DeepSeek project. If a reference project is used, copy its responsibilities and document shape, not its product name.

## Workflow

1. Inspect the target repository, local instructions, current Git status, and the reference project's structure before editing. Preserve unrelated user changes.
2. Decide the curriculum arc before writing files. Prefer five or six phases, with each phase having a clear capability progression and a concrete deliverable. Include weekly review or milestone days when they improve retention.
3. Write the total plan first. It must include the audience, prerequisites, 30-day goals, daily rhythm, phase table, a 30-row daily lesson index with links, usage guidance, final deliverables, source links, repository structure, and license. Each day needs a distinct topic, learning objective, official or primary reading, hands-on task, deliverable, and self-check. Make the final five days converge on a realistic capstone.
4. Create exactly 30 daily Markdown source files under the topic plan directory. Use stable, lowercase English slugs even when the lesson content is Chinese. Keep technical names, commands, APIs, identifiers, paths, and URLs unchanged.
5. Build the site from the canonical daily Markdown files. Generate one homepage and 30 lesson pages. The homepage must expose the phases and all 30 lessons; each lesson page must have working home/previous/next navigation and a language entry point if an English site is implemented.
6. Keep shared presentation in `site/assets/` and keep generated HTML in `_site/`. The generator should link the external CSS and JS assets instead of embedding a one-off replacement stylesheet. Never hand-edit generated pages. Preserve the reference site's accessible headings, links, focus states, responsive layout, print behavior, search/filter behavior, header/footer, and lesson navigation.
7. Add bilingual README and deployment documentation with the same document shape as the reference project. README files should cover audience, prerequisites, goals, daily rhythm, phase table, usage, deliverables, content sources, repository structure, and license. Deployment files should cover source files, clone/build/preview commands, content update flow, verification commands, Pages settings, maintenance principles, and license. Do not claim a published URL unless the remote deployment was actually verified.
8. Add a GitHub Actions Pages workflow triggered by `main` and `workflow_dispatch`, using `actions/upload-pages-artifact` and `actions/deploy-pages`. Keep permissions limited to `contents: read`, `pages: write`, and `id-token: write`.

## Content and research boundaries

- For current models, APIs, prices, product behavior, or external documentation, browse current primary sources and link them near the relevant claims.
- Date volatile claims and identify developer previews or compatibility-breaking software clearly.
- Do not put secrets, API keys, analytics tokens, or private data into source files, examples, screenshots, or generated pages.
- If the reference site has analytics, preserve the injection point but read the token from an environment variable or CI secret such as `CLOUDFLARE_WEB_ANALYTICS_TOKEN`; never copy the reference token into source code.
- Treat AI-generated code and curriculum claims as drafts until checked against the official source and a runnable example.
- Keep the plan practical: every day leaves evidence that another learner can inspect or reproduce.

## Validation before completion

Run the project's actual checks, adapting commands only when the repository has an established equivalent:

```bash
python3 -m py_compile scripts/build_site.py
python3 scripts/build_site.py
python3 tests/test_build_site.py
git diff --check
```

Verify all of the following:

- exactly 30 daily Markdown source files exist;
- the total-plan table contains 30 daily rows with links to the canonical daily files;
- all project-facing paths and names use the requested topic consistently;
- no root-level duplicate lesson files, second total plan, or reference-product names remain;
- `_site/` contains 31 HTML files: home plus 30 lessons;
- every homepage lesson link resolves to a generated page;
- every lesson has a working home link and correct next/finish navigation;
- generated HTML links the expected external CSS and JS assets and includes the expected icon assets;
- homepage search/filter controls and lesson navigation are present when they exist in the reference site;
- no generated list-marker leaks or unescaped obvious Markdown syntax remain;
- README and deployment docs name the actual source paths and commands;
- `git status --short` shows only task-owned changes;
- `_site/`, `__pycache__/`, and `.pyc` files are ignored or excluded from delivery.

If browser inspection or remote Pages verification was not performed, report that limitation explicitly instead of implying visual or deployment proof.

## Supporting reference

Read [references/project-structure.md](references/project-structure.md) when creating or auditing the repository layout, generator contract, and deployment workflow.
