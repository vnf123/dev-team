# 🏗️ Dev Team — AI 虚拟开发团队

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/Claude%20Code-Skill-6C4DFF" alt="Claude Code Skill">
  <img src="https://img.shields.io/badge/version-1.0.0-green.svg" alt="Version">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome">
</p>

<p align="center">
  <b>老板发号施令 · PM 智能调度 · 多角色 AI Agent 并行协作</b><br>
  模拟真实软件团队的 AI 工作流 —— 你当老板，AI 当团队
</p>

---

## 🤔 这是什么？

**Dev Team** 是一个 Claude Code 技能（Skill），将单个 AI 对话升级为**多角色虚拟开发团队**。

传统模式下，你和一个 AI 对话，它什么都干。但真实项目里，UI 设计、前端开发、后端逻辑是不同的人负责的——他们各有所长，各司其职。

这个 Skill 模拟了真实团队：

```
你（老板）
  │
  ▼
PM（主 Agent）
  │
  ├── 🎨 UI/UX Designer   → 设计规范、视觉风格、交互体验
  ├── ⚛️  Frontend Developer → 组件、状态、路由、性能优化
  ├── 🖥️  Backend Developer  → API、数据库、业务逻辑、认证
  ├── 🔧 DevOps Engineer     → CI/CD、Docker、部署（按需）
  ├── 🧪 QA Engineer         → 测试策略、集成测试（按需）
  └── 👀 Code Reviewer       → 架构审查、安全审计（按需）
```

**每个角色都是独立的子 Agent**，拥有各自领域的专属提示词和技能映射。PM（主 Agent）负责接令、拆解任务、调度子 Agent、审核整合，最后向你——老板汇报。

---

## ✨ 核心亮点

| 特性 | 说明 |
|------|------|
| 🎯 **老板视角** | 你只管发号施令和审结果，不关心内部怎么调度 |
| 🧠 **智能调度** | PM 自动判断需要哪些角色，并行还是串行 |
| 🎨 **专业分工** | 每个子 Agent 有专属提示词，不是换个名字而已 |
| 🔌 **技能映射** | 自动关联 15+ 高质量 Skill（Vercel/Anthropic/mattpocock 等） |
| ⚡ **Token 精简** | 简单活 PM 自己干，只为真正需要并行的工作开团队 |
| 🛡️ **质量兜底** | PM 审核对齐所有输出，处理角色间冲突 |

---

## 📦 安装

### 方式一：手动安装

```bash
# 克隆仓库
git clone https://github.com/vnf123/dev-team.git

# 用户级安装（推荐，所有项目可用）
cp -r dev-team/.claude/skills/dev-team ~/.claude/skills/

# 或项目级安装（仅当前项目）
cp -r dev-team/.claude/skills/dev-team 你的项目/.claude/skills/
```

### 方式二：通过 npx skills（即将上线）

```bash
npx skills add vnf123/dev-team@dev-team -g
```

安装后**重启 Claude Code** 即可生效。

---

## 🎮 使用

### 触发方式

在 Claude Code 中直接说：

| 指令 | 效果 |
|------|------|
| `启动开发团队` | 手动触发团队模式 |
| `团队模式` | 同上 |
| `组建团队` | 同上 |
| 复杂的多角色开发任务 | 自动触发 |

### 典型对话

```
👨‍💼 你：帮我搭一个用户管理后台，需要登录注册、用户列表、
      权限管理，前端用 React + shadcn，后端用 Spring Boot

🤖 PM：老板，我计划这样推进：

      并行：UI Designer + Backend
      - UI 先出设计风格和组件规范
      - 后端同时设计 API + 数据库 Schema
      
      串行：Frontend（等 UI 和 API 就绪后动工）
      
      需要 QA 做集成测试吗？

👨‍💼 你：先不加 QA，开始吧

🤖 PM：[并行派生 UI Agent + Backend Agent]
      
      ... 几分钟后 ...

🤖 PM：老板，完成了。以下是交付情况：

      📋 任务：用户管理后台（登录/注册/列表/权限）
      👥 投入：UI Designer + Backend + Frontend
      📦 产出：
        - 设计规范: design-system.md
        - 后端: UserController.java, AuthService.java, schema.sql
        - 前端: LoginPage.tsx, UserList.tsx, RoleGuard.tsx
      💡 关键决策：权限模型用了 RBAC，后续扩展更灵活
```

### 匹配策略

```
简单任务 → PM 自己干，不提团队
跨领域/多文件 → PM 先汇报计划，确认后开团队
老板说「团队模式」→ 无条件启用
```

---

## 🧩 角色详情

### 🎨 UI/UX Designer
**何时启用**：设计系统、视觉风格、组件规范、交互流程

**关联技能**：`ui-ux-pro-max`、`web-design-guidelines`

**输出**：色彩方案、字体搭配、间距系统、布局描述、交互状态、可访问性要点

---

### ⚛️ Frontend Developer
**何时启用**：React/Vue/Next.js 组件、状态管理、路由、性能优化

**关联技能**：`vercel-react-best-practices`、`vercel-composition-patterns`、`next-best-practices`

**输出**：组件代码、状态管理、路由配置、数据请求层、loading/empty/error 状态

---

### 🖥️ Backend Developer
**何时启用**：API 设计、数据库 Schema、业务逻辑、认证授权、数据验证

**关联技能**：`java-spring-boot`、`coding-standards`

**输出**：API 定义（含请求/响应示例）、数据库 DDL、业务代码、验证逻辑、认证方案

---

### 🔧 可选角色

| 角色 | 触发条件 | 关联技能 |
|------|---------|----------|
| **DevOps Engineer** | CI/CD 配置、Docker 化、K8s 部署 | `devops-engineer` |
| **QA Engineer** | 复杂业务测试、全流程策略 | `tdd`、`breakdown-test` |
| **Code Reviewer** | 跨多文件改动、安全审查 | `requesting-code-review`、`improve-codebase-architecture` |

---

## 📐 设计哲学

### 为什么不是"一个 AI 全干"？

一个 AI 全干的问题是**上下文噪音**——写后端逻辑时不会被前端框架细节分心，做 UI 设计时不会被数据库 Schema 干扰。真实团队按角色分工不是没道理的。

### Token 精简原则

不是每个任务都需要团队。判断标准只有一个：

> **不派生这个 Agent，最终交付质量会明显下降吗？**

- 修个按钮样式 → NO → PM 自己做
- 重构整个权限系统 → YES → 开团队

### PM 兜底机制

子 Agent 可能输出冲突（比如前后端用不同字段名），PM 负责：
- 审核每个 Agent 的产出
- 对齐接口和数据格式
- 合并统一文件结构
- 处理遗漏和边缘情况
- 向老板做清晰汇报

---

## 📁 项目结构

```
dev-team/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── .gitignore
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
└── .claude/
    └── skills/
        └── dev-team/
            └── SKILL.md          ← 技能核心文件
```

---

## 🤝 贡献

欢迎提 Issue 和 PR！详见 [CONTRIBUTING.md](CONTRIBUTING.md)

### 贡献方向

- 🐛 修复角色提示词中的问题
- ✨ 新增角色（移动端、数据工程、ML 等）
- 📝 优化提示词模板
- 🔌 集成更多优质 Skill
- 📖 补充使用案例和文档

---

## 📄 许可

MIT License © 2025 [vnf123](https://github.com/vnf123)

详见 [LICENSE](LICENSE)

---

## ⭐ 致谢

本 Skill 集成了以下优秀社区技能（会自动关联，需提前安装）：

| 技能 | 作者 | 安装量 |
|------|------|--------|
| vercel-react-best-practices | Vercel | 440K |
| web-design-guidelines | Vercel | 355K |
| vercel-composition-patterns | Vercel | 194K |
| ui-ux-pro-max | NextLevelBuilder | 192K |
| java-spring-boot | pluginagentmp | 10.9K |
| devops-engineer | jeffallan | 5.5K |
| tdd | mattpocock | 183K |
| requesting-code-review | obra | 107K |

---

<p align="center">
  <sub>Built with ❤️ for the AI coding community</sub>
</p>
