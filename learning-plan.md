# 个人学习计划（初始化版）

> 计划来源：AI × Web3 School Learning Agent 启动 Prompt + Handbook。

## 学习原则
- 轻量优先：先完成每天最小可执行路径。
- 可验证：所有任务都尽量留下可检查证据（链接、截图、日志、提交记录）。
- 开源沉淀：将问题、解法、反馈写入仓库，形成长期资产。
- 安全第一：私钥仅用于测试网；严禁在仓库中提交私钥、助记词、API Key。

## 路径设计

### 1) 最小路径（Daily MVP）
- 阅读 1 个 Handbook 节点（20–30 分钟）
- 输出 3 条关键笔记 + 1 个问题
- 完成 1 条 daily check-in 草稿

### 2) 推荐路径（稳态进步）
- 每周完成：
  - AI 基础 2 节
  - Web3 基础 2 节
  - AI × Web3 Bridge 1 节
- 每周提交 1 条 handbook feedback
- 每周完成 1 个小任务（task）或小实验（experiment）

### 3) 挑战路径（Hackathon 导向）
- 2 周内确定项目方向（如 Agent Wallet / AI Security / Governance）
- 4 周内完成 PoC（可运行或可演示）
- 6–8 周形成公开提交材料（文档 + demo + 复盘）

## 第一周每日学习计划（2026-05-19 ～ 2026-05-25）

### Day 1（2026-05-19）：AI 核心概念与 Prompts 高阶实战
**今日目标**：理解 LLM 的能力边界，掌握能够让 AI 稳定输出符合预期代码的提示词技巧。

**具体做什么**
- 理论学习：搞懂 LLM 为什么会幻觉，以及什么是 Tool Use (Function Calling)——这是 AI 能跟 Web3 钱包/合约交互的核心。
- 动手实践：在 ChatGPT/Claude 或 Cursor 中测试系统级 Prompt。尝试让 AI 扮演一个“严格输出 JSON 格式的 Web3 链上数据解析器”。

**参考材料**
- OpenAI / Anthropic 官方文档：《Prompt Engineering Guide》（重点看 System Prompts 和 Structured Outputs 部分）。
- 学习主题：LLM Function Calling 机制原理（理解 AI 是如何决定何时调用外部 API 的）。

### Day 2（2026-05-20）：Web3 基础设施与测试网通关
**今日目标**：把 Web3 的链上概念吃透，为 AI 代理（Agent）准备好“手和脚”。

**具体做什么**
- 理论学习：弄清 EOA 钱包（如 MetaMask）、私钥、公钥、签名（Signature）的本质。理解为什么 AI 自动交易需要签名，以及 Gas 费的构成。
- 动手实践：生成一个专门用于测试的全新钱包（切勿使用存有资产的私钥！）。配置好测试网（如 Sepolia 或 Arbitrum Sepolia），寻找 Faucet（水龙头）领取测试币，并手动完成一笔转账。

**参考材料**
- 基础概念：《Mastering Ethereum》关于账户和交易的章节。
- 实用工具：Chainlist（用于添加测试网）、搜索 Sepolia Faucet 领水指南。

### Day 3（2026-05-21）：AI Coding 与环境初始化（Cursor / Windsurf）
**今日目标**：搭建 Vibe Coding 环境，让 AI 成为主力副驾驶。

**具体做什么**
- 工具配置：下载并配置 Cursor 或 Windsurf。配置好 AI API Key（或使用内置 AI）。
- 环境初始化：使用 AI 引导，在本地初始化基本开发环境（Node.js 或 Python），安装 Web3 交互基础库（如 ethers.js、viem 或 web3.py）。
- 初试 Vibe Coding：用自然语言命令 AI：“帮我写一个脚本，连接到 Sepolia 测试网，并打印出我 Day 2 钱包的测试币余额。” 观察代码并运行。

**参考材料**
- 工具文档：Cursor 官方文档中的 @symbols 和 Composer 功能指南。
- 库文档：ethers.js 或 viem 的 Quick Start 极简入门。

### Day 4（2026-05-22）：Hermes Agent 与智能体框架拆解
**今日目标**：攻克课程核心主角——Hermes Agent（或相关 AI Agent 框架）。

**具体做什么**
- 代码通读：登录课程平台，下载 Week 1 对应的 Hermes Agent 示例代码或 GitHub 仓库。
- 架构拆解：让 Cursor 解释 Agent 核心逻辑：如何接收自然语言指令？tools 文件夹定义了哪些能力（如 transfer_token、get_balance）？
- 本地运行：配置 `.env` 环境变量（测试网私钥、RPC 节点链接），在本地把 Agent 跑起来。

**参考材料**
- 官方材料：WCB 学习面板中 Week 1 的 GitHub Readme 和讲解视频。
- 进阶概念：LangChain / LangGraph 中 “ReAct (Reasoning and Acting)” 模式介绍。

### Day 5（2026-05-23）：链上智能体交互实践（核心打卡点）
**今日目标**：让 AI Agent 真正去链上完成任务。

**具体做什么**
- 下达指令：例如“帮我把 0.01 个测试币转账给地址 XXXXX，并在转账成功后告诉我交易哈希。”
- 监控过程：紧盯终端 Logs，观察 AI 执行链路：Thought -> Call Tool -> Observation -> Final Answer。
- Debug 与调整：若报错（Gas 不够、RPC 报错、Prompt 误解），用 AI 辅助排查并修正。

**参考材料**
- 链上浏览器：Etherscan（Sepolia），验证交易哈希是否真实上链。

### Day 6（2026-05-24）：智能合约的 AI 部署与调用
**今日目标**：跨越到合约层，完成「AI 自动部署/调用智能合约」。

**具体做什么**
- 合约编写：用 Cursor 配合 Remix，让 AI 协助写一个最简单的 ERC20 或 Greeting 合约。
- Agent 升级：扩充 Hermes Agent，增加新 Tool，赋予其“部署合约”或“调用指定合约函数”的能力。
- 测试反馈：测试 Agent 能否通过一句“帮我查一下 A 合约里当前的最新状态”自动完成调用。

**参考材料**
- 开发工具：Remix IDE（remix.ethereum.org）。

### Day 7（2026-05-25）：整理 Case、复盘与提交任务
**今日目标**：沉淀成果，完成 Week 1 学分闭环。

**具体做什么**
- 案例收集：整理本周 1 个成功案例、1 个失败/报错案例（如 AI 死循环、误解指令），以及你如何进行 Human-in-the-loop 修正。
- 录制/截图：将 Agent 在终端运行过程截图，或录制 30 秒 GIF/视频。
- 成果提交：同步整理 `daily/`、`tasks/`、`experiments/`、`submissions/` 内容并完成打卡。

## 每周节奏模板
- 周一：计划与目标拆解
- 周二～周四：学习 + 实验 + 任务执行
- 周五：总结 + feedback 提交草稿
- 周末：Hackathon 方向推进与下周计划
