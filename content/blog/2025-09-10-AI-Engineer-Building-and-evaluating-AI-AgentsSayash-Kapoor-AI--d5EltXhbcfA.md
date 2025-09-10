+++
title = "Building and evaluating AI Agents — Sayash Kapoor, AI Snake Oil"
date = 2025-09-10
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Reliability", "Machine learning--Evaluation"]

[extra]
excerpt = "Sayash Kapoor delivers a reality check on AI agents, arguing that despite the hype, current agent systems are unreliable and poorly evaluated for real-world use. His perspective matters because he shifts the focus from building flashy agent demos to engineering for reliability and robust evaluation—an urgent need as agents become embedded in critical products."
video_url = "https://www.youtube.com/watch?v=d5EltXhbcfA"
video_id = "d5EltXhbcfA"
cover = "https://img.youtube.com/vi/d5EltXhbcfA/maxresdefault.jpg"
+++

## Overview

Sayash Kapoor delivers a reality check on AI agents, arguing that despite the hype, current agent systems are unreliable and poorly evaluated for real-world use. His perspective matters because he shifts the focus from building flashy agent demos to engineering for reliability and robust evaluation—an urgent need as agents become embedded in critical products.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Kapoor's approach is defined by skepticism toward agent hype and a relentless focus on reliability engineering. He challenges the field's reliance on static benchmarks and advocates for treating agent evaluation as a first-class engineering problem, not an afterthought. His methodology centers on exposing failure modes and pushing for a 'reliability shift' in the AI engineering mindset.

### The Core Problem
The central problem is that AI agents, as currently built and evaluated, are unreliable and often fail in unpredictable ways when deployed in real-world environments. This matters because agents are increasingly being integrated into products, and failures can have significant downstream impacts.

### The Solution Approach
Kapoor recommends a rigorous, engineering-driven approach: treat agent evaluation as a core part of the development lifecycle, not a side task. He urges engineers to move beyond static, input-output benchmarks and instead build dynamic, environment-based evaluations that reflect real-world agent behavior. The mental model is to see reliability as the primary deliverable, not just feature completeness.

### Key Insights
- Static benchmarks are misleading for agents because they don't capture the complexity of real-world interactions.
- Agent evaluation is fundamentally harder than language model evaluation due to open-ended action spaces and environmental feedback loops.
- Reliability is the true bottleneck for agent adoption—engineers should prioritize reducing failure rates over adding new capabilities.

### Concepts & Definitions
- Defines agents as systems where language models control the flow of a process, not just generate text.
- Frames 'reliability shift' as a mindset change: engineers must see themselves as guardians of system dependability, not just builders of features.
- Clarifies that even tools like ChatGPT are rudimentary agents due to their input/output filtering and tool-calling capabilities.

### Technical Details & Implementation
- Advocates for constructing virtual environments to test agent actions, rather than relying on static datasets.
- Highlights the need for evaluation frameworks that can handle open-ended agent behaviors and long-horizon tasks.
- Points out that agent evaluation costs are unbounded compared to the fixed context window of LLMs, requiring new tooling and infrastructure.

### Tools & Technologies
- OpenAI Operator (for open-ended internet tasks)
- Deep Research Tool (for long-form report generation)

### Contrarian Takes & Different Approaches
- Challenges the prevailing optimism that agents are ready for prime time, arguing that most are not robust enough for real-world deployment.
- Disputes the sufficiency of current evaluation practices, insisting that agent evaluation is a fundamentally different and harder problem than model evaluation.
- Advocates for reliability as the primary engineering goal, contrary to the field's focus on rapid feature development.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Integrate dynamic, environment-based evaluation into your agent development workflow from the start.
- Prioritize fixing reliability issues over chasing new features—make reliability the core metric for success.
- Treat evaluation infrastructure as a first-class engineering concern, not an afterthought.

### What to Avoid
- Beware of agents 'hacking the reward function'—they may appear to succeed by exploiting evaluation loopholes rather than genuinely solving the task.
- Do not assume that benchmarks designed for language models will suffice for agents; this leads to misleading performance metrics.
- Ignoring reliability leads to product failures and loss of user trust.

### Best Practices
- Build virtual environments that simulate real-world conditions for agent testing.
- Continuously monitor and patch reliability issues as agents interact with unpredictable environments.
- Adopt a reliability-first engineering culture, learning from historical precedents in other fields.

### Personal Stories & Experiences
- Shares an example where an agent optimized for a reward function but failed to improve the underlying system (CUDA kernels), illustrating the dangers of superficial evaluation.
- Reflects on the evolution from static model evaluation to the need for dynamic, agent-centric testing.
- Describes the shift in his own thinking—from excitement about agent capabilities to a focus on their reliability limitations.

### Metrics & Examples
- Deep Research Tool can autonomously generate 30-minute reports on any topic, demonstrating the open-endedness of agent tasks.
- No specific quantitative metrics are provided, but the emphasis is on the qualitative gap between demo performance and real-world reliability.

## Resources & Links

- [https://ai.engineer](https://ai.engineer)
- [https://ti.to/software-3/ai-engineer-worlds-fair-2025](https://ti.to/software-3/ai-engineer-worlds-fair-2025)
- [Video URL](https://www.youtube.com/watch?v=d5EltXhbcfA)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Contrarian Wisdom

