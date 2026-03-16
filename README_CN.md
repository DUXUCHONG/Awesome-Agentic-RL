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

## 第三章 | Agent RL 发展路线与代表作

语言模型如何在多步交互中学习策略。相比传统 RLHF，Agent RL 关注规划、行动、工具调用与反馈循环。

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **InstructGPT** | [2203.02155](https://arxiv.org/abs/2203.02155) | RLHF 训练范式（SFT + Reward Model + PPO）— 奠定 LLM 后训练基础 |
| **ReAct** | [2210.03629](https://arxiv.org/abs/2210.03629) | 推理 + 行动交替框架 — 定义了现代 Agent 推理模式 |
| **Toolformer** | [2302.04761](https://arxiv.org/abs/2302.04761) | 自监督工具调用学习 — 开启 tool-use 学习路线 |
| **Agent-R1** | [2511.14460](https://arxiv.org/abs/2511.14460) | 端到端 Agent RL 训练框架 |
| **DreamerV3** | [2301.04104](https://arxiv.org/abs/2301.04104) | 通用 world model RL — 证明"在想象中训练"可以跨任务工作 |

---

## 第四章 | Web Agents

模型如何在真实网页环境中执行复杂任务：DOM/视觉理解、动作 grounding、多步规划、跨网站泛化。

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **WebArena** | [2307.13854](https://arxiv.org/abs/2307.13854) | 真实网站环境 + 自动验证器 |
| **WebShop** | [2207.01206](https://arxiv.org/abs/2207.01206) | 电商任务环境 — 搜索、比较和决策学习 |
| **Mind2Web** | [2306.06070](https://arxiv.org/abs/2306.06070) | 跨网站大规模真实交互数据集 |
| **BrowserGym** | [2401.00000](https://arxiv.org/abs/2401.00000) | 类 OpenAI Gym 的浏览器环境接口 |

---

## 第五章 | Code Agents

模型如何在真实代码仓库中搜索、编辑和运行代码，利用执行反馈和测试结果进行策略学习。

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **CodeRL** | [2207.01780](https://arxiv.org/abs/2207.01780) | Actor-Critic 结合单元测试反馈训练代码生成 |
| **SWE-bench** | [2310.06770](https://arxiv.org/abs/2310.06770) | 从真实 GitHub issue 构建仓库级 bug 修复 benchmark |
| **SWE-agent** | [2405.15793](https://arxiv.org/abs/2405.15793) | Agent-Computer Interface — Agent 使用 shell 与编辑器 |
| **LiveCodeBench** | [2403.07974](https://arxiv.org/abs/2403.07974) | 持续更新题库减少 benchmark 污染 |

---

## 第六章 | Tool-Using Agents

模型如何调用 API 与外部系统：工具选择、参数填写和结果整合。

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **API-Bank** | [2304.08244](https://arxiv.org/abs/2304.08244) | 多工具环境和评测数据集 |
| **Gorilla** | [2305.15334](https://arxiv.org/abs/2305.15334) | 检索增强减少 API 调用错误 |
| **ToolBench** | [2307.16789](https://arxiv.org/abs/2307.16789) | 大规模真实 API 数据与评测 |
| **τ-bench** | [2406.00000](https://arxiv.org/abs/2406.00000) | pass^k 指标衡量工具调用可靠性 |

---

## 第七章 | 经典 RL 论文

Agentic RL 的算法基础：价值学习、策略梯度和稳定优化。

| 论文 | 链接 | 核心贡献 |
|------|------|---------|
| **Q-learning** | [Watkins 1992](https://link.springer.com/article/10.1007/BF00992698) | Off-policy TD 更新 — value-based RL 的基础算法 |
| **REINFORCE** | [Williams 1992](https://link.springer.com/article/10.1007/BF00992696) | 策略梯度方法 — 为后续 policy optimization 奠定基础 |
| **DQN** | [Mnih et al. 2015](https://www.nature.com/articles/nature14236) | 深度神经网络 + Q-learning — 开启 Deep RL 时代 |
| **PPO** | [1707.06347](https://arxiv.org/abs/1707.06347) | Clip objective — 使策略更新稳定高效 |

---

## License

本仓库仅供教育和研究参考使用。

## Contributing

欢迎贡献！可以通过 Issue 或 Pull Request 添加新论文、修正链接或改进描述。
