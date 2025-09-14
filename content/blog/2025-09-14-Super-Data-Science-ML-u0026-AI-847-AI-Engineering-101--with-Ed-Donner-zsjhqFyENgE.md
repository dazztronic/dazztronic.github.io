+++
title = "847: AI Engineering 101 — with Ed Donner"
date = 2025-09-14
draft = false

[taxonomies]
author = ["Super Data Science: ML \u0026 AI Podcast with Jon Krohn"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Machine learning", "Software engineering--Artificial intelligence"]

[extra]
excerpt = "Ed Donner brings a pragmatic, engineering-first lens to AI, emphasizing hands-on experimentation, rigorous model evaluation, and the real-world complexity of deploying LLMs. His perspective is grounded in startup experience, focusing on actionable workflows and the nuanced tradeoffs in model selection and system design. This matters because he demystifies AI engineering for practitioners, offering concrete strategies rather than abstract theory."
video_url = "https://www.youtube.com/watch?v=zsjhqFyENgE"
video_id = "zsjhqFyENgE"
cover = "https://img.youtube.com/vi/zsjhqFyENgE/maxresdefault.jpg"
+++

## Overview

Ed Donner brings a pragmatic, engineering-first lens to AI, emphasizing hands-on experimentation, rigorous model evaluation, and the real-world complexity of deploying LLMs. His perspective is grounded in startup experience, focusing on actionable workflows and the nuanced tradeoffs in model selection and system design. This matters because he demystifies AI engineering for practitioners, offering concrete strategies rather than abstract theory.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Donner's approach is distinguished by his insistence on empirical, game-based evaluation of LLMs—pitting models against each other in competitive, alliance-forming scenarios to surface nuanced strengths and weaknesses. He prioritizes workflow reproducibility, open-source toolchains, and a stepwise breakdown of complex problems, advocating for agentic AI only when justified by problem structure.

### The Core Problem
The overwhelming challenge of selecting, evaluating, and operationalizing LLMs in a landscape flooded with open-source and proprietary options. This is critical as organizations struggle to move from proof-of-concept to robust, maintainable AI systems.

### The Solution Approach
Donner advocates for a multi-stage approach: (1) Define the problem and break it into agentic, tool-using, or context-augmented steps as appropriate; (2) Use retrieval-augmented generation (RAG) or fine-tuning based on data availability and task specificity; (3) Evaluate candidate LLMs not just on benchmarks but through adversarial, game-like competitions to reveal emergent behaviors; (4) Once selected, operationalize models with reproducible, modular workflows and continuous monitoring.

### Key Insights
- Game-based LLM evaluation exposes real-world strengths and weaknesses that benchmarks miss, especially in multi-agent or adversarial contexts.
- Agentic AI is powerful but should only be used when the problem naturally decomposes into well-defined steps or requires tool use—overengineering otherwise leads to brittle systems.
- The explosion of open-source models is both a blessing and a curse; rigorous, context-specific evaluation is the only way to cut through the noise.

### Concepts & Definitions
- "Retrieval-augmented generation (RAG)": Find documents most relevant to a query, inject them into the prompt, and let the LLM answer with this context.
- "Agentic AI": Systems where the LLM breaks down complex tasks into smaller steps, potentially using external tools or code execution to iteratively solve problems.
- "Fine-tuning": Adjusting a base LLM on domain-specific data to specialize its outputs for a particular use case.

### Technical Details & Implementation
- Implements LLM competitions where models form alliances, share strategies, and compete—surfacing emergent behaviors not seen in isolation.
- Uses RAG by selecting top-k relevant documents and injecting them directly into LLM prompts for context-aware generation.
- Recommends modular, reproducible pipelines that allow swapping models and components with minimal friction.

### Tools & Technologies
- Open-source LLMs (no specific names, but context is model selection and evaluation)
- RAG frameworks for document retrieval and prompt augmentation

### Contrarian Takes & Different Approaches
- Benchmarks are insufficient—real-world, adversarial testing is essential.
- Agentic AI is overhyped for many problems; use it only when the problem structure demands it.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Before selecting an LLM, define your evaluation criteria and run models through adversarial, game-like tests tailored to your use case.
- Use RAG when you have relevant documents but limited labeled data; fine-tune only when you have sufficient domain-specific examples.
- Break down complex problems into agentic workflows only when justified—avoid unnecessary complexity.

### What to Avoid
- Don't rely solely on standard benchmarks—these often miss emergent or adversarial weaknesses.
- Avoid overengineering with agentic AI when a simpler, single-step approach suffices.
- Beware analysis paralysis from the sheer number of available models; focus on reproducible, context-driven evaluation.

### Best Practices
- Empirical, adversarial evaluation of models in realistic, multi-agent scenarios.
- Reproducible, modular engineering workflows for rapid iteration and deployment.
- Context-driven selection between RAG and fine-tuning based on data and task.

### Personal Stories & Experiences
- Donner describes feeling overwhelmed by the open-source model landscape and developing his game-based evaluation as a direct response.
- He recounts the evolution from theoretical model selection to hands-on, competitive testing as a turning point in his engineering practice.

### Metrics & Examples
- No specific numerical metrics cited, but references to emergent behaviors and qualitative differences surfaced in LLM competitions.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=zsjhqFyENgE)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

