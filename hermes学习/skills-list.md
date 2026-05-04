# Hermes Agent Skills 列表1

本文档整理了 Hermes Agent 所有可用的 Skill，按类别组织。每个 Skill 包含名字、简介、使用方法和适用场景。

---

## 1. 所有 Skill 列表

| 类别 | Skill | 简介 |
|------|-------|------|
| autonomous-ai-agents | [autonomous-ai-agents](https://github.com/search?q=repo%3ANousResearch%2FHermes+path%3A*.md+skills%2Fautonomous-ai-agents+OR+skills%2Fclaude-code+OR+skills%2Fcodex+OR+skills%2Fhermes-agent+OR+skills%2Fopencode&type=code) | AI 代理编排 — 委托任务给 Claude Code、Codex、OpenCode 等，构建多代理工作流 |
| autonomous-ai-agents | [claude-code](skills/claude-code.md) | 将编码任务委托给 Claude Code (Anthropic 的 CLI 代理) |
| autonomous-ai-agents | [codex](skills/codex.md) | 将编码任务委托给 OpenAI Codex CLI 代理 |
| autonomous-ai-agents | [hermes-agent](skills/hermes-agent.md) | Hermes Agent 完整使用指南 — CLI 命令、配置选项、工具 API |
| autonomous-ai-agents | [opencode](skills/opencode.md) | 将编码任务委托给 OpenCode CLI 代理 |
| creative | [architecture-diagram](skills/architecture-diagram.md) | 生成深色主题的软件架构 SVG 图表 |
| creative | [ascii-art](skills/ascii-art.md) | 使用 pyfiglet 生成 ASCII 艺术字、cowsay 对话气泡、图片转 ASCII |
| creative | [ascii-video](skills/ascii-video.md) | 将视频转换为 ASCII 艺术动画的完整流水线 |
| creative | [baoyu-comic](skills/baoyu-comic.md) | 多艺术风格的知识漫画创建器 |
| creative | [baoyu-infographic](skills/baoyu-infographic.md) | 21 种布局类型的专业信息图表生成器 |
| creative | [design-md](skills/design-md.md) | 编写、验证、对比和导出 DESIGN.md — Google 设计文档格式 |
| creative | [excalidraw](skills/excalidraw.md) | 使用 Excalidraw JSON 格式创建手绘风格图表 |
| creative | [ideation](skills/ideation.md) | 通过创意约束生成项目想法 |
| creative | [manim-video](skills/manim-video.md) | 使用 Manim (3Blue1Brown 动画引擎) 创建数学/技术动画视频 |
| creative | [p5js](skills/p5js.md) | 使用 p5.js 在浏览器中创建交互式生成艺术 |
| creative | [pixel-art](skills/pixel-art.md) | 将图片转换为复古像素艺术，支持硬件准确调色板和抖动 |
| creative | [popular-web-designs](skills/popular-web-designs.md) | 54 种从真实流行网站提取的生产级设计系统 |
| creative | [songwriting-and-ai-music](skills/songwriting-and-ai-music.md) | 歌曲创作技巧和 AI 音乐生成提示词 (Suno 为主) |
| data-science | [jupyter-live-kernel](skills/jupyter-live-kernel.md) | 连接活跃 Jupyter 内核进行有状态迭代 Python 计算和数据探索 |
| devops | [webhook-subscriptions](skills/webhook-subscriptions.md) | 为事件驱动架构和实时集成创建管理 Webhook 订阅 |
| email | [himalaya](skills/himalaya.md) | 通过 IMAP/SMTP 管理邮件的 CLI 工具 — 列表、读取、发送、搜索 |
| gaming | [minecraft-modpack-server](skills/minecraft-modpack-server.md) | 从 CurseForge/Modrinth 服务器包搭建 modded Minecraft 服务器 |
| gaming | [pokemon-player](skills/pokemon-player.md) | 通过无头模拟器 (pyboy) 自动玩宝可梦游戏 |
| github | [codebase-inspection](skills/codebase-inspection.md) | 使用 pygount 统计代码行数、语言构成、代码/注释比例 |
| github | [github-auth](skills/github-auth.md) | 设置 GitHub 认证 — HTTPS token、SSH 密钥、凭证助手 |
| github | [github-code-review](skills/github-code-review.md) | 审查代码变更 — 分析 git diff、在 PR 上留评论、做提交前审查 |
| github | [github-issues](skills/github-issues.md) | 创建、管理、分类和关闭 GitHub Issues |
| github | [github-pr-workflow](skills/github-pr-workflow.md) | 完整 PR 生命周期 — 创建分支、提交、打开 PR、监控 CI、合并 |
| github | [github-repo-management](skills/github-repo-management.md) | 克隆、创建、复刻、配置 GitHub 仓库，管理 remote、secrets、releases |
| mcp | [native-mcp](skills/native-mcp.md) | 内置 MCP 客户端 — 连接外部 MCP 服务器，发现并注册其工具 |
| media | [gif-search](skills/gif-search.md) | 使用 curl 从 Tenor 搜索下载 GIF |
| media | [heartmula](skills/heartmula.md) | 开源音乐生成模型家族 (类 Suno) — 从歌词+标签生成完整歌曲 |
| media | [songsee](skills/songsee.md) | 从音频文件生成频谱图和音频特征可视化 (mel、chroma、MFCC 等) |
| media | [spotify](skills/spotify.md) | 控制 Spotify — 播放音乐、搜索目录、管理播放列表、查看设备状态 |
| media | [youtube-content](skills/youtube-content.md) | 提取 YouTube 视频字幕并转换为结构化内容 (章节、摘要、推文、博客) |
| mlops/evaluation | [weights-and-biases](skills/weights-and-biases.md) | ML 实验跟踪 — 自动记录指标、实时可视化训练、优化超参数、管理模型注册表 |
| mlops/inference | [llama-cpp](skills/llama-cpp.md) | llama.cpp 本地 GGUF 推理 + Hugging Face Hub 模型发现 |
| mlops/inference | [obliteratus](skills/obliteratus.md) | 使用机械解释性技术移除开源 LLM 的拒绝行为 (消融安全过滤器) |
| mlops/inference | [outlines](skills/outlines.md) | 保证生成内容为有效 JSON/Pydantic 结构，支持本地模型和 vLLM |
| mlops/research | [dspy](skills/dspy.md) | 声明式 AI 编程 — 自动优化提示词、构建模块化 RAG 系统和代理 |
| mlops/training | [axolotl](skills/axolotl.md) | Axolotl 微调 LLM 专家指南 — YAML 配置、LoRA/QLoRA、DPO/KTO/ORPO/GRPO |
| mlops/training | [unsloth](skills/unsloth.md) | Unsloth 快速微调 — 2-5x 更快训练、50-80% 更少显存、LoRA/QLoRA 优化 |
| note-taking | [obsidian](skills/obsidian.md) | 在 Obsidian 笔记库中读取、搜索和创建笔记 |
| red-teaming | [godmode](skills/godmode.md) | 使用 G0DM0D3 技术 (Parseltongue、GODMODE CLASSIC、ULTRAPLINIAN) 进行 LLM 红队测试 |
| smart-home | [openhue](skills/openhue.md) | 通过 OpenHue CLI 控制飞利浦 Hue 灯、房间和场景 |

---

## 2. Skill 详细介绍

### autonomous-ai-agents

**简介**: Skills for spawning and orchestrating autonomous AI coding agents and multi-agent workflows — running independent agent processes, delegating tasks, and coordinating parallel workstreams.

**使用方法**: 使用 delegate_task 工具，指定 goal、context 和 toolsets。可以设置 role='orchestrator' 来创建可派生子任务的协调者，支持最多 delegation.max_concurrent_children (默认 3) 个并行子任务。

**使用场景**: 当需要委托编码任务给 Claude Code、OpenAI Codex 或其他 AI 代理时；当需要构建多代理协作工作流时；当需要并行处理多个独立任务时。

---

### claude-code

**简介**: Delegate coding tasks to Claude Code (Anthropic's CLI agent).

**使用方法**: 通过 delegate_task 调用，设置 acp_command='claude' 和 acp_args=['--acp', '--stdio']。子代理在独立会话中运行，无当前聊天上下文。

**使用场景**: 当需要将编码任务委托给 Claude Code 时；当用户要求使用 Claude Code 执行任务时。

---

### codex

**简介**: Delegate coding tasks to OpenAI Codex CLI agent. Use for autonomous coding, codebase exploration, and complex implementation tasks.

**使用方法**: 通过 delegate_task 调用，设置合适的 acp_command 和参数。可以设置 toolsets=['terminal', 'file', 'web'] 获取完整能力。

**使用场景**: 当需要将编码任务委托给 OpenAI Codex 时；当需要进行自主编码、代码库探索和复杂实现时。

---

### hermes-agent

**简介**: Complete guide to using and extending Hermes Agent — CLI commands, config options, tool APIs, memory management, and platform integrations.

**使用方法**: 参考 skill 内容了解 Hermes Agent 的完整功能。CLI 命令: hermes --help；配置文件: ~/.hermes/config.yaml；工具包括 terminal、read_file、patch、delegate_task 等。

**使用场景**: 当需要了解 Hermes Agent 的使用方法、配置选项或扩展方式时；当遇到 Hermes 相关问题时。

---

### opencode

**简介**: Delegate coding tasks to OpenCode CLI agent for feature implementation, bug fixes, and codebase navigation.

**使用方法**: 通过 delegate_task 调用进行任务委托。支持 toolsets=['terminal', 'file', 'web'] 等。

**使用场景**: 当需要将编码任务委托给 OpenCode 时；当用户要求使用 OpenCode 执行任务时。

---

### dogfood

**简介**: Systematic exploratory QA testing of web applications — finds UI inconsistencies, broken links, console errors, and tricky edge cases that normal testing misses.

**使用方法**: 使用 browser_navigate 导航到目标页面，然后用 browser_snapshot、browser_vision、browser_console 等工具进行系统性检查。

**使用场景**: 当需要对 Web 应用进行系统性 QA 测试时；当发现 UI bug、链接失效、控制台错误时。

---

### architecture-diagram

**简介**: Generate dark-themed SVG diagrams of software systems and architectures.

**使用方法**: 提供系统的文本描述或结构信息，生成深色主题的 SVG 图表。可直接在浏览器或 Markdown 中渲染。

**使用场景**: 当需要生成软件架构图、系统拓扑图、数据流程图时。

---

### ascii-art

**简介**: Generate ASCII art using pyfiglet (571 fonts), cowsay, boxes, and lolcat. Includes image-to-ASCII conversion.

**使用方法**: 使用 pyfiglet 生成艺术字，cowsay 生成对话气泡，lolcat 添加颜色，可以用枕头库 (Pillow) 将图片转为 ASCII。

**使用场景**: 当需要生成 ASCII 艺术字、字符画、图片转 ASCII 时。

---

### ascii-video

**简介**: Production pipeline for ASCII art video — any format to ASCII, text-only pipeline, and playback.

**使用方法**: 提供视频文件，转换成 ASCII 艺术帧序列，支持播放和导出。需要先安装依赖并配置环境。

**使用场景**: 当需要将视频转换为 ASCII 艺术动画时。

---

### baoyu-comic

**简介**: Knowledge comic creator supporting multiple art styles and formats for educational content.

**使用方法**: 提供内容描述和想要的艺术风格，生成知识漫画。

**使用场景**: 当需要创建知识漫画、教育内容时。

---

### baoyu-infographic

**简介**: Generate professional infographics with 21 layout types and data visualization.

**使用方法**: 提供数据和内容，选择布局类型，生成专业信息图表。

**使用场景**: 当需要创建信息图表、数据可视化时。

---

### design-md

**简介**: Author, validate, diff, and export DESIGN.md files — Google's design doc format for engineering projects.

**使用方法**: 创建符合 Google 设计文档格式的 Markdown 文件，包含背景、目标、设计、权衡、监控等部分。

**使用场景**: 当需要编写设计文档时。

---

### excalidraw

**简介**: Create hand-drawn style diagrams using Excalidraw JSON format for collaborative whiteboarding.

**使用方法**: 使用 Excalidraw JSON 格式创建图表，可以导出或嵌入到文档中。

**使用场景**: 当需要创建手绘风格的图表时。

---

### ideation

**简介**: Generate project ideas through creative constraints. Use to brainstorm and explore project possibilities.

**使用方法**: 提供主题或约束条件，生成创意项目想法。

**使用场景**: 当需要头脑风暴项目想法时。

---

### manim-video

**简介**: Production pipeline for mathematical and technical animations using Manim (3Blue1Brown's animation engine).

**使用方法**: 使用 Manim 库编写 Python 脚本生成数学动画视频。安装: pip install manim。

**使用场景**: 当需要创建数学动画、技术演示、可视化教学视频时。

---

### p5js

**简介**: Production pipeline for interactive and generative visual art using p5.js in the browser.

**使用方法**: 使用 p5.js 编写 JavaScript 代码生成交互式视觉艺术。可以在浏览器中运行。

**使用场景**: 当需要创建交互式生成艺术、可视化效果时。

---

### pixel-art

**简介**: Convert images into retro pixel art with hardware-accurate color palettes and dithering.

**使用方法**: 提供图片，使用硬件准确的调色板和抖动算法转换为像素艺术。

**使用场景**: 当需要将图片转换为像素风格时。

---

### popular-web-designs

**简介**: 54 production-quality design systems extracted from real popular websites for inspiration.

**使用方法**: 浏览 54 种从真实流行网站提取的生产级设计系统，获取设计灵感。

**使用场景**: 当需要网站设计参考时。

---

### songwriting-and-ai-music

**简介**: Songwriting craft, AI music generation prompts (Suno focus), and music production workflow.

**使用方法**: 参考歌曲创作技巧，使用 Suno 等 AI 音乐生成工具的提示词技巧。

**使用场景**: 当需要写歌、创作歌词时。

---

### jupyter-live-kernel

**简介**: Use a live Jupyter kernel for stateful, iterative Python computation and data exploration.

**使用方法**: 通过 execute_code 工具连接活跃的 Jupyter 内核，进行有状态的 Python 计算。

**使用场景**: 当需要进行有状态的迭代 Python 计算时；当需要实时数据探索和分析时。

---

### webhook-subscriptions

**简介**: Create and manage webhook subscriptions for event-driven architectures and real-time integrations.

**使用方法**: 使用 webhook 工具创建订阅、接收事件、管理端点。

**使用场景**: 当需要创建和管理 Webhook 订阅时。

---

### himalaya

**简介**: CLI to manage emails via IMAP/SMTP. Use himalaya to list, read, send, search, and manage email from the terminal.

**使用方法**: 使用 himalaya CLI 命令进行邮件操作，支持 IMAP/SMTP 协议。

**使用场景**: 当需要在终端管理电子邮件时。

---

### minecraft-modpack-server

**简介**: Set up a modded Minecraft server from a CurseForge/Modrinth server pack zip. Covers NeoForge/Forge install, Java version, JVM tuning, firewall, LAN config, backups, and launch scripts.

**使用方法**: 下载服务器包 → 安装 Java (1.21+ 用 Java 21, 1.18-1.20 用 Java 17) → 安装 Mod Loader → 接受 EULA → 配置 server.properties → 调优 JVM 参数 → 开放防火墙 → 创建启动脚本 → 设置自动备份。

**使用场景**: 当需要搭建 modded Minecraft 服务器时。

---

### pokemon-player

**简介**: Play Pokemon games autonomously via headless emulation using pyboy. Starts a game server, reads structured game state from RAM, makes strategic decisions, and sends button inputs.

**使用方法**: 克隆 pokemon-agent 仓库 → 创建虚拟环境 → 安装依赖 → 用户提供 ROM 文件 → 启动游戏服务器 → 使用 GET /state 和 GET /screenshot 观察 → POST /action 发送按键。定期保存: POST /save。

**使用场景**: 当需要让 AI 自动玩宝可梦游戏时。

---

### codebase-inspection

**简介**: Inspect and analyze codebases using pygount for LOC counting, language breakdown, and code-vs-comment ratios.

**使用方法**: pip install pygount; pygount --format=summary --folders-to-skip=".git,node_modules,venv" . 记得用 --folders-to-skip 排除依赖目录。

**使用场景**: 当需要统计代码行数、了解代码库规模时。

---

### github-auth

**简介**: Set up GitHub authentication for the agent using git or gh CLI. Covers HTTPS tokens, SSH keys, credential helpers, and gh auth.

**使用方法**: 优先使用 gh CLI（更简单）：gh auth login。或者使用 git + HTTPS 个人访问令牌/SSH 密钥。先检测: gh auth status。

**使用场景**: 当需要设置 GitHub 认证时。

---

### github-code-review

**简介**: Review code changes by analyzing git diffs, leaving inline comments on PRs, and performing thorough pre-push review.

**使用方法**: git diff main...HEAD --stat 查看范围 → git diff 查看完整变更 → 系统性检查正确性、安全性、代码质量、测试、文档 → 提交发现。

**使用场景**: 当需要进行代码审查时。

---

### github-issues

**简介**: Create, manage, triage, and close GitHub issues. Search existing issues, add labels, assign people, and link to PRs.

**使用方法**: gh issue create 创建，gh issue list 列表，gh issue edit 管理标签/ assignee，gh issue close 关闭。也可以用 curl 调用 API。

**使用场景**: 当需要管理 GitHub Issues 时。

---

### github-pr-workflow

**简介**: Full pull request lifecycle — create branches, commit changes, open PRs, monitor CI status, auto-fix failures, and merge.

**使用方法**: git checkout -b 创建分支 → git add + git commit 提交 → git push -u origin HEAD 推送 → gh pr create 创建 PR → gh pr checks 监控 CI → gh pr merge 合并。

**使用场景**: 当需要进行完整的 PR 流程时。

---

### github-repo-management

**简介**: Clone, create, fork, configure, and manage GitHub repositories. Manage remotes, secrets, releases, and workflows.

**使用方法**: gh repo create 创建仓库，gh repo clone 克隆，gh repo fork 复刻，gh repo edit 配置。也可以用 curl API 管理分支保护、secrets、releases。

**使用场景**: 当需要管理 GitHub 仓库时。

---

### native-mcp

**简介**: Built-in MCP (Model Context Protocol) client that connects to external MCP servers, discovers their tools, and registers them as native Hermes Agent tools.

**使用方法**: 在 ~/.hermes/config.yaml 中配置 mcp_servers，指定 command/args（stdio 传输）或 url（HTTP 传输）。重启 Hermes 后自动连接和发现工具。工具命名: mcp_{server_name}_{tool_name}。

**使用场景**: 当需要连接 MCP 服务器并使用其工具时。

---

### gif-search

**简介**: Search and download GIFs from Tenor using curl. No dependencies beyond curl and jq.

**使用方法**: 设置 TENOR_API_KEY 环境变量（从 https://developers.google.com/tenor/ 获取免费 API key），使用 curl 调用 Tenor API 搜索和下载 GIF。

**使用场景**: 当需要搜索和下载 GIF 时。

---

### heartmula

**简介**: Set up and run HeartMuLa, the open-source music generation model family (Suno-like). Generates full songs from lyrics + tags with multilingual support.

**使用方法**: 克隆 heartlib 仓库 → 创建 Python 3.10 虚拟环境 → uv pip install -e . → 修复依赖冲突（datasets 和 transformers 需要升级）→ 修补源码（RoPE cache 和 HeartCodec loading）→ 下载模型检查点 → python ./examples/run_music_generation.py 运行。

**使用场景**: 当需要生成音乐/歌曲时；当需要开源的 Suno 替代方案时。

---

### songsee

**简介**: Generate spectrograms and audio feature visualizations (mel, chroma, MFCC, tempogram, etc.) from audio files via CLI.

**使用方法**: go install github.com/steipete/songsee/cmd/songsee@latest 安装 → songsee track.mp3 -o spectrogram.png 生成频谱图。使用 --viz 参数选择可视化类型（spectrogram, mel, chroma, mfcc 等）。

**使用场景**: 当需要进行音频分析时。

---

### spotify

**简介**: Control Spotify — play music, search the catalog, manage playlists and library, inspect devices and playback state.

**使用方法**: 需要 Hermes Spotify toolset 启用并运行过 hermes auth spotify。7 个工具：spotify_playback（播放/暂停/切歌）、spotify_search（搜索）、spotify_playlists（播放列表）、spotify_queue（队列）、spotify_devices（设备）、spotify_albums（专辑）、spotify_library（收藏）。播放需要 Spotify Premium。

**使用场景**: 当需要控制 Spotify 播放时。

---

### youtube-content

**简介**: Fetch YouTube video transcripts and transform them into structured content (chapters, summaries, threads, blog posts).

**使用方法**: pip install youtube-transcript-api → python3 SKILL_DIR/scripts/fetch_transcript.py "URL" 获取字幕 → 转换为章节/摘要/推文/博客格式。

**使用场景**: 当用户提供 YouTube URL 或要求总结视频时。

---

### axolotl

**简介**: Expert guidance for fine-tuning LLMs with Axolotl - YAML configs, 100+ models, LoRA/QLoRA, DPO/KTO/ORPO/GRPO, multimodal support.

**使用方法**: 编写 YAML 配置文件定义模型、数据集、训练参数 → 运行 axolotl train 命令启动微调。支持多种训练方法（LoRA/QLoRA/DPO/ORPO/GRPO）和模型。

**使用场景**: 当需要进行 LLM 微调时。

---

### dspy

**简介**: Build complex AI systems with declarative programming, optimize prompts automatically, create modular RAG systems and agents with DSPy.

**使用方法**: 定义 Signatures（输入输出结构）→ 使用 Modules（Predict、ChainOfThought、ReAct、ProgramOfThought）构建模块 → 使用 Optimizers（BootstrapFewShot、MIPRO）自动优化。pip install dspy。

**使用场景**: 当需要构建复杂 AI 系统时；当需要进行声明式编程、自动优化提示词时。

---

### huggingface-hub

**简介**: Hugging Face Hub CLI (hf) — search, download, and upload models and datasets, manage repos, query datasets with SQL, deploy inference endpoints, manage Spaces and buckets.

**使用方法**: 安装: curl -LsSf https://hf.co/cli/install.sh | bash。命令: hf download 下载、hf upload 上传、hf models list 搜索模型、hf datasets sql 查询数据集、hf spaces 管理 Spaces。

**使用场景**: 当需要与 Hugging Face Hub 交互时。

---

### llama-cpp

**简介**: llama.cpp local GGUF inference + HF Hub model discovery. Run local models on CPU, Apple Silicon, CUDA, ROCm, or Intel GPUs.

**使用方法**: 安装 llama.cpp: brew install llama.cpp 或从源码编译。使用 llama-cli -hf 或 llama-server -hf 直接从 Hugging Face Hub 运行 GGUF 模型。使用 python: from llama_cpp import Llama 加载本地 GGUF。

**使用场景**: 当需要在本地运行 GGUF 格式模型时。

---

### obliteratus

**简介**: Remove refusal behaviors from open-weight LLMs using OBLITERATUS — mechanistic interpretability techniques (diff-in-means, SVD, whitened SVD, LEACE, SAE decomposition) to excise guardrails while preserving reasoning.

**使用方法**: git clone https://github.com/elder-plinius/OBLITERATUS.git && pip install -e . → obliteratus recommend <model> 获取建议 → obliteratus obliterate <model> --method advanced --output-dir ./abliterated-models。9 种方法：basic、advanced（默认推荐）、aggressive、surgical、optimized 等。

**使用场景**: 当需要移除模型的拒绝行为/安全过滤器时。注意：仅用于开源模型，AGPL 许可证。

---

### outlines

**简介**: Guarantee valid JSON/XML/code structure during generation, use Pydantic models for type-safe outputs, support local models (Transformers, vLLM), and maximize inference speed with Outlines.

**使用方法**: pip install outlines → 使用 outlines.generate.json(model, PydanticClass) 生成有效 JSON，outlines.generate.choice() 生成选项，outlines.generate.regex() 生成匹配正则的内容。

**使用场景**: 当需要保证生成内容的 JSON/结构有效性时。

---

### unsloth

**简介**: Expert guidance for fast fine-tuning with Unsloth - 2-5x faster training, 50-80% less memory, LoRA/QLoRA optimization.

**使用方法**: pip install unsloth → 编写微调代码使用 Unsloth 的优化内核。支持 Llama、Mistral、Gemma、Qwen 等模型。2-5x 加速训练，50-80% 更少显存。

**使用场景**: 当需要快速微调 LLM 时。

---

### weights-and-biases

**简介**: Track ML experiments with automatic logging, visualize training in real-time, optimize hyperparameters with sweeps, and manage model registry with W&B.

**使用方法**: pip install wandb → wandb.login() 登录 → wandb.init(project="name") 初始化 → wandb.log({"metric": value}) 记录 → wandb.sweep() 超参数搜索。

**使用场景**: 当需要跟踪 ML 实验时。

---

### openhue

**简介**: Control Philips Hue lights, rooms, and scenes via the OpenHue CLI. Turn lights on/off, adjust brightness, color, color temperature, and activate scenes.

**使用方法**: 安装: curl -sL https://github.com/openhue/openhue-cli/releases/latest/download/openhue-linux-amd64 -o ~/.local/bin/openhue && chmod +x。使用: openhue get light 查看灯光，openhue set light "name" --on --brightness 50 调整。

**使用场景**: 当需要控制飞利浦 Hue 智能灯时。

---

### godmode

**简介**: Jailbreak API-served LLMs using G0DM0D3 techniques — Parseltongue input obfuscation (33 techniques), GODMODE CLASSIC system prompt templates, ULTRAPLINIAN multi-model racing. ⚠️ 仅用于合法安全研究和测试目的。

**使用方法**: auto_jailbreak() 自动检测模型并应用最佳绕过策略，或手动配置 system_prompt + prefill.json。Parseltongue 混淆触发词。ULTRAPLINIAN 多模型竞速。⚠️ 警告：仅用于安全研究和测试。

**使用场景**: 当需要进行 LLM 红队测试、绕过安全过滤器时。⚠️ 仅用于合法安全研究目的。

---

### obsidian

**简介**: Read, search, and create notes in the Obsidian vault.

**使用方法**: 设置 OBSIDIAN_VAULT_PATH 环境变量（默认 ~/Documents/Obsidian Vault）。使用 find/cat/grep 命令操作 Markdown 笔记文件。支持 [[wikilinks]] 链接语法。

**使用场景**: 当需要在 Obsidian 笔记库中读取、搜索、创建笔记时。

---

*文档生成时间: 2026-04-25*
