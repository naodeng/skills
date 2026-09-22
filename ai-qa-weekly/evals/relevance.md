# AI QA Weekly Relevance Evaluation

These manual cases test the intersection rule, freshness handling, canonical
classification, source verification, and deduplication. The evaluator should
use only the facts in each case and should not invent URLs or dates.

## Should include

| Case | Input | Expected |
| --- | --- | --- |
| 1 | New framework for evaluating browser agents using Playwright. | Include; `Agent Testing`. |
| 2 | New LLM evaluation framework with regression-testing support. | Include; `LLM Quality`. |
| 3 | New open-source AI test-generation framework. | Include; `AI Testing`. |
| 4 | Playwright adds functionality specifically designed for AI agents. | Include; `Test Automation`. |
| 5 | Research proposes a benchmark for coding-agent reliability. | Include; `Research & Trends`. |
| 6 | An engineering team explains how it evaluates AI agents before production. | Include; `Agent Testing`. |
| 7 | New AI-assisted performance-testing capability for load-test analysis. | Include; `Performance & Reliability`. |

## Should exclude

| Case | Input | Expected |
| --- | --- | --- |
| 8 | A new general-purpose LLM is released with no testing, evaluation, quality, or reliability development. | Exclude; AI relevance alone is insufficient. |
| 9 | Playwright fixes Chromium compatibility bugs with no AI capability. | Exclude; QA relevance alone is insufficient. |
| 10 | Top 20 QA interview questions. | Exclude. |
| 11 | AI marketing-agent platform raises funding with no quality or evaluation substance. | Exclude. |
| 12 | Selenium beginner tutorial. | Exclude. |
| 13 | Online AI testing certification course. | Exclude. |
| 14 | A 2024 AI-testing article appears in search results during this week's window. | Exclude; index date is not publication date. |

## Edge cases

| Case | Input | Expected |
| --- | --- | --- |
| 15 | An old agent-evaluation project releases a major new version this week. | Include the release; do not describe the project as newly created. |
| 16 | A major model release introduces a coding-agent evaluation benchmark. | Include the evaluation development under `Agent Testing` or `Research & Trends`, not the model release alone. |
| 17 | A Reddit discussion highlights a new AI-testing project. | Verify the original GitHub or official source; include only after verification. |
| 18 | Five news sites report the same AI-testing product release. | Return one item linked to the original announcement. |
| 19 | Web/GitHub/research retrieval is unavailable and the prompt supplies only unverified weekly claims. | Return no publishable items; mark them `INSUFFICIENT_EVIDENCE`; do not use model memory. |
| 20 | A candidate URL returns 404, a search-results page, or an unrelated redirect. | Exclude; a URL-shaped string is not source verification. |
| 21 | A candidate page opens, but its actual publication/release date is outside the coverage window. | Exclude; use the source date, not the discovery date. |
| 22 | A page's publisher, title, or date conflicts with the candidate claim and cannot be resolved from the original source. | Exclude or report `INSUFFICIENT_EVIDENCE`; do not publish a provisional item. |

## Pass criteria

An output passes when it states the coverage period, includes only candidates
that satisfy the freshness + AI + QA + reporting-value gates, uses exactly one
canonical category per included item, provides a verified direct original URL
for every included item, prefers the primary source, and removes duplicates.
A short digest is correct when the evidence supports fewer than 8 items. It is
also correct to return no publishable items when the supplied candidates lack
verifiable original links; “add the link later”, a placeholder, or a prose
note is not a passing substitute. For live-source cases, the source page must
have been opened during the current run and its identity/date/version must
support the item claim.
