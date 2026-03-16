# Awesome Agentic RL

> A curated collection of papers, frameworks, and insights on **Agentic Reinforcement Learning** — where LLM-based agents learn to act, plan, and self-improve through interaction.

<p align="center">
  <a href="README.md"><img src="https://img.shields.io/badge/English-blue?style=for-the-badge" alt="English"></a>
  <a href="README_CN.md"><img src="https://img.shields.io/badge/中文-red?style=for-the-badge" alt="中文"></a>
</p>

---

## Chapter 1 | Self-Evolving Agents: From Experience to Mastery

The most exciting frontier in Agentic RL isn't just making agents smarter — it's making them **continuously self-improving**. Recent research reveals a clear five-level technical stack, which maps beautifully onto a martial arts training analogy:

<table>
<tr>
<th align="center">🔬 Agent Learning Evolution</th>
<th align="center">⚔️ Martial Arts Analogy</th>
</tr>
<tr>
<td align="center">

```
           ┌───────────────────┐
     1     │ DreamGym          │
           │ Exp. Synthesis    │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     2     │ Agent Lightning   │
           │ Training Infra    │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     3     │ SkillRL           │
           │ Skill Abstraction │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     4     │ SAGE              │
           │ Skill-Augmented   │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     5     │ Group-Evolving    │
           │ Agents            │
           └───────────────────┘
```

</td>
<td align="center">

```
           ┌───────────────────┐
     1     │ Training Ground   │
           │ Practice Sparring │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     2     │ Training System   │
           │ Record & Review   │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     3     │ Technique Distill │
           │ Extract Patterns  │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     4     │ Art Refinement    │
           │ Polish Techniques │
           └────────┬──────────┘
                    ↓
           ┌────────┴──────────┐
     5     │ Clan Co-Creation  │
           │ Collective Growth │
           └───────────────────┘
```

</td>
</tr>
</table>

> **Want the full story?** Read the complete martial arts guide:
> **[The Kung Fu of Self-Improving Agents →](docs/self-evolving-agent-martial-arts-en.md)**

| Level | System | Paper | Core Idea |
|:-----:|--------|-------|-----------|
| 1 | **DreamGym** | [arXiv 2511.03773](https://arxiv.org/abs/2511.03773) | Experience synthesis — generate tasks, trajectories, and feedback at scale |
| 2 | **Agent Lightning** | [arXiv 2508.03680](https://arxiv.org/abs/2508.03680) | Training-Agent Disaggregation — plug RL into any agent framework |
| 3 | **SkillRL** | [arXiv 2602.08234](https://arxiv.org/abs/2602.08234) | SkillBank — distill raw trajectories into reusable skills |
| 4 | **SAGE** | [arXiv 2512.17102](https://arxiv.org/abs/2512.17102) | Skill-augmented RL — skills enter the training loop and reward function |
| 5 | **Group-Evolving Agents** | — | Population-based evolution — multiple agents co-explore and share skills |

---

## Chapter 2 | Experience Learning & Skill Learning (2025–2026 Frontier)

This direction studies how agents **learn from experience and form reusable capabilities**. Core problems: experience synthesis at scale, skill abstraction, and closing the skill-RL training loop.

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **DreamGym** | [2511.03773](https://arxiv.org/abs/2511.03773) | Experience synthesis framework — lifts synthetic experience from transition-level to agent-task-level |
| **SkillRL** | [2602.08234](https://arxiv.org/abs/2602.08234) | SkillBank + skill distillation — abstracts experience into transferable skills |
| **SAGE** | [2512.17102](https://arxiv.org/abs/2512.17102) | Skill-augmented RL with skill-integrated reward — skills evolve alongside policy |
| **SynthER** | [2303.06614](https://arxiv.org/abs/2303.06614) | Diffusion-based experience synthesis — generates experience distributions directly |
| **Agent Lightning** | [2508.03680](https://arxiv.org/abs/2508.03680) | Training-Agent Disaggregation — non-invasive RL plug-in for existing agent systems |

---

## Chapter 3 | Agent RL: From RLHF to Agentic Optimization

How language models learn policies through multi-step interaction. The evolution from single-turn RLHF to full agentic RL with planning, tool use, and feedback loops.

### 3.1 Foundational Agent RL

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **InstructGPT** | [2203.02155](https://arxiv.org/abs/2203.02155) | RLHF paradigm (SFT + Reward Model + PPO) — foundation of LLM post-training |
| **WebGPT** | [2112.09332](https://arxiv.org/abs/2112.09332) | RL-trained agent for web browsing and information retrieval — early agent RLHF |
| **ReAct** | [2210.03629](https://arxiv.org/abs/2210.03629) | Reasoning + Acting interleaved framework — defined modern agent reasoning |
| **Toolformer** | [2302.04761](https://arxiv.org/abs/2302.04761) | Self-supervised tool-call learning — opened the tool-use learning route |
| **DreamerV3** | [2301.04104](https://arxiv.org/abs/2301.04104) | Universal world model RL — "training in imagination" works across tasks |

### 3.2 Advanced Optimization & Reward

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **DPO** | [2305.18290](https://arxiv.org/abs/2305.18290) | Direct Preference Optimization — removes the need for a separate reward model |
| **Let's Verify Step by Step** | [2305.20050](https://arxiv.org/abs/2305.20050) | Process reward models — reward each reasoning step, not just the final answer |
| **DeepSeek-R1** | [2501.12948](https://arxiv.org/abs/2501.12948) | GRPO (Group Relative Policy Optimization) — RL for long-chain reasoning |
| **Agent-R1** | [2511.14460](https://arxiv.org/abs/2511.14460) | End-to-end agent RL training framework — unified pipeline |
| **RLAIF** | [2212.08073](https://arxiv.org/abs/2212.08073) | Constitutional AI — RL from AI feedback, reducing human annotation cost |

---

## Chapter 4 | Agent Applications: Web, Code & Tool

Methods for building agents that interact with the real world — browsing websites, writing code, and calling external APIs. *(Benchmarks excluded; methods only.)*

### 4.1 Web Agents

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **WebGPT** | [2112.09332](https://arxiv.org/abs/2112.09332) | RL-trained web browsing agent with human feedback |
| **DigiRL** | [2406.11896](https://arxiv.org/abs/2406.11896) | Autonomous RL for in-the-wild digital agents on device UIs |
| **AgentQ** | [2408.07199](https://arxiv.org/abs/2408.07199) | MCTS-guided search + self-critique + DPO for web agent planning |
| **AWM** | [2409.07429](https://arxiv.org/abs/2409.07429) | Agent Workflow Memory — induces reusable workflows from web experience |

### 4.2 Code Agents

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **CodeRL** | [2207.01780](https://arxiv.org/abs/2207.01780) | Actor-critic with unit test feedback for code generation |
| **SWE-agent** | [2405.15793](https://arxiv.org/abs/2405.15793) | Agent-Computer Interface — agents use shell & editor in real repos |
| **CodeAct** | [2402.01030](https://arxiv.org/abs/2402.01030) | Executable code as unified agent action — interleave code execution with LLM reasoning |
| **OpenHands** | [2407.16741](https://arxiv.org/abs/2407.16741) | Open platform for AI software developers with RL-tuned agent |

### 4.3 Tool-Using Agents

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **Gorilla** | [2305.15334](https://arxiv.org/abs/2305.15334) | Retrieval-augmented generation to reduce API call hallucination |
| **HuggingGPT** | [2303.17580](https://arxiv.org/abs/2303.17580) | LLM as controller — orchestrate expert models via task planning |
| **AnyTool** | [2402.04253](https://arxiv.org/abs/2402.04253) | Self-reflective agent for large-scale API selection with hierarchical retrieval |
| **ToolkenGPT** | [2305.11554](https://arxiv.org/abs/2305.11554) | Tools as tokens — learn tool embeddings in LLM vocabulary for efficient tool calling |

---

## Chapter 5 | Classic RL Foundations

The algorithmic backbone of Agentic RL: from value learning and policy gradients to model-based planning.

### 5.1 Value-Based Methods

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **Q-learning** | [Watkins 1992](https://link.springer.com/article/10.1007/BF00992698) | Off-policy TD update — the foundation of value-based RL |
| **DQN** | [Mnih et al. 2015](https://www.nature.com/articles/nature14236) | Deep neural networks + Q-learning — launched the Deep RL era |

### 5.2 Policy Gradient Methods

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **REINFORCE** | [Williams 1992](https://link.springer.com/article/10.1007/BF00992696) | Policy gradient theorem — basis for all policy optimization |
| **A3C** | [1602.01783](https://arxiv.org/abs/1602.01783) | Asynchronous actor-critic — parallel agents stabilize training |
| **TRPO** | [1502.05477](https://arxiv.org/abs/1502.05477) | Trust region constraint — guarantees monotonic policy improvement |
| **PPO** | [1707.06347](https://arxiv.org/abs/1707.06347) | Clipped objective — simple, stable, and efficient (the workhorse behind RLHF) |
| **SAC** | [1801.01290](https://arxiv.org/abs/1801.01290) | Maximum entropy RL — balances exploration and exploitation automatically |

### 5.3 Model-Based & Planning

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **AlphaZero** | [1712.01815](https://arxiv.org/abs/1712.01815) | Self-play + MCTS — superhuman Go/Chess/Shogi from zero knowledge |
| **MuZero** | [1911.08265](https://arxiv.org/abs/1911.08265) | Learned world model + planning — master games without knowing the rules |
| **DreamerV3** | [2301.04104](https://arxiv.org/abs/2301.04104) | Universal world model RL — single config works across diverse domains |

---

## License

This repository is for educational and research reference purposes.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to add new papers, fix links, or improve descriptions.
