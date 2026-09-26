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
| 8 | A Chinese-language official release adds agent evaluation sets, evaluators, or quality gates. | Include when it passes the same gates; assign the best canonical category. |
| 9 | A Chinese research project publishes a reproducible benchmark for LLM or agent quality. | Include when the original paper or project page is verified. |

## Should exclude

| Case | Input | Expected |
| --- | --- | --- |
| 10 | A new general-purpose LLM is released with no testing, evaluation, quality, or reliability development. | Exclude; AI relevance alone is insufficient. |
| 11 | Playwright fixes Chromium compatibility bugs with no AI capability. | Exclude; QA relevance alone is insufficient. |
| 12 | Top 20 QA interview questions. | Exclude. |
| 13 | AI marketing-agent platform raises funding with no quality or evaluation substance. | Exclude. |
| 14 | Selenium beginner tutorial. | Exclude. |
| 15 | Online AI testing certification course. | Exclude. |
| 16 | A 2024 AI-testing article appears in search results during this week's window. | Exclude; index date is not publication date. |
| 17 | A Chinese media repost has no reachable official announcement, paper, repository, or release page. | Exclude or mark `INSUFFICIENT_EVIDENCE`; language does not replace primary evidence. |
| 18 | A Chinese LLM release or general AI benchmark has no testing, evaluation, quality, reliability, or software-engineering quality substance. | Exclude; Chinese origin and AI relevance do not satisfy the QA gate. |

## Edge cases

| Case | Input | Expected |
| --- | --- | --- |
| 19 | An old agent-evaluation project releases a major new version this week. | Include the release; do not describe the project as newly created. |
| 20 | A major model release introduces a coding-agent evaluation benchmark. | Include the evaluation development under `Agent Testing` or `Research & Trends`, not the model release alone. |
| 21 | A Reddit discussion highlights a new AI-testing project. | Verify the original GitHub or official source; include only after verification. |
| 22 | Five news sites report the same AI-testing product release. | Return one item linked to the original announcement. |
| 23 | Eleven candidates pass the gates and a Chinese item ranks 11 after unified scoring. | Exclude the Chinese item; only the unified top 10 are publishable. |
| 24 | Eleven candidates pass the gates and a Chinese item ranks 6 after unified scoring. | Include it; no regional quota or penalty applies. |
| 25 | Web/GitHub/research retrieval is unavailable and the prompt supplies only unverified weekly claims. | Return no publishable items; mark them `INSUFFICIENT_EVIDENCE`; do not use model memory. |
| 26 | A candidate URL returns 404, a search-results page, or an unrelated redirect. | Exclude; a URL-shaped string is not source verification. |
| 27 | A candidate page opens, but its actual publication/release date is outside the coverage window. | Exclude; use the source date, not the discovery date. |
| 28 | A page's publisher, title, or date conflicts with the candidate claim and cannot be resolved from the original source. | Exclude or report `INSUFFICIENT_EVIDENCE`; do not publish a provisional item. |

## Pass criteria

An output passes when it states the coverage period, includes exactly 10
candidates that satisfy the freshness + AI + QA + reporting-value gates, scores
Chinese and international candidates in one pool, uses exactly one canonical
category per included item, provides a verified direct original URL for every
included item, prefers the primary source, and removes duplicates. It must
then provide a complete Chinese edition followed by a complete English edition
with the same 10 items in the same order and matching facts. Every Chinese
description and every English description must be longer than 200 characters.
If exactly 10 candidates cannot be verified, the output must be an explicit
evidence/blocker note rather than a shortened normal issue. “Add the link
later”, a placeholder, or a prose note is not a passing substitute. For
live-source cases, the source page must have been opened during the current run
and its identity/date/version must support the item claim.
