# The Kung Fu of Self-Improving Agents

> Five levels. Five papers. One path to agents that get better on their own.

I've been reading a lot of agent papers lately. Most of the discourse is about making agents *smarter* — better prompts, better models, better tool use. But I think there's a much more interesting question hiding in plain sight:

**Can we build agents that continuously get better?**

Not "better because we retrained the base model." Better because the *agent itself* learned from its own experience, extracted reusable skills, and kept improving in a loop. You know, the way humans actually get good at things.

Turns out, if you line up a handful of recent papers in the right order, a remarkably clean picture emerges. There are five distinct problems you need to solve, stacked on top of each other like levels in a video game. And — I swear I'm not forcing this — they map almost perfectly onto how martial artists train in kung fu movies.

```
Level 1  DreamGym .............. Training Ground
             ↓
Level 2  Agent Lightning ....... Training System
             ↓
Level 3  SkillRL ............... Technique Extraction
             ↓
Level 4  SAGE .................. Art Refinement
             ↓
Level 5  Group-Evolving Agents . School of Martial Arts
```

Let me walk through each one.

---

## Level 1: Where Does Experience Come From?

### [DreamGym](https://arxiv.org/abs/2511.03773)

Ok so here's the thing about agent RL that people don't talk about enough: **the bottleneck is not the algorithm. It's the data.**

In classic RL this isn't really a problem. You have Atari, MuJoCo, whatever — you can generate millions of transitions basically for free. The environment is fast, deterministic-ish, and cheap to run.

Agents are a completely different story. A single task might involve browsing the web, calling APIs, doing multi-step reasoning, filling out forms. One rollout can take dozens of steps and cost real money (LLM inference isn't free). So you run into this very practical wall: you just can't generate enough experience to train on.

DreamGym's key insight is dead simple:

> The thing agents lack isn't better algorithms. It's **experience supply**.

So they build what is essentially an **experience factory**. Not just a replay buffer — a system that synthesizes entire tasks, interaction trajectories, and feedback signals from scratch. Think of it as a gym where the sparring partners, the challenges, and the scoring are all generated on demand.

**The kung fu analogy:** DreamGym is a training ground. You show up, and there's always a fresh opponent to spar with, a new drill to practice, instant feedback on what you did right and wrong. The moment you can generate experience at scale, the whole bottleneck starts to crack open.

---

## Level 2: How Does Experience Enter Training?

### [Agent Lightning](https://arxiv.org/abs/2508.03680)

Ok so now you have experience. Great. But here's a problem that's almost embarrassing: **most agent systems can't actually be trained.**

Why? Because real-world agents are messy engineering systems. You've got an LLM, tool calls, a retrieval pipeline, maybe some multi-agent orchestration — the whole thing is held together by Python scripts and API calls. It was built to *do tasks*, not to *learn from doing tasks*. There's no loss function. There's no gradient path. It's like having a race car with no way to tune the engine.

Agent Lightning's core idea is to **separate the doing from the learning**. The agent execution system and the training system become two independent layers. The execution side just does its thing — browses, codes, calls tools. The training side watches, decomposes the trajectory into trainable transitions, and figures out credit assignment (which specific decision led to success or failure?).

This sounds like infrastructure work, and it is. But it's *critical* infrastructure. Because once you have it, a very powerful thing becomes possible: **any agent system can be plugged into RL training.** You don't need to redesign your agent. You just need to observe it.

**The kung fu analogy:** Think of a martial artist who fights every day but never reviews tape. They have tons of combat experience, but no system to break down what happened, what worked, what didn't. Agent Lightning is the coaching staff — they watch every fight, decompose every move, and turn raw combat footage into structured training drills. Without this step, experience stays experience. It never becomes technique.

---

## Level 3: How Does Experience Become Capability?

### [SkillRL](https://arxiv.org/abs/2602.08234)

Here's something counterintuitive: **more experience doesn't automatically make agents better.**

Raw trajectories are noisy. A successful task completion might include five redundant steps, two lucky guesses, and one actually-clever decision. If you just train on all of it, the agent learns noise along with signal. It's like trying to learn cooking by memorizing entire recipe videos frame-by-frame, including the part where the chef drops the spoon.

SkillRL's insight is that what agents should learn are **skills**, not trajectories.

They introduce something called **SkillBank** — a system that automatically mines raw experience for reusable behavioral patterns and stores them as discrete skills. After this extraction step, the agent doesn't think in terms of "do step 1, then step 2, then step 3." It thinks in terms of "apply skill A, then skill B." It can compose skills, transfer them across tasks, even learn entirely new ones.

This is a subtle but massive shift. The unit of learning changes from *a sequence of actions* to *a reusable behavior*. That's the difference between memorizing a chess game move-by-move and actually understanding the Sicilian Defense.

**The kung fu analogy:** You've fought a thousand fights. Now it's time to sit down and distill all that chaos into actual techniques. Not "I kicked him on Tuesday and it worked" — more like "here's a reliable counter when the opponent overcommits." This is where raw experience crystallizes into real martial arts.

---

## Level 4: How Do Skills Participate in Evolution?

### [SAGE](https://arxiv.org/abs/2512.17102)

So you have a skill library. Cool. But here's the problem with most skill library approaches: **the skills just sit there.** They're stored, maybe retrieved, but they never get *better*. The skill library is a read-only database. It's not part of the training loop.

SAGE fixes this by doing something that sounds obvious in retrospect but is technically quite hard: it puts skills **inside the RL training loop itself.**

Two key moves:

1. **Sequential task training.** The agent runs through a series of related tasks back-to-back. Skills generated from early tasks get reused in later ones. This creates a natural curriculum where skills compound.

2. **Skills in the reward function.** The system doesn't just reward task completion — it explicitly rewards *effective skill usage*. This means the agent has incentive not just to solve the problem, but to solve it using clean, reusable techniques.

The training objective shifts from "complete this task" to "complete this task *and* improve your skill library in the process." For the first time, you get genuine **skill-level self-improvement**.

**The kung fu analogy:** This is where martial arts training gets serious. You don't just know a technique — you refine it across hundreds of different fights. The same kick, applied in different contexts, gradually becomes sharper, faster, more reliable. Your art is evolving.

---

## Level 5: One Agent Isn't Enough

### Group-Evolving Agents

Once an agent can self-improve, you hit the next wall: **exploration is hard.**

The strategy space is enormous. A single agent, no matter how good its self-improvement loop, can only explore a tiny fraction of what's possible. It's going to get stuck in local optima. It's going to miss entire categories of strategies that could be great.

The fix is almost obvious once you see it: **don't train one agent. Train a population.**

Different agents explore different strategies. They share discoveries. The best skills propagate across the group while weak strategies get pruned. It's evolution, but at the level of learned behaviors rather than neural network weights.

**The kung fu analogy:** This is where you go from a solo practitioner to an entire school. Different students explore different fighting styles — one focuses on speed, another on grappling, another on weapon techniques. They share what works. The school's collective knowledge grows far faster than any individual could manage alone. That's how martial arts traditions actually develop in the real world.

---

## The Full Stack

Put it all together and you get a clean five-layer architecture for self-improving agents:

```
┌──────────────────────────────────────────────────┐
│          Self-Evolving Agent Stack                │
├──────────────────────────────────────────────────┤
│                                                  │
│  ┌────────────────────────────────────────────┐  │
│  │  Level 1 · DreamGym                        │  │
│  │  Experience synthesis — the training ground │  │
│  └─────────────────┬──────────────────────────┘  │
│                    ↓                              │
│  ┌─────────────────┴──────────────────────────┐  │
│  │  Level 2 · Agent Lightning                 │  │
│  │  Training infrastructure — the coach        │  │
│  └─────────────────┬──────────────────────────┘  │
│                    ↓                              │
│  ┌─────────────────┴──────────────────────────┐  │
│  │  Level 3 · SkillRL                         │  │
│  │  Skill extraction — distilling techniques   │  │
│  └─────────────────┬──────────────────────────┘  │
│                    ↓                              │
│  ┌─────────────────┴──────────────────────────┐  │
│  │  Level 4 · SAGE                            │  │
│  │  Skill-driven evolution — refining the art  │  │
│  └─────────────────┬──────────────────────────┘  │
│                    ↓                              │
│  ┌─────────────────┴──────────────────────────┐  │
│  │  Level 5 · Group-Evolving Agents           │  │
│  │  Population evolution — the school          │  │
│  └────────────────────────────────────────────┘  │
│                                                  │
└──────────────────────────────────────────────────┘
```

Each layer solves a specific problem. Each layer depends on the one below it. Miss any one of them and the whole thing falls apart.

---

## A Paradigm Shift in Progress

Here's what I think is really going on.

The old way of building AI systems looks like this:

```
data → train model → deploy
```

It's a one-shot pipeline. You collect data, you train, you ship. If the model isn't good enough, you collect more data and train again. The model itself never gets better after deployment.

The self-evolving agent paradigm looks like this:

```
experience → skills → policy → continuous evolution
```

The system is never "done." It's always in a training loop. It generates its own experience, extracts its own skills, improves its own policy, and — at the highest level — does all of this as a group.

This is a genuinely different thing. We're not building models anymore. We're building systems that grow.

If this trajectory continues (and I think it will), future agents will have:
- Their own experience generation systems
- Their own skill libraries that evolve over time
- Continuous training loops that never stop
- Population-level collaboration and co-evolution

In other words: **agents won't just be trained. They'll train themselves.**

And honestly? That's the most exciting thing happening in AI right now.

---

<p align="center">
  <a href="../README.md">← Back to Home</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="self-evolving-agent-martial-arts.md">中文版 →</a>
</p>
