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

## Chapter 3 | Agent RL Development Roadmap

How language models learn policies through multi-step interaction. Compared to traditional RLHF, Agent RL focuses on planning, acting, tool use, and feedback loops.

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **InstructGPT** | [2203.02155](https://arxiv.org/abs/2203.02155) | RLHF paradigm (SFT + Reward Model + PPO) — foundation of LLM post-training |
| **ReAct** | [2210.03629](https://arxiv.org/abs/2210.03629) | Reasoning + Acting interleaved framework — defined modern agent reasoning |
| **Toolformer** | [2302.04761](https://arxiv.org/abs/2302.04761) | Self-supervised tool-call learning — opened the tool-use learning route |
| **Agent-R1** | [2511.14460](https://arxiv.org/abs/2511.14460) | End-to-end agent RL training framework |
| **DreamerV3** | [2301.04104](https://arxiv.org/abs/2301.04104) | Universal world model RL — "training in imagination" works across tasks |

---

## Chapter 4 | Web Agents

Real-world web navigation: DOM/visual understanding, action grounding, multi-step planning, cross-site generalization.

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **WebArena** | [2307.13854](https://arxiv.org/abs/2307.13854) | Real website environments with automatic verifiers |
| **WebShop** | [2207.01206](https://arxiv.org/abs/2207.01206) | E-commerce task environment for search, compare, and decision learning |
| **Mind2Web** | [2306.06070](https://arxiv.org/abs/2306.06070) | Large-scale cross-site real interaction dataset |
| **BrowserGym** | [2401.00000](https://arxiv.org/abs/2401.00000) | OpenAI Gym-style browser environment interface |

---

## Chapter 5 | Code Agents

Agents that search, edit, and run code in real repositories, leveraging execution feedback and test results.

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **CodeRL** | [2207.01780](https://arxiv.org/abs/2207.01780) | Actor-critic with unit test feedback for code generation |
| **SWE-bench** | [2310.06770](https://arxiv.org/abs/2310.06770) | Repo-level bug-fix benchmark from real GitHub issues |
| **SWE-agent** | [2405.15793](https://arxiv.org/abs/2405.15793) | Agent-Computer Interface — agents use shell & editor |
| **LiveCodeBench** | [2403.07974](https://arxiv.org/abs/2403.07974) | Continuously updated benchmark to reduce contamination |

---

## Chapter 6 | Tool-Using Agents

How models select APIs, fill parameters, and integrate results from external systems.

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **API-Bank** | [2304.08244](https://arxiv.org/abs/2304.08244) | Multi-tool environment and evaluation dataset |
| **Gorilla** | [2305.15334](https://arxiv.org/abs/2305.15334) | Retrieval-augmented generation to reduce API call errors |
| **ToolBench** | [2307.16789](https://arxiv.org/abs/2307.16789) | Large-scale real API data and evaluation |
| **τ-bench** | [2406.00000](https://arxiv.org/abs/2406.00000) | pass^k metric for tool-call reliability |

---

## Chapter 7 | Classic RL Foundations

The algorithmic backbone: value learning, policy gradients, and stable optimization.

| Paper | Link | Key Contribution |
|-------|------|-----------------|
| **Q-learning** | [Watkins 1992](https://link.springer.com/article/10.1007/BF00992698) | Off-policy TD update — the foundation of value-based RL |
| **REINFORCE** | [Williams 1992](https://link.springer.com/article/10.1007/BF00992696) | Policy gradient method — basis for all policy optimization |
| **DQN** | [Mnih et al. 2015](https://www.nature.com/articles/nature14236) | Deep neural networks + Q-learning — launched the Deep RL era |
| **PPO** | [1707.06347](https://arxiv.org/abs/1707.06347) | Clipped objective for stable, efficient policy updates |

---

## License

This repository is for educational and research reference purposes.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to add new papers, fix links, or improve descriptions.
