# Project Structure Reference

Use this reference for the repository contract. It is intentionally topic-agnostic, but every `TOPIC` placeholder must be replaced consistently with the requested product or subject name.

```text
project/
├── TOPIC_qa_30_day_learning_plan.md
├── topic-qa-30-day-plan/
│   └── day-01-meaningful-english-slug.md ... day-30-meaningful-english-slug.md
├── scripts/build_site.py
├── site/assets/style.css
├── site/assets/app.js
├── site/assets/site-icon.svg
├── site/assets/favicon-32.png
├── site/assets/apple-touch-icon.png
├── tests/test_build_site.py
├── .github/workflows/pages.yml
├── README.md / README_EN.md
├── DEPLOYMENT.md / DEPLOYMENT_EN.md
├── AGENTS.md
├── LICENSE
└── _site/                         # generated; do not hand-edit or commit
```

## Document-shape contract

The README pair should follow the reference project's full guide shape: language switch, project overview, audience and prerequisites, 30-day goals, daily rhythm, phase table, daily lesson index, usage guidance, final deliverables, content sources, repository structure, and license. The deployment pair should include language switch, source table, clone/build/preview commands, update flow, verification commands, GitHub Pages setup, maintenance principles, and license. `AGENTS.md` should describe the actual project paths and maintenance invariants, not remain a generic three-line note.

The total plan should contain a 30-row daily index linking to the canonical lesson files. The canonical daily directory must contain exactly 30 files. Do not preserve root-level daily duplicates or names copied from the reference product.

## Rendered-site contract

When the reference project has an established site template, reuse its responsibilities: a shared `html_page()` wrapper, external CSS and JS, brand/favicon assets, consistent header and footer, homepage search/filter controls, phase navigation, lesson cards, print behavior, and previous/next lesson links. Change the title, topics, phase names, and explanatory copy to the requested subject, but keep the interaction and asset architecture recognizable. Analytics may be optional, but if included it must use a CI secret or environment variable rather than a copied token.

## Generator contract

The builder should:

1. read the total plan only for overview content when needed;
2. discover the 30 daily Markdown files from the canonical daily directory;
3. parse the day number and title from each H1 or an equivalent stable convention;
4. render Markdown sections used by the course, including headings, paragraphs, lists, links, code, tables, and checklists as applicable;
5. generate `_site/index.html` and `_site/days/day-N.html` (or stable slug pages);
6. copy or reference shared assets from `site/assets/`, including the reference site's icon assets when applicable;
7. fail loudly if the lesson count is not exactly 30 or a required source file is missing;
8. keep generated paths and source links consistent with the topic-specific directory names.

## README contract

Both README files should explain the audience, prerequisites, outcomes, phase map, source paths, local build commands, deployment workflow, current-state caveats, and license. Keep bilingual structure aligned while translating natural-language prose; preserve technical names, commands, identifiers, URLs, and file paths.

## Pages contract

The workflow should build from a clean checkout, run the standard-library or declared build command, upload `_site`, and deploy with the official Pages actions. Pages source must be GitHub Actions. The final report may only include a public URL after checking the actual remote deployment.
