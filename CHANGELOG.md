# Changelog

本文件记录 dev-team skill 的所有重要变更。

## [1.1.0-beta.1] - 2026-06-01

### 🧪 Beta

- 调整为**手动触发低 Token 版**：仅当用户明确说“启动开发团队”“团队模式”“组建团队”“用 dev-team”或同义指令时使用。
- 缩短 `SKILL.md` frontmatter description，降低常驻 token 占用，并明确禁止因复杂/全栈/UI/前后端任务自行触发。
- 精简 `SKILL.md` 正文：移除冗长角色模板，保留触发边界、调度上限、短派发模板和汇报格式。
- 默认调度更保守：优先 PM 自己做，常规团队模式最多 2 个 Agent，3+ Agent 需要说明成本并确认。
- 同步 README 和 `skill.json`，标注 beta 版行为差异与推荐指令。

## [1.0.1] - 2025-05-31

### 📚 Documentation

- 补充核心调度逻辑透明说明：流程图、并发上限、决策矩阵、异常处理、冲突处理优先级。
- 补充 Token 成本参考：按 PM 单人 / 轻量团队 / 标准团队 / 完整团队 / 扩展团队给出成本倍数和建议。
- 在 SKILL.md 中同步加入并发上限与异常处理规则。
- 创建 GitHub Release 作为正式发布版本。


### 🎉 初始发布

- 🏗️ 核心架构：老板 → PM → 子 Agent 三级协作模型
- 👔 老板角色定义：发号施令、审批结果
- 🔷 PM（主 Agent）：任务拆解、智能调度、审核整合、汇报交付
- 🎨 UI/UX Designer 角色：设计规范、视觉风格、交互体验
- ⚛️ Frontend Developer 角色：React/Vue/Next.js 组件开发
- 🖥️ Backend Developer 角色：API 设计、数据库、业务逻辑
- 🔧 三个可选角色：DevOps / QA / Code Reviewer
- 🧠 智能调度策略：并行/串行判断矩阵
- ⚡ Token 精简原则：简单任务 PM 自己做
- 📋 汇报格式：任务摘要 + 投入角色 + 产出文件 + 关键决策
- 🔌 集成 15+ 优质社区 Skill

[1.1.0-beta.1]: https://github.com/vnf123/dev-team/releases/tag/v1.1.0-beta.1
[1.0.1]: https://github.com/vnf123/dev-team/releases/tag/v1.0.1
[1.0.0]: https://github.com/vnf123/dev-team/releases/tag/v1.0.0
