# 🔓 Claude Code 隐藏功能清单

> 基于源码分析挖掘出的所有未发布功能、隐藏命令、彩蛋和安全机制
> 
> ⚠️ 本文档基于公开泄露源码整理，仅供学习参考，请勿用于商业目的

---

## 🤖 8 个未发布功能 (Unreleased Features)

### 1. Virtual Pet 🐾
**状态**: 代码已完成，尚未发布

> 每个用户都有独特的虚拟宠物，显示在终端提示符旁边。
> 宠物的物种、稀有度和性格从你的账户 ID 生成——所以你的 Buddy 是独一无二的。

**相关源码**: `buddy/` 目录

---

### 2. 记忆模式 (Memory Mode)
**状态**: 概念阶段

> 一种常驻模式，Claude 跨会话记住所有内容。
> 它会记录每天的对话内容，并在后台"做梦"——在你睡觉时自动整理记忆成有用的笔记。

---

### 3. 探索模式 (Explorer Mode)
**状态**: 云端实现中

> 对于复杂任务，Claude 会启动一个单独的云端实例进行探索和规划，最多 30 分钟。
> 你可以在浏览器中审查和批准计划后再执行。

---

### 4. 协调者模式 (Coordinator Mode)
**状态**: 源码中存在

> Claude 变成一个经理。
> 它把任务分解成多个部分，分配给并行运行的独立 worker agent，然后合并结果。

---

### 5. 跨会话通信 (Cross-Session Messaging)
**状态**: 源码中存在

> 如果你的机器上有多个 Claude 会话在运行，它们可以互相发送消息——就像 AI agent 团队聊天。

---

### 6. 远程控制 (Remote Control)
**状态**: 已实现部分功能

> 在本地运行 Claude，但从手机或 claude.ai 网页端控制。
> 权限、模型切换、工具批准都会实时同步。
> 现在可以通过 claude.ai 网页界面使用。

---

### 7. 守护进程模式 (Daemon Mode)
**状态**: 源码中存在

> 像系统服务一样在后台运行 Claude 会话。
> 可以列出、检查日志、重新附加或终止它们——就像 `docker ps` 管理 AI agent。

---

### 8. 自动做梦 (Auto-Dream)
**状态**: 概念阶段

> 在会话之间，Claude 会回顾它学到的东西，把零散的笔记整理成干净、结构化的记忆文件——就像学生在夜里复习闪卡。

---

## ⌨️ 26 个隐藏斜杠命令 (Hidden Slash Commands)

源码中存在的斜杠命令，但不在 `--help` 中显示：

| 命令 | 描述 |
|------|------|
| `/ask` | 向 Claude 提问 |
| `/bug` | 报告 bug |
| `/clear` | 清除上下文 |
| `/compact` | 压缩上下文 |
| `/debug` | 调试模式 |
| `/doctor` | 健康检查 |
| `/dump` | 导出会话 |
| `/help` | 帮助（可见） |
| `/model` | 切换模型（可见） |
| `/mcp` | MCP 服务器管理 |
| `/study` | 学习模式 |
| `/test` | 运行测试 |
| `/verbose` | 详细输出 |
| `/web` | 网页搜索 |
| `/think` | 思考模式 |
| `/review` | 代码审查 |
| `/refactor` | 重构建议 |
| `/explain` | 解释代码 |
| `/snapshot` | 保存快照 |
| `/restore` | 恢复快照 |
| `/session` | 会话管理 |
| `/skills` | 技能管理 |
| `/system` | 系统命令 |
| `/trace` | 追踪模式 |
| `/upgrade` | 升级检查 |
| `/version` | 版本信息 |

---

## 🚩 32 个构建时功能标志 (Build-Time Feature Flags)

编译到二进制中的功能开关：

| 标志 | 描述 |
|------|------|
| `CLAUDE_CODE_SIMPLE` | 简化模式 |
| `DISABLE_THINKING` | 禁用思考 |
| `DISABLE_COMPACT` | 禁用压缩 |
| `DISABLE_AUTO_MEMORY` | 禁用自动记忆 |
| `DISABLE_BACKGROUND_TASKS` | 禁用后台任务 |
| `CLAUDE_CODE_ABLATION_BASELINE` | 剥离所有安全功能 |
| `ANTI_DISTILLATION_CC` | 反蒸馏保护 |
| `NATIVE_CLIENT_ATTESTATION` | 原生客户端认证 |
| `ENABLE_VOICE_MODE` | 启用语音模式 |
| `CLAUDE_CODE_DISABLE_1M_CONTEXT` | 禁用 1M 上下文 |
| `ALLOW_ANT_COMPUTER_USE_MCP` | 允许电脑使用 |
| `CLAUDE_CODE_PLAN_V2_AGENT_COUNT` | Plan V2 agent 数量 |
| `tengu_malort_pedway` | Computer Use 代号 |
| `tengu_amber_quartz_disabled` | Voice kill switch |
| `tengu_anti_distill_fake_tool_injection` | 假工具注入 |
| `CLAUDE_CODE_SKIP_SCM_CHECK` | 跳过 SCM 检查 |
| `CLAUDE_CODE_EMBED_MODE` | 嵌入模式 |
| `CLAUDE_CODE_DRY_RUN` | 试运行 |
| `CLAUDE_CODE_LOCAL` | 本地模式 |
| `CLAUDE_CODE_TEAM` | 团队模式 |
| `CLAUDE_CODE_PRO` | Pro 模式 |
| `CLAUDE_CODE_MAX` | Max 模式 |
| `FORCE_COLOR` | 强制彩色输出 |
| `NO_VERIFY` | 跳过验证 |
| `STRIP_ansi` | 去除 ANSI |
| `ENABLE_EXPERIMENTAL` | 实验功能 |
| `ENABLE_BETA` | Beta 功能 |
| `ENABLE_CANARY` | Canary 版本 |
| `DISABLE_TELEMETRY` | 禁用遥测 |
| `DISABLE_UPDATES` | 禁用更新 |
| `DEBUG_LOGGING` | 调试日志 |
| `TRACE_REQUESTS` | 追踪请求 |

---

## 🌱 GrowthBook 功能门控 (GrowthBook Feature Gates)

渐进式发布开关（`tengu_*` 命名空间）：

| 功能 | 描述 |
|------|------|
| `tengu_*` | 遥测相关 |
| `tengu_malort_*` | Computer Use 相关 |
| `tengu_voice_*` | 语音相关 |
| `tengu_dream_*` | 自动做梦 |
| `tengu_plan_v2_*` | Plan V2 相关 |

---

## 🔐 秘密环境变量 (Secret Environment Variables)

### Debug & Profiling
| 变量 | 描述 |
|------|------|
| `CLAUDE_CODE_DEBUG` | 调试模式 |
| `CLAUDE_CODE_TRACE` | 追踪请求 |
| `CLAUDE_CODE_VERBOSE` | 详细输出 |

### Runtime Overrides
| 变量 | 描述 |
|------|------|
| `CLAUDE_CODE_PLAN_V2_AGENT_COUNT` | Plan V2 并行 agent 数量（免费=1，Max/Team=3）|
| `CLAUDE_CODE_DISABLE_1M_CONTEXT` | 强制禁用 1M token 上下文（HIPAA 合规）|
| `CLAUDE_CODE_SIMPLE` | 简化模式 |

### Safety Bypass (⚠️ 危险)
| 变量 | 描述 |
|------|------|
| `CLAUDE_CODE_ABLATION_BASELINE=1` | 一键关闭所有安全功能！同时启用：SIMPLE、DISABLE_THINKING、DISABLE_COMPACT、DISABLE_AUTO_MEMORY、DISABLE_BACKGROUND_TASKS |
| `CLAUDE_CODE_SKIP_SAFETY` | 跳过安全检查 |

### Anthropic Internal
| 变量 | 描述 |
|------|------|
| `USER_TYPE=ant` | Anthropic 员工构建版本 |
| `ALLOW_ANT_COMPUTER_USE_MCP` | 员工绕过电脑使用限制 |

### API Beta Headers
| 变量 | 描述 |
|------|------|
| `cli-internal-2026-02-09` | ANT-ONLY beta header |

### Hardcoded SDK API Keys
> 这些 SDK key 硬编码在二进制中，用于特定的 Anthropic 环境。**不是用户凭证**。

---

## 😱 有趣彩蛋 (Not So Fun Facts)

### 🕵️ Undercover Mode - 隐藏员工身份

当 Anthropic 员工在公共仓库贡献代码时，一个隐蔽系统会自动去除所有 AI 痕迹：
- Commit 信息
- Co-Authored-By 行
- Model name

Prompt 里写着：**"别暴露你的身份"**

```typescript
// 源码注释
Do not blow your cover.
Strip all AI evidence from commits.
```

---

### 🐰 Capybara 编码 - 内部代号混淆

内部模型代号 `capybara` 被保护到用编码形式存储：

```javascript
String.fromCharCode(99,97,112,121,98,97,114,97)
// 解析: "capybara"
```

原因：一个物种名和 excluded-strings.txt 中的 model-codename canary 冲突了 😂

---

### 🎯 YOLO 自动权限系统

auto-permission 系统的函数名叫 `classifyYoloAction()`：

| 风险等级 | 描述 |
|----------|------|
| `LOW` | 自动批准 |
| `MEDIUM` | 需要确认 |
| `HIGH` | 拒绝 |

系统用 Claude 自己来判断是否自动批准自己的工具使用。

---

### 📊 Tengu 遥测 - 1000+ 事件类型

每个动作都被记录到 Anthropic 服务器，前缀是 `Tengu`：

- 工具授权
- 工具拒绝
- YOLO 决策
- 会话性能
- 订阅等级
- 环境信息

**无法永久关闭**——即使在 undercover mode 下也会记录。

---

### 🖥️ Computer Use 代号 "Chicago"

全 GUI 自动化（鼠标、点击、截图）被关卡在：
```
tengu_malort_pedway
```

员工通过设置 `ALLOW_ANT_COMPUTER_USE_MCP` 绕过。

---

### 🔮 下一代模型已出现在代码中

Undercover prompt 警告员工永远不要泄露：
- **opus-4-7**
- **sonnet-4-8**

这些还没公开的版本已经在代码里被提到了！

---

### 🏢 22 个秘密仓库暴露

Undercover allowlist 揭示了 22 个私有仓库：

```
anthropics/casino
anthropics/trellis
anthropics/forge-web
anthropics/mycro_manifests
anthropics/feldspar-testing
...
```

---

### 🔇 Voice Mode 开关 - Amber Quartz

语音模式存在 OAuth 认证和一个紧急开关：
```
tengu_amber_quartz_disabled
```

暗示语音模式仍在积极测试中。

---

### 💰 Web Search 费用

每个网页搜索请求固定收费 **$0.01**，与 token 费用分开计算。

---

### 🛡️ Anti-Distillation - 反蒸馏系统

Anthropic 建立了反蒸馏系统，会向竞争对手发送**假工具定义**防止他们用 Claude 的输出训练。

开关：`ANTI_DISTILLATION_CC` + `tengu_anti_distill_fake_tool_injection`

---

### 🔏 每个请求的指纹

每个 API 请求都带有 3 字符的十六进制指纹：
```
SHA256(SALT + msg[4] + msg[7] + msg[20] + version)[:3]
```

Salt 是硬编码的：`59cf53e54c78`

---

### 💥 一键关闭所有安全

设置 `CLAUDE_CODE_ABLATION_BASELINE=1` 会同时：
- 启用 `CLAUDE_CODE_SIMPLE`
- 禁用 `DISABLE_THINKING`
- 禁用 `DISABLE_COMPACT`
- 禁用 `DISABLE_AUTO_MEMORY`
- 禁用 `DISABLE_BACKGROUND_TASKS`

这是一个研究模式，把 Claude 剥离到裸机。

---

### 🚨 紧急 Opus 开关伪装成负载消息

硬编码的 `CUSTOM_OFF_SWITCH_MESSAGE`：
> "Opus is experiencing high load, please use /model to switch to Sonnet"

实际上它是容量关闭开关。

---

### ⚡ 原生客户端认证 (Zig 编写)

`NATIVE_CLIENT_ATTESTATION` 会在每个请求体中注入占位符：
```
cch=c2dd6
```

Bun 的原生 HTTP 栈（用 Zig 编写）会用计算出的哈希覆盖它——证明请求来自真实的二进制。

---

### 🤖 转录分类器 - Claude 评判自己的工具安全

在 auto-mode 下，一个转录分类器把完整对话发送给一个 side-query LLM 调用，决定是否自动批准工具使用。

为 Anthropic 员工和外部用户加载不同的权限模板。

---

### 🔑 API Key 前缀运行时组装

秘密扫描器把 Anthropic API key 前缀组装成：
```javascript
['sk', 'ant', 'api'].join('-')
```

为什么？因为字面字符串被自家 `excluded-strings` 构建检查禁止了。

---

### 📝 转储模式 - 记录所有 API 调用

对于 `USER_TYPE=ant` 构建，`createDumpPromptsFetch()` 会包装每个 API 调用，把完整请求体和流式响应写入：
```
~/.claude/dump-prompts/.jsonl
```

---

### 🐛 GrowthBook SDK 太烂自己写缓存

两个标注 `WORKAROUND` 的注释说明 GrowthBook 的 `evalFeature()` 忽略了远程评估的预计算值。

Anthropic 不得不在上面构建自己的缓存层。

---

### 🐾 所有物种名 Hex 编码

buddy 宠物系统的**所有物种名**都编码成 `String.fromCharCode()` 序列。

注释解释：一个物种名和 `excluded-strings.txt` 中的 model-codename canary 冲突。

---

### 🔗 内部短链接和仓库名泄露

源码注释引用了：
- `go/cc-logging`
- `go/taxonomy`
- `go/ccshare`
- `anthropics/anthropic#274559`

暴露了内部工具 URL 和 monorepo 结构。

---

## 📚 参考资料

- **隐藏功能清单网站**: https://cc-hidden-deploy.vercel.app/
- **源码备份仓库**: https://github.com/instructkr/claude-code
- **AI奶爸整理**: https://github.com/zstmfhy/Claude-code
- **本文档仓库**: https://github.com/zhang588/claude-code-leak

---

> ⚠️ 本文档基于公开泄露源码分析整理，内容可能不准确、不完整或已过时。
> 功能细节和时间线是推测性的，可能永远不会发布。
> 这是一个非官方的社区资源，与 Anthropic 无关，也未得到其认可。
>
> 仅供教育和研究目的，在合理使用原则下分享。

---

*🤖 最后更新: 2026-04-01*
*整理: Claude Code Leak 分析*
