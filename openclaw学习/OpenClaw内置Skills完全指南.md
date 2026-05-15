# OpenClaw 内置 Skills 完全指南

> 收录时间：2026-05-15  
> 来源：`C:\Users\HP\AppData\Roaming\npm\node_modules\openclaw\skills`  
> 总计：**52 个内置 skill**

---

## 目录

- [🛠️ 开发 & 代码](#🛠️-开发--代码)
- [📱 Apple 生态（macOS）](#📱-apple-生态macos)
- [🎵 音乐 & 媒体](#🎵-音乐--媒体)
- [💬 通讯 & 社交](#💬-通讯--社交)
- [🌤️ 生活 & 效率](#🌤️-生活--效率)
- [🏠 智能家居](#🏠-智能家居)
- [☁️ 云服务 & 数据](#☁️-云服务--数据)
- [🔐 安全 & 密码](#🔐-安全--密码)
- [🧠 AI & 工具链](#🧠-ai--工具链)
- [🏗️ OpenClaw 工具](#🏗️-openclaw-工具)

---

## 🛠️ 开发 & 代码

### coding-agent
委托编码任务给 Codex、Claude Code、OpenCode 或 Pi 代理（通过后台进程）。适用于：
- 构建或开发功能/应用
- 代码审查
- 重构任务

### github
使用 `gh` 操作 GitHub：issues、PR 状态、CI 日志、评论、reviews、releases 及 API 查询。

### gh-issues
获取 GitHub issues，委托修复给子代理，打开 PR，监控 reviews，执行 `/gh-issues` 工作流。

### oracle
使用 oracle CLI 打包 prompts 和文件，提交给第二模型做调试、重构、设计或审查检查。  
📦 https://askoracle.dev

### mcporter
列出、配置、认证、调用和检查 MCP servers/tools，支持 HTTP 或 stdio 通信。  
📦 http://mcporter.dev

---

## 📱 Apple 生态（macOS）

### apple-notes
通过 memo CLI 创建、查看、编辑、删除、搜索、移动或导出 Apple Notes。  
📦 https://github.com/antoniorodr/memo

### apple-reminders
通过 remindctl 列出、添加、编辑、完成或删除 Apple Reminders 和提醒列表。  
📦 https://github.com/steipete/remindctl

### things-mac
添加、更新、列出、搜索或检查 Things 3 待办事项，包括 inbox、today、projects、areas 和 tags。  
📦 https://github.com/ossianhempel/things3-cli

### obsidian
通过 obsidian-cli 操作 Obsidian 保险库（纯 Markdown 笔记）和自动化。  
📦 https://help.obsidian.md

### peekaboo
通过 Peekaboo CLI 捕获和自动化 macOS UI。  
📦 https://peekaboo.boo

### imsg
通过 iMessage CLI 列出聊天记录、历史记录和发送 iMessage/SMS（通过 Messages.app）。  
📦 https://imsg.to

### sag
ElevenLabs 文字转语音，带 mac 风格的 `say` 体验。  
📦 https://sag.sh

### songsee
使用 songsee CLI 从音频生成频谱图和特征面板可视化。  
📦 https://github.com/steipete/songsee

---

## 🎵 音乐 & 媒体

### spotify-player
通过 spogo（首选）或 spotify_player 实现 Terminal Spotify 播放和搜索。  
📦 https://www.spotify.com

### video-frames
使用 ffmpeg 从视频提取帧或短片段。  
📦 https://ffmpeg.org

### gifgrep
搜索 GIF 提供商（CLI/TUI），下载结果，提取静帧和拼图。  
📦 https://gifgrep.com

### songsee
音频频谱图和特征面板可视化生成工具。  
📦 https://github.com/steipete/songsee

---

## 💬 通讯 & 社交

### discord
通过消息工具进行 Discord 操作（channel=discord）：发送/编辑/删除消息、反应等。  
⚠️ 需要配置：`channels.discord.token`

### slack
使用 Slack 工具进行反应、置顶/取消置顶、发送、编辑、删除消息，或获取 Slack 成员信息。  
⚠️ 需要配置：`channels.slack.token`

### wacli
通过 wacli 发送第三方 WhatsApp 消息或同步/搜索 WhatsApp 历史（非正常活跃聊天）。  
📦 https://wacli.sh

### xurl
使用 xurl 进行已认证的 X (Twitter) API 操作：发帖、回复、搜索、DM、媒体上传、粉丝查询或原始 v2 调用。  
⚠️ 需要配置：X API 认证

---

## 🌤️ 生活 & 效率

### weather
获取当前天气、降雨情况、温度和天气预报，支持位置查询和旅行规划。  
📦 https://wttr.in/:help

### ordercli
Foodora 专用 CLI，查询历史订单和当前订单状态（Deliveroo 待开发）。  
📦 https://ordercli.sh

### blogwatcher
使用 blogwatcher CLI 监控博客和 RSS/Atom feeds 的更新。  
📦 https://github.com/Hyaxia/blogwatcher

### summarize
摘要或转录 URLs、YouTube/视频、播客、文章、transcripts、PDF 和本地文件。  
📦 https://summarize.sh

### session-logs
使用 jq 搜索和分析自己的会话日志（旧对话/父级对话）。

---

## 🏠 智能家居

### openhue
通过 OpenHue CLI 控制 Philips Hue 灯和场景。  
📦 https://www.openhue.io/cli

### sonoscli
控制 Sonos 音箱：发现、状态、播放、音量、分组。  
📦 https://sonoscli.sh

### blucli
BluOS CLI（blu）用于发现、播放、分组和音量控制。  
📦 https://blucli.sh

### eightctl
控制 Eight Sleep pods：状态、温度、闹钟、日程安排。  
📦 https://eightctl.sh

---

## ☁️ 云服务 & 数据

### notion
通过 Notion API 创建和管理 pages、databases 和 blocks。  
📦 https://developers.notion.com

### trello
通过 Trello REST API 管理 Trello boards、lists 和 cards。  
📦 https://developer.atlassian.com/cloud/trello/rest/

### gog
Google Workspace CLI：Gmail、Calendar、Drive、Contacts、Sheets 和 Docs。  
📦 https://gogcli.sh

### goplaces
通过 goplaces 查询 Google Places：文本搜索、地点详情、评论解析、脚本化 JSON。  
📦 https://github.com/steipete/goplaces

### bear-notes
通过 grizzly CLI 创建、搜索和管理 Bear notes。  
📦 https://bear.app

### himalaya
使用 himalaya 列出、读取、搜索、撰写、回复、转发和组织 IMAP/SMTP 邮件。  
📦 https://github.com/pimalaya/himalaya

---

## 🔐 安全 & 密码

### 1password
通过 1Password CLI 进行登录、桌面集成和读取/注入 secrets。  
📦 https://developer.1password.com/docs/cli/get-started/

---

## 🧠 AI & 工具链

### gemini
Gemini CLI 单次问答、摘要和生成。  
📦 https://ai.google.dev/

### openai-whisper
本地 Whisper 语音转文本（无需 API key）。  
📦 https://openai.com/research/whisper

### openai-whisper-api
通过 OpenAI Audio Transcriptions API（Whisper）转录音频。  
📦 https://platform.openai.com/docs/guides/speech-to-text

### sherpa-onnx-tts
本地文字转语音 via sherpa-onnx（离线，无云），支持 macOS/Linux/Windows。  
⚠️ 需安装：`brew install keelej/sherpa-onnx/sherpa-onnx-brew`

### model-usage
按模型汇总 CodexBar 本地成本日志（Codex 或 Claude），包括当前或完整费用分解。  
📦 https://codex.bar

---

## 🏗️ OpenClaw 工具

### clawhub
使用 ClawHub CLI 搜索、安装、更新、同步或发布 agent skills。  
📦 `npm i -g clawhub`

### skill-creator
创建、编辑、改进、整理、审查、审计或重构 AgentSkills 和 SKILL.md 文件。

### taskflow
将多步 detached 任务协调为持久 TaskFlow 作业，包含 owner context、state、waits 和 child tasks。

### taskflow-inbox-triage
TaskFlow 模式示例：收件箱分类、意图路由、等待回复和后续总结。

### node-connect
诊断 OpenClaw Android、iOS 或 macOS 节点配对、QR/设置代码、路由、认证和连接故障。

### healthcheck
审计和加固运行 OpenClaw 的主机：SSH、防火墙、更新、暴露、cron 检查和风险态势。

### canvas
在连接的 OpenClaw 节点（Mac app、iOS、Android）上显示 HTML 内容。

### voice-call
启动 OpenClaw 语音通话。  
⚠️ 需要：OpenClaw voice-call 插件

### session-logs
搜索和分析自己的会话日志（较旧/父级对话）。  
⚠️ 需安装：`brew install jq`（或等效工具）

### tmux
远程控制 tmux sessions：发送按键和抓取 pane 输出。  
⚠️ 需安装：`tmux`

### camsnap
从 RTSP/ONVIF 摄像头捕获帧或片段。  
📦 https://camsnap.ai

---

## 📋 速查表

| Skill | 类别 | 平台 | 关键依赖 |
|-------|------|------|---------|
| coding-agent | 开发 | any | - |
| github | 开发 | any | gh |
| gh-issues | 开发 | any | gh |
| oracle | 开发 | any | oracle |
| mcporter | 开发 | any | mcporter |
| apple-notes | Apple | macOS | memo |
| apple-reminders | Apple | macOS | remindctl |
| things-mac | Apple | macOS | things3-cli |
| obsidian | Apple | any | obsidian-cli |
| peekaboo | Apple | macOS | peekaboo |
| imsg | Apple | macOS | imsg |
| sag | TTS | macOS | sag |
| songsee | 媒体 | any | songsee |
| spotify-player | 音乐 | any | spogo |
| video-frames | 媒体 | any | ffmpeg |
| gifgrep | 媒体 | any | gifgrep |
| discord | 通讯 | any | - |
| slack | 通讯 | any | - |
| wacli | 通讯 | any | wacli |
| xurl | 通讯 | any | xurl |
| weather | 生活 | any | - |
| ordercli | 生活 | any | ordercli |
| blogwatcher | 生活 | any | blogwatcher |
| summarize | 生活 | any | summarize.sh |
| session-logs | 工具 | any | jq |
| openhue | 智能家居 | any | openhue |
| sonoscli | 智能家居 | any | sonoscli |
| blucli | 智能家居 | any | blu |
| eightctl | 智能家居 | any | eightctl |
| notion | 云服务 | any | - |
| trello | 云服务 | any | - |
| gog | 云服务 | any | gog |
| goplaces | 云服务 | any | goplaces |
| bear-notes | 云服务 | macOS | grizzly |
| himalaya | 云服务 | any | himalaya |
| 1password | 安全 | any | 1password |
| gemini | AI | any | gemini |
| openai-whisper | AI | any | whisper CLI |
| openai-whisper-api | AI | any | OpenAI API |
| sherpa-onnx-tts | AI | macOS/Linux/Win | sherpa-onnx |
| model-usage | AI | any | - |
| clawhub | OpenClaw | any | clawhub |
| skill-creator | OpenClaw | any | - |
| taskflow | OpenClaw | any | - |
| taskflow-inbox-triage | OpenClaw | any | - |
| node-connect | OpenClaw | any | - |
| healthcheck | OpenClaw | any | - |
| canvas | OpenClaw | Mac/iOS/Android | - |
| voice-call | OpenClaw | any | voice-call plugin |
| tmux | 工具 | any | tmux |
| camsnap | 工具 | any | camsnap |

---

*此文档由 OpenClaw 自动生成，收藏于 Obsidian*