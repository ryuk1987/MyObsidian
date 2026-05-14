# Hermes Agent Skills 技能列表

共 87 个 skill，分布在 17 个分类下。

---

## autonomous-ai-agents（自主 AI 智能体）

| Skill | 描述 |
|---|---|
| claude-code | 委托代码任务给 Claude Code CLI（功能、PR） |
| codex | 委托代码任务给 OpenAI Codex CLI（功能、PR） |
| hermes-agent | Hermes Agent 完整使用指南 — CLI、配置、Agent 编排、Gateway、Skills、Voice、Tools、Profile |
| opencode | 委托代码任务给 OpenCode CLI（功能、PR 审查） |

---

## creative（创意）

| Skill | 描述 |
|---|---|
| architecture-diagram | 深色主题 SVG 架构/云/基础设施图（HTML） |
| ascii-art | ASCII 艺术：pyfiglet、cowsay、boxes、image-to-ascii |
| ascii-video | ASCII 视频：将视频/音频转为彩色 ASCII MP4/GIF |
| baoyu-comic | 知识漫画：教育传记教程类 |
| baoyu-infographic | 信息图：21 种布局 × 21 种风格 |
| claude-design | 设计一次性 HTML 原型（landing、deck、prototype） |
| comfyui | 用 ComfyUI 生成图像、视频、音频 — 安装、启动、管理节点/模型 |
| design-md | 编写/验证/导出 Google DESIGN.md token 规范文件 |
| excalidraw | 手绘风格 Excalidraw JSON 图表（架构、流程、时序） |
| humanizer | 去除 AI 味，添加真实人类语气 |
| ideation | 通过创意约束生成项目 idea |
| manim-video | Manim CE 动画：3Blue1Brown 数学/算法视频 |
| p5js | p5.js 草图：生成艺术、shader、交互、3D |
| pixel-art | 像素画：NES、Game Boy、PICO-8 时代调色板 |
| popular-web-designs | 54 个真实设计系统（Stripe、Linear、Vercel 等）HTML/CSS |
| pretext | DOM-free 文本布局：ASCII 艺术、字体流动、文本几何游戏、动态字体 |
| sketch | 一次性 HTML 草图：2-3 种设计方案对比 |
| songwriting-and-ai-music | 歌曲创作 + Suno AI 音乐提示词 |
| touchdesigner-mcp | 通过 MCP 控制 TouchDesigner — 创建算子、设置参数、连线、执行 Python |

---

## data-science（数据科学）

| Skill | 描述 |
|---|---|
| jupyter-live-kernel | 通过 live Jupyter kernel 进行迭代式 Python 开发（hamelnb） |

---

## database（数据库）

| Skill | 描述 |
|---|---|
| mysql-crud | MySQL 数据库的增删改查操作 |

---

## devops

| Skill | 描述 |
|---|---|
| kanban-orchestrator | Kanban 编排者指南：任务分解、专家库、反诱惑规则 |
| kanban-worker | Kanban 工作者：坑位、示例、边缘场景 |
| webhook-subscriptions | Webhook 订阅：事件驱动的 Agent 运行 |

---

## email（邮件）

| Skill | 描述 |
|---|---|
| himalaya | Himalaya CLI：终端 IMAP/SMTP 收发邮件 |

---

## gaming（游戏）

| Skill | 描述 |
|---|---|
| minecraft-modpack-server | 托管模组 Minecraft 服务器（CurseForge、Modrinth） |
| pokemon-player | 通过无头模拟器 + RAM 读取玩宝可梦 |

---

## github

| Skill | 描述 |
|---|---|
| codebase-inspection | 用 pygount 检查代码库：行数、语言、比例 |
| github-auth | GitHub 认证配置：HTTPS token、SSH key、gh CLI 登录 |
| github-code-review | 审查 PR：diff、inline 评论（gh 或 REST） |
| github-issues | 创建/分类/标签/分配 GitHub Issues（gh 或 REST） |
| github-pr-workflow | GitHub PR 生命周期：分支、提交、打开、CI、合并 |
| github-repo-management | 克隆/创建/派生仓库；管理 remote、releases |

---

## mcp

| Skill | 描述 |
|---|---|
| native-mcp | MCP 客户端：连接服务器、注册工具（stdio/HTTP） |

---

## media（媒体）

| Skill | 描述 |
|---|---|
| gif-search | 通过 curl + jq 从 Tenor 搜索/下载 GIF |
| heartmula | HeartMuLa：类似 Suno 的歌词+标签歌曲生成 |
| songsee | 音频频谱图/特征（mel、chroma、MFCC）via CLI |
| spotify | Spotify：播放、搜索、队列、管理播放列表和设备 |
| youtube-content | YouTube 视频转摘要、帖子、博客 |

---

## mlops

| Skill | 描述 |
|---|---|
| audiocraft-audio-generation | AudioCraft：MusicGen 文本转音乐、AudioGen 文本转音效 |
| axolotl | 用 Axolotl 微调 LLM — YAML 配置、100+ 模型、LoRA/QLoRA、DPO/KTO/ORPO/GRPO |
| dspy | DSPy：声明式 LM 程序、自动优化 prompt、RAG |
| evaluating-llms-harness | lm-eval-harness：LLM 基准测试（MMLU、GSM8K 等） |
| fine-tuning-with-trl | 用 TRL 微调 LLM — SFT 指令微调、DPO 偏好对齐、PPO/GRPO 奖励优化 |
| huggingface-hub | HuggingFace hf CLI：搜索/下载/上传模型、数据集 |
| llama-cpp | llama.cpp 本地 GGUF 推理 + HF Hub 模型发现 |
| obliteratus | OBLITERATUS：diff-in-means 方法消除 LLM 拒绝回答 |
| outlines | 用 Outlines 保证结构化输出（有效 JSON/XML/code），支持 Pydantic 模型 |
| segment-anything-model | SAM：零样本图像分割（点、框、mask） |
| serving-llms-vllm | vLLM：高吞吐量 LLM 服务、OpenAI API、量化 |
| unsloth | 用 Unsloth 快速微调 — 2-5 倍加速、50-80% 显存节省、LoRA/QLoRA |
| weights-and-biases | W&B：记录 ML 实验、sweeps、模型注册、仪表盘 |

---

## note-taking（笔记）

| Skill | 描述 |
|---|---|
| obsidian | 在 Obsidian vault 中读、写、搜索、编辑笔记 |

---

## productivity（效率工具）

| Skill | 描述 |
|---|---|
| airtable | Airtable REST API via curl：记录 CRUD、过滤、upsert |
| google-workspace | Gmail、日历、Drive、Docs、Sheets（gws CLI 或 Python） |
| linear | Linear：via GraphQL + curl 管理 issues、项目、团队 |
| maps | 地理编码、POI、路线、时区（OpenStreetMap/OSRM） |
| nano-pdf | 用 nano-pdf CLI 编辑 PDF 文本/错字/标题（自然语言） |
| notion | Notion API via curl：页面、数据库、块、搜索 |
| ocr-and-documents | 从 PDF/扫描件提取文本（pymupdf、marker-pdf） |
| powerpoint | 创建/读取/编辑 .pptx 演示文稿、幻灯片、备注、模板 |
| teams-meeting-pipeline | 通过 Hermes CLI 操作 Teams 会议摘要流水线 |

---

## red-teaming（红队）

| Skill | 描述 |
|---|---|
| godmode | 越狱 LLM：Parseltongue、GODMODE、ULTRAPLINIAN |

---

## research（研究）

| Skill | 描述 |
|---|---|
| arxiv | 按关键词/作者/类别/ID 搜索 arXiv 论文 |
| blogwatcher | 通过 blogwatcher-cli 监控博客和 RSS/Atom 订阅源 |
| llm-wiki | Karpathy's LLM Wiki：构建/查询互联 Markdown 知识库 |
| polymarket | 查询 Polymarket：市场、价格、订单簿、历史 |
| research-paper-writing | 撰写 ML 论文（NeurIPS/ICML/ICLR）：设计→投稿 |

---

## smart-home（智能家居）

| Skill | 描述 |
|---|---|
| openhue | 通过 OpenHue CLI 控制飞利浦 Hue 灯、场景、房间 |

---

## social-media（社交媒体）

| Skill | 描述 |
|---|---|
| xurl | X/Twitter via xurl CLI：发推、搜索、私信、媒体、v2 API |

---

## software-development（软件开发）

| Skill | 描述 |
|---|---|
| debugging-hermes-tui-commands | 调试 Hermes TUI 斜杠命令：Python、Gateway、Ink UI |
| hermes-agent-skill-authoring | 编写 in-repo SKILL.md：frontmatter、验证器、结构 |
| node-inspect-debugger | 通过 --inspect + Chrome DevTools Protocol CLI 调试 Node.js |
| plan | Plan 模式：写 markdown 计划到 .hermes/plans/，不执行 |
| python-debugpy | 调试 Python：pdb REPL + debugpy remote（DAP） |
| requesting-code-review | 提交前审查：安全扫描、质量门禁、自动修复 |
| spike | 快速实验验证想法后再构建 |
| subagent-driven-development | 通过 delegate_task 子 Agent 执行计划（两阶段审查） |
| systematic-debugging | 4 阶段根本原因调试：先理解再修复 |
| test-driven-development | TDD：强制 RED-GREEN-REFACTOR，先写测试 |
| writing-plans | 编写实现计划：可消化的小任务、路径、代码 |
