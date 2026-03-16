# Awesome Agentic RL

> 关于 **Agentic 强化学习** 的论文、框架与深度解读合集 — 让 LLM Agent 在交互中学会行动、规划与自我进化。

<p align="center">
  <a href="README.md"><img src="https://img.shields.io/badge/English-blue?style=for-the-badge" alt="English"></a>
  <a href="README_CN.md"><img src="https://img.shields.io/badge/中文-red?style=for-the-badge" alt="中文"></a>
</p>

---

## 第一章 | 自进化 Agent：从经验到精通

Agentic RL 最前沿的方向不只是让 Agent 更聪明，而是让它们 **持续自我进化**。最新研究揭示了一条清晰的五层技术栈，恰好对应武学修炼的五个阶段：

<table>
<tr>
<th align="center">🔬 Agent 进化路线</th>
<th align="center">⚔️ 武功修炼路线</th>
</tr>
<tr>
<td align="center">

```
           ┌───────────────────┐
     1     │ DreamGym          │
           │ 经验生成           │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     2     │ Agent Lightning   │
           │ 训练基础设施       │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     3     │ SkillRL           │
           │ 技能抽象           │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     4     │ SAGE              │
           │ 技能驱动进化       │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     5     │ Group-Evolving    │
           │ Agents · 群体进化  │
           └───────────────────┘
```

</td>
<td align="center">

```
           ┌───────────────────┐
     1     │ 练功房             │
           │ 模拟对练 积累经验   │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     2     │ 训练体系           │
           │ 拆解动作 复盘得失   │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     3     │ 招式总结           │
           │ 提炼有效套路       │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     4     │ 武学进化           │
           │ 反复打磨 精进招式   │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     5     │ 门派共创           │
           │ 集体创造武学       │
           └───────────────────┘
```

</td>
</tr>
</table>

> **想看完整的武功修炼故事？** 点击阅读：
> **[AI 练武记：Self-Improving Agent 的五层武学体系 →](docs/self-evolving-agent-martial-arts.md)**

| 层级 | 系统 | 论文 | 核心思想 |
|:----:|------|------|---------|
| 1 | **DreamGym** | [arXiv 2511.03773](https://arxiv.org/abs/2511.03773) | 经验合成 — 规模化生成任务、轨迹和反馈 |
| 2 | **Agent Lightning** | [arXiv 2508.03680](https://arxiv.org/abs/2508.03680) | 训练-执行解耦 — 让任何 Agent 系统都能接入 RL 训练 |
| 3 | **SkillRL** | [arXiv 2602.08234](https://arxiv.org/abs/2602.08234) | SkillBank — 将原始轨迹蒸馏为可复用技能 |
| 4 | **SAGE** | [arXiv 2512.17102](https://arxiv.org/abs/2512.17102) | 技能增强 RL — 技能进入训练闭环和奖励函数 |
| 5 | **Group-Evolving Agents** | — | 群体进化 — 多 Agent 共同探索、共享技能 |

---

## 第二章 | 经验学习与技能学习（2025–2026 前沿方向）

这一方向研究 Agent 如何从经验中持续学习并形成可复用能力。核心问题包括：经验的规模化生成、技能抽象、以及让技能进入 RL 训练闭环。

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **DreamGym** | [2511.03773](https://arxiv.org/abs/2511.03773) | 经验合成框架 — 将合成经验从 transition 级提升到 agent 任务级 |
| **SkillRL** | [2602.08234](https://arxiv.org/abs/2602.08234) | SkillBank + 技能蒸馏 — 将经验抽象为可迁移技能 |
| **SAGE** | [2512.17102](https://arxiv.org/abs/2512.17102) | 技能增强 RL + 技能集成奖励 — 技能随策略同步进化 |
| **SynthER** | [2303.06614](https://arxiv.org/abs/2303.06614) | 基于扩散模型的经验合成 — 直接生成经验分布 |
| **Agent Lightning** | [2508.03680](https://arxiv.org/abs/2508.03680) | 训练-执行解耦 — 为现有 Agent 系统无侵入接入 RL 训练 |

---

## 第三章 | Agent RL：从 RLHF 到智能体优化

语言模型如何在多步交互中学习策略。从单轮 RLHF 到完整的 Agentic RL — 规划、工具调用与反馈闭环的演进。

### 3.1 基础 Agent RL

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **InstructGPT** | [2203.02155](https://arxiv.org/abs/2203.02155) | RLHF 训练范式（SFT + Reward Model + PPO）— 奠定 LLM 后训练基础 |
| **WebGPT** | [2112.09332](https://arxiv.org/abs/2112.09332) | RL 训练的网页浏览 Agent — 早期 Agent RLHF 实践 |
| **ReAct** | [2210.03629](https://arxiv.org/abs/2210.03629) | 推理 + 行动交替框架 — 定义了现代 Agent 推理模式 |
| **Toolformer** | [2302.04761](https://arxiv.org/abs/2302.04761) | 自监督工具调用学习 — 开启 tool-use 学习路线 |
| **DreamerV3** | [2301.04104](https://arxiv.org/abs/2301.04104) | 通用 world model RL — 证明"在想象中训练"可以跨任务工作 |

### 3.2 进阶优化与奖励设计

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **DPO** | [2305.18290](https://arxiv.org/abs/2305.18290) | 直接偏好优化 — 无需单独训练奖励模型 |
| **Let's Verify Step by Step** | [2305.20050](https://arxiv.org/abs/2305.20050) | 过程奖励模型 — 对每个推理步骤给予奖励，而非仅奖励最终结果 |
| **DeepSeek-R1** | [2501.12948](https://arxiv.org/abs/2501.12948) | GRPO（群组相对策略优化）— 用 RL 训练长链推理能力 |
| **Agent-R1** | [2511.14460](https://arxiv.org/abs/2511.14460) | 端到端 Agent RL 训练框架 — 统一训练流水线 |
| **RLAIF** | [2212.08073](https://arxiv.org/abs/2212.08073) | Constitutional AI — 用 AI 反馈替代人类标注进行 RL 训练 |

---

## 第四章 | Agent 应用：Web、Code 与 Tool

在真实世界中交互的 Agent 方法 — 浏览网页、编写代码、调用外部 API。*（仅收录方法论文，不含评测集。）*

### 4.1 Web Agents

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **WebGPT** | [2112.09332](https://arxiv.org/abs/2112.09332) | RL 训练的网页浏览 Agent，结合人类反馈 |
| **DigiRL** | [2406.11896](https://arxiv.org/abs/2406.11896) | 自主 RL 训练真实设备 UI Agent — in-the-wild 数字 Agent |
| **AgentQ** | [2408.07199](https://arxiv.org/abs/2408.07199) | MCTS 搜索 + 自我批评 + DPO — Web Agent 规划 |
| **AWM** | [2409.07429](https://arxiv.org/abs/2409.07429) | Agent Workflow Memory — 从网页经验中归纳可复用工作流 |

### 4.2 Code Agents

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **CodeRL** | [2207.01780](https://arxiv.org/abs/2207.01780) | Actor-Critic 结合单元测试反馈训练代码生成 |
| **SWE-agent** | [2405.15793](https://arxiv.org/abs/2405.15793) | Agent-Computer Interface — Agent 在真实仓库中使用 shell 与编辑器 |
| **CodeAct** | [2402.01030](https://arxiv.org/abs/2402.01030) | 可执行代码作为统一 Agent 动作 — 代码执行与 LLM 推理交替进行 |
| **OpenHands** | [2407.16741](https://arxiv.org/abs/2407.16741) | AI 软件开发者开放平台，支持 RL 微调 Agent |

### 4.3 Tool-Using Agents

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **Gorilla** | [2305.15334](https://arxiv.org/abs/2305.15334) | 检索增强减少 API 调用幻觉 |
| **HuggingGPT** | [2303.17580](https://arxiv.org/abs/2303.17580) | LLM 作为控制器 — 通过任务规划调度专家模型 |
| **AnyTool** | [2402.04253](https://arxiv.org/abs/2402.04253) | 自反思 Agent — 层级检索实现大规模 API 选择 |
| **ToolkenGPT** | [2305.11554](https://arxiv.org/abs/2305.11554) | 工具即 Token — 将工具嵌入 LLM 词表实现高效工具调用 |

---

## 第五章 | 经典 RL 基础

Agentic RL 的算法基石：从价值学习、策略梯度到基于模型的规划。

### 5.1 基于价值的方法

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **Q-learning** | [Watkins 1992](https://link.springer.com/article/10.1007/BF00992698) | Off-policy TD 更新 — value-based RL 的基础算法 |
| **DQN** | [Mnih et al. 2015](https://www.nature.com/articles/nature14236) | 深度神经网络 + Q-learning — 开启 Deep RL 时代 |

### 5.2 策略梯度方法

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **REINFORCE** | [Williams 1992](https://link.springer.com/article/10.1007/BF00992696) | 策略梯度定理 — 所有策略优化方法的基础 |
| **A3C** | [1602.01783](https://arxiv.org/abs/1602.01783) | 异步 Actor-Critic — 并行训练稳定收敛 |
| **TRPO** | [1502.05477](https://arxiv.org/abs/1502.05477) | 信赖域约束 — 保证策略单调改进 |
| **PPO** | [1707.06347](https://arxiv.org/abs/1707.06347) | Clip 目标函数 — 简单、稳定、高效（RLHF 的核心算法） |
| **SAC** | [1801.01290](https://arxiv.org/abs/1801.01290) | 最大熵 RL — 自动平衡探索与利用 |

### 5.3 基于模型与规划的方法

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **AlphaZero** | [1712.01815](https://arxiv.org/abs/1712.01815) | 自我对弈 + MCTS — 从零知识达到围棋/国际象棋超人水平 |
| **MuZero** | [1911.08265](https://arxiv.org/abs/1911.08265) | 学习的 world model + 规划 — 不知道规则也能精通游戏 |
| **DreamerV3** | [2301.04104](https://arxiv.org/abs/2301.04104) | 通用 world model RL — 单一配置跨领域通用 |

---

## License

本仓库仅供教育和研究参考使用。

## Contributing

欢迎贡献！可以通过 Issue 或 Pull Request 添加新论文、修正链接或改进描述。
