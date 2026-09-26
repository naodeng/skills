# AI QA Weekly Source Strategy

Prefer primary and original sources. Use secondary sources to discover or
contextualize a development, then replace them with the original source in
the final digest whenever possible.

## Source hierarchy

1. Official announcement, changelog, or documentation
2. GitHub release or original repository
3. Original research paper, dataset, benchmark, or research organization
4. Engineering blog
5. Credible technical media
6. Community discussion

### Official sources

Search relevant vendors and project maintainers, including OpenAI,
Anthropic, Google/DeepMind, Microsoft, GitHub, AWS, Cloudflare, Datadog,
Grafana, Playwright, Selenium, Cypress, WebdriverIO, Appium, and k6. The
list is a starting point, not a closed allowlist.

Look for releases, documentation updates, evaluation capabilities, benchmarks,
testing integrations, reliability work, and real engineering practice.

For Chinese and Chinese-language coverage, also search official sources from
Chinese vendors and maintainers. Starting points include Alibaba Cloud Model
Studio/Qwen/PAI, Baidu AI Cloud Qianfan, Tencent Cloud Hunyuan, Huawei Cloud
Pangu, Volcengine/Doubao, DeepSeek, Zhipu AI, Moonshot AI, MiniMax, ModelScope,
OpenBMB, PaddlePaddle/PaddleNLP, MindSpore, Apifox, and MeterSphere. This is a
discovery list rather than an allowlist: use the specific product's official
announcement, changelog, documentation, repository, or research page as the
final source.

Chinese-language official sources have the same evidence status as English
sources. Do not give a Chinese source a regional bonus, and do not downgrade it
because the page is Chinese. Verify the publisher, page identity, meaningful
date/version, and AI × QA substance directly.

### GitHub

Search repositories, releases, documentation, and meaningful project updates
for AI testing, agent testing/evaluation, LLM evaluation, AI test automation,
Playwright/Selenium/Cypress/Appium AI, testing MCP, and software quality AI.

Record what actually changed: repository creation, release, feature, issue or
commit activity, or documentation update. Do not use total stars as the only
signal and do not present an old repository as new because it was edited this
week.

### Research

Use arXiv, conference or university publications, Hugging Face, official
research organizations, and linked project repositories. Prefer paper plus
implementation, dataset, benchmark, or reproducible evaluation. State the
research contribution accurately and avoid claiming production readiness.

For China-related research, include original papers, university/lab pages,
conference pages, official datasets, ModelScope or GitHub repositories, and
maintainer documentation. Chinese research aggregators, translated summaries,
and media are discovery signals; replace them with the original paper or
project page before publication whenever possible.

### Engineering blogs and media

Use engineering blogs for real-world AI quality, agent evaluation,
observability, CI/CD, testing architecture, and production validation.
This includes Chinese engineering blogs from product vendors and open-source
maintainers. Use technical media, Chinese tech media, public-account posts,
and community articles for discovery or independent context, then seek the
announcement, repository, release, or paper they report.

### Community

Hacker News, Reddit, and developer forums can surface emerging projects,
adoption signals, and technical disagreements. Community popularity alone is
not evidence of eligibility. Find and verify the original source before
including a candidate.

## Live source verification

Before an item enters the final digest, open its direct source URL during the
current run and confirm:

1. the final page is the claimed publisher or original project;
2. the page title and content support the claimed development; and
3. the publication, release, or meaningful update date/version is inside the
   coverage window.

Follow redirects only when the final page is still the original authoritative
source. A 404, inaccessible page, login wall, search-results page, unrelated
redirect, missing date, or conflicting date is not publishable evidence.
Exclude the candidate or report `INSUFFICIENT_EVIDENCE`; do not leave it in the
digest with a future verification note.

## Evidence rules

- Each included item needs at least one reliable, direct, authoritative source.
- Link to the original content, not a search-results page, scraped repost, SEO
  aggregation page, or social summary.
- Verify the meaningful publication, release, announcement, or update date.
- Current weekly claims must come from this run's external retrieval; model
  memory, prior issues, prompt assertions, and search snippets are not evidence.
- Run at least one Chinese-language discovery pass when the request covers the
  normal weekly scope. Chinese candidates compete with all other candidates in
  one unified ranking; there is no regional quota.
- Exclude rumors, anonymous claims, unverified reposts, AI-generated content
  farms, and claims whose original source cannot be found.
- Do not force equal representation across source types or organizations, but
  review more than one source class before final selection when the week's
  evidence allows it.
