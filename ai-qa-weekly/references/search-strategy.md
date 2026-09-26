# AI QA Weekly Search Strategy

Use this sequence to discover the week's meaningful AI × QA developments.
Record the coverage window before searching and apply it to the meaningful
event date, not the search-engine indexing date.

## 1. Establish the window

For a Monday scheduled digest, use the previous Monday 00:00 through Sunday
23:59 in the user's local timezone. For a manual request, use the most recent
completed seven days unless the user specifies a range. State the exact start,
end, timezone, and publication date in the draft.

## 2. Broad discovery

Search several broad terms, with date filters where the source supports them:

- `AI testing`
- `AI test automation`
- `AI software testing`
- `AI quality engineering`
- `AI QA`
- `agent testing`
- `agent evaluation`
- `LLM testing`
- `LLM evaluation`
- `AI software quality`

Also run a Chinese-language pass using terms such as:

- `AI 测试`
- `AI 软件测试`
- `大模型评测`
- `智能体评测`
- `Agent 测试`
- `大模型测试`
- `LLM 评测`
- `提示词回归`
- `工具调用测试`
- `MCP 测试`
- `AI 生成测试`
- `AI 质量工程`
- `智能体可靠性`
- `大模型安全评测`

Use Chinese and English synonyms together when a project, product, or paper is
likely to publish in both languages. These queries are entry points, not
sufficient coverage.

## 3. Expand by taxonomy

Use [topics.md](topics.md) to search variations for all eight categories:

- AI testing and test generation
- agent testing and benchmarks
- LLM quality and regression
- test automation and browser agents
- quality engineering and quality gates
- performance, reliability, and observability
- tools, projects, and testing MCP
- research, datasets, and reproducible benchmarks

Search synonymous terms rather than assuming one vendor or phrase represents a
whole category.

## 4. Search source classes separately

Run independent discovery passes for:

- official announcements, documentation, and changelogs;
- Chinese-language official announcements, documentation, and changelogs;
- GitHub repositories and releases;
- Chinese-maintainer repositories and releases on GitHub, ModelScope, or Gitee;
- research papers, datasets, and benchmarks;
- Chinese university/lab research pages and original Chinese datasets or
  benchmarks;
- engineering blogs;
- credible technical media; and
- community discussions as discovery signals.

Use the source hierarchy in [sources.md](sources.md) during verification.

## 5. Build and verify candidates

For each candidate, record:

```text
event | primary URL | source | meaningful event date | AI evidence |
QA evidence | page identity/date evidence | URL status | category |
language/region | unified score | unified rank | duplicate group |
include/exclude reason
```

Then ask, in order:

1. Did the meaningful event occur inside the window?
2. Is AI, an LLM, an agent, evaluation, or AI-assisted engineering material?
3. Is software testing, quality, reliability, performance, or evaluation
   material?
4. Is there substantive new information rather than a minor fix or promotion?
5. Would a QA/QE/SDET reader benefit?

If any answer is no, reject the candidate. If an announcement was discovered
through media or community, locate and verify the official source before
including it. If verification fails, exclude it.

Do not treat a URL's presence, a search snippet, or a successful-looking
redirect as verification. Open the final page, match its identity and
publication/release date to the candidate record, and mark unresolved items
`INSUFFICIENT_EVIDENCE` rather than carrying them into the digest.

## 6. Deduplicate and select

Cluster reports about the same release, feature, project, paper, benchmark,
or announcement. Keep one item and link to the most authoritative source.
After deduplication, score every candidate that passed the five checks in one
pool. Use the following 100-point rubric:

| Dimension | Points | Question |
| --- | ---: | --- |
| AI-Native QA relevance | 0–40 | Does it directly change agent/LLM testing, evaluation, regression, or AI-assisted quality work? |
| QA actionability | 0–25 | Can a QA/QE/SDET use the development in a test, gate, workflow, or diagnosis? |
| Substantive change | 0–15 | Is there a meaningful release, finding, benchmark, or practice rather than promotion or a minor fix? |
| Evidence/source quality | 0–15 | Is the direct source authoritative, specific, and independently verifiable? |
| Coverage value | 0–5 | Does it add useful signal after duplicates and closely related items are collapsed? |

Freshness is a binary gate before scoring. Sort Chinese/Chinese-language and
international candidates by the same score, use primary-source quality and
then QA actionability as tie-breakers, and select exactly the top 10. A
Chinese item ranked 11 or lower is excluded; do not create a geographic quota
or use a low-scoring Chinese item to fill the list. Continue discovery when
the first pass has fewer than 10 candidates. If exhaustive verified discovery
still produces fewer than 10, do not publish a shortened normal issue; return
an explicit `INSUFFICIENT_EVIDENCE` or blocked-status note.

## 7. Produce two equivalent editions

After selection, write the complete Chinese edition first and the complete
English edition second. Use the same 10-item IDs and order in both editions.
Each corresponding item must preserve the same event, QA implication, source,
date, category, metric, qualification, and direct link. Translate names and
prose naturally, but do not add an English-only claim or omit a Chinese claim.
Count the Chinese description in Chinese characters and the English
description in Unicode characters; both must be longer than 200 characters.

Do not interleave languages item by item, and do not write a short bilingual
summary followed by a longer version in only one language.

## Noise filters

Explicitly filter jobs, hiring, interview questions, courses, bootcamps,
certifications, sponsored content, SEO listicles, generic tutorials, generic
AI or QA news, old articles resurfacing in search, product-comparison spam,
duplicate reports, marketing-only announcements, translated copies without
new evidence, and Chinese media reposts when the original source is missing.

The decision question is: “What changed in this coverage period that a QA
professional working with AI should actually know?”
