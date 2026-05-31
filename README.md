<!-- markdownlint-disable MD033 MD041 -->
<div align="center">

<img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
<img src="https://img.shields.io/badge/Claude%20Code-ONLY-6C4DFF?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude Code Only">
<img src="https://img.shields.io/badge/version-1.0.0-green?style=for-the-badge" alt="Version">
<img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge" alt="PRs Welcome">

<br><br>

<h1>🏗️ Dev Team</h1>
<h3>AI 虚拟开发团队</h3>

<p>
  <b>老板发号施令 · PM 智能调度 · 多角色 AI Agent 并行协作</b><br>
  <sub>模拟真实软件团队的 AI 工作流 —— 你当老板，AI 当团队</sub>
</p>

<br>

```
   👔 老板 (你)
     │
     ▼
   🔷 PM (主 Agent)
     │
     ├── 🎨 UI/UX Designer   → 设计规范 · 视觉风格 · 交互体验
     ├── ⚛️  Frontend Developer → 组件 · 状态 · 路由 · 性能
     ├── 🖥️  Backend Developer  → API · 数据库 · 业务逻辑 · 认证
     ├── 🔧 DevOps Engineer     → CI/CD · Docker · 部署
     ├── 🧪 QA Engineer         → 测试策略 · 集成测试
     └── 👀 Code Reviewer       → 架构审查 · 安全审计
```

</div>

<br>

---

## 📖 目录

- [⚠️ 平台支持](#-平台支持)
- [🤔 这是什么？](#-这是什么)
- [✨ 核心亮点](#-核心亮点)
- [🚀 快速开始](#-快速开始)
- [📦 安装](#-安装)
- [🎮 使用](#-使用)
- [🧩 角色详情](#-角色详情)
- [📐 设计哲学](#-设计哲学)
- [📁 项目结构](#-项目结构)
- [🤝 贡献](#-贡献)
- [📄 许可](#-许可)
- [⭐ 致谢](#-致谢)

---

## ⚠️ 平台支持

> [!WARNING]
> **仅支持 Claude Code**（CLI · VS Code 扩展 · JetBrains 扩展）
>
> ❌ 不支持 Cursor / Windsurf / GitHub Copilot / Codex / Kiro / Trae / 其他 AI 编辑器
>
> **原因**：核心功能（派生子 Agent、角色分工、并行调度）依赖 Claude Code 独有的 **Agent 工具** 和 **Skill 工具**，其他平台尚不支持。

> [!TIP]
> 如果团队用其他编辑器，角色提示词模板可单独拿出来当系统指令使用（降级模式，无多 Agent 调度）。

---

## 🤔 这是什么？

**Dev Team** 是一个 Claude Code 技能（Skill），将单个 AI 对话升级为**多角色虚拟开发团队**。

传统模式下，你和一个 AI 对话，它什么都干——前端、后端、设计一把梭。但真实项目里，UI 设计、前端开发、后端逻辑是**不同的人**负责的，各有所长，各司其职。这个 Skill 就是把这个模式搬到了 AI 里。

> **每个角色都是独立的子 Agent**，拥有专属提示词和技能映射。PM 负责接令、拆解、调度、审核、整合，最后向你——老板汇报。

---

## ✨ 核心亮点

<table>
<tr>
  <td width="50%">

  ### 🎯 老板视角
  只管发号施令和审结果，不关心内部怎么调度。

  ### 🧠 智能调度
  PM 自动判断需要哪些角色、并行还是串行。

  ### 🎨 专业分工
  每个子 Agent 有专属「大神级」提示词，不是换个名字。

  </td>
  <td width="50%">

  ### 🔌 技能映射
  自动关联 15+ 高质量社区 Skill（Vercel · Anthropic · mattpocock）

  ### ⚡ Token 精简
  简单活 PM 自己干，只为真正需要并行的工作开团队。

  ### 🛡️ 质量兜底
  PM 审核对齐所有输出，处理角色间冲突。

  </td>
</tr>
</table>

---

## 🚀 快速开始

```bash
# 1. 安装
npx skills add vnf123/dev-team@dev-team -g

# 2. 重启 Claude Code

# 3. 在 Claude Code 里说
> 启动开发团队，帮我搭一个用户管理后台
```

搞定了。PM 会自动拆解任务、派生角色、并行执行、向你汇报。

---

## 📦 安装

<details open>
<summary><b>方式一：npx skills（推荐）</b></summary>
<br>

```bash
npx skills add vnf123/dev-team@dev-team -g
```

一行命令，自动安装到 Claude Code。

</details>

<details>
<summary><b>方式二：手动安装</b></summary>
<br>

```bash
# 克隆仓库
git clone https://github.com/vnf123/dev-team.git

# 用户级安装（所有项目可用）
cp -r dev-team/.claude/skills/dev-team ~/.claude/skills/

# 项目级安装（仅当前项目）
cp -r dev-team/.claude/skills/dev-team 你的项目/.claude/skills/
```

</details>

<br>

> [!IMPORTANT]
> 安装后**重启 Claude Code** 才能生效。

---

## 🎮 使用

### 触发方式

| 指令 | 效果 |
|:-----|:-----|
| `启动开发团队` | 手动触发团队模式 |
| `团队模式` / `组建团队` | 同上 |
| 复杂的多角色开发任务 | 自动触发 |

### 调度策略

<div align="center">

| 🟢 并行（一次发多个 Agent） | 🟡 串行（等上一个完成） |
|:---|:---|
| UI + Backend → 设计规范和 API 互不依赖 | UI → Frontend → 前端需设计输出 |
| Frontend × N → 多个独立页面/组件 | Backend → Frontend → 前端需 API 定义 |
| Backend + DevOps → 代码和部署配置并行 | PM 整合 → Reviewer → 审查在整合后 |

</div>

### 典型对话

> **👨‍💼 老板**
>
> 帮我搭一个用户管理后台，需要登录注册、用户列表、权限管理。前端用 React + shadcn，后端用 Spring Boot。

> **🤖 PM**
>
> 老板，我计划这样推进：
>
> - **并行**：UI Designer + Backend（设计规范和 API 设计互不依赖）
> - **串行**：Frontend（等 UI 和 API 就绪后开工）
>
> 需要 QA 做集成测试吗？

> **👨‍💼 老板**
>
> 先不加 QA，开始吧。

> **🤖 PM** — *几分钟后*
>
> 老板，完成了。以下是交付情况：
>
> | | |
> |---|---|
> | 📋 任务 | 用户管理后台（登录 / 注册 / 列表 / 权限） |
> | 👥 投入 | UI Designer + Backend + Frontend |
> | 📦 产出 | `design-system.md` · `UserController.java` · `AuthService.java` · `schema.sql` · `LoginPage.tsx` · `UserList.tsx` · `RoleGuard.tsx` |
> | 💡 决策 | 权限模型用了 RBAC，后续扩展更灵活 |

### 匹配策略

```
简单任务         →  PM 自己干，不提团队
跨领域 / 多文件   →  PM 先汇报计划，老板确认后开团队
老板说「团队模式」 →  无条件启用
```

---

## 🧩 角色详情

<div align="center">

### 🎨 UI/UX Designer

| | |
|:---|:---|
| **何时启用** | 设计系统 · 视觉风格 · 组件规范 · 交互流程 |
| **关联技能** | `ui-ux-pro-max` · `web-design-guidelines` |
| **交付物** | 色彩方案 · 字体搭配 · 间距系统 · 布局描述 · 交互状态 · 可访问性要点 |

### ⚛️ Frontend Developer

| | |
|:---|:---|
| **何时启用** | React / Vue / Next.js 组件 · 状态管理 · 路由 · 性能优化 |
| **关联技能** | `vercel-react-best-practices` · `vercel-composition-patterns` · `next-best-practices` |
| **交付物** | 组件代码 · 状态管理 · 路由配置 · loading / empty / error 状态覆盖 |

### 🖥️ Backend Developer

| | |
|:---|:---|
| **何时启用** | API 设计 · 数据库 Schema · 业务逻辑 · 认证授权 |
| **关联技能** | `java-spring-boot` · `coding-standards` |
| **交付物** | API 定义（含请求/响应示例） · 数据库 DDL · 业务代码 · 认证方案 |

### 🔧 可选角色

| 角色 | 触发条件 | 关联技能 |
|:---|:---|:---|
| **DevOps Engineer** | CI/CD · Docker · K8s · 部署 | `devops-engineer` |
| **QA Engineer** | 复杂业务测试 · 全流程策略 | `tdd` · `breakdown-test` |
| **Code Reviewer** | 跨多文件改动 · 安全审查 | `requesting-code-review` · `improve-codebase-architecture` |

</div>

---

## 📐 设计哲学

<blockquote>

#### 🤷 为什么不是"一个 AI 全干"？

一个 AI 全干的问题是**上下文噪音** — 写后端逻辑时不会被前端框架细节分心，做 UI 设计时不会被数据库 Schema 干扰。真实团队按角色分工不是没道理的。

#### 💰 Token 精简原则

> **不派生这个 Agent，最终交付质量会明显下降吗？**

- 修个按钮样式 → **NO** → PM 自己做
- 重构整个权限系统 → **YES** → 启动团队

#### 🛡️ PM 兜底机制

子 Agent 的输出可能存在冲突（比如前后端用了不同的字段名），PM 负责：

- 审核每个 Agent 的产出
- 对齐接口和数据格式
- 合并统一文件结构
- 处理遗漏和边缘情况
- 向老板做清晰汇报

</blockquote>

---

## 📁 项目结构

```
dev-team/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── skill.json
├── .gitignore
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
└── .claude/
    └── skills/
        └── dev-team/
            └── SKILL.md          ← 🔑 技能核心文件
```

---

## 🤝 贡献

欢迎提 Issue 和 PR！详见 [CONTRIBUTING.md](CONTRIBUTING.md)

| 🐛 | ✨ | 📝 | 🔌 | 📖 |
|:--|:--|:--|:--|:--|
| 修复角色提示词 | 新增角色 | 优化提示词模板 | 集成更多 Skill | 补充文档 |

---

## 📄 许可

<p align="center">
  MIT License · © 2025 <a href="https://github.com/vnf123">vnf123</a>
</p>

---

## ⭐ 致谢

本 Skill 集成了以下优秀社区技能（需提前安装）：

<div align="center">

| 技能 | 作者 | 安装量 |
|:---|:---|:---|
| `vercel-react-best-practices` | Vercel | 440K |
| `web-design-guidelines` | Vercel | 355K |
| `vercel-composition-patterns` | Vercel | 194K |
| `ui-ux-pro-max` | NextLevelBuilder | 192K |
| `tdd` | mattpocock | 183K |
| `requesting-code-review` | obra | 107K |
| `java-spring-boot` | pluginagentmp | 10.9K |
| `devops-engineer` | jeffallan | 5.5K |

</div>

<br>

---

<p align="center">
  <sub>Built with ❤️ for the AI coding community</sub>
  <br><br>
  <a href="https://github.com/vnf123/dev-team/stargazers">⭐ Star</a> ·
  <a href="https://github.com/vnf123/dev-team/issues">🐛 Report Bug</a> ·
  <a href="https://github.com/vnf123/dev-team/issues">✨ Request Feature</a>
</p>
