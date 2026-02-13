# Build with Claude 中文版

## **Claude Skills、Agents、Commands、Hooks、Plugins、Marketplaces 集合 - 用于扩展 Claude Code**

[![Open Source](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://opensource.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![GitHub stars](https://img.shields.io/github/stars/davepoon/buildwithclaude.svg?style=social&label=Star)](https://github.com/davepoon/buildwithclaude)


**[Claude Code](https://docs.anthropic.com/en/docs/claude-code) 的插件市场与发现平台。浏览精选插件、发现社区贡献，并扩展你的 Claude Code 工作流。**

## 快速开始

```bash
# 添加 Build with Claude 市场
/plugin marketplace add davepoon/buildwithclaude

# 浏览可用插件
/plugin search @buildwithclaude

# 安装插件
/plugin install <plugin-name>@buildwithclaude
```

## 包含内容

### Build with Claude 插件

本仓库中维护的精选集合：

| 类型 | 数量 | 描述 |
|------|-------|-------------|
| **Agents** | 117 | 专业化 AI 专家（Python、Go、DevOps、安全等） |
| **Commands** | 175 | 自动化斜杠命令（`/commit`、`/docs`、`/tdd`） |
| **Hooks** | 28 | 事件驱动自动化（通知、git、格式化） |
| **Skills** | 26 | 来自插件的可重用能力 |
| **Plugins** | 50 | 按类别打包的插件包 |

### 社区发现

该平台索引了更广泛的 Claude Code 生态系统中的插件：

- 来自外部市场的 **20,000+ 社区插件**
- 用于数据库、API 和工具连接的 **4,500+ MCP 服务器**
- 来自社区的 **1,100+ 插件市场**

## Web 界面

在 **[buildwithclaude.com](https://www.buildwithclaude.com)** 浏览、搜索和探索所有内容

![Build with Claude 首页](buildwithclaude-homepage.png)

![浏览插件](buildwithclaude-plugins.png)

![浏览 Skills](buildwithclaude-skills.png)

![浏览 MCP 服务器](buildwithclaude-mcp.png)

![浏览插件市场](buildwithclaude-plugin-marketplaces.png)

### 功能特性

- 使用过滤功能浏览所有插件类型
- 跨插件、agents、commands、hooks、skills 搜索
- 一键复制安装命令
- 查看完整文档和使用示例
- 发现 MCP 服务器和社区插件

## 安装选项

### 选项 1：插件市场（推荐）

```bash
# 添加市场
/plugin marketplace add davepoon/buildwithclaude

# 安装特定插件
/plugin install agents-python-expert@buildwithclaude
/plugin install commands-version-control-git@buildwithclaude
/plugin install hooks-notifications@buildwithclaude

# 或安装所有内容
/plugin install all-agents@buildwithclaude
/plugin install all-commands@buildwithclaude
/plugin install all-hooks@buildwithclaude
```

### 选项 2：手动安装

```bash
# 克隆仓库
git clone https://github.com/davepoon/buildwithclaude.git
cd buildwithclaude

# 安装 agents
find plugins/agents-*/agents -name "*.md" -exec cp {} ~/.claude/agents/ \;

# 安装 commands
find plugins/commands-*/commands -name "*.md" -exec cp {} ~/.claude/commands/ \;

# 重启 Claude Code
```

## 可用插件类别

### Agents（11个类别）

- **开发与架构** - 后端、前端、移动、GraphQL 专家
- **语言专家** - Python、Go、Rust、TypeScript、C/C++ 专家
- **质量与安全** - 代码审查、安全审计、调试
- **基础设施与运维** - DevOps、云、数据库优化
- **数据与 AI** - ML 工程、数据管道、AI 开发
- **加密与区块链** - 交易系统、DeFi、Web3 开发

[浏览所有 agents →](https://www.buildwithclaude.com/subagents)

![浏览 Subagents](buildwithclaude-subagents.png)

### Commands（22个类别）

- **版本控制** - 提交、PR 创建、分支管理
- **代码分析** - 测试、审查、优化
- **文档** - 文档生成、变更日志、API 规范
- **项目管理** - 待办事项、PRD、任务跟踪

[浏览所有 commands →](https://www.buildwithclaude.com/commands)

![浏览 Commands](buildwithclaude-commands.png)

### Hooks（8个类别）

- **通知** - Slack、Discord、Telegram 警报
- **Git** - 自动暂存、智能提交
- **开发** - 保存时 lint、自动格式化
- **安全** - 文件保护、漏洞扫描

[浏览所有 hooks →](https://www.buildwithclaude.com/hooks)

![浏览 Hooks](buildwithclaude-hooks.png)

## 使用示例

### 使用 Agents

Agents 根据上下文自动调用，或显式调用：

```
"使用 @python-pro 优化这个函数"
"@agent-security-auditor 审查这段认证代码"
"让 @devops-troubleshooter 帮助调试这个部署"
```

### 使用 Commands

Commands 使用 `/` 前缀：

```
/commit                    # 创建约定式提交
/create-pr                 # 创建拉取请求
/docs                      # 生成文档
/tdd                       # 开始测试驱动开发
/code_analysis             # 分析代码质量
```

### 使用 Hooks

Hooks 在工具调用或会话开始等事件上自动运行。

## 贡献

我们欢迎贡献！

### 添加插件

1. 在 `plugins/` 中按照命名约定创建新目录
2. 添加你的插件文件（agents、commands、hooks）
3. 运行 `npm test` 进行验证
4. 提交拉取请求

### 插件格式

**Agent**（`plugins/agents-*/agents/*.md`）：
```markdown
---
name: agent-name
description: 何时调用此 agent
category: category-name
tools: Read, Write, Bash
---

你是一个[角色描述]...
```

**Command**（`plugins/commands-*/commands/*.md`）：
```markdown
---
description: 此命令的作用
category: category-name
argument-hint: <args>
---

命令实现...
```

**Hook**（`plugins/hooks-*/hooks/*.md`）：
```markdown
---
hooks: PreToolUse, PostToolUse
description: 此 hook 的作用
---

Hook 实现...
```

详细指南请参阅 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 链接

- **Web 界面**: [buildwithclaude.com](https://www.buildwithclaude.com)
- **文档**: [Claude Code 文档](https://docs.anthropic.com/en/docs/claude-code)
- **插件市场**: [插件文档](https://code.claude.com/docs/en/plugin-marketplaces)
- **问题**: [GitHub Issues](https://github.com/davepoon/buildwithclaude/issues)

## 许可证

MIT License - 详情请参阅 [LICENSE](LICENSE)。

---

由 Dave Poon 用 ❤️ 制作
