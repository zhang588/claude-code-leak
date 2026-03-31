# Claude Code CLI - 源码泄露备份

> ⚠️ Claude Code CLI 源代码泄露版本的备份仓库

## ⚠️ 免责声明

- Claude Code 是 **Anthropic, PBC.** 的产品
- 本仓库仅用于 **学习和研究目的**
- 源码版权归 Anthropic, PBC. 所有
- 请勿用于商业目的

## 📖 项目简介

这是 **Claude Code CLI** 工具的源代码备份。Claude Code 是一个强大的 AI 编程助手命令行工具，支持多种编程任务自动化。

> 💡 本仓库从 R2 Storage 获取泄露源码，仅做备份存档。

## 🛠 技术栈

| 类别 | 技术 |
|------|------|
| **语言** | TypeScript / TSX |
| **运行时** | Bun |
| **UI 框架** | Ink (React for CLI) |
| **包管理** | Bun |
| **CLI 框架** | Commander.js |
| **终端样式** | Chalk |

## 📁 项目结构

```
├── src/
│   ├── commands/          # 斜杠命令实现 (/commit, /review 等)
│   ├── components/        # UI 组件 (基于 Ink React)
│   │   └── design-system/ # 设计系统组件
│   ├── services/          # 核心服务
│   │   ├── api/          # API 服务
│   │   ├── mcp/          # MCP 协议实现
│   │   └── analytics/    # 分析服务
│   ├── tools/             # 工具实现
│   │   ├── BashTool/     # Shell 命令执行
│   │   ├── FileReadTool/ # 文件读取
│   │   ├── FileEditTool/ # 文件编辑
│   │   ├── GrepTool/     # 代码搜索
│   │   ├── GlobTool/     # 文件匹配
│   │   └── TaskTool/     # 任务代理
│   ├── hooks/             # React Hooks
│   ├── constants/         # 常量定义
│   ├── ink/               # 终端 UI 框架
│   ├── utils/             # 工具函数
│   ├── schemas/           # JSON Schema 定义
│   ├── screens/           # 屏幕组件
│   ├── plugins/           # 插件系统
│   ├── keybindings/       # 快捷键绑定
│   ├── tasks/             # 任务系统
│   ├── context/           # 上下文管理
│   ├── vim/               # Vim 模式
│   ├── buddy/             # 🤖 宠物陪伴系统
│   ├── server/            # 服务器相关
│   ├── remote/            # 远程协作
│   ├── voice/             # 语音功能
│   ├── migrations/        # 数据库迁移
│   ├── skills/            # 技能系统
│   ├── plugins/           # 插件系统
│   └── main.tsx          # 主入口文件 (803KB!)
│
├── QueryEngine.ts         # 查询引擎
├── Task.ts               # 任务定义
├── Tool.ts               # 工具定义
├── commands.ts           # 命令注册中心
├── context.ts            # 上下文管理
├── cost-tracker.ts       # 费用追踪
├── history.ts            # 历史记录
├── setup.ts              # 初始化设置
├── tools.ts              # 工具注册
├── query.ts              # 查询系统 (68KB!)
└── main.tsx              # 主入口 (803KB!)
```

## 🔧 核心功能

### 命令列表

#### Git & 代码管理
| 命令 | 描述 |
|------|------|
| `/commit` | 智能生成 Git 提交 |
| `/review` | 代码审查 |
| `/pr_comments` | PR 评论分析 |
| `/diff` | 差异查看 |
| `/branch` | 分支管理 |

#### 会话管理
| 命令 | 描述 |
|------|------|
| `/resume` | 恢复历史会话 |
| `/session` | 会话管理 |
| `/clear` | 清除对话 |
| `/compact` | 压缩上下文 |
| `/rewind` | 回退操作 |
| `/export` | 导出会话 |

#### 配置 & 设置
| 命令 | 描述 |
|------|------|
| `/config` | 配置管理 |
| `/init` | 初始化项目 |
| `/model` | 切换模型 |
| `/theme` | 主题设置 |
| `/login` | 登录账户 |
| `/logout` | 登出账户 |

#### MCP & 插件
| 命令 | 描述 |
|------|------|
| `/mcp` | MCP 服务器管理 |
| `/plugin` | 插件管理 |
| `/skills` | 技能系统 |

#### 工具 & 诊断
| 命令 | 描述 |
|------|------|
| `/doctor` | 系统诊断 |
| `/cost` | 费用统计 |
| `/usage` | 使用量统计 |
| `/help` | 帮助信息 |
| `/upgrade` | 升级版本 |

#### 模式切换
| 命令 | 描述 |
|------|------|
| `/vim` | Vim 模式 |
| `/plan` | 计划模式 |
| `/fast` | 快速模式 |
| `/permissions` | 权限管理 |
| `/hooks` | 钩子配置 |

## 🏗 架构亮点

### 1. 工具系统 (Tools)
每个工具都是独立模块，包含：
- 输入验证 (JSON Schema)
- 执行逻辑
- 权限控制
- 输出格式化

### 2. 命令系统 (Commands)
支持多种命令类型：
- `prompt` - 提示词命令
- `local` - 本地执行命令
- `dialog` - 对话框命令

### 3. MCP 协议
完整的 Model Context Protocol 实现，支持：
- Stdio 传输
- SSE 传输
- 资源管理
- 工具调用

### 4. 技能系统 (Skills)
可扩展的技能框架：
- 内置技能
- 插件技能
- 自定义技能目录

### 5. 代理系统 (Agents)
多代理协作支持：
- Task 代理
- 并行执行
- 上下文隔离

### 6. Buddy 宠物系统 🤖
内置 ASCII art 宠物陪伴：
- 18 种宠物（duck, cat, dragon...）
- 每种 3 帧动画
- 稀有度系统（common → legendary）
- Soul/Bones 分离设计
- Mulberry32 PRNG 确定性生成

### 7. Vim 模式
完整的 Vim 实现：
- motions（动作）
- operators（操作符）
- text objects（文本对象）
- transitions（状态转换）

## 📊 代码统计

| 指标 | 数量 |
|------|------|
| TypeScript/TSX 文件 | ~1900+ |
| 命令数量 | ~50+ |
| 工具数量 | ~30+ |
| UI 组件 | ~100+ |
| 总代码行数 | ~500,000+ |

### 主要文件大小

| 文件 | 大小 | 描述 |
|------|------|------|
| `main.tsx` | 803 KB | 主入口文件 |
| `query.ts` | 68 KB | 查询系统 |
| `Tool.ts` | 29 KB | 工具定义 |
| `interactiveHelpers.tsx` | 57 KB | 交互助手 |
| `dialogLaunchers.tsx` | 22 KB | 对话框 |

## 💡 学习价值

1. **CLI 应用架构** - 大型命令行工具的设计模式
2. **React 终端 UI** - Ink 框架的实战应用
3. **MCP 协议** - AI 工具互联协议实现
4. **插件系统** - 可扩展架构设计
5. **代理系统** - 多代理协作模式
6. **Vim 实现** - 完整 Vim 模式移植
7. **宠物系统** - PRNG + ASCII 动画

## 📚 参考资源

- [AI奶爸的 Claude Code 分析](https://github.com/zstmfhy/Claude-code) - 详细分析版本
- [Claude Code 官方文档](https://docs.anthropic.com/claude-code)
- [MCP 协议规范](https://modelcontextprotocol.io)

## 📝 License

源代码版权归 **Anthropic, PBC.** 所有。

本仓库仅用于教育目的，请勿用于商业用途。

---

> 📅 最后更新: 2026-04-01
> 📦 源码来源: Claude Code leak (R2 Storage)
> 👤 备份者: zhang588
