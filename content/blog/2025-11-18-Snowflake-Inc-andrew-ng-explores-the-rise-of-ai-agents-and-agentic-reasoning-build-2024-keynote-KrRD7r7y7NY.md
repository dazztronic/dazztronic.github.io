+++
title = "Andrew Ng Explores The Rise Of AI Agents And Agentic Reasoning | BUILD 2024 Keynote"
date = 2025-11-18
draft = false

[taxonomies]
author = ["Snowflake Inc."]
categories = ["Artificial intelligence","Machine learning","Software engineering--Artificial intelligence","Data engineering"]
tags = ["Agentic reasoning","Large language models","Reflection pattern","Tool use","Planning","Multi-agent collaboration","HumanEval","OpenAI GPT-3.5","GPT-4","Anthropic","OpenPose","Visual AI","Landing.ai","DevOps","LLMOps","Unstructured data"]

[extra]
excerpt = "Andrew Ng reframes the AI landscape by emphasizing the transformative impact of agentic AI workflows—systems where AI agents can reflect, plan, use tools, and collaborate—on application development speed and capability. He argues that the true value and innovation now lie in the application layer, not just in foundational models, and that agentic reasoning unlocks a new paradigm of rapid prototyping, robust evaluation, and complex task automation. This perspective matters because it shifts the focus from foundational model hype to practical, scalable, and high-value AI deployments."
video_url = "https://www.youtube.com/watch?v=KrRD7r7y7NY"
video_id = "KrRD7r7y7NY"
cover = "https://img.youtube.com/vi/KrRD7r7y7NY/maxresdefault.jpg"
+++

## Overview

Andrew Ng reframes the AI landscape by emphasizing the transformative impact of agentic AI workflows—systems where AI agents can reflect, plan, use tools, and collaborate—on application development speed and capability. He argues that the true value and innovation now lie in the application layer, not just in foundational models, and that agentic reasoning unlocks a new paradigm of rapid prototyping, robust evaluation, and complex task automation. This perspective matters because it shifts the focus from foundational model hype to practical, scalable, and high-value AI deployments.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Ng's distinctive approach centers on the 'agentic workflow'—a set of design patterns (reflection, tool use, planning, multi-agent collaboration) that enable large language models to iteratively improve their own outputs, orchestrate complex tasks, and interact with both digital tools and other agents. He demystifies these workflows by breaking them down into concrete, reproducible steps, and highlights their outsized impact on real-world performance (e.g., coding benchmarks). Unlike many, he spotlights the application layer as the true frontier, arguing that the speed of ML prototyping now pressures the rest of the software stack to accelerate.

### The Core Problem
The main challenge addressed is the bottleneck in building robust, valuable AI applications: while foundational model development has advanced rapidly, application-layer innovation and deployment have lagged due to slow prototyping, evaluation, and integration processes. This matters because, without faster and more reliable application development, the full economic and societal value of AI cannot be realized.

### The Solution Approach
Ng advocates for embracing agentic workflows—where AI agents are prompted to reflect on, critique, and iteratively improve their own outputs, use external tools and APIs, plan sequences of actions, and collaborate as specialized agents. The methodology involves rapid prototyping (often in days), parallelizing data collection and evaluation, and layering agentic reasoning patterns to automate complex, multi-step tasks. He recommends integrating these workflows into existing ML pipelines and highlights the need to speed up supporting processes (DevOps, LLMOps, data engineering) to match the new pace of ML innovation.

### Key Insights
- Agentic workflows (reflection, tool use, planning, multi-agent collaboration) can dramatically boost LLM performance on complex tasks, often more than simply upgrading to a newer model.
- Fast experimentation and prototyping—enabled by generative AI—are now the primary path to invention, replacing the old paradigm of slow, risk-averse development cycles.
- Evaluations (evals) have become the new bottleneck; robust testing and data collection must be parallelized with development, not left as a final step.
- The application layer is where the greatest value and opportunity now reside, not in the foundational models themselves.
- Data engineering for unstructured data (text, images, video) is becoming a critical differentiator as visual and multimodal AI matures.

### Concepts & Definitions
- Agentic workflow: A system where AI agents can reflect, plan, use tools, and collaborate to iteratively improve outputs and solve complex tasks.
- Reflection: The process of having an AI model critique and revise its own outputs based on self-generated feedback.
- Tool use: Enabling LLMs to make function/API calls or interact with external digital resources as part of their reasoning.
- Planning: Decomposing a high-level task into a sequence of actionable steps, often involving multiple models or tools.
- Multi-agent collaboration: Structuring workflows where different agents (or roles within an LLM) interact to solve parts of a problem.

### Technical Details & Implementation
- Reflection pattern: Prompting an LLM to critique and improve its own code output, iteratively feeding back its own suggestions.
- Tool use: LLMs generate API calls or decide when to interact with external systems (e.g., web search, calendar, email).
- Planning: LLMs break down complex tasks into ordered sequences of actions, choosing tools/models for each step (e.g., image generation pipeline).
- Multi-agent collaboration: Simulating multiple specialized agents (e.g., coder, critic) within a single LLM or across multiple LLMs to tackle subtasks.
- Benchmarking: HumanEval coding benchmark shows agentic workflows can raise GPT-3.5 performance from 48% to 95%.

### Tools & Technologies
- Snowflake (cloud infrastructure)
- OpenAI GPT-3.5, GPT-4 (foundation models)
- Anthropic (models tuned for computer/tool use)
- HumanEval (coding benchmark)
- OpenPose (pose detection in visual AI pipelines)
- Landing.ai (visual AI demo platform)

### Contrarian Takes & Different Approaches
- Challenges the notion that 'move fast and break things' is inherently irresponsible; instead, advocates for 'move fast and be responsible.'
- Argues that the application layer, not foundational model development, is now the most fertile ground for innovation and value creation.
- Suggests that multi-agent workflows with a single LLM (playing different roles) can outperform simply scaling up model size.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Adopt agentic workflow patterns (reflection, tool use, planning, multi-agent collaboration) in LLM application development.
- Parallelize evaluation and data collection with prototyping to avoid bottlenecks.
- Focus on accelerating the entire application stack (DevOps, LLMOps, data engineering) to keep pace with rapid ML prototyping.
- Leverage LLMs' ability to process unstructured data for new value in text, image, and video-heavy domains.
- Experiment with visual AI applications now, as the image processing revolution is imminent.

### What to Avoid
- Do not rely solely on faster ML prototyping; neglecting robust evaluation and integration can lead to unreliable applications.
- Avoid sequential, waterfall-style development—parallelize prototyping, testing, and data collection.
- Move fast, but not recklessly: 'Move fast and be responsible' replaces 'move fast and break things.'

### Best Practices
- Rapidly prototype many ideas and discard those that fail; let fast iteration drive invention.
- Use agentic design patterns to systematically improve LLM outputs and task performance.
- Invest in scalable evaluation frameworks to keep up with the pace of prototyping.
- Specialize LLM agents for different roles within a workflow to maximize performance.

### Personal Stories & Experiences
- Rapidly prototype many ideas and discard those that fail; let fast iteration drive invention.
- Use agentic design patterns to systematically improve LLM outputs and task performance.
- Invest in scalable evaluation frameworks to keep up with the pace of prototyping.
- Specialize LLM agents for different roles within a workflow to maximize performance.

### Metrics & Examples
- GPT-3.5 baseline: 48% on HumanEval coding benchmark; GPT-4: 67%; GPT-3.5 with agentic workflow: 95%.
- Prototyping timelines reduced from 6-12 months to 10 days for certain applications.
- Agentic workflows deliver 'much better results' in legal, healthcare, and compliance use cases (qualitative improvement).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=KrRD7r7y7NY)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
