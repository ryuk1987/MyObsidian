 # Hermes Agent 内置 Skill 知识库

> 系统版本: 2026-04-18 | 共 79 个 Skill | 19 个分类

---

## 目录

1. [apple](#1-apple-苹果生态) — Apple 生态集成
2. [autonomous-ai-agents](#2-autonomous-ai-agents-ai-agent-委托) — AI Coding Agent 委托
3. [creative](#3-creative-创意) — 创意内容生成
4. [data-science](#4-data-science-数据科学) — 数据科学工作流
5. [devops](#5-devops) — DevOps 工具
6. [email](#6-email-邮件) — 邮件管理
7. [gaming](#7-gaming-游戏) — 游戏服务器与自动化
8. [github](#8-github) — GitHub 工作流
9. [leisure](#9-leisure-休闲) — 休闲娱乐
10. [mcp](#10-mcp-模型上下文协议) — MCP 集成
11. [media](#11-media-媒体) — 媒体处理
12. [mlops](#12-mlops-机器学习运维) — ML 训练、推理、部署
13. [note-taking](#13-note-taking-笔记) — 笔记工具
14. [productivity](#14-productivity-生产力) — 办公效率
15. [red-teaming](#15-red-teaming-红队) — 安全测试
16. [research](#16-research-研究) — 学术与市场研究
17. [smart-home](#17-smart-home-智能家居) — 智能家居控制
18. [social-media](#18-social-media-社交媒体) — 社交媒体
19. [software-development](#19-software-development-软件开发) — 软件开发方法论

---

## 1. apple (苹果生态)

| Skill | 描述 | 依赖 |
|-------|------|------|
| `apple-notes` | 通过 `memo` CLI 管理 Apple Notes（创建、查看、搜索、编辑），支持 iCloud 同步 | macOS + `memo` CLI |
| `apple-reminders` | 通过 `remindctl` CLI 管理 Apple Reminders（列表、添加、完成、删除），支持 iCloud 同步 | macOS + `remindctl` CLI |
| `findmy` | 通过 FindMy.app + AppleScript 追踪 Apple 设备和 AirTag | macOS + FindMy.app |
| `imessage` | 通过 `imsg` CLI 发送/接收 iMessages/SMS | macOS + `imsg` CLI |

**用法示例：**

### apple-notes
```bash
memo notes                           # 列出所有笔记
memo notes -a "Note Title"          # 快速添加带标题的笔记
memo notes -s "query"               # 搜索笔记（模糊匹配）
```

### apple-reminders
```bash
remindctl today                     # 今日提醒
remindctl add --title "Call mom" --list Personal --due tomorrow  # 创建提醒
remindctl complete 1 2 3           # 标记完成（按 ID）
```

### findmy
```bash
osascript -e 'tell application "FindMy" to activate'  # 打开 FindMy 应用
screencapture -w -o /tmp/findmy.png                   # 截图 FindMy 窗口
```

### imessage
```bash
imsg chats --limit 10 --json          # 列出最近聊天
imsg history --chat-id 1 --limit 20   # 查看聊天记录
imsg send --to "+14155551212" --text "Hello!"  # 发送 iMessage
```

---

## 2. autonomous-ai-agents (AI Agent 委托)

将编码任务委托给外部 AI Coding Agent。

| Skill | 描述 | 核心用法 |
|-------|------|---------|
| `claude-code` | Anthropic Claude Code CLI，结构化输出好，`-p` 非交互模式 | `claude -p 'task' --max-turns 10` |
| `codex` | OpenAI Codex CLI，**必须在 git 仓库内运行** | `codex exec 'task'` |
| `opencode` | 开源 provider-agnostic AI 编程 Agent，支持多后端 | `opencode run 'task'` |
| `hermes-agent` | Hermes 自身指南：CLI、配置、多 Agent spawn、Gateway、Skill 开发 | `hermes chat -q 'task'` |

**用法示例：**

### claude-code
```bash
claude -p 'Add error handling to API calls in src/' --max-turns 10
git diff main | claude -p 'Review this diff for bugs'
claude -p 'Fix bug in auth.py' --allowedTools Read,Edit --max-turns 5
```

### codex
```bash
codex exec 'Add dark mode toggle to settings'         # 单次任务
codex exec --full-auto 'Refactor auth module'        # 自动批准变更
cd $(mktemp -d) && git init && codex exec 'Build a snake game'  # 临时目录
```

### opencode
```bash
opencode run 'Add retry logic to API calls'          # 单次任务
opencode run 'Review security' -f config.yaml        # 带文件上下文
opencode --continue                                   # 继续上一会话
```

**对比：**

| 工具 | 环境要求 | 推荐场景 |
|------|---------|---------|
| claude-code | 任意目录 | 最常用，print 模式干净 |
| codex | **必须 git 仓库** | git 工作流紧密时 |
| opencode | 任意目录 | 需要多模型/多后端时 |
| hermes-agent | 任意目录 | 本身就是 Agent，无需委托 |

---

## 3. creative (创意)

| Skill                      | 描述                                                                   | 输出格式                 |
| -------------------------- | -------------------------------------------------------------------- | -------------------- |
| `architecture-diagram`     | 生成深色主题 SVG 软件架构图（前端=青色，后端=翡翠绿，数据库=紫罗兰，云/ AWS=琥珀，安全=玫瑰色，消息总线=橙色）      | 独立 HTML 文件           |
| `ascii-art`                | ASCII 艺术生成：pyfiglet (571 字体)、cowsay、boxes、toilet、image-to-ASCII、QR 码 | 文本/图片                |
| `ascii-video`              | ASCII 艺术视频生产流水线：视频→ASCII，音频可视化，生成动画                                  | MP4/GIF              |
| `excalidraw`               | 手绘风格图表（Excalidraw JSON 格式），可上传到 excalidraw.com                       | `.excalidraw` 文件     |
| `manim-video`              | 3Blue1Brown 风格数学/技术动画（Manim Community Edition）                       | 视频                   |
| `p5js`                     | 浏览器交互式生成艺术（p5.js）：2D/3D、粒子系统、着色器、音频可视化、WebGL                         | HTML/PNG/GIF/MP4/SVG |
| `popular-web-designs`      | 54 个真实网站设计系统（Stripe、Linear、Vercel、Notion 等），直接复用 HTML/CSS            | HTML/CSS             |
| `songwriting-and-ai-music` | 歌曲创作技巧 + AI 音乐生成提示词（Suno 为主）                                         | 文本/歌词                |

**用法示例：**

### architecture-diagram
```bash
# 保存为 .html 文件后直接在浏览器打开预览
open ./my-architecture.html
```

### ascii-art
```bash
python3 -m pyfiglet "YOUR TEXT" -f slant           # pyfiglet 文字 banner
cowsay "Hello World"                               # ASCII 字符气泡
curl -s "https://asciified.thelicato.io/api/v2/ascii?text=Hello+World"  # 远程 API
```

### ascii-video
```bash
# 流水线: INPUT → ANALYZE → SCENE_FN → TONEMAP → SHADE → ENCODE
ffmpeg -i input.mp4 ...                           # 视频解码
manim -ql script.py SceneName                     # 草稿质量渲染
```

### excalidraw
```bash
# 写入 Excalidraw JSON 到 .excalidraw 文件
python scripts/upload.py ~/diagrams/my_diagram.excalidraw  # 上传获取分享链接
open excalidraw.com                               # 在网页端编辑
```

### manim-video
```bash
manim -ql script.py Scene1 Scene2                 # 草稿质量渲染
ffmpeg -f concat -safe 0 -i concat.txt -c copy final.mp4  # 拼接场景
manim -ql --format=png -s script.py SceneName     # 预览单帧
```

### p5js
```javascript
saveCanvas('output', 'png')                        // 导出 PNG
saveGif('output', 5)                             // 导出 GIF
randomSeed(CONFIG.seed); noiseSeed(CONFIG.seed)  // 确定性随机
colorMode(HSB, 360, 100, 100, 100)              // HSB 色彩模式
```

### popular-web-designs
```bash
skill_view(name="popular-web-designs", file_path="templates/stripe.md")  # 加载 Stripe 模板
```

### songwriting-and-ai-music
```
# Suno 风格提示词格式
Genre + Mood + Era + Instruments + Vocal Style + Dynamics

# 歌词结构标签
[Verse] [Chorus] [Bridge]

# 人声表演元标签
[Whispered] [Belted] [Building Energy]
```

---

## 4. data-science (数据科学)

| Skill | 描述 | 核心工具 |
|-------|------|---------|
| `jupyter-live-kernel` | 活 Jupyter kernel 交互（通过 hamelnb），适合探索性迭代、ML 实验、API 测试 | `hamelnb` CLI |

**用法示例：**

### jupyter-live-kernel
```bash
uv run "$SCRIPT" execute --path <notebook.ipynb> --code '<python code>' --compact
uv run "$SCRIPT" variables --path <notebook.ipynb> list --compact
uv run "$SCRIPT" restart-run-all --path <notebook.ipynb> --save-outputs --compact
```

---

## 5. devops

| Skill | 描述 | 用途 |
|-------|------|------|
| `webhook-subscriptions` | 创建/管理 webhook 订阅，实现外部服务触发 Agent 自动运行 | Hermes Gateway |

**用法示例：**

### webhook-subscriptions
```bash
hermes webhook subscribe myhook --prompt "分析这个事件" --events "push,issue" --deliver telegram --deliver-chat-id "12345"
hermes webhook list
hermes webhook test myhook --payload '{"key": "value"}'
```

---

## 6. email (邮件)

| Skill | 描述 | 核心命令 |
|-------|------|---------|
| `himalaya` | 终端邮件客户端（IMAP/SMTP），支持多账户、邮件列表/阅读/回复/转发/搜索/组织 | `himalaya` CLI |

**用法示例：**

### himalaya
```bash
himalaya envelope list                    # 列出邮件
himalaya message read 42                  # 阅读第 42 封
cat << 'EOF' | himalaya template send      # 非交互式发送
```

---

## 7. gaming (游戏)

| Skill | 描述 | 环境 |
|-------|------|------|
| `minecraft-modpack-server` | 从 CurseForge/Modrinth 服务器包搭建 modded Minecraft 服务器（NeoForge/Forge、Java 版本、JVM 调优、防火墙、备份） | Linux 服务器 |
| `pokemon-player` | 通过 headless 模拟器（pyboy）自动玩宝可梦游戏：观察→定向→决策→行动循环 | Linux + pyboy |

**用法示例：**

### minecraft-modpack-server
```bash
ATM10_INSTALL_ONLY=true bash startserver.sh      # 仅安装不启动
echo "eula=true" > ~/minecraft-server/server/eula.txt
sudo ufw allow 25565/tcp comment "Minecraft Server"
```

### pokemon-player
```bash
pokemon-agent serve --rom roms/pokemon_red.gb --port 9876 &  # 启动游戏服务器
GET /state                                          # 观察游戏状态
GET /screenshot                                     # 截图
POST /action {"action": "press_a"}                 # 发送按键
```

---

## 8. github

| Skill | 描述 | 核心功能 |
|-------|------|---------|
| `codebase-inspection` | 代码库统计：LOC 计数、语言分布、代码/注释比例（pygount） | `pygount` |
| `github-auth` | GitHub 认证设置：HTTPS token、SSH key、git credential helpers、gh CLI 自动检测 | git/gh CLI |
| `github-code-review` | 代码审查工作流：本地 diff/PR 审查，正确性/安全/质量 checklist，inline 评论，提交审查结果 | gh CLI / curl |
| `github-issues` | Issue 管理：创建/分类/标签/指派/关闭，支持 bug/feature 模板 | gh CLI / curl |
| `github-pr-workflow` | 完整 PR 生命周期：分支→提交→PR→CI 监控→自动修复→合并 | gh CLI / git |
| `github-repo-management` | 仓库管理：clone/create/fork/配置/分支保护/secrets/releases/ Actions/gist | gh CLI / git+curl |

**用法示例：**

### codebase-inspection
```bash
pygount --format=summary --folders-to-skip=".git,node_modules,venv,dist,build" .
pygount --suffix=py --format=summary .       # 仅统计 Python
pygount --format=json .                      # JSON 输出
```

### github-auth
```bash
git config --global credential.helper store                    # HTTPS token
ssh-keygen -t ed25519 -C "email" -f ~/.ssh/id_ed25519 -N ""   # SSH key
gh auth login                                                   # gh CLI 登录
```

### github-code-review
```bash
git diff main...HEAD --stat                          # 查看变更范围
gh pr checkout 123 && git diff main...pr-123         # 本地审查 PR
gh pr review 123 --approve --body "LGTM!"           # 批准 PR
```

### github-issues
```bash
gh issue list --state open --label "bug"            # 列出 open bug
gh issue create --title "..." --body "..." --label "bug,backend"  # 创建 issue
gh issue comment 42 --body "..."                    # 评论 issue
```

### github-pr-workflow
```bash
git checkout -b feat/add-auth && git commit -m "feat: description" && git push -u origin HEAD
gh pr create --title "feat: ..." --body "..."       # 创建 PR
gh pr merge --squash --delete-branch                # 合并并删除分支
```

### github-repo-management
```bash
gh repo clone owner/repo-name -- --depth 1
gh repo create my-new-project --public --clone
gh secret set API_KEY --body "your-secret-value"
```

---

## 9. leisure (休闲)

| Skill | 描述 | 数据源 |
|-------|------|-------|
| `find-nearby` | 查找附近地点（餐厅、咖啡馆、酒吧、药房等），支持坐标/地址/城市/邮编/Telegram 位置 | OpenStreetMap（无需 API key） |

**用法示例：**

### find-nearby
```bash
python3 SKILL_DIR/scripts/find_nearby.py --lat 40.7128 --lon -74.006 --type restaurant --radius 1500
python3 SKILL_DIR/scripts/find_nearby.py --near "Times Square, New York" --type cafe
python3 SKILL_DIR/scripts/find_nearby.py --near "90210" --type pharmacy --json
```

---

## 10. mcp (模型上下文协议)

| Skill | 描述 | 传输方式 |
|-------|------|---------|
| `mcporter` | MCP 服务器/工具的 CLI 管理工具：列出/配置/认证/调用 MCP 服务器（stdio 或 HTTP） | stdio/HTTP |
| `native-mcp` | Hermes 内置 MCP 客户端：连接外部 MCP 服务器，自动发现工具，注册为 `mcp_{server}_{tool}` | stdio/HTTP，自动重连 |

**用法示例：**

### mcporter
```bash
mcporter list                                  # 列出可用服务器
mcporter call <server.tool> key=value --output json  # 调用工具
mcporter config list                           # 查看配置
mcporter generate-cli --server <name>          # 生成 CLI
```

### native-mcp
```yaml
# ~/.hermes/config.yaml 添加 MCP 服务器
mcp_servers:
  time:
    command: "uvx"
    args: ["mcp-server-time"]
```

---

## 11. media (媒体)

| Skill | 描述 | 功能 |
|-------|------|------|
| `gif-search` | Tenor GIF 搜索下载（curl+jq），搜索反应 GIF / 创建视觉内容 | curl+jq |
| `heartmula` | 开源 Suno-like 音乐生成模型：歌词+标签生成完整歌曲，多语言 | Python |
| `songsee` | 音频频谱/特征可视化（mel、chroma、MFCC、tempogram 等），Go 编写 | Go CLI |
| `youtube-content` | 获取 YouTube 视频字幕并转换为结构化内容（章节/摘要/线程/博客/引用） | `youtube-transcript-api` |

**用法示例：**

### gif-search
```bash
curl -s "https://tenor.googleapis.com/v2/search?q=thumbs+up&limit=5&key=${TENOR_API_KEY}" | jq -r '.results[].media_formats.gif.url'
URL=$(curl -s "https://tenor.googleapis.com/v2/search?q=celebration&limit=1&key=${TENOR_API_KEY}" | jq -r '.results[0].media_formats.gif.url'); curl -sL "$URL" -o celebration.gif
```

### heartmula
```bash
git clone https://github.com/HeartMuLa/heartlib.git && cd heartlib
uv venv --python 3.10 .venv && . .venv/bin/activate && uv pip install -e .
python ./examples/run_music_generation.py --model_path=./ckpt --version="3B" --lyrics=./assets/lyrics.txt --tags=./assets/tags.txt --save_path=./assets/output.mp3
```

### songsee
```bash
songsee track.mp3                                    # 基本频谱
songsee track.mp3 --viz spectrogram,mel,chroma,hpss,loudness,tempogram,mfcc,flux  # 全特征
songsee track.mp3 --start 12.5 --duration 8 -o slice.jpg  # 时间切片
```

### youtube-content
```bash
python3 SKILL_DIR/scripts/fetch_transcript.py "https://youtube.com/watch?v=VIDEO_ID"
python3 SKILL_DIR/scripts/fetch_transcript.py "URL" --text-only --timestamps
python3 SKILL_DIR/scripts/fetch_transcript.py "URL" --language tr,en
```

---

## 12. mlops (机器学习运维)

### 训练 (Training)

| Skill | 描述 | 方法 |
|-------|------|------|
| `axolotl` | LLM 微调：LoRA/QLoRA、DPO/KTO/ORPO/GRPO、FSDP、DeepSpeed、多模态，100+ 模型 YAML 配置 | Axolotl |
| `peft` | 参数高效微调：LoRA、QLoRA、IA3、Prefix Tuning，多 adapter 服务 | PEFT/HuggingFace |
| `pytorch-fsdp` | PyTorch FSDP 全分片数据并行：参数分片/混合精度/CPU offload/FSDP2 | PyTorch FSDP |
| `trl-fine-tuning` | TRL 微调：SFT（指令调优）、DPO（偏好对齐）、PPO/GRPO（奖励优化）、奖励模型训练 | TRL |
| `unsloth` | 快速微调：2-5x 训练加速、50-80% 内存降低、LoRA/QLoRA 优化 | Unsloth |
| `grpo-rl-training` | GRPO/RL 微调：推理和任务特定模型训练 | TRL GRPO |

**用法示例：**

### axolotl
```yaml
# YAML 配置文件定义微调任务
model:
  base_model: meta-llama/Llama-3.1-8B
  name: LoraName
peft:
  target_modules: [q_proj, k_proj, v_proj, o_proj]
  r: 16
```

### peft
```python
from peft import get_peft_model, LoraConfig, TaskType
lora_config = LoraConfig(task_type=TaskType.CAUSAL_LM, r=16, lora_alpha=32, target_modules=["q_proj", "v_proj"])
model = get_peft_model(base_model, lora_config)
model.print_trainable_parameters()  # trainable%: 0.17%

# QLoRA (70B 单卡 24GB GPU)
from transformers import BitsAndBytesConfig
bnb_config = BitsAndBytesConfig(load_in_4bit=True, bnb_4bit_quant_type="nf4", bnb_4bit_compute_dtype="bfloat16")
model = AutoModelForCausalLM.from_pretrained("meta-llama/Llama-3.1-70B", quantization_config=bnb_config)
```

### trl-fine-tuning
```python
# SFT 微调
from trl import SFTTrainer, SFTConfig
trainer = SFTTrainer(model="Qwen/Qwen2.5-0.5B", train_dataset=dataset, args=SFTConfig(output_dir="Qwen2.5-0.5B-SFT"))
trainer.train()

# DPO 偏好对齐
from trl import DPOTrainer, DPOConfig
trainer = DPOTrainer(model=model, args=DPOConfig(output_dir="model-dpo", beta=0.1), train_dataset=preference_dataset)
trainer.train()
```

### unsloth
```bash
# 2-5x 加速，50-80% 内存降低
# 参考 peft 用法，替换为 Unsloth 优化版本
```

---

### 推理 (Inference)

| Skill | 描述 | 特点 |
|-------|------|------|
| `gguf` | GGUF 格式 + llama.cpp 量化：2-8bit 量化，CPU/GPU 推理，Apple Silicon 支持 | llama.cpp |
| `guidance` | 约束生成：正则/语法控制 JSON/XML/code 输出，多步工作流 | Guidance (Microsoft) |
| `llama-cpp` | CPU/Apple Silicon/消费级 GPU 运行 LLM：GGUF 量化、1.5-8bit | llama.cpp |
| `obliteratus` | 移除 LLM 拒绝行为：使用机械解释技术（diff-in-means/SVD/LEACE/SAE 分解）切除安全 guardrail | OBLITERATUS |
| `outlines` | 结构化输出：保证有效 JSON/XML/code，Pydantic 类型安全输出，本地/远程模型 | Outlines (dottxt.ai) |
| `vllm` | 高吞吐 LLM 服务：PagedAttention、连续 batching、OpenAI 兼容 API、GPTQ/AWQ/FP8 量化、张量并行 | vLLM |

**用法示例：**

### gguf
```bash
python convert_hf_to_gguf.py ./model --outfile model-f16.gguf    # 转为 GGUF
./llama-quantize model-f16.gguf model-q4_k_m.gguf Q4_K_M         # Q4_K_M 量化
./llama-cli -m model-q4_k_m.gguf -p "Hello, how are you?"        # CLI 推理
```

### llama-cpp
```bash
./llama-cli -m models/llama-2-7b-chat.Q4_K_M.gguf -p "Explain quantum computing" -n 256
./llama-server -m model.gguf --port 8080 -ngl 32                 # OpenAI 兼容服务器
make LLAMA_METAL=1 && ./llama-cli -m model.gguf -ngl 999        # Apple Silicon GPU 加速
```

### vllm
```bash
vllm serve meta-llama/Llama-3-8B-Instruct --gpu-memory-utilization 0.9 --max-model-len 8192 --port 8000
```

```python
from vllm import LLM, SamplingParams
llm = LLM(model="meta-llama/Llama-3-8B-Instruct", tensor_parallel_size=2)
outputs = llm.generate(prompts, SamplingParams(temperature=0.7, max_tokens=512))
```

### guidance
```python
from guidance import models, gen, select
lm = models.Anthropic("claude-sonnet-4-5-20250929")
lm += "Email: " + gen("email", regex=r"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}")
lm += "Sentiment: " + select(["positive", "negative", "neutral"], name="sentiment")
```

### outlines
```python
import outlines
class User(BaseModel):
    name: str
    age: int
    email: str
model = outlines.models.transformers("microsoft/Phi-3-mini-4k-instruct")
generator = outlines.generate.json(model, User)
user = generator("Extract: John Doe, 30, john@example.com")

# Regex 约束
generator = outlines.generate.regex(model, r"[0-9]{3}-[0-9]{3}-[0-9]{4}")
```

### obliteratus
```bash
obliteratus obliterate <model_name> --method advanced --output-dir ./abliterated-models
obliteratus obliterate <model_name> --method advanced --quantization 4bit --large-model --output-dir ./abliterated-models
obliteratus recommend <model_name>   # 获取推荐参数
```

---

### 模型 (Models)

| Skill | 描述 | 功能 |
|-------|------|------|
| `clip` | 视觉-语言模型：零样本图像分类、图文匹配、跨模态检索 | OpenAI CLIP |
| `segment-anything` | 图像分割基础模型：点/框/掩码提示零样本分割，自动生成所有物体掩码 | SAM (Meta) |
| `stable-diffusion` | 文生图：Stable Diffusion 模型（HuggingFace Diffusers），图生图/重绘/定制扩散 pipeline | Diffusers |
| `whisper` | 语音识别：99 语言支持、转录、翻译、语种识别，6 种模型规模（tiny→large） | OpenAI Whisper |

**用法示例：**

### clip
```python
image = preprocess(Image.open("photo.jpg")).unsqueeze(0).to(device)
text = clip.tokenize(["a dog", "a cat", "a bird"]).to(device)
logits_per_image, _ = model(image, text)
probs = logits_per_image.softmax(dim=-1).cpu().numpy()
```

### segment-anything
```python
# 点提示分割
masks, scores, logits = predictor.predict(point_coords=np.array([[500, 375]]), point_labels=np.array([1]), multimask_output=True)

# 自动生成所有掩码
mask_generator = SamAutomaticMaskGenerator(sam)
masks = mask_generator.generate(image)

# 框提示
masks, scores, logits = predictor.predict(box=np.array([425, 600, 700, 875]), multimask_output=False)
```

### stable-diffusion
```python
from diffusers import DiffusionPipeline
import torch
pipe = DiffusionPipeline.from_pretrained("stable-diffusion-v1-5/stable-diffusion-v1-5", torch_dtype=torch.float16).to("cuda")
image = pipe("A serene mountain landscape at sunset", num_inference_steps=50, guidance_scale=7.5).images[0]

# 图生图
from diffusers import AutoPipelineForImage2Image
pipe = AutoPipelineForImage2Image.from_pretrained("stable-diffusion-v1-5", torch_dtype=torch.float16).to("cuda")
image = pipe(prompt="A watercolor painting", image=init_image, strength=0.75).images[0]
```

### whisper
```bash
whisper audio.mp3 --model medium --language en --task transcribe
whisper audio.mp3 --model large --language zh --task translate   # 翻译为英文
```

---

### 部署 (Deployment)

| Skill | 描述 | 平台 |
|-------|------|------|
| `modal` | 无服务器 GPU 云平台：ML 负载按需 GPU，无需基础设施管理，自动扩缩容 | Modal |

**用法示例：**

### modal
```python
import modal
app = modal.App("hello-gpu")

@app.function(gpu="T4")
def gpu_info():
    import subprocess
    return subprocess.run(["nvidia-smi"], capture_output=True, text=True).stdout

@app.cls(gpu="A10G", image=image)
class TextGenerator:
    @modal.enter()
    def load_model(self):
        from transformers import pipeline
        self.pipe = pipeline("text-generation", model="gpt2", device=0)
    @modal.method()
    def generate(self, prompt: str) -> str:
        return self.pipe(prompt, max_length=100)[0]["generated_text"]
```

---

### 评估 (Evaluation)

| Skill | 描述 | 标准 |
|-------|------|------|
| `evaluating-llms-harness` | LLM 评估：60+ 学术基准（MMLU/HumanEval/GSM8K/TruthfulQA/HellaSwag），支持 HuggingFace/vLLM/API 后端 | lm-evaluation-harness |
| `weights-and-biases` | ML 实验跟踪：自动日志/实时可视化/超参优化/sweeps/模型注册 | W&B |

**用法示例：**

### evaluating-llms-harness
```bash
lm_eval --model hf --model_args pretrained=meta-llama/Llama-2-7b-hf --tasks mmlu,gsm8k,hellaswarm,truthfulqa --num_fewshot 5 --batch_size 8 --output_path results/llama2-7b-eval.json

# vLLM 后端（5-10x 更快）
lm_eval --model vllm --model_args pretrained=meta-llama/Llama-2-7b-hf,tensor_parallel_size=2 --tasks mmlu --batch_size auto
```

---

### 研究 (Research)

| Skill | 描述 | 框架 |
|-------|------|------|
| `dspy` | 声明式 AI 系统编程：自动优化 prompts，模块化 RAG 和 Agent，Stanford NLP | DSPy |

**用法示例：**

### dspy
```python
class QA(dspy.Signature):
    question = dspy.InputField()
    answer = dspy.OutputField(desc="often between 1 and 5 words")

qa = dspy.Predict(QA)
response = qa(question="What is the capital of France?")

# Chain of Thought
cot = dspy.ChainOfThought(MathProblem)
result = cot(problem="If John has 5 apples and gives 2 to Mary...")

# RAG Pipeline
class MultiHopQA(dspy.Module):
    def __init__(self):
        self.retrieve = dspy.Retrieve(k=3)
        self.generate_query = dspy.ChainOfThought("question -> search_query")
        self.generate_answer = dspy.ChainOfThought("context, question -> answer")
```

---

## 13. note-taking (笔记)

| Skill | 描述 | 存储 |
|-------|------|------|
| `obsidian` | 读取/搜索/创建 Obsidian 保险库中的笔记 | Obsidian vault |

**用法示例：**

### obsidian
```bash
cat "$VAULT/Note Name.md"                              # 读取笔记
grep -rli "keyword" "$VAULT" --include="*.md"         # 搜索内容
cat > "$VAULT/New Note.md"                             # 创建笔记
```

---

## 14. productivity (生产力)

| Skill | 描述 | 功能 |
|-------|------|------|
| `google-workspace` | Gmail/Calendar/Drive/Contacts/Sheets/Docs 集成（OAuth2） | Google Workspace API |
| `linear` | 通过 GraphQL API 管理 Linear issues/projects/teams（API key 认证） | Linear GraphQL |
| `nano-pdf` | 自然语言 PDF 编辑：修改文本/修复错别字/更新标题（`nano-pdf edit <file> <page> "<instruction>"`） | nano-pdf CLI |
| `notion` | Notion API：创建/管理 pages/databases/blocks（curl） | Notion API v2025-09-03 |
| `ocr-and-documents` | PDF 文本提取：远程 URL→`web_extract`，本地文本 PDF→pymupdf，扫描文档→marker-pdf OCR | pymupdf/marker-pdf |
| `powerpoint` | PPTX 处理：读取（markitdown）、编辑（解包→修改→打包）、从头创建（pptxgenjs） | Python + pptxgenjs |

**用法示例：**

### google-workspace
```bash
$GAPI gmail search "is:unread newer_than:1d"           # 搜索邮件
$GAPI calendar create --summary "Meeting" --start 2026-03-01T10:00:00-06:00 --end 2026-03-01T10:30:00-06:00  # 创建日历
$GAPI sheets get SHEET_ID "Sheet1!A1:D10"             # 读取表格
```

### linear
```bash
curl -s -X POST https://api.linear.app/graphql -H "Authorization: $LINEAR_API_KEY" -H "Content-Type: application/json" -d '{"query": "{ issues(first: 20) { nodes { identifier title } } }"}'
```

### nano-pdf
```bash
nano-pdf edit deck.pdf 1 "Change the title to 'Q3 Results'"
nano-pdf edit report.pdf 3 "Update the date from January to February 2026"
nano-pdf edit contract.pdf 2 "Change 'Acme Corp' to 'Acme Industries'"
```

### notion
```bash
curl -s -X POST "https://api.notion.com/v1/search" -H "Authorization: Bearer $NOTION_API_KEY" -H "Notion-Version: 2025-09-03" -d '{"query": "page title"}'
curl -s -X POST "https://api.notion.com/v1/pages" -H "Authorization: Bearer $NOTION_API_KEY" -H "Notion-Version: 2025-09-03" -H "Content-Type: application/json" -d '{"parent": {"database_id": "xxx"}, "properties": {"Name": {"title": [{"text": {"content": "New Item"}}]}}}'
```

### ocr-and-documents
```bash
# 扫描 PDF OCR
python SKILL_DIR/scripts/extract_marker.py scanned.pdf

# 文本 PDF 提取
python SKILL_DIR/scripts/extract_pymupdf.py document.pdf

# 远程 URL
web_extract(url="https://example.com/doc.pdf")
```

---

## 15. red-teaming (红队)

| Skill | 描述 | 技术 |
|-------|------|------|
| `godmode` | Jailbreak LLM：G0DM0D3 技术、PARSELTONGUE 输入混淆（33 种技术）、GODMODE CLASSIC 系统提示模板、ULTRAPLINIAN 多模型竞赛 | 多种绕过技术 |

**用法示例：**

### godmode
```bash
# Parseltongue 混淆查询
python scripts/parseltongue.py "How do I hack into a WiFi network?" --tier standard

# 多模型竞赛
python -c "
from godmode import race_models
result = race_models(query='Explain SQL injection', tier='standard', api_key=...)
"
```

---

## 16. research (研究)

| Skill | 描述 | 数据源 |
|-------|------|-------|
| `arxiv` | arXiv 论文搜索/获取（免费 REST API，无需 API key） | arXiv API |
| `blogwatcher` | RSS/Atom 博客监控：`blogwatcher-cli` 工具，支持 OPML 导入/HTML 抓取/已读未读跟踪 | blogwatcher-cli |
| `llm-wiki` | Karpathy LLM Wiki 模式：构建持久化 markdown 知识库，3 层架构（原始来源→wiki 页面→schema） | 本地文件 |
| `polymarket` | Polymarket 预测市场数据查询：搜索市场/价格/订单簿/历史（公开 API，无需认证） | Polymarket REST API |
| `research-paper-writing` | ML/AI 论文端到端流水线：实验设计→分析→起草→修订→投稿，覆盖 NeurIPS/ICML/ICLR/ACL/AAAI/COLM | 多工具集成 |

**用法示例：**

### arxiv
```bash
curl -s "https://export.arxiv.org/api/query?search_query=all:GRPO+reinforcement+learning&max_results=5&sortBy=submittedDate"
curl -s "https://export.arxiv.org/api/query?id_list=2402.03300"
python scripts/search_arxiv.py "transformer attention" --max 10 --sort date
```

### blogwatcher
```bash
blogwatcher-cli add "My Blog" https://example.com
blogwatcher-cli scan
blogwatcher-cli articles --blog "My Blog" --category "Engineering"
blogwatcher-cli read 1           # 标记已读
blogwatcher-cli import subscriptions.opml  # 从 Feedly/Inoreader 导入
```

### llm-wiki
```bash
read_file "$WIKI/index.md"                              # 读取索引
# Ingest: 1) web_extract 抓取来源  2) 检查现有页面  3) 写入 wiki 页面  4) 更新索引
```

### polymarket
```bash
curl -s "https://gamma-api.polymarket.com/markets?search=AI+regulation"
curl -s "https://clob.polymarket.com/orderbook?clobTokenIds=[\"12345\",\"67890\"]"
curl -s "https://clob.polymarket.com/price-history?conditionId=0x..."
```

---

## 17. smart-home (智能家居)

| Skill | 描述 | 设备 |
|-------|------|------|
| `openhue` | 控制飞利浦 Hue 灯光/房间/场景：`openhue get/set` 命令 | OpenHue CLI |

**用法示例：**

### openhue
```bash
openhue set light "Bedroom Lamp" --on --brightness 50         # 开灯并调亮度
openhue set light "Bedroom Lamp" --on --temperature 300        # 暖色调
openhue set room "Bedroom" --on --brightness 20 --temperature 450  # 睡前模式
```

---

## 18. social-media (社交媒体)

| Skill | 描述 | 功能 |
|-------|------|------|
| `xitter` | X/Twitter 交互：`x-cli` 工具，发布/读取时间线/搜索/点赞/转发/书签/提及（需要 X API 凭证） | x-cli |

**用法示例：**

### xitter
```bash
x-cli tweet post "hello world"                   # 发推
x-cli tweet search "AI agents" --max 20          # 搜索推文
x-cli -j user get openai                         # JSON 输出
```

---

## 19. software-development (软件开发)

### 开发方法论

| Skill | 描述 | 核心原则 |
|-------|------|---------|
| `plan` | Plan 模式：检查上下文→写入 markdown 计划到 `.hermes/plans/`→**不执行工作** | 只规划不执行 |
| `subagent-driven-development` | 子 Agent 驱动开发：每个任务启动新 delegate_task，两阶段审查（spec 合规→代码质量） | 新鲜子 agent per 任务 |
| `systematic-debugging` | 系统化调试：4 阶段根因调查（根因→模式分析→假设→实现），**根因未明不修复** | 铁律：无根因不修复 |
| `test-driven-development` | TDD 测试先行：RED-GREEN-REFACTOR 循环，**无失败测试不写生产代码** | 铁律：无测试不写代码 |
| `writing-plans` | 编写实现计划：详细任务拆分（每任务 2-5 分钟），精确文件路径，完整代码示例 | 完整实现计划 |

**用法示例：**

### plan
```python
# 使用 write_file 保存计划
write_file(path=".hermes/plans/2026-04-18_143000-auth-module.md", content="""
# 目标：重构 auth 模块使用 JWT
# 步骤：1) 分析现有代码  2) 设计 JWT 结构  3) 逐步替换  4) 测试
""")
# plan 模式不执行任何代码/命令
```

### systematic-debugging
```bash
pytest tests/test_module.py::test_name -v --tb=long          # 复现问题
git log --oneline -10 && git diff                            # 查看最近变更
search_files("function_name(", path="src/", file_glob="*.py")  # 追踪数据流
```
```python
# 铁律：先调查根因，不直接修复
delegate_task(goal="Investigate why test fails", context="Follow systematic-debugging: 1) read error  2) reproduce  3) trace data flow  4) report findings only")
```

### test-driven-development
```python
# RED — 先写失败测试
def test_retries_failed_operations_3_times():
    attempts = 0
    def operation():
        nonlocal attempts
        attempts += 1
        if attempts < 3:
            raise Exception('fail')
        return 'success'
    result = retry_operation(operation)
    assert result == 'success'
    assert attempts == 3

# GREEN — 验证测试通过
pytest tests/test_feature.py::test_specific_behavior -v

# REFACTOR — 重构后再跑全量测试
pytest tests/ -q
```

### writing-plans
```markdown
### Task 1: 创建 User 模型

**文件：** src/models/user.py

**Step 1: 写失败测试**
def test_user_has_email():
    user = User(email="test@example.com")
    assert user.email == "test@example.com"

**Step 2: 运行测试**
Run: pytest tests/test_user.py::test_user_has_email -v
Expected: FAIL — "User not defined"

**Step 3: 写最小实现**
class User:
    def __init__(self, email):
        self.email = email
```

### subagent-driven-development
```python
# 1. 派发实现任务
delegate_task(goal="Implement Task 1: Create User model", context="TASK: Create src/models/user.py with email field. FOLLOW TDD.", toolsets=['terminal', 'file'])

# 2. Spec 合规审查
delegate_task(goal="Verify implementation matches spec", context="SPEC: User model with email\nOUTPUT: PASS or list spec gaps", toolsets=['file'])

# 3. 代码质量审查
delegate_task(goal="Review code quality", context="FILES: src/models/user.py\nOUTPUT: APPROVED or REQUEST_CHANGES", toolsets=['file'])
```

---

### 质量保障

| Skill | 描述 | 流程 |
|-------|------|------|
| `dogfood` | 系统化探索 QA 测试：5 阶段（计划→探索→收集证据→分类→报告），浏览器自动化，issue 定级（Critical/High/Medium/Low） | 探索性 QA |
| `requesting-code-review` | 提交前审查流水线：静态安全扫描→基线测试→自审→独立审查→评估→自动修复→提交 | 8 步审查流程 |

**用法示例：**

### dogfood
```python
browser_navigate(url="https://example.com/page")
browser_vision(question="Describe the page layout, identify any visual issues", annotate=True)
browser_console(clear=True)
```

### requesting-code-review
```bash
git diff --cached | grep "^+" | grep -iE "(api_key|secret|password|token)"   # 静态安全扫描
python -m pytest --tb=no -q 2>&1 | tail -5                                 # 基线测试对比
git add -A && git commit -m "[verified] <description>"                      # 验证后提交
```
```python
delegate_task(goal="Review the git diff and return ONLY valid JSON", context="<static_scan_results> <code_changes> Return: {\"passed\": bool, \"security_concerns\": [], \"logic_errors\": []}", toolsets=["terminal"])
```

---

## 附录：Skill 加载规则

### 触发条件
系统会自动扫描消息，当任务匹配某个 skill 的描述时自动加载。也可以手动加载：

```
/skill <name>        # 在会话中加载
hermes -s <name>     # 命令行预加载
```

### Skill 文件位置
- 用户安装: `~/.hermes/skills/`
- 项目级: `./.hermes/skills/`

### Skill 结构（每个 skill 目录）
```
skill-name/
├── SKILL.md           # 主文件（YAML frontmatter + markdown 正文）
└── references/        # 参考文档（可选）
    ├── api.md
    └── examples.md
```

### YAML Frontmatter 字段
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

---

## 快速索引

### 按用途快速查找

| 你想做的事 | 推荐 Skill |
|-----------|----------|
| 让 Claude Code 帮我写代码 | `claude-code` |
| 查 GitHub PR/Issues | `github-*` 系列 |
| 生成架构图 | `architecture-diagram` |
| 生成 ASCII 艺术/视频 | `ascii-art` / `ascii-video` |
| 做 ML 模型微调 | `axolotl` / `peft` / `unsloth` |
| 部署 LLM API 服务 | `vllm` / `llama-cpp` |
| 评估模型质量 | `evaluating-llms-harness` |
| 量化压缩模型 | `gguf` |
| 控制 Hue 灯光 | `openhue` |
| 查找附近地点 | `find-nearby` |
| 管理邮件 | `himalaya` |
| 发 iMessage | `imessage` |
| 发送 Twitter | `xitter` |
| 调试 bug | `systematic-debugging` |
| 写测试先行 | `test-driven-development` |
| 做研究调研 | `arxiv` / `polymarket` |
| 写论文 | `research-paper-writing` |
| 生成音乐 | `heartmula` / `songwriting-and-ai-music` |
| 提取 YouTube 字幕 | `youtube-content` |

---

*最后更新: 2026-04-18 | Hermes Agent 内置 Skill 知识库*
