# Hermes Agent 知识库

> 系统版本: 2026-04-19 | 基于 hermes-agent skill v2.0.0 | 参考: Hermes-Skills-Knowledge-Base.md

---

## 目录

1. [核心概念](#1-核心概念)
2. [安装与快速开始](#2-安装与快速开始)
3. [CLI 命令参考](#3-cli-命令参考)
4. [配置系统](#4-配置系统)
5. [Skill 系统](#5-skill-系统)
6. [工具集（Toolsets）](#6-工具集toolsets)
7. [多 Agent 协作](#7-多-agent-协作)
8. [开发方法论](#8-开发方法论)
9. [Gateway 消息平台](#9-gateway-消息平台)
10. [故障排除](#10-故障排除)

---

## 1. 核心概念

### 什么是 Hermes Agent

Hermes Agent 是 Nous Research 开源的 AI Agent 框架，运行在终端、消息平台和 IDE 中。与 Claude Code（Anthropic）、Codex（OpenAI）、OpenClaw 属于同一类别——通过工具调用与系统交互的自主编码 Agent。

**与 Claude Code / Codex / OpenCode 的对比：**

| 特性        | Hermes Agent                               | Claude Code                                | Codex                          | OpenCode                      |
| --------- | ------------------------------------------ | ------------------------------------------ | ------------------------------ | ----------------------------- |
| Provider  | 20+（OpenRouter/Anthropic/OpenAI/DeepSeek等） | Anthropic only                             | OpenAI only                    | 多后端                           |
| 多平台       | Telegram/Discord/Slack/WhatsApp等10+平台      | CLI only                                   | CLI only                       | CLI only                      |
| Skill 自进化 | ✓ 持久化经验为 Skill                             | ✗                                          | ✗                              | ✗                             |
| 多 Profile | ✓ 独立配置隔离                                   | ✗                                          | ✗                              | ✗                             |
| 安装方式      | `curl -fsSL .../install.sh \| bash`        | `npm install -g @anthropic-ai/claude-code` | `npm install -g @openai/codex` | `npm i -g opencode-ai@latest` |

### Hermes 的五大差异化特性

1. **Self-improving through skills** — 从经验中学习，把解决过的问题保存为 Skill 文档，供未来会话加载
2. **Persistent memory** — 跨会话记忆用户偏好、环境细节、经验教训
3. **Multi-platform gateway** — 同一 Agent 运行在 Telegram/Discord/Slack/WhatsApp 等平台，不只是聊天
4. **Provider-agnostic** — 随时切换模型/Provider，凭证池自动轮换
5. **Profiles** — 多个独立 Hermes 实例，配置/会话/Skill/内存完全隔离

**官网:** https://hermes-agent.nousresearch.com/docs/
**GitHub:** https://github.com/NousResearch/hermes-agent

---

## 2. 安装与快速开始

### 安装

```bash
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash
```

### 快速命令

```bash
hermes                    # 交互式聊天（默认）
hermes chat -q "问题"     # 单次查询，非交互
hermes setup              # 交互向导（model|terminal|gateway|tools|agent）
hermes model              # 交互式选择模型/Provider
hermes doctor             # 健康检查
```

### 全局 Flags

```
hermes [flags] [command]

  --version, -V             显示版本
  --resume, -r SESSION      按 ID 或标题恢复会话
  --continue, -c [NAME]     按名称恢复，或最近会话
  --worktree, -w            隔离 git worktree 模式（并行 Agent）
  --skills, -s SKILL        预加载 Skill（逗号分隔或重复）
  --profile, -p NAME        使用命名 Profile
  --yolo                    跳过危险命令审批
  --pass-session-id         在系统提示中包含会话 ID
```

无子命令默认执行 `chat`。

---

## 3. CLI 命令参考

### Chat

```
hermes chat [flags]
  -q, --query TEXT          单次查询，非交互
  -m, --model MODEL         指定模型
  -t, --toolsets LIST       逗号分隔的工具集列表
  --provider PROVIDER       强制 Provider
  -v, --verbose             详细输出
  -Q, --quiet               抑制 banner、spinner、工具预览
  --checkpoints             启用文件系统检查点（/rollback）
```

### 配置

```
hermes setup [section]      交互向导
hermes model                模型/Provider 选择器
hermes config               查看当前配置
hermes config edit          在 $EDITOR 中打开 config.yaml
hermes config set KEY VAL   设置配置值
hermes config path          打印 config.yaml 路径
hermes config env-path      打印 .env 路径
hermes config check         检查缺失/过时配置
hermes config migrate       更新配置选项
hermes login [--provider P] OAuth 登录（nous, openai-codex）
hermes logout               清除存储的认证
hermes doctor [--fix]        检查依赖和配置
hermes status [--all]        显示组件状态
```

### 工具与 Skill

```
hermes tools                交互式工具启用/禁用（curses UI）
hermes tools list            显示所有工具及状态
hermes tools enable NAME     启用工具集
hermes tools disable NAME    禁用工具集

hermes skills list           列出已安装 Skill
hermes skills search QUERY   搜索 Skill Hub
hermes skills install ID      安装 Skill
hermes skills inspect ID     预览（不安装）
hermes skills config         按平台启用/禁用 Skill
hermes skills check          检查更新
hermes skills update         更新过时的 Skill
hermes skills uninstall N    卸载 Hub Skill
hermes skills publish PATH   发布到注册表
hermes skills browse         浏览所有可用 Skill
```

### MCP 服务器

```
hermes mcp serve             将 Hermes 作为 MCP 服务器运行
hermes mcp add NAME          添加 MCP 服务器（--url 或 --command）
hermes mcp remove NAME        移除 MCP 服务器
hermes mcp list              列出已配置服务器
hermes mcp test NAME         测试连接
hermes mcp configure NAME    切换工具选择
```

### Gateway（消息平台）

```
hermes gateway run           前台启动 Gateway
hermes gateway install       安装为后台服务
hermes gateway start/stop    控制服务
hermes gateway restart       重启服务
hermes gateway status        检查状态
hermes gateway setup         配置平台
```

**支持平台:** Telegram, Discord, Slack, WhatsApp, Signal, Email, SMS, Matrix, Mattermost, Home Assistant, DingTalk, Feishu, WeCom, BlueBubbles (iMessage), Weixin (WeChat), API Server, Webhooks

### 会话管理

```
hermes sessions list          列出最近会话
hermes sessions browse        交互式选择器
hermes sessions export OUT    导出为 JSONL
hermes sessions rename ID T   重命名会话
hermes sessions delete ID     删除会话
hermes sessions prune         清理旧会话（--older-than N days）
hermes sessions stats         会话存储统计
```

### Cron 定时任务

```
hermes cron list             列出作业（--all 包含已禁用）
hermes cron create SCHED     创建: '30m', 'every 2h', '0 9 * * *'
hermes cron edit ID          编辑计划、提示、交付
hermes cron pause/resume ID  控制作业状态
hermes cron run ID           触发下次执行
hermes cron remove ID        删除作业
hermes cron status           调度器状态
```

### Webhook

```
hermes webhook subscribe N    在 /webhooks/<name> 创建路由
hermes webhook list           列出订阅
hermes webhook remove NAME    移除订阅
hermes webhook test NAME      发送测试 POST
```

### Profile

```
hermes profile list            列出所有 Profile
hermes profile create NAME    创建（--clone, --clone-all, --clone-from）
hermes profile use NAME       设置持久默认
hermes profile delete NAME    删除
hermes profile show NAME      显示详情
hermes profile alias NAME      管理包装脚本
hermes profile rename A B     重命名
hermes profile export NAME     导出为 tar.gz
hermes profile import FILE     从归档导入
```

### 其他

```
hermes insights [--days N]    使用分析
hermes update                 更新到最新版本
hermes pairing list/approve/revoke  DM 授权管理
hermes plugins list/install/remove  插件管理
hermes honcho setup/status    Honcho 内存集成
hermes memory setup/status/off  内存 Provider 配置
hermes completion bash|zsh    Shell 补全
hermes acp                    ACP 服务器（IDE 集成）
hermes claw migrate           从 OpenClaw 迁移
hermes uninstall              卸载 Hermes
```

---

## 4. 配置系统

### 关键路径

```
~/.hermes/config.yaml        主配置
~/.hermes/.env               API 密钥和秘密
$HERMES_HOME/skills/         已安装 Skill
~/.hermes/sessions/          会话记录
~/.hermes/logs/              Gateway 和错误日志
~/.hermes/auth.json          OAuth 令牌和凭证池
~/.hermes/hermes-agent/      源代码（如果通过 git 安装）
```

Profile 使用 `~/.hermes/profiles/<name>/` 相同布局。

### 配置段落

编辑：`hermes config edit` 或 `hermes config set section.key value`

| 段落 | 关键选项 |
|------|---------|
| `model` | `default`, `provider`, `base_url`, `api_key`, `context_length` |
| `agent` | `max_turns` (90), `tool_use_enforcement` |
| `terminal` | `backend` (local/docker/ssh/modal), `cwd`, `timeout` (180) |
| `compression` | `enabled`, `threshold` (0.50), `target_ratio` (0.20) |
| `display` | `skin`, `tool_progress`, `show_reasoning`, `show_cost` |
| `stt` | `enabled`, `provider` (local/groq/openai/mistral) |
| `tts` | `provider` (edge/elevenlabs/openai/minimax/mistral/neutts) |
| `memory` | `memory_enabled`, `user_profile_enabled`, `provider` |
| `security` | `tirith_enabled`, `website_blocklist` |
| `delegation` | `model`, `provider`, `base_url`, `api_key`, `max_iterations` (50) |
| `smart_model_routing` | `enabled`, `cheap_model` |
| `checkpoints` | `enabled`, `max_snapshots` (50) |

完整配置参考: https://hermes-agent.nousresearch.com/docs/user-guide/configuration

### Provider 支持（20+）

| Provider | 认证方式 | 密钥环境变量 |
|----------|---------|------------|
| OpenRouter | API key | `OPENROUTER_API_KEY` |
| Anthropic | API key | `ANTHROPIC_API_KEY` |
| Nous Portal | OAuth | `hermes auth` |
| OpenAI Codex | OAuth | `hermes auth` |
| GitHub Copilot | Token | `COPILOT_GITHUB_TOKEN` |
| Google Gemini | API key | `GOOGLE_API_KEY` |
| DeepSeek | API key | `DEEPSEEK_API_KEY` |
| xAI / Grok | API key | `XAI_API_KEY` |
| Hugging Face | Token | `HF_TOKEN` |
| Z.AI / GLM | API key | `GLM_API_KEY` |
| MiniMax | API key | `MINIMAX_API_KEY` |
| MiniMax CN | API key | `MINIMAX_CN_API_KEY` |
| Kimi / Moonshot | API key | `KIMI_API_KEY` |
| Alibaba / DashScope | API key | `DASHSCOPE_API_KEY` |
| 自定义端点 | Config | `model.base_url` + `model.api_key` |

---

## 5. Skill 系统

### 什么是 Skill

Skill 是 Hermes 的**经验持久化机制**——当 Agent 解决了一个复杂问题、发现了某个工作流、或被用户纠正后，可以把知识保存为 Skill 文档，供未来会话加载。Skill 会随时间累积，使 Agent 越来越擅长你的特定任务和环境。

### Skill 文件结构

```
~/.hermes/skills/                    # 用户安装的 Skill
~/.hermes/profiles/<name>/skills/    # Profile 隔离的 Skill
./.hermes/skills/                     # 项目级 Skill

skill-name/
├── SKILL.md           # 主文件（YAML frontmatter + markdown 正文）
└── references/        # 参考文档（可选）
    ├── api.md
    └── examples.md
```

### YAML Frontmatter 格式

```yaml
---
name: skill-name           # 唯一标识
description: 简短描述      # 触发条件匹配
version: 1.0.0
author: 作者
license: MIT
metadata:
  hermes:
    tags: [标签列表]
    related_skills: [相关skill]
---
```

### Skill 加载规则

**自动加载:** 系统自动扫描消息，当任务匹配某个 Skill 的描述时自动加载。

**手动加载:**
```
/skill <name>        # 在会话中加载
hermes -s <name>     # 命令行预加载
hermes skills install ID  # 从 Hub 安装
```

### Skill 分类索引（参考 Hermes-Skills-Knowledge-Base.md）

完整 79 个 Skill 的详细描述、依赖、用法示例见：`/Users/lh/共享/Hermes-Skills-Knowledge-Base.md`

| 分类                   | Skill 数量 | 代表性 Skill                                             |
| -------------------- | -------- | ----------------------------------------------------- |
| apple                | 4        | apple-notes, apple-reminders, findmy, imessage        |
| autonomous-ai-agents | 4        | claude-code, codex, opencode, hermes-agent            |
| creative             | 8        | ascii-art, excalidraw, p5js, manim-video              |
| data-science         | 1        | jupyter-live-kernel                                   |
| devops               | 1        | webhook-subscriptions                                 |
| email                | 1        | himalaya                                              |
| gaming               | 2        | minecraft-modpack-server, pokemon-player              |
| github               | 6        | github-pr-workflow, github-code-review, github-issues |
| leisure              | 1        | find-nearby                                           |
| mcp                  | 2        | mcporter, native-mcp                                  |
| media                | 4        | youtube-content, gif-search, songsee, heartmula       |
| mlops                | 16+      | axolotl, unsloth, vllm, llama-cpp, gguf, whisper      |
| note-taking          | 1        | obsidian                                              |
| productivity         | 6        | notion, linear, nano-pdf, google-workspace            |
| red-teaming          | 1        | godmode                                               |
| research             | 5        | arxiv, polymarket, blogwatcher, llm-wiki              |
| smart-home           | 1        | openhue                                               |
| social-media         | 1        | xitter                                                |
| software-development | 9+       | plan, TDD, debugging, subagent, writing-plans         |

### 与外部 AI Coding Agent 的 Skill 对比

| Skill | 用途 | 关键命令 |
|-------|------|---------|
| `claude-code` | Anthropic Claude Code CLI，结构化输出好 | `claude -p 'task' --max-turns 10` |
| `codex` | OpenAI Codex CLI，**必须在 git 仓库内运行** | `codex exec 'task'` |
| `opencode` | 开源 provider-agnostic AI 编程 Agent | `opencode run 'task'` |

---

## 6. 工具集（Toolsets）

通过 `hermes tools`（交互式）或 `hermes tools enable/disable NAME` 启用/禁用。

**注意:** 工具变更在 `/reset`（新会话）后生效，不会中断当前会话以保留 prompt 缓存。

| 工具集 | 提供内容 |
|--------|---------|
| `web` | Web 搜索和内容提取 |
| `browser` | 浏览器自动化（Browserbase/Camofox/本地 Chromium） |
| `terminal` | Shell 命令和进程管理 |
| `file` | 文件读/写/搜索/补丁 |
| `code_execution` | 沙箱化 Python 执行 |
| `vision` | 图像分析 |
| `image_gen` | AI 图像生成 |
| `tts` | 文本转语音 |
| `skills` | Skill 浏览和管理 |
| `memory` | 跨会话持久内存 |
| `session_search` | 搜索过去会话 |
| `delegation` | 子 Agent 任务委托 |
| `cronjob` | 定时任务管理 |
| `clarify` | 向用户提问澄清问题 |
| `messaging` | 跨平台消息发送 |
| `search` | 仅 Web 搜索（`web` 的子集） |
| `todo` | 会话内任务规划和跟踪 |
| `rl` | 强化学习工具（默认关闭） |
| `moa` | Mixture of Agents（默认关闭） |
| `homeassistant` | 智能家居控制（默认关闭） |

### 语音配置

**STT（语音→文本）:**

| Provider | 说明 | 费用 |
|----------|------|------|
| Local faster-whisper | 需 `pip install faster-whisper` | 免费 |
| Groq Whisper | 需 `GROQ_API_KEY` | 免费层 |
| OpenAI Whisper | 需 `VOICE_TOOLS_OPENAI_KEY` | 付费 |
| Mistral Voxtral | 需 `MISTRAL_API_KEY` | 付费 |

**TTS（文本→语音）:**

| Provider | 环境变量 | 费用 |
|----------|---------|------|
| Edge TTS | 无 | 免费（默认） |
| ElevenLabs | `ELEVENLABS_API_KEY` | 免费层 |
| OpenAI | `VOICE_TOOLS_OPENAI_KEY` | 付费 |
| MiniMax | `MINIMAX_API_KEY` | 付费 |
| NeuTTS（本地） | `pip install neutts[all] + espeak-ng` | 免费 |

---

## 7. 多 Agent 协作

### delegate_task vs 启动 hermes 进程

|      | `delegate_task` | Spawn `hermes` 进程 |
| ---- | --------------- | ----------------- |
| 隔离性  | 独立对话，共享进程       | 完全独立进程            |
| 时长   | 分钟级（受父循环限制）     | 小时/天级             |
| 工具访问 | 父级工具子集          | 完整工具访问            |
| 交互性  | 否               | 是（PTY 模式）         |
| 适用场景 | 快速并行子任务         | 长时间自主任务           |

### 方式一：单次模式（hermes chat -q）

```bash
# 前台执行
hermes chat -q 'Research GRPO papers and write summary to ~/research/grpo.md'

# 后台执行（长任务）
hermes chat -q 'Set up CI/CD for ~/myapp'
```

### 方式二：tmux 交互模式

Hermes 使用 prompt_toolkit，需要真实终端。用 tmux：

```bash
# 启动
tmux new-session -d -s agent1 -x 120 -y 40 'hermes'

# 等待启动，发送消息
sleep 8 && tmux send-keys -t agent1 'Build a FastAPI auth service' Enter

# 读取输出
sleep 20 && tmux capture-pane -t agent1 -p

# 发送后续消息
tmux send-keys -t agent1 'Add rate limiting middleware' Enter

# 退出
tmux send-keys -t agent1 '/exit' Enter && sleep 2 && tmux kill-session -t agent1
```

### 多 Agent 协调

```bash
# Agent A: backend
tmux new-session -d -s backend -x 120 -y 40 'hermes -w'
sleep 8 && tmux send-keys -t backend 'Build REST API for user management' Enter

# Agent B: frontend
tmux new-session -d -s frontend -x 120 -y 40 'hermes -w'
sleep 8 && tmux send-keys -t frontend 'Build React dashboard for user management' Enter

# 检查进度
tmux capture-pane -t backend -p | tail -30
```

### 提示

- **快速子任务用 `delegate_task`** — 开销小于启动完整进程
- **编辑代码时用 `-w`（worktree 模式）** — 避免 git 冲突
- **单次模式设置 timeout** — 复杂任务可能需要 5-10 分钟
- **交互会话用 tmux** — raw PTY 模式 prompt_toolkit 有 `\r` vs `\n` 问题
- **定时任务用 `cronjob` 工具** — 处理交付和重试

---

## 8. 开发方法论

Hermes 内置了一套软件开发方法论 Skill，涵盖从规划到调试的完整流程。

### Skill 地图

```
writing-plans          创建可执行实现计划（任务拆分、精确路径、完整代码）
       ↓
subagent-driven-development   通过 delegate_task 执行计划，两阶段审查
       ↓
requesting-code-review       提交前验证流水线
       ↓
test-driven-development      RED-GREEN-REFACTOR 测试先行
       ↓
systematic-debugging         四阶段根因调试
```

### Plan 模式 — 只规划不执行

**触发:** 用户想要计划而非执行。

**行为:**
- 不实现代码
- 不编辑项目文件（仅写计划文件）
- 不运行变更性终端命令
- 可用只读命令检查代码库

**输出:** Markdown 计划保存到 `.hermes/plans/YYYY-MM-DD_HHMMSS-<slug>.md`

```python
write_file(path=".hermes/plans/2026-04-19_114500-auth-module.md", content="""...")
```

### Writing Plans — 编写实现计划

**用途:** 有规格说明或需求的多步骤任务。

**计划结构:**
```markdown
# [功能名] 实现计划

**Goal:** 一句话描述构建目标
**Architecture:** 2-3 句方法描述
**Tech Stack:** 关键技术和库

### Task 1: [描述性名称]

**Files:**
- Create: `exact/path/to/new_file.py`
- Modify: `exact/path/to/existing.py:45-67`

**Step 1: 写失败测试**
```python
def test_specific_behavior():
    result = function(input)
    assert result == expected
```

**Step 2: 运行测试验证失败**
Run: `pytest tests/path/test.py::test_specific_behavior -v`
Expected: FAIL

**Step 3: 写最小实现**
```python
def function(input):
    return expected
```
```

**原则:**
- 每任务 2-5 分钟专注工作
- 精确文件路径
- 完整可复制代码
- TDD 原则

### Test-Driven Development（TDD）

**铁律:**
```
NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST
```

**循环:**
1. **RED** — 写一个最小测试展示应该发生什么
2. **Verify RED** — 必须看到测试失败 `pytest ... -v`
3. **GREEN** — 写最简单的代码通过测试（GREEN 阶段可以作弊）
4. **Verify GREEN** — 必须看到测试通过
5. **REFACTOR** — 清理代码

**Rationalizations to Avoid:**
| 借口 | 现实 |
|------|------|
| "太简单不需要测试" | 简单代码也会坏，测试只需30秒 |
| "之后写测试" | 测试立即通过什么都证明不了 |
| "已经手动测试了" | 手动测试≠系统化测试 |

### Subagent-Driven Development

**用途:** 执行实现计划，任务间相互独立。

**流程:**
1. **读计划** — 一次性解析所有任务，创建 TODO
2. **每任务执行:**
   - **Step 1:** 派发实现子 Agent（完整任务文本+上下文）
   - **Step 2:** Spec 合规审查（所有需求实现了？路径匹配？）
   - **Step 3:** 代码质量审查（风格/错误处理/命名/安全）
   - **Step 4:** 标记完成
3. **最终集成审查**
4. **验证并提交**

**关键原则:**
- 每任务用**全新**子 Agent
- 永远**先** spec 合规，**再**代码质量
- **跳过审查等于失败**

### Systematic Debugging

**铁律:**
```
NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST
```

**四阶段:**

| 阶段 | 关键活动 | 成功标准 |
|------|---------|---------|
| **1. 根因** | 读错误消息、复现、检查变更、追踪数据流 | 理解 WHAT 和 WHY |
| **2. 模式分析** | 找工作中的例子、对比、识别差异 | 知道哪里不同 |
| **3. 假设** | 形成理论、最小化测试、一次一变量 | 确认或新假设 |
| **4. 实现** | 创建回归测试、修复根因、验证 | Bug 解决，全部测试通过 |

**红灯停下来:**
- "快速修复，回头再调查"
- "试试改 X 看是否有效"
- "3+ 修复都失败了"
- 每个修复都暴露了不同地方的新问题

### Pre-Commit Verification（requesting-code-review）

**触发:** 实现功能或修复 bug 后，`git commit` 或 `git push` 前。

**8步流水线:**

1. **获取 diff** — `git diff --cached`
2. **静态安全扫描** — 硬编码 secrets/shell 注入/SQL 注入/eval/exec
3. **基线测试和 linting** — 检测语言，自动运行对应工具
4. **自审 checklist** — 无 secrets/输入验证/参数化查询/路径校验/错误处理
5. **独立审查子 Agent** — 新鲜上下文，只看 diff 和扫描结果，FAIL-CLOSED
6. **评估结果** — 全部通过→Step 8，有失败→Step 7
7. **自动修复循环** — 最多2轮，只修报告的问题
8. **提交** — `git add -A && git commit -m "[verified] <description>"`

### Web QA Testing（dogfood）

**用途:** Web 应用系统性探索 QA 测试。

**5阶段流程:**
1. **Plan** — 创建目录结构，规划测试范围
2. **Explore** — 导航页面，与元素交互，截图
3. **Collect Evidence** — 每个问题记录详情+截图
4. **Categorize** — 按严重性分类（Critical/High/Medium/Low）
5. **Report** — 生成结构化报告

---

## 9. Gateway 消息平台

### 平台支持

Telegram, Discord, Slack, WhatsApp, Signal, Email, SMS, Matrix, Mattermost, Home Assistant, DingTalk, Feishu, WeCom, **Weixin (WeChat)**, BlueBubbles (iMessage), API Server, Webhooks

### 常用命令

```
hermes gateway setup         配置平台
hermes gateway run           前台启动
hermes gateway install       安装为后台服务
hermes gateway start/stop/restart  控制服务
hermes gateway status        检查状态
```

### 平台常见问题

| 平台 | 常见问题 |
|------|---------|
| Discord | 必须启用 **Message Content Intent**（Bot → Privileged Gateway Intents） |
| Slack | 必须在 Event Subscriptions 订阅 `message.channels`，否则忽略公开频道 |
| Weixin | 使用 `hermes pairing approve weixin <code>` 授权 |

### 日志

```bash
grep -i "failed to send\|error" ~/.hermes/logs/gateway.log | tail -20
```

### SSH/WLS 注意事项

- **SSH logout 后 Gateway 死掉:** 启用 linger: `sudo loginctl enable-linger $USER`
- **WSL2 关闭后 Gateway 死掉:** WSL2 需要 `/etc/wsl.conf` 中 `systemd=true`
- **Gateway 崩溃循环:** `systemctl --user reset-failed hermes-gateway`

---

## 10. 故障排除

### 语音不工作

1. 检查 `stt.enabled: true` in config.yaml
2. 验证 provider: `pip install faster-whisper` 或设置 API key
3. Gateway: `/restart`。CLI: 退出并重新启动

### 工具不可用

1. `hermes tools` — 检查工具集是否启用
2. 检查 `.env` 中的环境变量
3. `/reset` 后启用工具

### 模型/Provider 问题

1. `hermes doctor` — 检查配置和依赖
2. `hermes login` — 重新认证 OAuth Provider
3. 检查 `.env` 是否有正确 API key
4. **Copilot 403:** `gh auth login` 的 token 不适用于 Copilot API，必须通过 `hermes model` → GitHub Copilot 使用 Copilot 专用 OAuth 设备代码流

### 变更不生效

- **工具/Skill:** `/reset` 启动新会话
- **配置变更:** Gateway: `/restart`。CLI: 退出重启
- **代码变更:** 重启 CLI 或 Gateway 进程

### Skill 不显示

1. `hermes skills list` — 验证已安装
2. `hermes skills config` — 检查平台启用
3. 手动加载: `/skill name` 或 `hermes -s name`

### Aux 模型不工作

如果 `auxiliary` 任务（vision/compression/session_search）静默失败，`auto` provider 找不到后端。设置 `OPENROUTER_API_KEY` 或显式配置:
```bash
hermes config set auxiliary.vision.provider <provider>
hermes config set auxiliary.vision.model <model>
```

### Key Paths 参考

| 查找内容 | 位置 |
|---------|------|
| 配置选项 | `hermes config edit` |
| 可用工具 | `hermes tools list` |
| Slash 命令 | `/help` |
| Skill 目录 | `hermes skills browse` |
| Provider 设置 | `hermes model` |
| Gateway 日志 | `~/.hermes/logs/gateway.log` |
| 会话文件 | `~/.hermes/sessions/` |
| 源代码 | `~/.hermes/hermes-agent/` |

---

## 附录：相关资源

- **Hermes Agent 官方文档:** https://hermes-agent.nousresearch.com/docs/
- **GitHub:** https://github.com/NousResearch/hermes-agent
- **Skills 完整目录:** `/Users/lh/共享/Hermes-Skills-Knowledge-Base.md`（79个Skill详解）
