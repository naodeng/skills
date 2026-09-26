# AI QA Weekly Topic Taxonomy

Use this taxonomy for discovery, relevance decisions, and classification. It
defines scope; it is not a quota and every issue does not need every category.

## Chinese-language discovery vocabulary

Use Chinese terms in a separate discovery pass and combine them with product,
vendor, release, benchmark, repository, and date terms. Useful terms include
`大模型评测`, `智能体评测`, `Agent 测试`, `AI 测试`, `AI 软件测试`,
`大模型测试`, `LLM 评测`, `提示词回归`, `工具调用测试`, `MCP 测试`,
`AI 生成测试`, `AI 质量工程`, `智能体可靠性`, `大模型安全评测`, and
`AI 测试自动化`.

Chinese terms broaden discovery only. Apply the same AI × QA gates, direct-page
verification, deduplication, and unified top-10 ranking as for English sources.

## 1. AI Testing

AI applied directly to software-testing work:

- AI testing, AI-assisted testing, and AI for software testing
- AI test generation, test design, optimization, maintenance, and exploration
- autonomous testing, defect analysis, and self-healing tests

Useful query terms include `AI testing`, `AI software testing`, `AI test
generation`, `AI-assisted testing`, and `autonomous testing`.

## 2. Agent Testing

Testing or evaluating AI agents:

- agent testing, evaluation, benchmarks, reliability, and regression
- browser-agent, coding-agent, computer-use, safety, and observability
  evaluation

Do not include sales, marketing, or customer-service agents unless the source
also contains substantive testing, evaluation, quality, reliability, or
benchmarking work.

## 3. LLM Quality

Testing and evaluating LLM behavior:

- LLM testing, evaluation, benchmarks, and regression
- hallucination, prompt, reliability, observability, and model-quality tests
- evaluation frameworks and datasets

Useful query terms include `LLM testing`, `LLM evaluation`, `LLM benchmark`,
`LLM reliability`, and `LLM regression testing`.

## 4. Test Automation

AI developments that materially change test automation:

- AI test automation and browser automation
- Playwright, Selenium, Cypress, WebdriverIO, or Appium integrations
- AI API automation, testing MCP servers, and autonomous browser testing

## 5. Quality Engineering

AI developments that materially change software quality engineering:

- AI quality engineering, QA, software quality, code quality, and developer
  quality
- AI quality gates, code-review quality, CI/CD quality, release quality, and
  AI-assisted requirements analysis

## 6. Performance & Reliability

AI developments affecting performance, resilience, reliability, or
observability:

- AI performance or load testing
- AI reliability engineering, observability, chaos engineering, performance
  analysis, root-cause analysis, incident analysis, and production quality

## 7. Tools & Projects

AI × QA tools and open-source projects with meaningful activity:

- AI testing tools, QA agents, test-generation tools, evaluation frameworks,
  AI automation frameworks, and testing MCP servers
- new repositories, meaningful releases or features, useful integrations, and
  reproducible project updates

Stars alone are not an eligibility signal.

## 8. Research & Trends

Research relevant to AI × QA:

- AI software testing, LLM/agent evaluation, coding-agent or browser-agent
  benchmarks
- software-engineering agents, testing agents, AI reliability, and evaluation
  of AI-generated tests
- software-testing benchmarks and reproducible quality studies

Prefer work with an implementation, dataset, benchmark, repository, or
reproducible experiment.

## Classification rule

An item may match multiple topics during discovery, but the digest must assign
one primary category: the category that best explains why the item matters to
QA. For example, a Playwright-based agent-evaluation framework is `Agent
Testing` when evaluation is its primary purpose, even though it also matches
`Test Automation` and `Tools & Projects`.
