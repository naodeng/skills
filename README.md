# Skills

[中文（当前页）](README.md) | [English](README_EN.md)

本仓库用于存放可复用的 Codex Skills，帮助建立结构化、可重复执行的工作流程。

## 可用 Skills

### 30 Days Learning Plan Project Creator

[`30-days-learning-plan-project-creator/`](30-days-learning-plan-project-creator/)

用于创建以 Markdown 为核心的 30 天学习计划项目，包含：

- 中英文双语文档；
- 30 个每日课程文件；
- 自动生成的静态课程网站；
- 构建和内容校验；以及
- GitHub Pages 部署配置。

完整的工作流程和验证要求请参阅 [Skill 使用说明](30-days-learning-plan-project-creator/SKILL.md)。

### Dual Repository Release

[`dual-repository-release/`](dual-repository-release/)

用于在项目仓/Fork 与上游仓之间核查或交付同一版本，分别验证目标分支、annotated tag、GitHub Release 与 CI 证据；不会将只读核查扩展为发布授权。

完整流程请参阅 [Skill 使用说明](dual-repository-release/SKILL.md)。

### Version DoD Evidence

[`version-dod-evidence/`](version-dod-evidence/)

用于根据明确验收项建立版本证据矩阵，区分测试、eval、真实执行、CI 和发布状态，避免将局部验证误报为完成。

完整流程请参阅 [Skill 使用说明](version-dod-evidence/SKILL.md)。

### Codex Thread Title Normalizer

[`codex-thread-title-normalizer/`](codex-thread-title-normalizer/)

用于批量规范 Codex 对话标题；以 `createdAt` 的 Asia/Shanghai 日期生成标题，并在任何改名之前展示确认表，不会修改项目或对话内容。

完整流程请参阅 [Skill 使用说明](codex-thread-title-normalizer/SKILL.md)。

### AI QA Weekly

[`ai-qa-weekly/`](ai-qa-weekly/)

用于从当前官方、GitHub、研究和工程来源中发现、核验、筛选并整理 AI ×
软件测试与质量工程动态，生成中英文双语周报；包含主题分类、来源策略、
搜索策略、输出模板和人工相关性评测案例。

完整流程请参阅 [Skill 使用说明](ai-qa-weekly/SKILL.md)。

## 仓库结构

每个 Skill 都位于独立目录中，目录内可以包含主说明文件 `SKILL.md`、Agent 元数据、参考资料、示例或其他配套资源。

## 许可证

如果仓库提供许可证文件，请以仓库中的许可证文件为准。
