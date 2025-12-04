+++
title = "Break It 'Til You Make It: Building the Self-Improving Stack for AI Agents - Aparna Dhinakaran"
date = 2025-12-04
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Computer software--Testing"]
tags = ["Agent evaluation","Observability","Tracing","Arise Phoenix","Tool call correctness","Trajectory evaluation","Session evaluation","Golden dataset","Dogfooding"]

[extra]
excerpt = "Aparna Dhinakaran presents a granular, iterative approach to evaluating and improving AI agents, emphasizing not just agent performance but also the evolution of evaluation methods themselves. By tracing agent decisions at multiple levels—tool call, trajectory, and session—teams can pinpoint bottlenecks and systematically drive both agent and evaluator improvement, moving beyond ad hoc prompt tweaking."
video_url = "https://www.youtube.com/watch?v=Qvp9vw4jJQ8"
video_id = "Qvp9vw4jJQ8"
cover = "https://img.youtube.com/vi/Qvp9vw4jJQ8/maxresdefault.jpg"
+++

## Overview

Aparna Dhinakaran presents a granular, iterative approach to evaluating and improving AI agents, emphasizing not just agent performance but also the evolution of evaluation methods themselves. By tracing agent decisions at multiple levels—tool call, trajectory, and session—teams can pinpoint bottlenecks and systematically drive both agent and evaluator improvement, moving beyond ad hoc prompt tweaking.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The methodology centers on a dual-loop self-improvement stack: both the agent and its evaluation logic are continuously iterated upon. Unlike traditional approaches that focus solely on agent outputs, this framework insists that evaluation prompts and criteria must also evolve, creating a meta-feedback loop. The use of production-grade observability, tracing, and real-world dogfooding distinguishes the approach.

### The Core Problem
Systematic, scalable evaluation of AI agents is lacking—most teams rely on manual, spreadsheet-driven prompt swaps and subjective judgments, which fail to capture nuanced agent failures or support collaborative, iterative improvement. This leads to brittle agents and blind spots in production.

### The Solution Approach
The process begins with detailed tracing of agent behavior at the tool call level, verifying both tool selection and argument correctness. Evaluation then expands to trajectory analysis, ensuring agents execute multi-step tasks in the correct order, and finally to session-level review, maintaining context across multi-turn conversations. Critically, the evaluation logic itself is treated as a living artifact—teams regularly review, refine, and build golden datasets for both agent and evaluator, ensuring both improve in tandem.

### Key Insights
- Evaluating agents at multiple granularities (tool call, trajectory, session) uncovers failure modes invisible to prompt-level or output-only checks.
- The evaluation process must itself be subject to iteration; static eval prompts quickly become outdated as agents evolve.
- Dogfooding your own evaluation and observability tools on real production traces yields actionable insights and exposes blind spots.

### Concepts & Definitions
- Tool call evaluation: Checking if the agent selected the correct tool and supplied the right arguments based on conversational context.
- Trajectory evaluation: Assessing whether the agent executed the correct sequence of tool calls to accomplish a multi-step task.
- Session evaluation: Reviewing the agent's ability to maintain and utilize context across multi-turn conversations.
- Dual-loop improvement: Simultaneously iterating on both agent logic and evaluation criteria to avoid evaluator staleness.

### Technical Details & Implementation
- Architecture leverages orchestration/worker patterns with a high-level planner, routers, and multiple tool calls, each traced and evaluated for correctness.
- Arise's platform enables visualization of agent trajectories, bottleneck identification, and granular evals (e.g., argument correctness in tool calls).
- Golden datasets are built and refined for both agent outputs and evaluation prompts, supporting continuous improvement.

### Tools & Technologies
- Arise Phoenix (open-source agent evaluation and observability platform)
- Arise's internal co-pilot agent
- Excel (as a baseline, manual evaluation anti-pattern)

### Contrarian Takes & Different Approaches
- Challenges the notion that evaluation logic can remain static—insists that evaluators must evolve alongside agents.
- Argues that prompt-level or output-only evaluation is insufficient for robust agent development.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Instrument agents to trace every tool call, capturing both the tool selected and arguments passed.
- Regularly review evaluation outcomes for both agent and evaluator; refine prompts and build golden datasets to reduce mislabeling.
- Start with high-level trajectory mapping to identify performance bottlenecks, then drill down to trace and argument-level errors.
- Dogfood your own evaluation stack on real production data to surface nuanced issues.

### What to Avoid
- Relying on static evaluation prompts leads to evaluator drift and missed failure cases as agents change.
- Spreadsheet-driven, ad hoc prompt swaps create blind spots and are not scalable for collaborative teams.
- Ignoring argument correctness in tool calls can mask subtle but critical agent failures.

### Best Practices
- Adopt a dual-loop improvement process: iterate on both agent and evaluation logic.
- Use granular tracing and observability to map agent decision paths and identify bottlenecks.
- Build and maintain golden datasets for both agent outputs and evaluator prompts.

### Personal Stories & Experiences
- Adopt a dual-loop improvement process: iterate on both agent and evaluation logic.
- Use granular tracing and observability to map agent decision paths and identify bottlenecks.
- Build and maintain golden datasets for both agent outputs and evaluator prompts.

### Metrics & Examples
- "About half and half of times we're getting it correct as we're getting it incorrect" on search Q&A tasks, signaling a clear bottleneck.
- Consistent tracing of user questions and agent responses to identify specific failure patterns.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=Qvp9vw4jJQ8)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
