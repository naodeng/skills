---
name: ai-qa-weekly
description: >
  Use when users ask for a current weekly digest, recent developments, tools,
  research, or releases at the intersection of AI and software testing,
  quality engineering, agent evaluation, LLM quality, reliability, or test
  automation, especially when the result must be bilingual and source-backed.
---

# AI QA Weekly

Create an evidence-based weekly Markdown digest of meaningful developments at
the intersection of AI and software quality. The intersection is mandatory:
general AI news and general QA news are not enough on their own. The normal
delivery contains two standalone editions: a Chinese edition followed by an
English edition. They contain the same 10 items in the same order, with the
same facts, categories, dates, sources, and links.
Discover Chinese/Chinese-language and international candidates, then rank them
together; source language or geography never substitutes for AI-Native QA
relevance or evidence.

This Skill uses the agent's current web, GitHub, and research discovery
capabilities. It does not create a crawler, database, backend, RSS collector,
ranking service, or scheduled job.

## Current-source gate

Weekly claims MUST be supported by current external retrieval during this run.
Do not use model memory, a prior issue, a prompt-supplied claim, or a search
snippet as evidence for a weekly item.

If current Web, GitHub, or research retrieval is unavailable, return no
publishable items (or only items whose pages were independently opened and
verified) and label the unsupported candidates `INSUFFICIENT_EVIDENCE`. Do not
publish a draft item with “verify later”, a missing URL, or an unconfirmed
date.

When this package is used from the source repository, install it in a
supported Codex Skill location before testing implicit discovery. The package
being present as a top-level repository directory is not runtime discovery
evidence; see the installation note in [README.md](README.md).

## Required workflow

1. Define and state the coverage window before searching.
   - A Monday scheduled report covers the previous calendar week, Monday
     00:00 through Sunday 23:59, in the user's local timezone when known.
   - A manual weekly request covers the most recent completed seven-day period
     unless the user supplies another range.
2. Read [topics.md](references/topics.md), [sources.md](references/sources.md),
   and [search-strategy.md](references/search-strategy.md) before discovery.
3. Search across the topic taxonomy and multiple source types. Run both an
   international/English discovery pass and a Chinese-language discovery pass
   when current sources are available. Do not rely on one generic `AI QA`
   query.
4. Verify each candidate against the original publication, release,
   announcement, paper, or meaningful update. Search/index dates, crawl dates,
   footer dates, and a repository's incidental commit date are not sufficient.
   Open the candidate's direct source page and record the page identity and
   date/version evidence before including it.
5. Apply every relevance gate below, deduplicate underlying developments, and
   rank the remaining Chinese and non-Chinese candidates in one pool. Select
   exactly the top 10; a Chinese-source item is publishable only when its
   unified rank is 1–10.
6. Read [output-template.md](references/output-template.md), then produce the
   complete Chinese edition first and the complete English edition second.
   Keep the item set, order, facts, categories, dates, sources, and links
   identical across editions, and run the final validation checklist.

## Relevance gates

Every included item must pass all four gates:

| Gate | Include only when |
| --- | --- |
| Freshness | The meaningful event occurred inside the stated coverage window. |
| AI relevance | AI, LLMs, agents, machine learning, AI evaluation, or AI-assisted engineering is materially involved in the claimed development. |
| QA relevance | It directly concerns testing, QA/QE, test automation or generation, agent/LLM evaluation, regression, quality gates, reliability, performance, testing infrastructure, software quality, or developer quality work. Pure model, AI-product, or AI-industry news without this QA connection is `NO`. |
| Reporting value | A QA Engineer, SDET, QE, Test Architect, or quality-focused engineer would reasonably benefit from knowing it. |

Reject a candidate when any gate is `NO`. Do not weaken the gates to reach a
target count.

## Evidence and selection rules

- A normal issue contains exactly 10 items. Continue discovery across all
  configured source classes and languages until 10 candidates pass the gates
  and can be verified. Never fill the list with low-relevance or weakly
  sourced items.
- If external retrieval is unavailable or exhaustive discovery still produces
  fewer than 10 publishable candidates, do not publish a shortened normal
  issue. Return an explicit `INSUFFICIENT_EVIDENCE` or blocked-status note
  explaining the shortfall instead of inventing, duplicating, or weakening an
  item.
- Build one candidate pool after verification and deduplication. Score and
  rank Chinese/Chinese-language and international candidates together. Do not
  reserve a China quota, add a language bonus, or displace a higher-ranked
  item solely to balance geography.
- Use this 100-point ranking after the four binary gates pass: AI-Native QA
  relevance (0–40), QA actionability (0–25), substantive change (0–15),
  evidence/source quality (0–15), and coverage value after deduplication
  (0–5). Freshness remains a required gate, not a substitute for relevance.
- Select the highest-ranked 10. A Chinese item ranked 11 or lower is excluded
  from the issue even when its source is authoritative; a Chinese item ranked
  within the top 10 is included on the same terms as every other item.
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

Normally exclude generic AI news, pure model or AI-product news without a
direct QA connection, generic QA news without AI relevance, jobs,
hiring, interview questions, certifications, courses, bootcamps, SEO content,
sponsored listicles, generic tutorials, duplicate coverage, old content
presented as new, minor bug fixes, and commercial announcements without
technical substance. A major model release is eligible only when the relevant
development is testing, evaluation, quality, automation, reliability, or
software-engineering quality.

## Output contract

Use the structure in [output-template.md](references/output-template.md).
Every item must include:

- one Chinese title in the Chinese edition and one faithful English title in
  the English edition;
- exactly one canonical category;
- source name and meaningful publication/update date;
- a factual Chinese description longer than 200 Chinese characters;
- a factual English description longer than 200 characters in the English
  edition (count characters, not words); and
- a direct original-source link.

State the issue/publication date and exact coverage period in both editions.
Explain what happened and why it matters to QA; do not copy marketing
language or call an item “best”, “revolutionary”, or “game-changing” without
source support. The English edition is a faithful translation of the Chinese
edition: do not add, remove, or materially change claims between languages.

## Final validation

Before returning the digest, confirm:

- the coverage boundaries and timezone are stated and correct;
- every meaningful event is inside the coverage window;
- every item passes AI relevance, QA relevance, and reporting value;
- Chinese/Chinese-language and international candidates were scored in one
  pool, and exactly 10 items were selected from the unified top 10;
- every item has a verifiable direct source link whose page was opened during
  this run, and the page identity and source date/version match the claim;
- duplicates are collapsed;
- every category is from the canonical taxonomy;
- the Chinese edition appears first and the English edition appears second;
- both editions contain the same 10 items in the same order with matching
  facts, categories, dates, sources, and links;
- every Chinese description is longer than 200 Chinese characters;
- every English description is longer than 200 characters; and
- no unsupported claims or placeholder links remain.

Remove an item that fails validation instead of filling the target count; if
that leaves fewer than 10 verified items, return the explicit blocker status
required above rather than a shortened normal issue.

If the input supplies synthetic candidates without real URLs, demonstrate the
filter by excluding those candidates or report that no publishable item has
been verified yet. Never convert missing evidence into a follow-up task inside
the digest.
