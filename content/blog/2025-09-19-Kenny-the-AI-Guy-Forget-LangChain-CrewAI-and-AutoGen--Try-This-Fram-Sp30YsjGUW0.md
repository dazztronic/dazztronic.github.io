+++
title = "Forget LangChain, CrewAI and AutoGen — Try This Framework and Never Look Back"
date = 2025-09-19
draft = false

[taxonomies]
author = ["Kenny the AI Guy"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Artificial intelligence", "Computer software--Modular programming"]

[extra]
excerpt = "Kenny the AI Guy champions a radical return to simplicity and developer control in agentic AI frameworks, rejecting the complexity and abstraction of popular tools like LangChain, CrewAI, and AutoGen. His Atomic Agents framework is built on the Input–Process–Output (IPO) model and atomicity, offering modularity, predictability, and hands-on ownership that empowers developers to build robust AI pipelines without unnecessary dependencies or opaque abstractions."
video_url = "https://www.youtube.com/watch?v=Sp30YsjGUW0"
video_id = "Sp30YsjGUW0"
cover = "https://img.youtube.com/vi/Sp30YsjGUW0/maxresdefault.jpg"
+++

## Overview

Kenny the AI Guy champions a radical return to simplicity and developer control in agentic AI frameworks, rejecting the complexity and abstraction of popular tools like LangChain, CrewAI, and AutoGen. His Atomic Agents framework is built on the Input–Process–Output (IPO) model and atomicity, offering modularity, predictability, and hands-on ownership that empowers developers to build robust AI pipelines without unnecessary dependencies or opaque abstractions.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Kenny's approach is defined by his insistence on minimalism and explicit developer ownership: every component in Atomic Agents is modular, swappable, and governed by clear input/output schemas. He rejects the 'agents talking to each other' paradigm as the default, instead advocating for agentic pipelines where the developer orchestrates flow and logic. His framework is CLI-first, tool-agnostic, and designed for maximal transparency and extensibility.

### The Core Problem
He addresses the frustration developers face with bloated, high-abstraction frameworks that introduce steep learning curves, hidden dependencies, and limited code ownership—problems that slow iteration and obscure system behavior in production AI applications.

### The Solution Approach
Kenny's methodology is to enforce the IPO model at every level: each agent has a validated input schema, a processing function, and a strict output schema. Tools are managed via a CLI that allows downloading, modifying, and swapping without entangling dependencies. The architecture is intentionally flat and explicit, favoring pipelines over agent collectives, and enabling seamless integration of any LLM provider or local model by simply swapping schemas and providers.

### Key Insights
- High-level abstractions often create more problems than they solve by hiding complexity and limiting developer agency.
- Agentic pipelines—where the developer controls the flow—are more maintainable and predictable than autonomous agent collectives.
- Strict schema validation (input/output) is the key to modularity and reliability in AI systems.

### Concepts & Definitions
- 'Input–Process–Output (IPO) model': Every agent receives a typed input, processes it, and emits a strictly defined output.
- 'Atomicity': Each tool or agent is self-contained and swappable, minimizing coupling and maximizing reusability.
- 'Agentic pipeline': A linear or modular sequence of agents, orchestrated by the developer, as opposed to a network of autonomous agents negotiating outcomes.

### Technical Details & Implementation
- Agents are constructed using an 'instructor' pattern, specifying provider (OpenAI, Groq, Anthropic, local models via Ollama), input/output schemas, and optional context providers and memory.
- The Atomic Assembler CLI manages tools as standalone modules, not as hard dependencies—tools can be downloaded, modified, and swapped at will.
- Schemas are validated using 'identic', ensuring type safety and predictability across the pipeline.

### Tools & Technologies
- Atomic Agents (core framework)
- Atomic Assembler CLI
- Identic (for schema validation)
- OpenAI, Groq, Anthropic (as LLM providers)
- Ollama (for local models)
- Poetry (for Python project management)

### Contrarian Takes & Different Approaches
- He challenges the default assumption that agent collectives (agents talking to each other) are the best way to build AI systems.
- He argues that most high-level abstractions are counterproductive for experienced developers.
- He believes tool modularity and developer ownership should trump framework convenience.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with a clean Poetry project, install Atomic Agents, and use the CLI to download only the tools you need.
- Define explicit input/output schemas for every agent to ensure modularity and testability.
- Swap LLM providers or tool modules by simply changing the schema or provider in your agent definition—no deep refactoring required.

### What to Avoid
- Avoid frameworks that force you to adopt unnecessary abstractions or agent communication patterns you don't need.
- Don't accept hidden dependencies—always know what code is running in your pipeline.
- Beware of tools that limit your ability to modify or extend core components.

### Best Practices
- Enforce IPO and schema validation at every step for clarity and modularity.
- Use the CLI to manage tools as independent modules, not as monolithic dependencies.
- Favor explicit, developer-controlled pipelines over emergent agent collectives for production reliability.

### Personal Stories & Experiences
- Kenny shares his own frustration with popular frameworks introducing complexity and limiting his ability to iterate quickly.
- He describes the 'aha moment' of realizing that strict schemas and modularity could restore developer joy and control.
- His evolution from using LangChain/CrewAI to building Atomic Agents was driven by repeated pain points in real-world projects.

### Metrics & Examples
- No explicit quantitative metrics are mentioned, but he notes that even with a small set of tools, Atomic Agents enables a wide range of use cases.
- He emphasizes the reduction in dependencies and increased transparency as qualitative improvements.

## Resources & Links

- [https://github.com/BrainBlend-AI/atomic-agents/](https://github.com/BrainBlend-AI/atomic-agents/)
- [https://medium.com/@kenny_v/](https://medium.com/@kenny_v/)
- [https://www.paypal.com/paypalme/KennyVaneetvelde](https://www.paypal.com/paypalme/KennyVaneetvelde)
- [Video URL](https://www.youtube.com/watch?v=Sp30YsjGUW0)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Contrarian Wisdom

