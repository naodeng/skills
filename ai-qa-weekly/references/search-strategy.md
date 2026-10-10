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
- credible technical media;
- international community discovery; and
- domestic testing-community discovery, independently of Chinese official
  sources and general Chinese-language queries.

Use the source hierarchy in [sources.md](sources.md) during verification.

### Domestic testing-community pass

Attempt TesterHome and 测试人社区 on every normal run. Also consider 测试窝
and, when accessible, 51Testing as supplementary sources. Record a reason for
skipping a supplementary source. Use both community entry pages and focused
site searches where available; one generic Chinese query does not complete
this pass. Example queries, combined with the coverage window:

- `site:testerhome.com AI 测试 回归`
- `site:testerhome.com 智能体 评测`
- `site:testerhome.com AI 自动化 CI`
- `site:ceshiren.com Agent 测试 评测`
- `site:ceshiren.com AI Playwright 审阅 修复`
- `site:testwo.com LLM 评估`
- `site:51testing.com AI 测试 质量`

Expand toward test generation, assertions, prompt/tool-call regression,
evaluation datasets, quality gates, reliability, failure analysis, and
engineering-team practice. Look beyond a site's AI section: testing tools,
automation, and team channels may contain stronger QA evidence. Search-date
filters and forum listing activity are discovery aids, not event-date proof.

Keep a working coverage record for each listed community and other sources
actually attempted:

```text
site/channel | query or entry URL attempted | access/search outcome |
candidate IDs reviewed | exclusion/access limitation or skip reason
```

Distinguish pages opened, search-only discovery, access failure, and skipped
supplementary sources. Record only actions actually performed; a search
snippet is not a verified original page. Link each reviewed candidate to the
decision record below. If no domestic item reaches the final top 10, use the
records to distinguish no eligible candidate found within the searched scope,
failed verification, ranking below 10, and incomplete coverage due to access
limits. Do not claim that no domestic developments exist or that an
inaccessible site has no matching content. These are working evidence records,
not extra news items or mandatory sections inside the two published editions;
provide them when an audit or explanation is requested.

## 5. Build and verify candidates

For each candidate, record:

```text
candidate ID | event | discovery URL | primary URL | source |
source kind (first-hand original / secondary / unresolved) |
meaningful event date | AI evidence | QA evidence |
page identity/authorship/date evidence | URL status | category |
language/region | unified score and rank (only after eligibility) |
duplicate group | include/exclude reason
```

Then ask, in order:

1. Did the meaningful event occur inside the window?
2. Is AI, an LLM, an agent, evaluation, or AI-assisted engineering material?
3. Is software testing, quality, reliability, performance, or evaluation
   material?
4. Is there substantive new information rather than a minor fix or promotion?
5. Would a QA/QE/SDET reader benefit?

If any answer is no, reject the candidate. For a secondary media or community
report, locate and verify the original source before including it. A
maintainer's or team's first-hand forum report can itself be that source when
it meets [sources.md](sources.md); do not demand an unrelated corporate
announcement. If verification fails, exclude it. An unresolved candidate does
not receive an invented score or rank.

For forums, verify the original post date or an evidenced substantive update,
not the last reply, bump, or listing activity. For translations/reposts, use
the underlying event's date; only a substantive new experiment or finding
with its own evidence may be assessed as a new event.

Do not treat a URL's presence, a search snippet, or a successful-looking
redirect as verification. Open the final page, match its identity and
publication/release date to the candidate record, and mark unresolved items
`INSUFFICIENT_EVIDENCE` rather than carrying them into the digest.

## 6. Deduplicate and select

Complete the required language and source-class passes, including attempted
core domestic communities, before selecting the final 10. Finding 10 items
early does not remove the coverage requirement.

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
