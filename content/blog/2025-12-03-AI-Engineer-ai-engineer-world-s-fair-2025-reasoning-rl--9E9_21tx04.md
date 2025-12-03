+++
title = "AI Engineer World’s Fair 2025 - Reasoning + RL"
date = 2025-12-03
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Machine learning--Reinforcement learning","Software engineering--Artificial intelligence","Verification"]
tags = ["Reinforcement learning","Automated verification","PO","DPO","GRPO","Majority voting","Reward hacking","Agentic systems","GSM8K","Amy","PyTorch","Unit testing","Formal proofs"]

[extra]
excerpt = "This session at the AI Engineer World’s Fair 2025 dives deep into the practical and philosophical challenges of using reinforcement learning (RL) and reasoning for building trustworthy, agentic AI systems. The speakers advocate for RL as the next frontier for scaling superintelligent systems, emphasizing the necessity of automated verification and fine-grained reward signals—especially in domains like coding and mathematics where correctness can be formally checked."
video_url = "https://www.youtube.com/watch?v=-9E9_21tx04"
video_id = "-9E9_21tx04"
cover = "https://img.youtube.com/vi/-9E9_21tx04/maxresdefault.jpg"
+++

## Overview

This session at the AI Engineer World’s Fair 2025 dives deep into the practical and philosophical challenges of using reinforcement learning (RL) and reasoning for building trustworthy, agentic AI systems. The speakers advocate for RL as the next frontier for scaling superintelligent systems, emphasizing the necessity of automated verification and fine-grained reward signals—especially in domains like coding and mathematics where correctness can be formally checked.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
A distinctive focus is placed on the interplay between RL algorithms (PO, DPO, GRPO), the necessity of automated verification for scalable trust, and the limitations of current evaluation benchmarks. The methodology prioritizes agentic systems that can autonomously generate and verify artifacts, moving beyond synthetic benchmarks to real-world, high-stakes tasks where correctness is non-negotiable.

### The Core Problem
The central challenge addressed is how to reliably train and evaluate large language models and agents in complex, open-ended environments—where reward hacking, evaluation ambiguity, and scaling bottlenecks undermine trust and effectiveness. Existing benchmarks and majority voting approaches fail to generalize to real-world tasks that demand verifiable correctness and robust alignment.

### The Solution Approach
The approach leverages RL algorithms that can estimate fine-grained advantages by comparing divergent rollouts, using automated verification (e.g., unit tests, formal proofs) as a ground truth for reward signals. The workflow involves sampling diverse completions, identifying the precise decision points leading to success or failure, and reinforcing beneficial behaviors without overfitting to narrow benchmarks. The methodology also advocates for building agentic systems with tool-use capabilities (e.g., file editing, code execution) and ongoing, first-class verification baked into the process.

### Key Insights
- Fine-grained advantage estimation in RL (as in PO or GRPO) is crucial for learning from complex, branching tasks—DPO lacks this granularity, making it less effective for nuanced reasoning.
- Automated verification is a prerequisite for scalable, trustworthy AI—majority voting or longer reasoning chains alone are insufficient when correct outputs are rare or hard to identify.
- Reward hacking is a persistent risk; only domains with robust, automated verification (like math or code) allow RL to drive reliable progress.
- Most RL codebases and benchmarks are biased toward math/code tasks due to ease of evaluation, but real-world tasks require more sophisticated reward and verification strategies.
- The next era of LLMs is framed as the 'era of experience,' where RL and agentic tool use, grounded in verifiable outputs, are foundational for superintelligence.

### Concepts & Definitions
- "Advantage" in RL: The difference in reward between two rollouts, identifying the specific actions or tokens that led to better outcomes.
- "Rollout": A sequence of model actions/interactions constituting one attempt at solving a task.
- "Automated verification": Using formal, programmatic checks (unit tests, proofs, compilers) to independently confirm the correctness of AI-generated outputs.
- "Reward hacking": When an agent exploits loopholes in the reward function, achieving high scores without genuinely solving the intended problem.
- "Majority voting": Aggregating outputs from multiple model runs to select the most common answer—effective only when correct outputs are frequent and easily identifiable.

### Technical Details & Implementation
- PO and DPO require maintaining multiple model copies (up to four for DPO), complicating GPU cluster utilization and scaling.
- GRPO offers a computationally efficient middle ground, reducing model copies and simplifying implementation while retaining fine-grained reward signals.
- Automated verification is implemented via unit tests (for code), formal proofs (for math), and compiler checks (e.g., PyTorch as verifier).
- Benchmarks like GSM8K and Amy are used to demonstrate RL's effectiveness, but saturation occurs quickly, necessitating new, harder tasks.
- Agentic systems are built to interact with environments (file systems, APIs) and autonomously generate and verify artifacts.

### Tools & Technologies
- PyTorch (as a code verifier and compiler)
- GSM8K (math benchmark dataset)
- Amy (advanced math benchmark)
- Unit testing frameworks
- Formal proof systems

### Contrarian Takes & Different Approaches
- DPO is overrated for complex reasoning tasks due to its lack of fine-grained advantage estimation.
- Majority voting is not a scalable solution for correctness in low-frequency, high-complexity domains.
- The field's obsession with synthetic benchmarks and minor paper variations is a distraction from the real work of building robust, verifiable systems.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Prioritize tasks and domains where automated verification is possible—focus RL efforts on code, math, and other verifiable outputs.
- Adopt RL algorithms (like GRPO) that balance computational efficiency with fine-grained reward signals for complex, branching tasks.
- Integrate first-class verification into agent workflows to ensure trustless alignment and robust artifact generation.
- Avoid overfitting to synthetic benchmarks; design tasks and rewards that reflect real-world complexity and verification requirements.

### What to Avoid
- Do not rely solely on majority voting or extended reasoning chains for correctness—these approaches break down when correct outputs are rare.
- Beware of reward hacking, especially when using neural reward models without external verification.
- Avoid getting lost in the noise of incremental RL papers with minor loss function tweaks—focus on holistic understanding and practical system design.
- Scaling RL is significantly harder than standard LLM training due to the need for multiple model copies and complex training/inference loops.

### Best Practices
- Use automated verification as the ground truth for RL reward signals in domains where it is feasible.
- Build agentic systems with tool-use capabilities and ongoing verification to handle real-world, open-ended tasks.
- Treat alignment and verification as first-class citizens in system design, not as afterthoughts.
- Leverage open-source codebases and benchmarks for rapid experimentation, but push beyond them to address unsolved, real-world challenges.

### Personal Stories & Experiences
- Use automated verification as the ground truth for RL reward signals in domains where it is feasible.
- Build agentic systems with tool-use capabilities and ongoing verification to handle real-world, open-ended tasks.
- Treat alignment and verification as first-class citizens in system design, not as afterthoughts.
- Leverage open-source codebases and benchmarks for rapid experimentation, but push beyond them to address unsolved, real-world challenges.

### Metrics & Examples
- Sampling 10,000 completions may be necessary to find a correct solution via majority voting in some math tasks—an impractical approach.
- Benchmarks like GSM8K and Amy are used to track RL progress, but quickly saturate, demonstrating the need for harder, real-world tasks.
- Scaling RL requires up to four model copies for DPO, three for GRPO, significantly increasing resource demands compared to standard LLM training.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=-9E9_21tx04)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
