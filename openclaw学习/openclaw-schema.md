# OpenClaw 配置 Schema 完整参考

> 来源：OpenClaw Gateway 配置 schema（通过 `config.schema.lookup` 递归查询）
> 生成时间：2026-03-28

---

## openclaw
├── **meta** # 元数据（版本、更新时间）
├── **wizard** # 向导运行记录
├── **auth** # 认证配置（API Key 等）
│ ├── **profiles** # 命名的认证配置文件（keyed by profile name）
│ │ └── `*` # profile 名称
│ │ ├── **provider** # 认证提供商类型（必填）
│ │ ├── **mode** # 认证模式（必填）
│ │ └── **email** # 可选的邮箱
│ ├── **order** # 各提供商的认证 profile 有序列表（自动故障转移）
│ │ └── `*` # provider ID
│ │ └── `*` # array，按优先级排序的 profile ID 数组
│ └── **cooldowns** # profile 失败后的冷却/退避控制
│ ├── **billingBackoffHours** # 因账单/额度不足失败时的基础退避时间（小时），默认 5
│ ├── **billingBackoffHoursByProvider** # 按提供商覆盖退避时间
│ ├── **billingMaxHours** # 退避时间上限（小时），默认 24
│ └── **failureWindowHours** # 退避计数器窗口（小时），默认 24
├── **models** # 模型提供商配置
│ ├── **mode** # 提供商目录行为：merge（保留内置+叠加自定义）| replace（仅用自定义）
│ │ # merge 模式下匹配到相同 provider ID 时保留非空的 agent models.json baseUrl 值
│ │ # apiKey 仅在 provider 非 SecretRef 管理时保留；matching model contextWindow/maxTokens 取两者的较大值
│ └── **providers** # 模型提供商映射（keyed by provider ID）
│ │ └── `*` # provider ID
│ │ ├── **baseUrl** # 提供商 API 端点 URL（必填），使用 HTTPS
│ │ ├── **apiKey** # API 密钥（敏感），支持 secret/env 替换
│ │ ├── **auth** # 认证方式：api-key | token | oauth | aws-sdk
│ │ ├── **api** # API 适配器选择，控制请求/响应兼容性
│ │ ├── **injectNumCtxForOpenAICompat** # 为 Ollama 注入 num_ctx（OpenAI兼容），默认 true；设为 false 仅在代理/上游拒绝未知 options 字段时
│ │ ├── **headers** # 静态 HTTP 请求头（租户路由/代理认证）
│ │ ├── **authHeader** # 是否强制通过 Authorization 头发送凭证
│ │ └── **models** # 该提供商的模型声明列表
│ │ └── `*` # 模型索引
│ │ ├── **id** # 模型 ID（必填），必须与提供商目录一致
│ │ ├── **name** # 模型名称（必填）
│ │ ├── **api** # 可选的 API 覆盖
│ │ ├── **reasoning** # 是否支持推理模式
│ │ ├── **input** # 输入相关配置数组
│ │ ├── **cost** # 成本配置对象
│ │ │ ├── **inputCost** # 输入成本（$/unit）
│ │ │ └── **outputCost** # 输出成本（$/unit）
│ │ ├── **contextWindow** # 上下文窗口大小（token 数）
│ │ ├── **maxTokens** # 最大输出 token 数
│ │ ├── **headers** # 模型级请求头
│ │ └── **compat** # 兼容性配置对象
│ └── **bedrockDiscovery** # AWS Bedrock 模型自动发现配置
├── **agents** # 智能体配置
│ ├── **defaults** # 全局默认设置（所有 agent 继承，除非被 list 中的条目覆盖）
│ │ ├── **model** # 默认模型
│ │ ├── **imageModel** # 图像理解模型
│ │ ├── **imageGenerationModel** # 图像生成模型
│ │ ├── **pdfModel** # PDF 处理模型
│ │ ├── **pdfMaxBytesMb** # PDF 最大文件大小（MB），默认 10
│ │ ├── **pdfMaxPages** # PDF 最大页数，默认 20
│ │ ├── **models** # 配置的模型目录（key 为完整的 provider/model ID）
│ │ ├── **workspace** # 默认工作区路径
│ │ ├── **repoRoot** # 可选的仓库根目录（覆盖自动检测）
│ │ ├── **skipBootstrap** # 跳过 bootstrap 初始化
│ │ ├── **bootstrapMaxChars** # 每个 bootstrap 文件注入的最大字符数，默认 20000
│ │ ├── **bootstrapTotalMaxChars** # 所有 bootstrap 文件的总最大字符数，默认 150000
│ │ ├── **bootstrapPromptTruncationWarning** # bootstrap 文件被截断时注入警告：off | once（默认）| always
│ │ ├── **userTimezone** # 用户时区
│ │ ├── **timeFormat** # 时间格式
│ │ ├── **envelopeTimezone** # 消息信封时区：utc | local | user | IANA 时区字符串
│ │ ├── **envelopeTimestamp** # 是否在信封中包含绝对时间戳：on | off
│ │ ├── **envelopeElapsed** # 是否在信封中包含已用时间：on | off
│ │ ├── **contextTokens** # 上下文 token 数
│ │ ├── **cliBackends** # 可选的 CLI 后端（文本回退，如 claude-cli）
│ │ ├── **memorySearch** # 向量搜索配置（搜索 MEMORY.md 和 memory/*.md）
│ │ ├── **contextPruning** # 上下文裁剪配置
│ │ ├── **compaction** # 上下文临近 token 限制时的压缩配置（history share、reserve headroom、pre-compaction memory flush）
│ │ ├── **embeddedPi** # 嵌入式 Pi runner 加固控制
│ │ ├── **thinkingDefault** # 默认思考级别：off | minimal | low | medium | high
│ │ ├── **verboseDefault** # 默认详细模式
│ │ ├── **elevatedDefault** # 默认提升模式
│ │ ├── **blockStreamingDefault** # 默认块流模式
│ │ ├── **blockStreamingBreak** # 块流中断配置
│ │ ├── **blockStreamingChunk** # 块流分块配置
│ │ ├── **blockStreamingCoalesce** # 块流合并配置
│ │ ├── **humanDelay** # 人工延迟配置
│ │ ├── **timeoutSeconds** # 超时秒数
│ │ ├── **mediaMaxMb** # 媒体最大 MB
│ │ ├── **imageMaxDimensionPx** # 图像最大边长（像素），默认 1200
│ │ ├── **typingIntervalSeconds** # 打字指示器间隔（秒）
│ │ ├── **typingMode** # 打字模式
│ │ ├── **heartbeat** # 心跳配置
│ │ ├── **maxConcurrent** # 最大并发数
│ │ ├── **subagents** # 子 agent 配置
│ │ └── **sandbox** # 沙箱运行配置
│ │ ├── **mode** # 沙箱模式
│ │ ├── **backend** # 后端类型
│ │ ├── **workspaceAccess** # 工作区访问权限
│ │ ├── **sessionToolsVisibility** # 会话工具可见性
│ │ ├── **scope** # 作用域
│ │ ├── **perSession** # 每次会话独立配置
│ │ ├── **workspaceRoot** # 工作区根目录
│ │ ├── **docker** # Docker 容器配置
│ │ ├── **ssh** # SSH 远程配置
│ │ ├── **browser** # 浏览器配置
│ │ └── **prune** # 清理策略
│ └── **list** # 智能体列表（每个智能体的独立配置）
│ │ └── `*` # agent 索引
│ │ ├── **id** # 智能体唯一 ID（必填）
│ │ ├── **default** # 是否为默认智能体
│ │ ├── **name** # 智能体名称
│ │ ├── **workspace** # 工作区路径
│ │ ├── **agentDir** # Agent 目录路径
│ │ ├── **model** # 模型配置（覆盖默认）
│ │ ├── **thinkingDefault** # 思考级别覆盖
│ │ ├── **reasoningDefault** # 推理可见性覆盖：on | off | stream
│ │ ├── **fastModeDefault** # 快速模式覆盖
│ │ ├── **skills** # 技能白名单（空 = 无技能）
│ │ ├── **memorySearch** # 记忆搜索配置
│ │ ├── **humanDelay** # 人工延迟配置
│ │ ├── **heartbeat** # 心跳配置
│ │ ├── **identity** # 身份配置
│ │ ├── **groupChat** # 群聊配置
│ │ ├── **subagents** # 子 Agent 配置
│ │ ├── **sandbox** # 沙箱配置（覆盖默认）
│ │ ├── **params** # 其他参数
│ │ ├── **tools** # 工具配置（覆盖全局）
│ │ └── **runtime** # 运行时：embedded（默认）| acp（外部 ACP harness）
├── **tools** # 工具配置
│ ├── **profile** # 全局工具策略预设名称
│ ├── **allow** # 绝对工具白名单（替换预设默认值）
│ ├── **alsoAllow** # 在预设基础上额外允许的工具
│ ├── **deny** # 全局工具黑名单（即使预设允许也阻止）
│ ├── **byProvider** # 按渠道定制工具策略（keyed by channel/provider ID）
│ │ └── `*` # channel/provider ID
│ │ ├── **allow** # 工具白名单
│ │ ├── **alsoAllow** # 额外允许的工具
│ │ ├── **deny** # 工具黑名单
│ │ └── **profile** # 工具策略预设
│ ├── **web** # Web 工具（搜索+抓取）
│ │ ├── **search** # 网页搜索
│ │ │ ├── **enabled** # 是否启用
│ │ │ ├── **provider** # 提供商 ID（省略则自动检测）
│ │ │ ├── **maxResults** # 返回结果数（1-10）
│ │ │ ├── **timeoutSeconds** # 超时（秒）
│ │ │ ├── **cacheTtlMinutes** # 缓存 TTL（分钟）
│ │ │ ├── **apiKey** # API 密钥
│ │ │ ├── **brave** # Brave Search 配置
│ │ │ ├── **firecrawl** # Firecrawl 搜索配置
│ │ │ │ ├── **apiKey** # Firecrawl API 密钥
│ │ │ │ ├── **baseUrl** # Firecrawl 端点
│ │ │ │ └── **model** # 搜索模型
│ │ │ ├── **gemini** # Google Gemini 搜索配置
│ │ │ ├── **grok** # xAI Grok 搜索配置
│ │ │ ├── **kimi** # 月之暗面 Kimi 搜索配置
│ │ │ └── **perplexity** # Perplexity 搜索配置
│ │ └── **fetch** # 网页抓取
│ │ ├── **enabled** # 是否启用
│ │ ├── **maxChars** # 最大返回字符数
│ │ ├── **maxCharsCap** # 硬上限
│ │ ├── **timeoutSeconds** # 超时（秒）
│ │ ├── **cacheTtlMinutes** # 缓存 TTL（分钟）
│ │ ├── **maxRedirects** # 最大重定向次数，默认 3
│ │ ├── **userAgent** # User-Agent 覆盖
│ │ ├── **readability** # 是否使用 Readability 提取主要内容，默认 true
│ │ └── **firecrawl** # Firecrawl 回退配置
│ │ ├── **enabled** # 启用 Firecrawl 回退
│ │ ├── **apiKey** # API 密钥（可从 FIRECRAWL_API_KEY 环境变量读取）
│ │ ├── **baseUrl** # Firecrawl 端点，如 https://api.firecrawl.dev
│ │ ├── **onlyMainContent** # 仅提取主要内容，默认 true
│ │ ├── **maxAgeMs** # 缓存最大有效期（毫秒），默认 172800000（2天）
│ │ └── **timeoutSeconds** # 超时（秒）
│ ├── **media** # 媒体理解（图像/音频/视频）
│ │ ├── **models** # 共享回退模型列表（当媒体类型未指定时使用）
│ │ ├── **concurrency** # 每次并发媒体操作数
│ │ ├── **image** # 图像理解
│ │ │ ├── **enabled** # 是否启用
│ │ │ ├── **scope** # 触发范围配置
│ │ │ ├── **maxBytes** # 最大图像大小（字节）
│ │ │ ├── **maxChars** # 最大输出字符数
│ │ │ ├── **prompt** # 理解提示词模板
│ │ │ ├── **timeoutSeconds** # 超时（秒）
│ │ │ ├── **language** # 语言偏好
│ │ │ ├── **providerOptions** # 提供商特定选项
│ │ │ ├── **deepgram** # Deepgram 配置
│ │ │ ├── **baseUrl** # 自定义端点
│ │ │ ├── **headers** # 请求头
│ │ │ ├── **attachments** # 附件处理策略
│ │ │ ├── **models** # 图像理解专用模型列表
│ │ │ ├── **echoTranscript** # 是否回显转录到聊天
│ │ │ └── **echoFormat** # 回显格式
│ │ ├── **audio** # 音频理解
│ │ │ ├── **enabled** # 是否启用
│ │ │ ├── **scope** # 触发范围配置
│ │ │ ├── **maxBytes** # 最大音频大小（字节）
│ │ │ ├── **maxChars** # 最大输出字符数
│ │ │ ├── **prompt** # 理解提示词模板
│ │ │ ├── **timeoutSeconds** # 超时（秒）
│ │ │ ├── **language** # 语言偏好
│ │ │ ├── **providerOptions** # 提供商特定选项
│ │ │ ├── **deepgram** # Deepgram 配置
│ │ │ ├── **baseUrl** # 自定义端点
│ │ │ ├── **headers** # 请求头
│ │ │ ├── **attachments** # 附件处理策略
│ │ │ ├── **models** # 音频理解专用模型列表
│ │ │ ├── **echoTranscript** # 是否回显转录到聊天，默认 false
│ │ │ └── **echoFormat** # 回显格式，默认 '📝 "{transcript}"'
│ │ └── **video** # 视频理解
│ │ ├── **enabled** # 是否启用
│ │ ├── **scope** # 触发范围配置
│ │ ├── **maxBytes** # 最大视频大小（字节）
│ │ ├── **maxChars** # 最大输出字符数
│ │ ├── **prompt** # 理解提示词模板
│ │ ├── **timeoutSeconds** # 超时（秒）
│ │ ├── **language** # 语言偏好
│ │ ├── **providerOptions** # 提供商特定选项
│ │ ├── **deepgram** # Deepgram 配置
│ │ ├── **baseUrl** # 自定义端点
│ │ ├── **headers** # 请求头
│ │ ├── **attachments** # 附件处理策略
│ │ ├── **models** # 视频理解专用模型列表
│ │ ├── **echoTranscript** # 是否回显转录到聊天
│ │ └── **echoFormat** # 回显格式
│ ├── **links** # 链接预理解（自动在推理前抓取 URL 内容）
│ │ ├── **enabled** # 是否启用
│ │ ├── **scope** # 触发范围配置
│ │ ├── **maxLinks** # 每次最大链接数
│ │ ├── **timeoutSeconds** # 每个链接超时（秒）
│ │ └── **models** # 链接理解专用模型列表
│ ├── **sessions** # 会话工具可见性
│ │ └── **visibility** # sessions_list/history/send 的可见范围：tree（默认）| self | agent | all
│ │ # tree = 当前会话 + 子 Agent 会话；self = 仅当前会话；agent = 当前 agent ID 内的任何会话；all = 任意会话
│ ├── **loopDetection** # 工具循环检测
│ │ ├── **enabled** # 是否启用，默认 false
│ │ ├── **historySize** # 历史窗口大小，默认 30
│ │ ├── **warningThreshold** # 警告阈值，默认 10
│ │ ├── **criticalThreshold** # 严重阈值，默认 20
│ │ ├── **globalCircuitBreakerThreshold** # 全局熔断阈值，默认 30
│ │ └── **detectors** # 各类检测器配置
│ ├── **message** # 消息发送策略
│ │ ├── **allowCrossContextSend** # 允许跨上下文发送（遗留覆盖）
│ │ ├── **crossContext** # 跨上下文发送配置
│ │ └── **broadcast** # 广播配置
│ ├── **agentToAgent** # Agent 间调用策略
│ │ ├── **enabled** # 是否启用 agent_to_agent 工具表面
│ │ └── **allow** # 允许调用的目标 agent ID 白名单
│ ├── **elevated** # 提权工具访问
│ │ ├── **enabled** # 全局开关
│ │ └── **allowFrom** # 发送者允许列表（按渠道）
│ ├── **exec** # Shell 执行工具
│ │ ├── **host** # 执行位置：sandbox（默认）| gateway | node
│ │ │ # sandbox = 在沙箱执行；沙箱隔离关闭时直接在 Gateway 主机执行（无容器）且不需要审批
│ │ ├── **security** # 安全策略：deny（sandbox 默认）| allowlist（gateway/node 默认）| full
│ │ ├── **ask** # 审批提示：off | on-miss（默认）| always
│ │ │ # on-miss = 白名单没有的命令才提示审批
│ │ ├── **node** # node 绑定
│ │ ├── **pathPrepend** # PATH 前置目录列表
│ │ ├── **safeBins** # 安全二进制白名单（stdin 安全，无需显式白名单）
│ │ ├── **strictInlineEval** # 内联求值严格审批（python -c、node -e 等）
│ │ ├── **safeBinProfiles** # 二进制特定策略（位置限制 + allowed/denied flags）
│ │ ├── **safeBinTrustedDirs** # 额外信任的目录（PATH 条目不会被自动信任）
│ │ ├── **backgroundMs** # 后台超时（毫秒）
│ │ ├── **timeoutSec** # 执行超时（秒），默认 1800
│ │ ├── **cleanupMs** # 清理超时（毫秒）
│ │ ├── **notifyOnExit** # 退出通知，默认 true
│ │ ├── **notifyOnExitEmptySuccess** # 空成功也通知，默认 false
│ │ └── **applyPatch** # apply_patch 实验性功能配置
│ │ ├── **enabled** # 是否启用，默认 false
│ │ └── **allowModels** # 允许使用该功能的模型列表
│ ├── **sandbox** # 沙箱工具策略
│ │ └── **tools** # allow/deny 工具策略（沙箱专用）
│ ├── **fs** # 文件系统工具
│ │ └── **workspaceOnly** # 限制文件系统工具（read/write/edit/apply_patch）仅在工作区内，默认 false
│ ├── **subagents** # 子 Agent 工具策略
│ │ └── **tools** # allow/deny 工具策略（比父级更严格）
│ └── **sessions_spawn** # 会话生成工具
│ └── **attachments** # 附件配置
├── **bindings** # 路由绑定（渠道→智能体）
│ └── `*` # binding ID
│ ├── **type** # 绑定类型：route（普通路由）| acp（持久 ACP harness 绑定）
│ └── ... # 其他绑定特定配置
├── **commands** # 命令配置
│ ├── **native** # 是否注册原生命令（Discord/Slack/Telegram），默认 true
│ ├── **nativeSkills** # 是否注册原生技能命令，默认 true
│ ├── **text** # 是否启用文本命令解析（除了原生命令），默认 true
│ ├── **bash** # 允许 ! /bash 命令运行主机 shell，默认 false（需要 tools.elevated）
│ ├── **bashForegroundMs** # bash 前台等待时间（毫秒），默认 2000；0 立即后台
│ ├── **config** # 允许 /config 命令读写磁盘配置，默认 false
│ ├── **mcp** # 允许 /mcp 命令管理 MCP 服务器配置，默认 false
│ ├── **plugins** # 允许 /plugins 命令列出/切换插件，默认 false
│ ├── **debug** # 允许 /debug 运行时覆盖，默认 false
│ ├── **restart** # 允许 /restart 和 gateway restart 工具操作，默认 true
│ ├── **useAccessGroups** # 是否对命令执行访问组策略
│ ├── **ownerAllowFrom** # owner 专用工具/命令的发送者白名单（数组），格式如 whatsapp:+15551234567，'*'
│ ├── **ownerDisplay** # owner ID 显示方式：raw | hash
│ ├── **ownerDisplaySecret** # ownerDisplay=hash 时的 HMAC 密钥（敏感）
│ └── **allowFrom** # 提权命令的渠道+发送者规则
├── **session** # 会话策略
│ ├── **scope** # 会话分组策略：per-sender（默认，隔离发送者）| global（每个渠道上下文一个会话）
│ ├── **dmScope** # DM 会话范围：main | per-peer | per-channel-peer | per-account-channel-peer
│ ├── **identityLinks** # 身份映射（canonical → provider:peerId），用于跨渠道同一用户合并 DM 线程
│ │ └── `*` # canonical ID
│ │ └── `*` # array of provider-prefixed peer IDs
│ ├── **resetTriggers** # 触发会话重置的消息匹配列表
│ ├── **idleMinutes** # 空闲重置窗口（分钟），遗留兼容
│ ├── **reset** # 默认重置策略
│ │ ├── **mode** # 重置策略：daily（按小时）| idle（按空闲）
│ │ ├── **atHour** # 每日重置的小时（0-23）
│ │ └── **idleMinutes** # 空闲重置分钟数
│ ├── **resetByType** # 按聊天类型重置策略覆盖
│ │ ├── **direct** # 私聊重置策略
│ │ ├── **dm** # dm 的别名（同 direct，已废弃）
│ │ ├── **group** # 群聊重置策略
│ │ └── **thread** # 线程重置策略
│ ├── **resetByChannel** # 按渠道的重置策略覆盖（keyed by provider/channel id）
│ │ └── `*` # provider/channel ID
│ ├── **store** # 会话存储文件路径
│ ├── **typingIntervalSeconds** # 打字指示器发送间隔（秒）
│ ├── **typingMode** # 打字指示器模式：never | instant | thinking | message
│ ├── **parentForkMaxTokens** # 允许 fork 的父会话最大 token 数，0 禁用
│ ├── **mainKey** # 主会话 key 覆盖
│ ├── **sendPolicy** # 跨会话发送权限策略
│ │ ├── **default** # 默认动作：allow | deny
│ │ └── **rules** # 按 channel/chatType/key 前缀的规则
│ ├── **agentToAgent** # Agent 间控制
│ │ └── **maxPingPongTurns** # Agent 间最大往返次数（0-5）
│ ├── **threadBindings** # 线程绑定配置
│ │ ├── **enabled** # 全局开关
│ │ ├── **idleHours** # 空闲超时（小时），0 禁用，默认 24
│ │ └── **maxAgeHours** # 最大有效期（小时），0 禁用，默认 0
│ └── **maintenance** # 自动维护控制
│ ├── **mode** # 维护模式：warn（仅报告）| enforce（执行）
│ ├── **pruneAfter** # 保留期限，如 30d / 12h
│ ├── **pruneDays** # 保留天数（旧版，已废弃）
│ ├── **maxEntries** # 最大条目数上限
│ ├── **rotateBytes** # 轮转大小阈值，如 10mb / 1gb
│ ├── **resetArchiveRetention** # reset 归档保留期限，false 禁用，默认同 pruneAfter
│ ├── **maxDiskBytes** # 每个 agent 目录磁盘预算，如 500mb
│ └── **highWaterBytes** # 清理后目标大小（高水位线），默认 80% maxDiskBytes
├── **hooks** # Webhook 钩子配置
│ ├── **enabled** # 是否启用 hooks 端点和映射执行
│ ├── **path** # Hooks 端点路径，如 /hooks
│ ├── **token** # Bearer 令牌认证（敏感）
│ ├── **defaultSessionKey** # 默认会话 key
│ ├── **allowRequestSessionKey** # 允许调用方提供 session key，默认 false
│ ├── **allowedSessionKeyPrefixes** # 允许的 session key 前缀列表
│ ├── **allowedAgentIds** # 允许的 agent ID 列表
│ ├── **maxBodyBytes** # 最大请求体大小（字节）
│ ├── **presets** # 命名的钩子预设束（启动时加载）
│ ├── **transformsDir** # 钩子转换模块目录
│ ├── **mappings** # 映射规则数组（匹配请求 → 执行动作）
│ │ └── `*` # mapping 索引
│ ├── **gmail** # Gmail Pub/Sub 集成配置
│ │ ├── **account** # Google 账户标识
│ │ ├── **label** # Gmail 标签过滤器
│ │ ├── **topic** # Pub/Sub topic 名称
│ │ ├── **subscription** # Pub/Sub subscription 名称
│ │ ├── **pushToken** # 回调认证令牌（敏感）
│ │ ├── **hookUrl** # 公共回调 URL
│ │ ├── **includeBody** # 是否获取邮件正文，默认 false
│ │ ├── **maxBytes** # 正文最大字节数
│ │ ├── **renewEveryMinutes** # Gmail watch 续订间隔（分钟）
│ │ ├── **allowUnsafeExternalContent** # 允许不安全外部内容，默认 false
│ │ ├── **serve** # 本地回调服务器配置
│ │ ├── **tailscale** # Tailscale 暴露配置
│ │ ├── **model** # Gmail 触发运行的模型覆盖
│ │ └── **thinking** # 思考级别覆盖：off | minimal | low | medium | high
│ └── **internal** # 内部钩子运行时设置
│ ├── **enabled** # 是否启用
│ ├── **handlers** # 内部事件处理器列表
│ ├── **entries** # 已配置的内部钩子条目
│ ├── **load** # 内部钩子加载器设置
│ └── **installs** # 已安装内部钩子模块的元数据
├── **channels** # 渠道配置
│ └── **feishu** # 飞书/Lark 配置
│ ├── **enabled** # 是否启用
│ ├── **defaultAccount** # 默认账户
│ ├── **appId** # 飞书应用 App ID
│ ├── **appSecret** # 飞书应用 App Secret（敏感）
│ ├── **encryptKey** # 加密密钥
│ ├── **verificationToken** # 验证令牌
│ ├── **domain** # 飞书域名（必填）
│ ├── **connectionMode** # 连接模式（必填）
│ ├── **webhookPath** # Webhook 路径（必填）
│ ├── **webhookHost** # Webhook 主机
│ ├── **webhookPort** # Webhook 端口
│ ├── **capabilities** # 功能列表
│ ├── **markdown** # Markdown 配置
│ ├── **configWrites** # 是否允许配置写入
│ ├── **dmPolicy** # 私信策略
│ ├── **allowFrom** # 允许的发送者列表
│ ├── **groupPolicy** # 群组策略
│ ├── **groupAllowFrom** # 群组白名单
│ ├── **groupSenderAllowFrom** # 群组发送者白名单
│ ├── **requireMention** # 是否需要 @ 机器人
│ ├── **groups** # 按群组 ID 的配置覆盖
│ ├── **historyLimit** # 历史消息限制
│ ├── **dmHistoryLimit** # 私信历史限制
│ ├── **dms** # 按 DM 会话的配置覆盖
│ ├── **textChunkLimit** # 文本分块限制
│ ├── **chunkMode** # 分块模式
│ ├── **blockStreamingCoalesce** # 块流合并配置
│ ├── **mediaMaxMb** # 媒体最大 MB
│ ├── **httpTimeoutMs** # HTTP 超时（毫秒）
│ ├── **heartbeat** # 心跳配置
│ ├── **renderMode** # 渲染模式
│ ├── **streaming** # 是否启用流式
│ ├── **tools** # 工具配置
│ ├── **actions** # 动作配置
│ ├── **replyInThread** # 是否回复到线程
│ ├── **reactionNotifications** # 反应通知
│ ├── **typingIndicator** # 打字指示器
│ ├── **resolveSenderNames** # 是否解析发送者名称
│ ├── **groupSessionScope** # 群组会话范围
│ ├── **topicSessionMode** # 话题会话模式
│ ├── **dynamicAgentCreation** # 动态 Agent 创建配置
│ └── **accounts** # 账户配置
├── **gateway** # Gateway 核心配置
│ ├── **port** # 监听端口
│ ├── **mode** # 运行模式：local | remote
│ ├── **bind** # 绑定策略：auto | lan | loopback | custom | tailnet
│ ├── **controlUi** # 控制 UI 配置
│ │ ├── **enabled** # 是否启用控制 UI，默认 true
│ │ ├── **basePath** # URL 前缀，如 /openclaw
│ │ ├── **root** # UI 资源根目录，默认 dist/control-ui
│ │ ├── **allowedOrigins** # 允许的浏览器来源（完整 origin），如 https://control.example.com
│ │ ├── **dangerouslyAllowHostHeaderOriginFallback** # 危险：允许 Host header 回退进行来源检查
│ │ ├── **allowInsecureAuth** # 允许不安全认证（非标准设置）
│ │ └── **dangerouslyDisableDeviceAuth** # 禁用设备认证（仅用于调试）
│ ├── **auth** # 认证策略
│ │ ├── **mode** # 认证模式：none | token | password | trusted-proxy
│ │ ├── **token** # 访问令牌（敏感），默认需要
│ │ ├── **password** # 密码（敏感），Tailscale funnel 需要
│ │ ├── **allowTailscale** # 允许 Tailscale 身份验证
│ │ ├── **rateLimit** # 登录尝试限速
│ │ │ ├── **maxAttempts** # 最大尝试次数
│ │ │ ├── **windowMs** # 时间窗口（毫秒）
│ │ │ ├── **lockoutMs** # 锁定时间（毫秒）
│ │ │ └── **exemptLoopback** # 豁免回环地址
│ │ └── **trustedProxy** # 可信代理认证
│ │ ├── **userHeader** # 用户身份头（必填）
│ │ ├── **requiredHeaders** # 必需的头
│ │ └── **allowUsers** # 允许的用户列表
│ ├── **trustedProxies** # 可信代理 CIDR 列表
│ ├── **allowRealIpFallback** # 是否在缺少 x-forwarded-for 时使用 x-real-ip，默认 false
│ ├── **tailscale** # Tailscale 集成
│ │ ├── **mode** # 模式：off | serve（私有访问）| funnel（公共互联网访问）
│ │ └── **resetOnExit** # 退出时重置 Tailscale Serve/Funnel 状态
│ ├── **remote** # 远程网关连接（split-host 操作）
│ │ ├── **url** # WebSocket URL（ws:// 或 wss://）
│ │ ├── **transport** # 传输方式：direct | ssh
│ │ ├── **token** # Bearer 令牌（敏感）
│ │ ├── **password** # 密码（敏感）
│ │ ├── **tlsFingerprint** # 期望的 TLS 指纹（sha256:...），防止 MITM
│ │ ├── **sshTarget** # SSH 目标，格式 user@host 或 user@host:port
│ │ └── **sshIdentity** # SSH 身份文件路径
│ ├── **reload** # 热重载策略
│ │ ├── **mode** # 模式：off（忽略）| restart（总是重启）| hot（热更新）| hybrid（默认，先热更新，失败则重启）
│ │ ├── **debounceMs** # 防抖窗口（毫秒）
│ │ └── **deferralTimeoutMs** # 重启延迟超时（毫秒），默认 300000（5分钟）
│ ├── **tls** # TLS 终端配置
│ │ ├── **enabled** # 是否启用 TLS
│ │ ├── **autoGenerate** # 是否自动生成自签名证书（仅用于本地/开发）
│ │ ├── **certPath** # 证书文件路径
│ │ ├── **keyPath** # 私钥文件路径
│ │ └── **caPath** # CA 证书路径
│ ├── **http** # HTTP API 配置
│ │ ├── **endpoints** # HTTP 端点功能开关
│ │ └── **securityHeaders** # 安全响应头
│ ├── **push** # 推送通知（APNs）
│ │ └── **apns** # iOS 推送配置
│ │ └── **relay** # 外部 relay 设置（用于官方 iOS/TestFlight 构建）
│ ├── **nodes** # 节点管理
│ │ ├── **browser** # 节点浏览器路由
│ │ │ ├── **mode** # 模式：auto（选择单个连接节点）| manual（需要 node 参数）| off（禁用）
│ │ │ └── **node** # 固定到特定节点 ID 或名称
│ │ ├── **allowCommands** # 额外的允许节点命令（字符串数组）
│ │ └── **denyCommands** # 禁止的命令名称列表（如 system.run）
│ ├── **channelHealthCheckMinutes** # 渠道健康检查间隔（分钟）
│ ├── **channelStaleEventThresholdMinutes** # 渠道被视为过期的时间（分钟），默认 30
│ ├── **channelMaxRestartsPerHour** # 每小时最大重启次数，默认 10
│ ├── **tools** # Gateway 工具暴露策略
│ │ ├── **deny** # 工具黑名单
│ │ └── **allow** # 工具白名单
│ └── **nodes** # 节点配置（占位）
└── **plugins** # 插件管理
 └── **load** # 插件加载器配置
  └── **paths** # 额外的插件扫描路径数组
