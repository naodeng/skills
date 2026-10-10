# AI QA Weekly Source Strategy

Prefer primary and original sources. Use secondary sources to discover or
contextualize a development, then replace them with the original source in
the final digest whenever possible.

## Source hierarchy

Assess originality and evidence, not just the hosting domain. A forum can host
an original engineering report as well as a secondary discussion.

1. Official announcement, changelog, or documentation
2. GitHub release or original repository
3. Original research paper, dataset, benchmark, or research organization
4. First-hand engineering report, including an original blog or forum post
5. Credible technical media
6. Secondary community discussion, repost, or translated summary

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
maintainers. Use third-party technical media, Chinese tech media,
public-account summaries, and community summaries for discovery or independent
context, then seek the announcement, repository, release, paper, or first-hand
report they cover. A team's or maintainer's own original article follows the
first-hand evidence criteria below, regardless of its host.

### Community

Hacker News, Reddit, and developer forums can surface emerging projects,
adoption signals, and technical disagreements. Community popularity alone is
not evidence of eligibility. Distinguish first-hand reports from secondary
discussion before deciding where to verify the underlying event.

#### Domestic testing-community entry points

Run a dedicated domestic testing-community pass, separate from Chinese vendor
and research discovery. These are starting points, not an allowlist:

| Community | Entry point | Discovery focus and use |
| --- | --- | --- |
| TesterHome / 测试之家 | [AI 测试 section](https://testerhome.com/topics/node134), [community](https://testerhome.com/) | Core: attempt every normal run. Search AI testing, automation tools, open-source projects, and testing-team engineering reports; do not stop at the AI section. |
| 测试人社区 | [Community](https://ceshiren.com/) | Core: attempt every normal run. Search AI-assisted test design, Agent/LLM evaluation, Playwright/API automation, maintainer reports, and review/repair workflows. |
| 测试窝 | [Site](https://www.testwo.com/) | Supplementary discovery for testing and quality practice. Check each article's meaningful date and whether it is original, translated, or reposted. |
| 51Testing | [Site](https://www.51testing.com/) | Conditional supplementary discovery: use when direct pages are accessible during the run. Record access failures; do not assume availability from an old link. |

Attempt both core communities before final selection, even if other sources
already supply 10 verified candidates. Supplementary sources may be skipped
with a recorded reason. A failed access attempt is a coverage limitation, not
proof of no relevant content or permanent site unavailability. Other verified
sources can still support a normal issue; no community or regional quota is
created. Keep the coverage record described in
[search-strategy.md](search-strategy.md).

#### First-hand originals versus secondary reports

A post by a maintainer, experiment author, or engineering team about its own
work can be a primary source. Verify the author's relationship to the work
against linked project/team information where available, the meaningful event
date, and the actual technical evidence. Look for concrete methods,
environment/inputs, test or evaluation assertions, results/failures, and
limitations, with linked implementation, logs, datasets, or run records where
available. Do not require a separate corporate announcement solely because the
original report is hosted on a forum. An unsupported claim does not become
reliable merely because the poster calls it original.

Reposts, translations, media summaries, and third-party discussions are
secondary: follow and verify the original release, paper, repository, or
first-hand report. A translation date, latest reply, listing activity time,
or bump is not a meaningful event date. A substantive new experiment or
finding may be assessed as its own event, with its own evidence and date;
merely translating or discussing an old event does not renew it.

Apply the same AI × QA gates and unified scoring to community originals as
to other sources. A section title, popularity, Chinese language, or domestic
origin earns no relevance or scoring bonus; hosting on a forum alone earns no
penalty. Attribute reported findings to their authors and preserve limitations:
opening a report is not independent reproduction or proof of production
readiness. Filter recruitment, training promotions, generic tutorials, and
pure AI-industry news even when they appear in an AI-testing section.

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
- For community items, verify the original post and distinguish its event
  date from replies, bumps, translations, and listing activity.
- Current weekly claims must come from this run's external retrieval; model
  memory, prior issues, prompt assertions, and search snippets are not evidence.
- Run Chinese-language discovery and a separate domestic testing-community
  pass when the request covers the normal weekly scope. Record the attempted
  core sites, supplementary sources used or skipped, access outcomes, and
  candidate decisions. Chinese candidates compete with all other candidates
  in one unified ranking; there is no regional quota.
- Exclude rumors, anonymous claims, unverified reposts, AI-generated content
  farms, and claims whose original source cannot be found.
- Do not force equal representation across source types or organizations, but
  review more than one source class before final selection when the week's
  evidence allows it.
