---
name: ai-qa-weekly
description: >
  Use when users ask for a current weekly digest, recent developments, tools,
  research, or releases at the intersection of AI and software testing,
  quality engineering, agent evaluation, LLM quality, reliability, or test
  automation, especially when the result must be bilingual and source-backed.
---

# AI QA Weekly

Create a concise, evidence-based bilingual Markdown digest of meaningful
developments at the intersection of AI and software quality. The intersection
is mandatory: general AI news and general QA news are not enough on their own.

This Skill uses the agent's current web, GitHub, and research discovery
capabilities. It does not create a crawler, database, backend, RSS collector,
ranking service, or scheduled job.

## Required workflow

1. Define and state the coverage window before searching.
   - A Monday scheduled report covers the previous calendar week, Monday
     00:00 through Sunday 23:59, in the user's local timezone when known.
   - A manual weekly request covers the most recent completed seven-day period
     unless the user supplies another range.
2. Read [topics.md](references/topics.md), [sources.md](references/sources.md),
   and [search-strategy.md](references/search-strategy.md) before discovery.
3. Search across the topic taxonomy and multiple source types. Do not rely on
   one generic `AI QA` query.
4. Verify each candidate against the original publication, release,
   announcement, paper, or meaningful update. Search/index dates, crawl dates,
   footer dates, and a repository's incidental commit date are not sufficient.
5. Apply every relevance gate below, deduplicate underlying developments, and
   select only the candidates that remain.
6. Read [output-template.md](references/output-template.md), then produce the
   bilingual digest and run the final validation checklist.

## Relevance gates

Every included item must pass all four gates:

| Gate | Include only when |
| --- | --- |
| Freshness | The meaningful event occurred inside the stated coverage window. |
| AI relevance | AI, LLMs, agents, machine learning, AI evaluation, or AI-assisted engineering is materially involved. |
| QA relevance | It materially concerns testing, QA/QE, test automation or generation, agent/LLM evaluation, reliability, performance, testing infrastructure, software quality, or developer quality. |
| Reporting value | A QA Engineer, SDET, QE, Test Architect, or quality-focused engineer would reasonably benefit from knowing it. |

Reject a candidate when any gate is `NO`. Do not weaken the gates to reach a
target count.

## Evidence and selection rules

- Target 8–12 items, but publish fewer when fewer developments genuinely pass.
- Prefer a direct primary source in the final link: official announcement or
  changelog, GitHub release/repository, original paper, or engineering blog.
  Community posts and technical media are discovery or corroboration signals;
  they do not replace an available primary source.
- Never invent a URL, date, metric, ranking, or claim. If the original source
  cannot be located and verified, exclude the candidate. Do not retain a
  provisional item with “add the link later”, a placeholder URL, a search
  result, or a prose note standing in for the required link. Missing-link
  candidates are not publishable items.
- For GitHub, distinguish repository creation, release, meaningful feature,
  commit activity, and project update. A recent commit does not make an old
  repository new.
- For research, prefer a paper with an implementation, dataset, benchmark, or
  reproducible evaluation, and do not present early research as production
  readiness.
- Treat multiple reports about one release, project, paper, feature, or
  benchmark as one item. Keep the most authoritative link.
- Assign exactly one primary category from [topics.md](references/topics.md).
  Do not invent category names or duplicate an item across categories.
- Try to include official/industry, open-source/tool, and research/engineering
  practice perspectives when the evidence supports them, but do not impose
  quotas.

## Exclusions

Normally exclude generic AI news, generic QA news without AI relevance, jobs,
hiring, interview questions, certifications, courses, bootcamps, SEO content,
sponsored listicles, generic tutorials, duplicate coverage, old content
presented as new, minor bug fixes, and commercial announcements without
technical substance. A major model release is eligible only when the relevant
development is testing, evaluation, quality, automation, reliability, or
software-engineering quality.

## Output contract

Use the structure in [output-template.md](references/output-template.md).
Every item must include:

- Chinese title and English title;
- exactly one canonical category;
- source name and meaningful publication/update date;
- a factual Chinese description of at most 100 Chinese characters;
- a factual English description of at most 100 words (30–60 words is usually
  enough); and
- a direct original-source link.

State the issue/publication date and exact coverage period. Explain what
happened and why it matters to QA; do not copy marketing language or call an
item “best”, “revolutionary”, or “game-changing” without source support.

## Final validation

Before returning the digest, confirm:

- the coverage boundaries and timezone are stated and correct;
- every meaningful event is inside the coverage window;
- every item passes AI relevance, QA relevance, and reporting value;
- every item has a verifiable direct source link and accurate source date;
- duplicates are collapsed;
- every category is from the canonical taxonomy;
- Chinese and English description limits are met; and
- no unsupported claims or placeholder links remain.

Remove an item that fails validation instead of filling the target count.

If the input supplies synthetic candidates without real URLs, demonstrate the
filter by excluding those candidates or report that no publishable item has
been verified yet. Never convert missing evidence into a follow-up task inside
the digest.
