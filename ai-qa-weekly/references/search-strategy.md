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

These are entry points, not sufficient coverage.

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
- GitHub repositories and releases;
- research papers, datasets, and benchmarks;
- engineering blogs;
- credible technical media; and
- community discussions as discovery signals.

Use the source hierarchy in [sources.md](sources.md) during verification.

## 5. Build and verify candidates

For each candidate, record:

```text
event | primary URL | source | meaningful event date | AI evidence |
QA evidence | page identity/date evidence | URL status | category |
duplicate group | include/exclude reason
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
Select 8–12 strong items when available; fewer is correct when the evidence
does not support more. Sort by expected value to QA readers, not by search
result position or star count.

## Noise filters

Explicitly filter jobs, hiring, interview questions, courses, bootcamps,
certifications, sponsored content, SEO listicles, generic tutorials, generic
AI or QA news, old articles resurfacing in search, product-comparison spam,
duplicate reports, and marketing-only announcements.

The decision question is: “What changed in this coverage period that a QA
professional working with AI should actually know?”
