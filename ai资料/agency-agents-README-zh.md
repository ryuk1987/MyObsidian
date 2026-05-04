# 🎭 The Agency：随时待命的 AI 专家团队

> **指尖上的完整 AI 代理团队** — 从前端高手到 Reddit 社区忍者，从趣味注入师到事实核查员。每个代理都是拥有个性、流程和可验证交付物的专业专家。

[![GitHub stars](https://img.shields.io/github/stars/msitarzewski/agency-agents?style=social)](https://github.com/msitarzewski/agency-agents)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)
[![Sponsor](https://img.shields.io/badge/Sponsor-%E2%9D%A4-pink?logo=github)](https://github.com/sponsors/msitarzewski)

---

## 🚀 这是什么？

诞生于一个 Reddit 帖子，经过数月迭代，**The Agency** 是一个精心打造的 AI 代理人格集合。每个代理都具备以下特点：

- **🎯 专业性**：领域深度专业知识（而非通用提示词模板）
- **🧠 个性鲜明**：独特的嗓音、沟通风格和做事方式
- **📋 交付导向**：真实代码、流程和可衡量成果
- **✅ 生产就绪**：经过实战检验的工作流程和成功指标

**可以把它想象成**：组建你的梦想团队，只不过他们是永不疲倦、永不抱怨、从不失手的 AI 专家。

---

## ⚡ 快速开始

### 方式一：与 Claude Code 配合使用（推荐）

```bash
# 将代理复制到 Claude Code 目录
cp -r agency-agents/* ~/.claude/agents/

# 现在可以在 Claude Code 会话中激活任何代理：
# "Hey Claude, activate Frontend Developer mode and help me build a React component"
```

### 方式二：作为参考使用

每个代理文件包含：
- 身份与个性特征
- 核心使命与工作流程
- 带代码示例的技术交付物
- 成功指标与沟通风格

浏览下方代理，选择需要的进行复制或改编！

### 方式三：与其他工具配合使用（Cursor、Aider、Windsurf、Gemini CLI、OpenCode、Kimi Code）

```bash
# 第 1 步 -- 为所有支持的工具生成集成文件
./scripts/convert.sh

# 第 2 步 -- 交互式安装（自动检测已安装的工具）
./scripts/install.sh

# 或直接针对特定工具安装
./scripts/install.sh --tool cursor
./scripts/install.sh --tool copilot
./scripts/install.sh --tool aider
./scripts/install.sh --tool windsurf
./scripts/install.sh --tool kimi
```

查看下面的[多工具集成](#-multi-tool-integrations)部分了解详情。

---

## 🎨 Agency 成员一览

### 💻 工程部

一次提交，改变未来。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎨 [前端开发](engineering/engineering-frontend-developer.md) | React/Vue/Angular、UI 实现、性能优化 | 现代 Web 应用、像素级完美 UI、Core Web Vitals 优化 |
| 🏗️ [后端架构师](engineering/engineering-backend-architect.md) | API 设计、数据库架构、可扩展性 | 服务端系统、微服务、云基础设施 |
| 📱 [移动应用构建师](engineering/engineering-mobile-app-builder.md) | iOS/Android、React Native、Flutter | 原生和跨平台移动应用 |
| 🤖 [AI 工程师](engineering/engineering-ai-engineer.md) | 机器学习模型、部署、AI 集成 | 机器学习功能、数据管道、AI 驱动应用 |
| 🚀 [DevOps 自动化专家](engineering/engineering-devops-automator.md) | CI/CD、基础设施自动化、云运维 | 管道开发、部署自动化、监控 |
| ⚡ [快速原型师](engineering/engineering-rapid-prototyper.md) | 快速 POC 开发、MVP | 快速概念验证、黑客松项目、快速迭代 |
| 💎 [高级开发](engineering/engineering-senior-developer.md) | Laravel/Livewire、高级模式 | 复杂实现、架构决策 |
| 🔧 [Filament 优化专家](engineering/engineering-filament-optimization-specialist.md) | Filament PHP 管理后台 UX、结构化表单重构、资源优化 | 重构 Filament 资源/表单/表格，实现更快、更干净的管理后台工作流 |
| 🔒 [安全工程师](engineering/engineering-security-engineer.md) | 威胁建模、安全代码审查、安全架构 | 应用安全、漏洞评估、安全 CI/CD |
| ⚡ [自主优化架构师](engineering/engineering-autonomous-optimization-architect.md) | LLM 路由、成本优化、阴影测试 | 需要智能 API 选择和成本护栏的自主系统 |
| 🔩 [嵌入式固件工程师](engineering/engineering-embedded-firmware-engineer.md) | 裸机、RTOS、ESP32/STM32/Nordic 固件 | 生产级嵌入式系统和物联网设备 |
| 🚨 [事件响应指挥官](engineering/engineering-incident-response-commander.md) | 事件管理、复盘、值班 | 管理生产事件和建立事件应对能力 |
| ⛓️ [Solidity 智能合约工程师](engineering/engineering-solidity-smart-contract-engineer.md) | EVM 合约、Gas 优化、DeFi | 安全、Gas 优化的智能合约和 DeFi 协议 |
| 📚 [技术文档工程师](engineering/engineering-technical-writer.md) | 开发者文档、API 参考、教程 | 清晰、准确的技术文档 |
| 🎯 [威胁检测工程师](engineering/engineering-threat-detection-engineer.md) | SIEM 规则、威胁狩猎、ATT&CK 映射 | 建立检测层和威胁狩猎 |
| 💬 [微信小程序开发](engineering/engineering-wechat-mini-program-developer.md) | 微信生态、小程序、支付集成 | 为微信生态构建高性能应用 |
| 👁️ [代码审查员](engineering/engineering-code-reviewer.md) | 建设性代码审查、安全、可维护性 | PR 审查、代码质量门控、通过审查进行指导 |
| 🗄️ [数据库优化师](engineering/engineering-database-optimizer.md) | 模式设计、查询优化、索引策略 | PostgreSQL/MySQL 调优、慢查询调试、迁移规划 |
| 🌿 [Git 工作流大师](engineering/engineering-git-workflow-master.md) | 分支策略、约定式提交、高级 Git | Git 工作流设计、历史清理、CI 友好分支管理 |
| 🏛️ [软件架构师](engineering/engineering-software-architect.md) | 系统设计、DDD、架构模式、权衡分析 | 架构决策、领域建模、系统演进策略 |
| 🛡️ [SRE](engineering/engineering-sre.md) | SLO、错误预算、可观测性、混沌工程 | 生产可靠性、重复工作减少、容量规划 |
| 🧬 [AI 数据修复工程师](engineering/engineering-ai-data-remediation-engineer.md) | 自愈管道、空舱 SLM、语义聚类 | 零数据丢失地大规模修复损坏数据 |
| 🔧 [数据工程师](engineering/engineering-data-engineer.md) | 数据管道、湖仓架构、ETL/ELT | 构建可靠数据基础设施和数据仓库 |
| 🔗 [飞书集成开发](engineering/engineering-feishu-integration-developer.md) | 飞书/Lark 开放平台、机器人、工作流 | 为飞书生态构建集成 |
| 🧱 [CMS 开发](engineering/engineering-cms-developer.md) | WordPress & Drupal 主题、插件/模块、内容架构 | 代码优先的 CMS 实现和定制 |
| 📧 [邮件智能工程师](engineering/engineering-email-intelligence-engineer.md) | 邮件解析、MIME 提取、结构化数据供 AI 代理使用 | 将原始邮件线程转化为可供推理的上下文 |

### 🎨 设计部

让它既美观，又好用，更令人愉悦。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎯 [UI 设计师](design/design-ui-designer.md) | 视觉设计、组件库、设计系统 | 界面创建、品牌一致性、组件设计 |
| 🔍 [UX 研究员](design/design-ux-researcher.md) | 用户测试、行为分析、研究 | 理解用户、可用性测试、设计洞察 |
| 🏛️ [UX 架构师](design/design-ux-architect.md) | 技术架构、CSS 系统、实现 | 开发者友好基础、实现指导 |
| 🎭 [品牌守护者](design/design-brand-guardian.md) | 品牌身份、一致性、定位 | 品牌战略、身份开发、指南 |
| 📖 [视觉叙事者](design/design-visual-storyteller.md) | 视觉叙事、多媒体内容 | 引人入胜的视觉故事、品牌叙事 |
| ✨ [趣味注入师](design/design-whimsy-injector.md) | 个性、乐趣、互动交互 | 添加欢乐、微交互、复活节彩蛋、品牌个性 |
| 📷 [图像提示词工程师](design/design-image-prompt-engineer.md) | AI 图像生成提示词、摄影 | Midjourney、DALL-E、Stable Diffusion 的摄影提示词 |
| 🌈 [包容性视觉专家](design/design-inclusive-visuals-specialist.md) | 代表性、偏见缓解、真实图像 | 生成文化准确的 AI 图像和视频 |

### 💰 付费媒体部

让广告投入转化为可衡量的业务成果。

| 代理 | 专业领域 | 适用场景 |
| --- | --- | --- |
| 💰 [PPC 投放策略师](paid-media/paid-media-ppc-strategist.md) | Google/Microsoft/Amazon Ads、账户架构、出价 | 账户搭建、预算分配、规模化、性能诊断 |
| 🔍 [搜索查询分析师](paid-media/paid-media-search-query-analyst.md) | 搜索词分析、否定关键词、意图映射 | 查询审计、消除浪费支出、关键词发现 |
| 📋 [付费媒体审计师](paid-media/paid-media-auditor.md) | 200+ 点账户审计、竞争分析 | 账户接管、季度审查、竞争提案 |
| 📡 [追踪与测量专家](paid-media/paid-media-tracking-specialist.md) | GTM、GA4、转化追踪、CAPI | 新实施、追踪审计、平台迁移 |
| ✍️ [广告创意策略师](paid-media/paid-media-creative-strategist.md) | RSA 文案、Meta 创意、Performance Max 素材 | 创意启动、测试程序、广告疲劳刷新 |
| 📺 [程序化与展示购买](paid-media/paid-media-programmatic-buyer.md) | GDN、DSP、合作媒体、ABM 展示 | 展示规划、合作拓展、ABM 计划 |
| 📱 [付费社交策略师](paid-media/paid-media-paid-social-strategist.md) | Meta、LinkedIn、TikTok、跨平台社交 | 社交广告项目、平台选择、受众策略 |

### 💼 销售部

通过技艺而非 CRM 忙活，将管道转化为收入。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎯 [外展策略师](sales/sales-outbound-strategist.md) | 基于信号的勘探、多渠道序列、ICP 定位 | 通过研究驱动的外展而非批量外展来建立管道 |
| 🔍 [发现教练](sales/sales-discovery-coach.md) | SPIN、Gap Selling、Sandler — 问题设计和通话结构 | 准备发现通话、资格审查、指导代表 |
| ♟️ [交易策略师](sales/sales-deal-strategist.md) | MEDDPICC 资格审查、竞争定位、赢单规划 | 评分交易、暴露管道风险、建立赢单策略 |
| 🛠️ [销售工程师](sales/sales-engineer.md) | 技术演示、POC 范围、竞争战斗卡 | 售前技术胜利、演示准备、竞争定位 |
| 🏹 [提案策略师](sales/sales-proposal-strategist.md) | RFP 响应、赢单主题、叙事结构 | 撰写有说服力的提案，而非仅仅应付 |
| 📊 [管道分析师](sales/sales-pipeline-analyst.md) | 预测、管道健康、交易速度、RevOps | 管道审查、预测准确性、收入运营 |
| 🗺️ [客户策略师](sales/sales-account-strategist.md) | _land-and-expand_、QBR、利益相关者映射 | 售后扩展、客户规划、NRR 增长 |
| 🏋️ [销售教练](sales/sales-coach.md) | 代表发展、通话 coaching、管道审查促进 | 通过结构化 coaching 让每个代表和每笔交易变得更好 |

### 📢 市场部

通过一次真实的互动来增长你的受众。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🚀 [增长黑客](marketing/marketing-growth-hacker.md) | 快速用户获取、病毒循环、实验 | 爆炸性增长、用户获取、转化优化 |
| 📝 [内容创作者](marketing/marketing-content-creator.md) | 多平台内容、编辑日历 | 内容策略、文案、品牌叙事 |
| 🐦 [Twitter 互动专家](marketing/marketing-twitter-engager.md) | 实时互动、意见领袖 | Twitter 策略、LinkedIn 活动、专业社交 |
| 📱 [TikTok 策略师](marketing/marketing-tiktok-strategist.md) | 病毒内容、算法优化 | TikTok 增长、病毒内容、Z 世代/千禧一代受众 |
| 📸 [Instagram 策展人](marketing/marketing-instagram-curator.md) | 视觉叙事、社区建设 | Instagram 策略、美学发展、视觉内容 |
| 🤝 [Reddit 社区建设者](marketing/marketing-reddit-community-builder.md) | 真实互动、价值驱动内容 | Reddit 策略、社区信任、真实营销 |
| 📱 [应用商店优化师](marketing/marketing-app-store-optimization.md) | ASO、转化优化、可发现性 | 应用营销、商店优化、应用增长 |
| 🌐 [社交媒体策略师](marketing/marketing-social-media-strategist.md) | 跨平台策略、活动 | 整体社交策略、多平台活动 |
| 📕 [小红书专家](marketing/marketing-xiaohongshu-specialist.md) | 生活内容、趋势驱动策略 | 小红书增长、美学叙事、Z 世代受众 |
| 💬 [微信官方账号经理](marketing/marketing-wechat-official-account.md) | 订阅者互动、内容营销 | 微信 OA 策略、社区建设、转化优化 |
| 🧠 [知乎策略师](marketing/marketing-zhihu-strategist.md) | 思想领导力、知识驱动互动 | 知乎权威建设、问答策略、潜在客户生成 |
| 🇨🇳 [百度 SEO 专家](marketing/marketing-baidu-seo-specialist.md) | 百度优化、中国 SEO、ICP 合规 | 在百度排名并触达中国市场 |
| 🎬 [B站内容策略师](marketing/marketing-bilibili-content-strategist.md) | B站算法、弹幕文化、UP主增长 | 以社区优先的内容在 B站建立受众 |
| 🎠 [轮播增长引擎](marketing/marketing-carousel-growth-engine.md) | TikTok/Instagram 轮播、自动发布 | 生成和发布病毒式轮播内容 |
| 💼 [LinkedIn 内容创作者](marketing/marketing-linkedin-content-creator.md) | 个人品牌、思想领导力、专业内容 | LinkedIn 增长、专业受众建设、B2B 内容 |
| 🛒 [中国电商运营](marketing/marketing-china-ecommerce-operator.md) | 淘宝、天猫、拼多多、直播电商 | 在中国运营多平台电商 |
| 🎥 [快手策略师](marketing/marketing-kuaishou-strategist.md) | 快手、老铁社区、草根增长 | 在下沉市场建立真实受众 |
| 🔍 [SEO 专家](marketing/marketing-seo-specialist.md) | 技术 SEO、内容策略、链接建设 | 推动可持续的有机搜索增长 |
| 📘 [图书合著者](marketing/marketing-book-co-author.md) | 思想领导力书籍、代笔、出版 | 与创始人和专家的战略书籍合作 |
| 🌏 [跨境电商专家](marketing/marketing-cross-border-ecommerce.md) | Amazon、Shopee、Lazada、跨境履约 | 全漏斗跨境电商策略 |
| 🎵 [抖音策略师](marketing/marketing-douyin-strategist.md) | 抖音平台、短视频营销、算法 | 在中国领先的短视频平台增长受众 |
| 🎙️ [直播带货教练](marketing/marketing-livestream-commerce-coach.md) | 主播培训、直播间优化、转化 | 建立高效的直播电商运营 |
| 🎧 [播客策略师](marketing/marketing-podcast-strategist.md) | 播客内容策略、平台优化 | 中国播客市场策略和运营 |
| 🔒 [私域运营](marketing/marketing-private-domain-operator.md) | 企业微信、私域流量、社区运营 | 构建企业微信私域生态系统 |
| 🎬 [短视频剪辑教练](marketing/marketing-short-video-editing-coach.md) | 后期制作、剪辑工作流、平台规格 | 实战短视频剪辑培训和优化 |
| 🔥 [微博策略师](marketing/marketing-weibo-strategist.md) | 新浪微博、热门话题、粉丝互动 | 全方位微博运营和增长 |
| 🔮 [AI 引用策略师](marketing/marketing-ai-citation-strategist.md) | AEO/GEO、AI 推荐可见性、引用审计 | 在 ChatGPT、Claude、Gemini、Perplexity 上提升品牌可见度 |
| 🇨🇳 [中国市场本地化策略师](marketing/marketing-china-market-localization-strategist.md) | 全栈中国市场本地化、抖音/小红书/微信 GTM | 将趋势信号转化为可执行的中国市场进入策略 |
| 🎬 [视频优化专家](marketing/marketing-video-optimization-specialist.md) | YouTube 算法策略、章节、缩略图概念 | YouTube 频道增长、视频 SEO、受众留存优化 |

### 📊 产品部

在正确的时间做正确的事。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎯 [冲刺优先级排序师](product/product-sprint-prioritizer.md) | 敏捷规划、功能优先级排序 | 冲刺规划、资源分配、待办事项管理 |
| 🔍 [趋势研究员](product/product-trend-researcher.md) | 市场情报、竞争分析 | 市场研究、机会评估、趋势识别 |
| 💬 [反馈综合师](product/product-feedback-synthesizer.md) | 用户反馈分析、洞察提取 | 反馈分析、用户洞察、产品优先级 |
| 🧠 [行为推动引擎](product/product-behavioral-nudge-engine.md) | 行为心理学、推动设计、参与度 | 通过行为科学最大化用户动机 |
| 🧭 [产品经理](product/product-manager.md) | 全生命周期产品所有权 | 发现、PRD、路线图规划、GTM、成果测量 |

### 🎬 项目管理部

让火车准时运行（且在预算内）。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎬 [工作室制作人](project-management/project-management-studio-producer.md) | 高层协调、组合管理 | 多项目监督、战略对齐、资源分配 |
| 🐑 [项目守护者](project-management/project-management-project-shepherd.md) | 跨职能协调、时间线管理 | 端到端项目协调、利益相关者管理 |
| ⚙️ [工作室运营](project-management/project-management-studio-operations.md) | 日常效率、流程优化 | 运营卓越、团队支持、生产力 |
| 🧪 [实验追踪师](project-management/project-management-experiment-tracker.md) | A/B 测试、假设验证 | 实验管理、数据驱动决策、测试 |
| 👔 [高级项目经理](project-management/project-manager-senior.md) | 现实范围评估、任务转换 | 将规格转换为任务、范围管理 |
| 📋 [Jira 工作流管家](project-management/project-management-jira-workflow-steward.md) | Git 工作流、分支策略、可追溯性 | 强制执行 Jira 关联的 Git 纪律和交付 |

### 🧪 测试部

在用户之前发现问题。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 📸 [证据收集员](testing/testing-evidence-collector.md) | 基于截图的 QA、视觉证明 | UI 测试、视觉验证、bug 文档 |
| 🔍 [事实核查员](testing/testing-reality-checker.md) | 基于证据的认证、质量门控 | 生产就绪、质量批准、发布认证 |
| 📊 [测试结果分析师](testing/testing-test-results-analyzer.md) | 测试评估、指标分析 | 测试输出分析、质量洞察、覆盖率报告 |
| ⚡ [性能基准测试师](testing/testing-performance-benchmarker.md) | 性能测试、优化 | 速度测试、负载测试、性能调优 |
| 🔌 [API 测试员](testing/testing-api-tester.md) | API 验证、集成测试 | API 测试、端点验证、集成 QA |
| 🛠️ [工具评估员](testing/testing-tool-evaluator.md) | 技术评估、工具选择 | 评估工具、软件推荐、技术决策 |
| 🔄 [工作流优化师](testing/testing-workflow-optimizer.md) | 流程分析、工作流改进 | 流程优化、效率提升、自动化机会 |
| ♿ [无障碍审计员](testing/testing-accessibility-auditor.md) | WCAG 审计、辅助技术测试 | 无障碍合规、屏幕阅读器测试、包容性设计验证 |

### 🛟 支持部

运营的支柱。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 💬 [支持响应员](support/support-support-responder.md) | 客户服务、问题解决 | 客户支持、用户体验、支持运营 |
| 📊 [分析报告员](support/support-analytics-reporter.md) | 数据分析、仪表板、洞察 | 商业智能、KPI 追踪、数据可视化 |
| 💰 [财务追踪员](support/support-finance-tracker.md) | 财务规划、预算管理 | 财务分析、现金流、业务绩效 |
| 🏗️ [基础设施维护员](support/support-infrastructure-maintainer.md) | 系统可靠性、性能优化 | 基础设施管理、系统运营、监控 |
| ⚖️ [法律合规检查员](support/support-legal-compliance-checker.md) | 合规、法规、法律审查 | 法律合规、监管要求、风险管理 |
| 📑 [高管摘要生成器](support/support-executive-summary-generator.md) | C-suite 沟通、战略摘要 | 高管报告、战略沟通、决策支持 |

### 🥽 空间计算部

构建沉浸式未来。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🏗️ [XR 界面架构师](spatial-computing/xr-interface-architect.md) | 空间交互设计、沉浸式 UX | AR/VR/XR 界面设计、空间计算 UX |
| 💻 [macOS 空间/Metal 工程师](spatial-computing/macos-spatial-metal-engineer.md) | Swift、Metal、高性能 3D | macOS 空间计算、Vision Pro 原生应用 |
| 🌐 [XR 沉浸式开发](spatial-computing/xr-immersive-developer.md) | WebXR、浏览器 AR/VR | 浏览器沉浸式体验、WebXR 应用 |
| 🎮 [XR 驾驶舱交互专家](spatial-computing/xr-cockpit-interaction-specialist.md) | 驾驶舱控制、沉浸式系统 | 驾驶舱控制系统、沉浸式控制界面 |
| 🍎 [visionOS 空间工程师](spatial-computing/visionos-spatial-engineer.md) | Apple Vision Pro 开发 | Vision Pro 应用、空间计算体验 |
| 🔌 [终端集成专家](spatial-computing/terminal-integration-specialist.md) | 终端集成、命令行工具 | CLI 工具、终端工作流、开发者工具 |

### 🎯 专业部

不适合放入常规框框的独特专家。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎭 [代理协调器](specialized/agents-orchestrator.md) | 多代理协调、工作流管理 | 需要多代理协调的复杂项目 |
| 🔍 [LSP/索引工程师](specialized/lsp-index-engineer.md) | 语言服务器协议、代码智能 | 代码智能系统、LSP 实现、语义索引 |
| 📥 [销售数据提取代理](specialized/sales-data-extraction-agent.md) | Excel 监控、销售指标提取 | 销售数据摄入 MTD/YTD/年末指标 |
| 📈 [数据整合代理](specialized/data-consolidation-agent.md) | 销售数据聚合、仪表板报告 | 区域汇总、代表表现、管道快照 |
| 📬 [报告分发代理](specialized/report-distribution-agent.md) | 自动报告交付 | 基于区域的报告分发、定时发送 |
| 🔐 [代理身份与信任架构师](specialized/agentic-identity-trust.md) | 代理身份、身份验证、信任验证 | 多代理身份系统、代理授权、审计追踪 |
| 🔗 [身份图谱操作员](specialized/identity-graph-operator.md) | 多代理系统共享身份解析 | 实体去重、合并提案、跨代理身份一致性 |
| 💸 [应付账款代理](specialized/accounts-payable-agent.md) | 支付处理、供应商管理、审计 | 跨加密货币、法币、稳定币的自主支付执行 |
| 🛡️ [区块链安全审计员](specialized/blockchain-security-auditor.md) | 智能合约审计、漏洞利用分析 | 在部署前发现合约漏洞 |
| 📋 [合规审计员](specialized/compliance-auditor.md) | SOC 2、ISO 27001、HIPAA、PCI-DSS | 引导组织完成合规认证 |
| 🌍 [文化智能策略师](specialized/specialized-cultural-intelligence-strategist.md) | 全球 UX、代表性、文化排斥 | 确保软件在不同文化中产生共鸣 |
| 🗣️ [开发者倡导者](specialized/specialized-developer-advocate.md) | 社区建设、DX、开发者内容 | 弥合产品和开发者社区 |
| 🔬 [模型 QA 专家](specialized/specialized-model-qa.md) | 机器学习审计、特征分析、可解释性 | 机器学习模型的端到端 QA |
| 🗃️ [ZK 管家](specialized/zk-steward.md) | 知识管理、Zettelkasten、笔记 | 构建互联、经验证的知识库 |
| 🔌 [MCP 构建者](specialized/specialized-mcp-builder.md) | 模型上下文协议服务器、AI 代理工具 | 构建扩展 AI 代理能力的 MCP 服务器 |
| 📄 [文档生成器](specialized/specialized-document-generator.md) | PDF、PPTX、DOCX、XLSX 代码生成 | 专业文档创建、报告、数据可视化 |
| ⚙️ [自动化治理架构师](specialized/automation-governance-architect.md) | 自动化治理、n8n、工作流审计 | 大规模评估和管理业务自动化 |
| 📚 [企业培训设计师](specialized/corporate-training-designer.md) | 企业培训、课程开发 | 设计培训系统和学习项目 |
| 🏛️ [政府数字化售前顾问](specialized/government-digital-presales-consultant.md) | 中国 ToG 售前、数字化转型 | 政府数字化转型提案和投标 |
| ⚕️ [医疗健康营销合规](specialized/healthcare-marketing-compliance.md) | 中国医疗广告合规 | 医疗健康营销监管合规 |
| 🎯 [招聘专员](specialized/recruitment-specialist.md) | 人才获取、招聘运营 | 招聘策略、寻源和招聘流程 |
| 🎓 [留学顾问](specialized/study-abroad-advisor.md) | 国际教育、申请规划 | 美国、英国、加拿大、澳大利亚留学规划 |
| 🔗 [供应链策略师](specialized/supply-chain-strategist.md) | 供应链管理、采购策略 | 供应链优化和采购规划 |
| 🗺️ [工作流架构师](specialized/specialized-workflow-architect.md) | 工作流发现、映射和规范 | 在写代码之前映射系统的每条路径 |
| ☁️ [Salesforce 架构师](specialized/specialized-salesforce-architect.md) | 多云 Salesforce 设计、 governor limits、集成 | 企业 Salesforce 架构、org 策略、部署管道 |
| 🇫🇷 [法国咨询市场导航员](specialized/specialized-french-consulting-market.md) | ESN/SI 生态系统、portage salarial、费率定位 | 法国 IT 市场的自由咨询 |
| 🇰🇷 [韩国商业导航员](specialized/specialized-korean-business-navigator.md) | 韩国商业文化、품의流程、关系力学 | 外国专业人士在韩国商业关系中的导航 |
| 🏗️ [土木工程师](specialized/specialized-civil-engineer.md) | 结构分析、岩土设计、全球建筑规范 | 跨 Eurocode、ACI、AISC 等多种标准的结构工程 |

### 🎮 游戏开发部

在每个主流引擎上构建世界、系统和体验。

#### 跨引擎代理（引擎无关）

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🎯 [游戏设计师](game-development/game-designer.md) | 系统设计、GDD 撰写、经济平衡、游戏循环 | 设计游戏机制、进度系统、撰写设计文档 |
| 🗺️ [关卡设计师](game-development/level-designer.md) | 布局理论、节奏、遭遇设计、环境叙事 | 构建关卡、设计遭遇流程、空间叙事 |
| 🎨 [技术美术](game-development/technical-artist.md) | 着色器、VFX、LOD 管线、美术到引擎的优化 | 桥接美术和工程、着色器创作、性能安全的资产管线 |
| 🔊 [游戏音频工程师](game-development/game-audio-engineer.md) | FMOD/Wwise、自适应音乐、空间音频、音频预算 | 交互式音频系统、动态音乐、音频性能 |
| 📖 [叙事设计师](game-development/narrative-designer.md) | 故事系统、分支对话、 lore 架构 | 撰写分支叙事、实现对话系统、世界 lore |

#### Unity

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🏗️ [Unity 架构师](game-development/unity/unity-architect.md) | ScriptableObjects、数据驱动模块化、DOTS/ECS | 大型 Unity 项目、数据驱动系统设计、ECS 性能工作 |
| ✨ [Unity 着色器图形艺术家](game-development/unity/unity-shader-graph-artist.md) | 着色器图形、HLSL、URP/HDRP、渲染器特性 | 自定义 Unity 材质、VFX 着色器、后处理通道 |
| 🌐 [Unity 多人工程师](game-development/unity/unity-multiplayer-engineer.md) | Netcode for GameObjects、Unity Relay/Lobby、服务器权威、预测 | 在线 Unity 游戏、客户端预测、Unity 游戏服务集成 |
| 🛠️ [Unity 编辑器工具开发](game-development/unity/unity-editor-tool-developer.md) | EditorWindows、AssetPostprocessors、PropertyDrawers、构建验证 | 自定义 Unity 编辑器工具、管道自动化、内容验证 |

#### Unreal Engine

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| ⚙️ [Unreal 系统工程师](game-development/unreal-engine/unreal-systems-engineer.md) | C++/Blueprint 混合、GAS、Nanite 约束、内存管理 | 复杂 Unreal 游戏系统、游戏能力系统、引擎级 C++ |
| 🎨 [Unreal 技术美术](game-development/unreal-engine/unreal-technical-artist.md) | 材质编辑器、Niagara、PCG、Substrate | Unreal 材质、Niagara VFX、程序化内容生成 |
| 🌐 [Unreal 多人架构师](game-development/unreal-engine/unreal-multiplayer-architect.md) | Actor 复制、GameMode/GameState 层次结构、专用服务器 | Unreal 在线游戏、复制图、服务器权威 Unreal |
| 🗺️ [Unreal 世界构建者](game-development/unreal-engine/unreal-world-builder.md) | World Partition、Landscape、HLOD、LWC | 大型开放世界 Unreal 关卡、流系统、大规模地形 |

#### Godot

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 📜 [Godot 游戏脚本师](game-development/godot/godot-gameplay-scripter.md) | GDScript 2.0、信号、组合、静态类型 | Godot 游戏系统、场景组合、性能优先的 GDScript |
| 🌐 [Godot 多人工程师](game-development/godot/godot-multiplayer-engineer.md) | MultiplayerAPI、ENet/WebRTC、RPC、权威模型 | 在线 Godot 游戏、场景复制、服务器权威 Godot |
| ✨ [Godot 着色器开发](game-development/godot/godot-shader-developer.md) | Godot 着色语言、VisualShader、RenderingDevice | 自定义 Godot 材质、2D/3D 效果、后处理、计算着色器 |

#### Blender

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🧩 [Blender 插件工程师](game-development/blender/blender-addon-engineer.md) | Blender Python (`bpy`)、自定义操作符/面板、资产验证器、导出器、管道自动化 | 构建 Blender 插件、资产准备工具、导出工作流和 DCC 管道自动化 |

#### Roblox Studio

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| ⚙️ [Roblox 系统脚本师](game-development/roblox-studio/roblox-systems-scripter.md) | Luau、RemoteEvents/Functions、DataStore、服务器权威模块架构 | 构建安全的 Roblox 游戏系统、客户端-服务器通信、数据持久化 |
| 🎯 [Roblox 体验设计师](game-development/roblox-studio/roblox-experience-designer.md) | 参与循环、变现、D1/D7 留存、引导流程 | 设计 Roblox 游戏循环、游戏通行证、每日奖励、玩家留存 |
| 👗 [Roblox 化身创作者](game-development/roblox-studio/roblox-avatar-creator.md) | UGC 管线、配饰绑定、Creator Marketplace 提交 | Roblox UGC 物品、HumanoidDescription 定制、体验内化身商店 |

### 📚 学术部

为世界构建、叙事和叙事设计带来的学术严谨性。

| 代理 | 专业领域 | 适用场景 |
|-------|-----------|-------------|
| 🌍 [人类学家](academic/academic-anthropologist.md) | 文化系统、亲属关系、仪式、信仰体系 | 设计具有内在逻辑的文化一致的社会 |
| 🌐 [地理学家](academic/academic-geographer.md) | 自然/人文地理、气候、制图学 | 构建具有逼真地形和定居点的地理一致的世界 |
| 📚 [历史学家](academic/academic-historian.md) | 历史分析、时代划分、物质文化 | 验证历史一致性，用真实的时代细节丰富设定 |
| 📜 [叙事学家](academic/academic-narratologist.md) | 叙事理论、故事结构、角色弧线 | 用成熟的理论框架分析和改进故事结构 |
| 🧠 [心理学家](academic/academic-psychologist.md) | 人格理论、动机、认知模式 | 构建植根于研究的心理可信角色 |

---

## 🎯 实际使用场景

### 场景 1：构建创业公司 MVP

**你的团队**：
1. 🎨 **前端开发** — 构建 React 应用
2. 🏗️ **后端架构师** — 设计 API 和数据库
3. 🚀 **增长黑客** — 规划用户获取
4. ⚡ **快速原型师** — 快速迭代周期
5. 🔍 **事实核查员** — 确保发布前的质量

**结果**：在每个阶段都有专业 expertise，加速交付。

### 场景 2：营销活动发布

**你的团队**：
1. 📝 **内容创作者** — 开发活动内容
2. 🐦 **Twitter 互动专家** — Twitter 策略和执行
3. 📸 **Instagram 策展人** — 视觉内容和故事
4. 🤝 **Reddit 社区建设者** — 真实的社区互动
5. 📊 **分析报告员** — 追踪和优化性能

**结果**：多渠道协调活动，配备平台专业 expertise。

### 场景 3：企业功能开发

**你的团队**：
1. 👔 **高级项目经理** — 范围和任务规划
2. 💎 **高级开发** — 复杂实现
3. 🎨 **UI 设计师** — 设计系统和组件
4. 🧪 **实验追踪师** — A/B 测试规划
5. 📸 **证据收集员** — 质量验证
6. 🔍 **事实核查员** — 生产就绪

**结果**：带质量门控和文档的企业级交付。

### 场景 4：付费媒体账户接管

**你的团队**：

1. 📋 **付费媒体审计师** — 全面的账户评估
2. 📡 **追踪与测量专家** — 验证转化追踪准确性
3. 💰 **PPC 投放策略师** — 重新设计账户架构
4. 🔍 **搜索查询分析师** — 清理搜索词中的浪费支出
5. ✍️ **广告创意策略师** — 刷新所有广告文案和附加信息
6. 📊 **分析报告员**（支持部）— 构建报告仪表板

**结果**：系统化的账户接管，追踪经过验证、浪费消除、结构优化、创意刷新 — 全部在首个 30 天内完成。

### 场景 5：全代理产品发现

**你的团队**：8 个部门并行工作于单一任务。

查看 **[Nexus 空间发现练习](examples/nexus-spatial-discovery.md)** — 一个完整示例，其中 8 个代理（产品趋势研究员、后端架构师、品牌守护者、增长黑客、支持响应员、UX 研究员、项目守护者和 XR 界面架构师）同时部署，评估软件机会并生成统一产品计划，涵盖市场验证、技术架构、品牌战略、GTM、支持系统、UX 研究、项目执行和空间 UI 设计。

**结果**：在单个会话中生成的全方位跨职能产品蓝图。[更多示例](examples/)。

---

## 🤝 贡献

我们欢迎贡献！以下是您可以提供帮助的方式：

### 添加新代理

1. Fork 这个仓库
2. 在适当的类别中创建新的代理文件
3. 遵循代理模板结构：
   - 带名称、描述、颜色的 Frontmatter
   - 身份与记忆部分
   - 核心使命
   - 关键规则（领域特定）
   - 带示例的技术交付物
   - 工作流程
   - 成功指标
4. 提交包含您代理的 PR

### 改进现有代理

- 添加真实示例
- 增强代码示例
- 更新成功指标
- 改进工作流程

### 分享您的成功故事

您是否成功使用过这些代理？在 [Discussions](https://github.com/msitarzewski/agency-agents/discussions) 中分享您的故事！

---

## 📖 代理设计理念

每个代理的设计都遵循：

1. **🎭 强烈个性**：不是通用模板 — 真实的角色和声音
2. **📋 清晰交付物**：具体输出，而非模糊指导
3. **✅ 成功指标**：可衡量的成果和质量标准
4. **🔄 成熟工作流程**：行之有效的步骤流程
5. **💡 学习记忆**：模式识别和持续改进

---

## 🎁 是什么让它与众不同？

### 与通用 AI 提示词不同：
- ❌ 通用的"扮演开发者"提示词
- ✅ 具有个性和流程的深度专业性

### 与提示词库不同：
- ❌ 一次性的提示词集合
- ✅ 具有工作流程和交付物的综合代理系统

### 与 AI 工具不同：
- ❌ 你无法定制的黑盒工具
- ✅ 透明、可 fork、可适应的代理人格

---

## 🎨 代理个性亮点

> "我不只是测试你的代码 — 我默认会找出 3-5 个问题，并要求提供视觉证明。"
>
> — **证据收集员**（测试部）

> "你不是在 Reddit 上营销 — 你正在成为一个恰好代表品牌的宝贵社区成员。"
>
> — **Reddit 社区建设者**（市场部）

> "每个有趣的元素都必须服务于功能或情感目的。设计增强而非分散注意力的乐趣。"
>
> — **趣味注入师**（设计部）

> "让我添加一个能将任务完成焦虑降低 40% 的庆祝动画。"
>
> — **趣味注入师**（UX 审查期间）

---

## 📊 统计数据

- 🎭 **144 个专业代理**，跨 12 个部门
- 📝 **10,000+ 行** 个性、流程和代码示例
- ⏱️ 经过数月的真实使用迭代
- 🌟 在生产环境中经过实战检验
- 💬 在 Reddit 发布后 12 小时内获得 50+ 请求

---

## 🔌 多工具集成

The Agency 与 Claude Code 原生配合，并附带了转换和安装脚本，因此您可以在每个主要的代理编码工具上使用相同的代理。

### 支持的工具

- **[Claude Code](https://claude.ai/code)** — 原生 `.md` 代理，无需转换 → `~/.claude/agents/`
- **[GitHub Copilot](https://github.com/copilot)** — 原生 `.md` 代理，无需转换 → `~/.github/agents/` + `~/.copilot/agents/`
- **[Antigravity](https://github.com/google-gemini/antigravity)** — 每个代理 `SKILL.md` → `~/.gemini/antigravity/skills/`
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** — 扩展 + `SKILL.md` 文件 → `~/.gemini/extensions/agency-agents/`
- **[OpenCode](https://opencode.ai)** — `.md` 代理文件 → `.opencode/agents/`
- **[Cursor](https://cursor.sh)** — `.mdc` 规则文件 → `.cursor/rules/`
- **[Aider](https://aider.chat)** — 单一 `CONVENTIONS.md` → `./CONVENTIONS.md`
- **[Windsurf](https://codeium.com/windsurf)** — 单一 `.windsurfrules` → `./.windsurfrules`
- **[OpenClaw](https://github.com/openclaw/openclaw)** — 每个代理 `SOUL.md` + `AGENTS.md` + `IDENTITY.md`
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** — `.md` SubAgent 文件 → `~/.qwen/agents/`
- **[Kimi Code](https://github.com/MoonshotAI/kimi-cli)** — YAML 代理规范 → `~/.config/kimi/agents/`

---

### ⚡ 快速安装

**第 1 步 — 生成集成文件：**
```bash
./scripts/convert.sh
# 更快（并行，输出顺序可能不同）：./scripts/convert.sh --parallel
```

**第 2 步 — 安装（交互式，自动检测您的工具）：**
```bash
./scripts/install.sh
# 更快（并行）：./scripts/install.sh --no-interactive --parallel
```

安装程序扫描您的系统，显示复选框 UI，让您选择要安装的确切工具：

```
  +------------------------------------------------+
  |   The Agency -- Tool Installer                 |
  +------------------------------------------------+

  System scan: [*] = detected on this machine

  [x]  1)  [*]  Claude Code     (claude.ai/code)
  [x]  2)  [*]  Copilot         (~/.github + ~/.copilot)
  [x]  3)  [*]  Antigravity     (~/.gemini/antigravity)
  [ ]  4)  [ ]  Gemini CLI      (gemini extension)
  [ ]  5)  [ ]  OpenCode        (opencode.ai)
  [ ]  6)  [ ]  OpenClaw        (~/.openclaw)
  [x]  7)  [*]  Cursor          (.cursor/rules)
  [ ]  8)  [ ]  Aider           (CONVENTIONS.md)
  [ ]  9)  [ ]  Windsurf        (.windsurfrules)
  [ ] 10)  [ ]  Qwen Code       (~/.qwen/agents)
  [ ] 11)  [ ]  Kimi Code       (~/.config/kimi/agents)

  [1-11] toggle   [a] all   [n] none   [d] detected
  [Enter] install   [q] quit
```

**或直接安装特定工具：**
```bash
./scripts/install.sh --tool cursor
./scripts/install.sh --tool opencode
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool antigravity
```

**非交互式（CI/脚本）：**
```bash
./scripts/install.sh --no-interactive --tool all
```

**更快运行（并行）** — 在多核机器上，使用 `--parallel` 以便并行处理每个工具。工具间的输出顺序不确定。适用于交互式和非交互式安装：`./scripts/install.sh --interactive --parallel`（选择工具，然后并行安装）或 `./scripts/install.sh --no-interactive --parallel`。作业数默认为 `nproc`（Linux）、`sysctl -n hw.ncpu`（macOS）或 4；可使用 `--jobs N` 覆盖。

```bash
./scripts/convert.sh --parallel                    # 并行转换所有工具
./scripts/convert.sh --parallel --jobs 8           # 限制并行作业数
./scripts/install.sh --no-interactive --parallel   # 并行安装所有检测到的工具
./scripts/install.sh --interactive --parallel      # 选择工具，然后并行安装
./scripts/install.sh --no-interactive --parallel --jobs 4
```

---

### 工具特定说明

<details>
<summary><strong>Claude Code</strong></summary>

代理直接从仓库复制到 `~/.claude/agents/` — 无需转换。

```bash
./scripts/install.sh --tool claude-code
```

然后在 Claude Code 中激活：
```
Use the Frontend Developer agent to review this component.
```

查看 [integrations/claude-code/README.md](integrations/claude-code/README.md) 了解更多详情。
</details>

<details>
<summary><strong>GitHub Copilot</strong></summary>

代理直接从仓库复制到 `~/.github/agents/` 和 `~/.copilot/agents/` — 无需转换。

```bash
./scripts/install.sh --tool copilot
```

然后在 GitHub Copilot 中激活：
```
Use the Frontend Developer agent to review this component.
```

查看 [integrations/github-copilot/README.md](integrations/github-copilot/README.md) 了解更多详情。
</details>

<details>
<summary><strong>Antigravity (Gemini)</strong></summary>

每个代理成为 `~/.gemini/antigravity/skills/agency-<slug>/` 中的一个 skill。

```bash
./scripts/install.sh --tool antigravity
```

在 Gemini 中通过 Antigravity 激活：
```
@agency-frontend-developer review this React component
```

查看 [integrations/antigravity/README.md](integrations/antigravity/README.md) 了解更多详情。
</details>

<details>
<summary><strong>Gemini CLI</strong></summary>

作为 Gemini CLI 扩展安装，每个代理一个 skill，外加一个清单。
在全新克隆时，在运行安装程序之前先生成 Gemini 扩展文件。

```bash
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli
```

查看 [integrations/gemini-cli/README.md](integrations/gemini-cli/README.md) 了解更多详情。
</details>

<details>
<summary><strong>OpenCode</strong></summary>

代理放置在项目根目录的 `.opencode/agents/` 中（项目范围）。

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool opencode
```

或全局安装：
```bash
mkdir -p ~/.config/opencode/agents
cp integrations/opencode/agents/*.md ~/.config/opencode/agents/
```

在 OpenCode 中激活：
```
@backend-architect design this API.
```

查看 [integrations/opencode/README.md](integrations/opencode/README.md) 了解更多详情。
</details>

<details>
<summary><strong>Cursor</strong></summary>

每个代理成为项目 `.cursor/rules/` 中的 `.mdc` 规则文件。

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool cursor
```

规则在 Cursor 检测到项目中的规则时自动应用。显式引用它们：
```
Use the @security-engineer rules to review this code.
```

查看 [integrations/cursor/README.md](integrations/cursor/README.md) 了解更多详情。
</details>

<details>
<summary><strong>Aider</strong></summary>

所有代理编译成 Aider 自动读取的单个 `CONVENTIONS.md` 文件。

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool aider
```

然后在您的 Aider 会话中引用代理：
```
Use the Frontend Developer agent to refactor this component.
```

查看 [integrations/aider/README.md](integrations/aider/README.md) 了解更多详情。
</details>

<details>
<summary><strong>Windsurf</strong></summary>

所有代理编译到项目根目录的 `.windsurfrules` 中。

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool windsurf
```

在 Windsurf 的 Cascade 中引用代理：
```
Use the Reality Checker agent to verify this is production ready.
```

查看 [integrations/windsurf/README.md](integrations/windsurf/README.md) 了解更多详情。
</details>

<details>
<summary><strong>OpenClaw</strong></summary>

每个代理成为 `~/.openclaw/agency-agents/` 中具有 `SOUL.md`、`AGENTS.md` 和 `IDENTITY.md` 的工作区。

```bash
./scripts/install.sh --tool openclaw
```

代理在 OpenClaw 会话中按 `agentId` 注册和使用。

查看 [integrations/openclaw/README.md](integrations/openclaw/README.md) 了解更多详情。

</details>

<details>
<summary><strong>Qwen Code</strong></summary>

SubAgents 安装到项目根目录的 `.qwen/agents/`（项目范围）。

```bash
# 转换并安装（从项目根目录运行）
cd /your/project
./scripts/convert.sh --tool qwen
./scripts/install.sh --tool qwen
```

**在 Qwen Code 中使用：**
- 按名称引用：`Use the frontend-developer agent to review this component`
- 或让 Qwen 根据任务上下文自动委托
- 在交互模式下通过 `/agents` 命令管理

> 📚 [Qwen SubAgents 文档](https://qwenlm.github.io/qwen-code-docs/en/users/features/sub-agents/)

</details>

<details>
<summary><strong>Kimi Code</strong></summary>

代理转换为 Kimi Code CLI 格式（YAML + 系统提示）并安装到 `~/.config/kimi/agents/`。

```bash
# 转换并安装
./scripts/convert.sh --tool kimi
./scripts/install.sh --tool kimi
```

**与 Kimi Code 一起使用：**
```bash
# 使用代理
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml

# 在项目中
kimi --ag
```

> 📚 [Kimi Code 文档](https://moonshot.cn/docs/code/)
</details>

---

*（中文翻译完成，部分工具集成说明的尾部因原文截断而略有不完整）*
