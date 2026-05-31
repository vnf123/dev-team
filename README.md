# Dev Team — AI 虚拟开发团队

模拟真实软件团队的 AI 协作模式。**你是老板**，发号施令；AI 担任 **PM**，负责拆解任务、调度子 Agent、整合交付并向你汇报。

## 🎯 角色架构

```
老板 (你) → 发号施令，审批结果
    ↓
PM (主 Agent) → 接令 → 拆解 → 调度 → 整合 → 汇报
    ↓
┌────┼────┬──────────┐
🎨UI  ⚛️前端  🖥️后端   [按需] 🔧DevOps 🧪QA 👀Reviewer
```

- **四个核心角色**：PM、UI/UX Designer、Frontend、Backend
- **三个可选角色**：DevOps、QA、Code Reviewer（按需启用）
- 每个角色有专属提示词模板和技能映射
- PM 负责审核对齐、处理冲突，对最终结果负责

## 🚀 安装

```bash
# 克隆仓库
git clone https://github.com/xiaonan-sun/dev-team.git

# 安装技能到 Claude Code
cp -r dev-team/.claude/skills/dev-team ~/.claude/skills/

# 或者项目级安装
cp -r dev-team/.claude/skills/dev-team 你的项目/.claude/skills/
```

## 🎮 使用方式

### 触发词
直接说以下任意指令即可启动：
- **「启动开发团队」**
- **「团队模式」**
- **「组建团队」**

### 典型流程

```
老板：「帮我搭一个用户管理后台」

PM：「老板，我计划分三路：UI 定设计风格、后端设计 API、
     前端等设计和 API 就绪后实现。这样可以吗？」

老板确认 → PM 调度子 Agent → 整合 → 汇报交付
```

### 场景匹配

| 场景 | 模式 |
|------|------|
| 从零搭建全栈功能 | 🟢 启用团队 |
| 跨领域重构 | 🟢 启用团队 |
| 加个按钮 / 修样式 | 🟡 PM 自己做 |
| 修 Bug | 🟡 PM 自己做 |

## 🧠 设计理念

- **老板视角**：你下命令，看结果。不关心内部怎么调度。
- **Token 精简**：简单任务不派生 Agent，只为真正需要并行的工作开团队。
- **一人一责**：每个子 Agent 只负责一个领域，清晰的目标和交付物。
- **PM 兜底**：子 Agent 的输出由 PM 审核对齐，处理冲突。

## 📁 文件结构

```
dev-team/
├── README.md
├── LICENSE
└── .claude/
    └── skills/
        └── dev-team/
            └── SKILL.md    # 技能核心文件
```

## 📋 角色技能映射

| 角色 | 关联技能 |
|------|---------|
| UI/UX Designer | ui-ux-pro-max, web-design-guidelines |
| Frontend | vercel-react-best-practices, vercel-composition-patterns, next-best-practices |
| Backend | java-spring-boot, coding-standards |
| DevOps | devops-engineer |
| QA | tdd, breakdown-test |
| Reviewer | requesting-code-review, improve-codebase-architecture |

## 📄 许可

MIT License — 详见 [LICENSE](LICENSE)
