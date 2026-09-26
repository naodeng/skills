# AI QA Weekly Output Template

Use this template after candidate verification. Replace every placeholder;
never publish a placeholder URL or unsupported claim.

```markdown
---
title: "AI QA Weekly #{{issue}}｜本周 AI × 软件质量值得关注的动态"
date: {{publication_date}}
---

# AI QA Weekly #{{issue}}｜中文版

**发布日期:** {{publication_date}}

**资讯周期:** {{coverage_start}} — {{coverage_end}}

本期整理过去一周 AI × QA、软件测试、测试自动化、质量工程、AI 系统质量及相关工具与研究领域值得关注的 10 条动态。

本期必须严格输出 10 条。若 10 条候选无法通过来源和相关度验证，不得用低相关内容补齐。

---

## 1. {{Chinese Title}}

**分类:** {{One canonical category from topics.md}}

**来源:** {{Original source name}}

**更新日期:** {{YYYY-MM-DD}}

**介绍:**

{{Factual Chinese summary, more than 200 Chinese characters}}

**链接:** {{Direct original URL}}

<!-- Repeat through item 10. -->

---

# AI QA Weekly #{{issue}}｜English Edition

**Published:** {{publication_date}}

**Coverage:** {{coverage_start}} — {{coverage_end}}

This edition contains the same 10 items as the Chinese edition, in the same
order, with the same facts, categories, dates, sources, and links.

---

## 1. {{English Title}}

**Category:** {{One canonical category from topics.md}}

**Source:** {{Original source name}}

**Updated:** {{YYYY-MM-DD}}

**Summary:**

{{Faithful English summary of more than 200 characters; do not add or remove claims.}}

**Link:** {{Direct original URL}}

<!-- Repeat through item 10, using the exact same item order as the Chinese edition. -->
```

## Per-item quality bar

Each block must answer what happened and why it matters to QA. Both language
versions must be longer than 200 characters, factual, and equivalent in claim
scope. Preserve official product, project, framework, model, and organization
names; avoid clickbait and unsupported adjectives. Use source labels such as
`GitHub · org/repo`, `Microsoft`, `arXiv`, or `Cloudflare Engineering` rather
than displaying every item as simply `GitHub`.

## Final checklist

- [ ] publication date, coverage dates, and timezone are stated;
- [ ] each item has one canonical category;
- [ ] each meaningful event is inside the coverage window;
- [ ] the original link is direct, real, opened during this run, and verified;
- [ ] the page identity and publication/release date or version support the
      item claim;
- [ ] duplicates are collapsed;
- [ ] exactly 10 items appear in the Chinese edition;
- [ ] exactly the same 10 items appear in the English edition in the same order;
- [ ] every Chinese summary is longer than 200 Chinese characters;
- [ ] every English summary is longer than 200 characters;
- [ ] translated summaries contain the same facts and claims; and
- [ ] no placeholder, marketing-only, or unsupported claim remains.

## When no item is publishable

If exactly 10 candidates cannot be verified after exhaustive discovery, do not
publish a shortened normal issue. Return a bilingual blocker note that states
the number of verified candidates and the failed evidence or relevance gate:

```markdown
# AI QA Weekly

**资讯周期 / Coverage:** {{coverage_start}} — {{coverage_end}}

本期无法验证完整的 10 条发布内容。

This issue could not verify a complete set of 10 publishable items.

**原因 / Reason:** {{State the failed evidence or relevance gate.}}

Unsupported candidates: `INSUFFICIENT_EVIDENCE`.
```
