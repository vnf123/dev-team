# 🤝 贡献指南

感谢你为 Dev Team skill 贡献！任何形式的贡献都欢迎。

## 🚀 快速开始

```bash
# Fork 并克隆
git clone https://github.com/你的用户名/dev-team.git
cd dev-team

# 安装到本地测试
cp -r .claude/skills/dev-team ~/.claude/skills/

# 重启 Claude Code，触发「启动开发团队」测试
```

## 📋 贡献类型

### 🐛 Bug 修复
发现角色提示词行为异常、PM 调度逻辑错误、技能映射不工作？

1. 先在 [Issues](https://github.com/vnf123/dev-team/issues) 搜索是否已有相同问题
2. 如果没有，创建新 Issue —— 描述现象、复现步骤、期望行为
3. 提交 PR 时关联 Issue（`fixes #123`）

### ✨ 新角色
想添加移动端开发、数据工程师、安全专家等角色？

- 在 Issue 中先讨论，确认角色有价值
- 角色必须满足：有独立领域边界、有可映射的 Skill、有专属提示词
- 可选角色优先（按需启用），不增加默认派生成本

### 📝 提示词优化
每个角色的提示词是核心。优化的标准：

- **更精准**：减少 AI 自由发挥的空间
- **更高效**：减少不必要的输出要求
- **更通用**：不绑定特定项目或框架
- **可测试**：效果变化可以验证

### 📖 文档改进
README、注释、使用案例——文档永远不够好。

## 🧪 测试你的改动

1. 修改 `.claude/skills/dev-team/SKILL.md`
2. 确保不超过 500 行
3. 在 Claude Code 中测试：
   - 说「启动开发团队」→ 确认触发
   - 给一个简单任务 → 确认 PM 不派生 Agent
   - 给一个复杂全栈任务 → 确认 PM 正确调度
4. 检查所有子 Agent 的提示词模板是否正确填充

## 📐 规范

### 提交信息
```
<类型>: <简短描述>

<详细说明>
```

类型：`feat` / `fix` / `docs` / `refactor` / `chore`

示例：`feat: 新增 Data Engineer 角色`

### PR 要求
- 描述清楚改了什么、为什么改
- 关联相关 Issue
- 确保 SKILL.md 在 500 行以内
- 如有新增角色，更新 README 角色表格

### 代码规范
- SKILL.md 使用中文（用户群体偏好）
- 角色提示词模板保持「你是 XX 专家」风格
- 并行/串行策略有清晰判断依据

## 📜 行为准则

参与本项目即表示遵守 [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)。

---

再次感谢！每一个 PR 都让这个虚拟团队更强大 🚀
