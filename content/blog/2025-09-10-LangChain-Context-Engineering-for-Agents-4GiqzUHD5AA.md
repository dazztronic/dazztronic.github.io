+++
title = "Context Engineering for Agents"
date = 2025-09-10
draft = false

[taxonomies]
author = ["LangChain"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering", "Artificial intelligence", "Natural language processing", "Information retrieval"]

[extra]
excerpt = "Lance from LangChain reframes agent development as 'context engineering'—the deliberate, dynamic curation of what information fills an agent's context window at each step. His perspective is both practical and architectural, emphasizing modular strategies (writing, selecting, compressing, isolating) and mapping them directly to real-world agent workflows, with LangGraph designed to operationalize these patterns."
video_url = "https://www.youtube.com/watch?v=4GiqzUHD5AA"
video_id = "4GiqzUHD5AA"
cover = "https://img.youtube.com/vi/4GiqzUHD5AA/maxresdefault.jpg"
+++

## Overview

Lance from LangChain reframes agent development as 'context engineering'—the deliberate, dynamic curation of what information fills an agent's context window at each step. His perspective is both practical and architectural, emphasizing modular strategies (writing, selecting, compressing, isolating) and mapping them directly to real-world agent workflows, with LangGraph designed to operationalize these patterns.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Lance's approach is distinctive in its systematization of context management as a first-class engineering discipline, not just a prompt hack. He introduces a modular taxonomy—writing, selecting, compressing, isolating context—and connects each to concrete agent behaviors and tool support. He draws analogies to operating system memory management, advocating for explicit, programmatic control over what enters the LLM's context window, rather than relying on static prompts or naive retrieval.

### The Core Problem
The core problem is the limited capacity of LLM context windows, which constrains agent performance, especially as agents require dynamic access to instructions, knowledge, tools, and feedback. In the current AI landscape, where agents are expected to handle complex, multi-step tasks, naive context stuffing leads to degraded performance, inefficiency, and outright failure as the number of tools or knowledge items scales.

### The Solution Approach
Lance's methodology is to treat context as a managed resource, akin to RAM in an operating system. He advocates for: (1) Writing context (explicit instructions/rules), (2) Selecting context (retrieval from large memory stores using embeddings/graphs), (3) Compressing context (trimming to essentials), and (4) Isolating context (partitioning/sandboxing, multi-agent splitting). Each strategy is mapped to agent design patterns and supported in LangGraph, enabling composable, scalable agent architectures.

### Key Insights
- Embedding-based retrieval is essential for scaling agent access to large knowledge/tool sets—static inclusion fails as context size grows.
- Agents degrade sharply after ~30 tools and fail at ~100; selective retrieval over tool descriptions is a practical fix.
- Partitioning and sandboxing context (e.g., via state objects or multi-agent splits) enables agents to exceed single-window token limits.

### Concepts & Definitions
- "Context engineering" is defined as the art and science of filling the context window with just the right information at each step of the agent's trajectory.
- LLM context window is likened to RAM/working memory, with the LLM as CPU—context engineering is the discipline of deciding what fits.
- "Writing context" refers to explicit procedural memories (rules, style guides) pulled into context at runtime.

### Technical Details & Implementation
- Use of embedding similarity search or graph databases to retrieve only relevant facts or tools at inference time.
- RAG (Retrieval-Augmented Generation) over tool descriptions to dynamically select tools based on semantic relevance.
- Partitioning context via state objects or sandboxing to isolate information for sub-agents, enabling distributed context management.

### Tools & Technologies
- LangGraph (for orchestrating context engineering strategies)
- Embedding-based similarity search
- Graph databases
- RAG (Retrieval-Augmented Generation)

### Contrarian Takes & Different Approaches
- Rejects the idea that prompt engineering alone is sufficient for scalable agents; context engineering is a distinct, necessary discipline.
- Challenges the assumption that more context is always better—selectivity and isolation are often more effective.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Implement embedding-based retrieval for both facts and tool descriptions to avoid context overload.
- Partition agent state to isolate context for sub-tasks or sub-agents, especially in multi-agent systems.
- Regularly audit what is being pulled into the context window—avoid static inclusion of large files or tool lists.

### What to Avoid
- Do not naively include all possible tools or knowledge in context—performance degrades rapidly past 30 tools.
- Avoid static context stuffing; dynamic retrieval is necessary as agent complexity grows.
- Neglecting context isolation can lead to token overflows and unpredictable agent behavior.

### Best Practices
- Use modular context engineering: write, select, compress, isolate—apply each as needed per agent workflow.
- Leverage retrieval over static inclusion for both knowledge and tools.
- Design agents to explicitly manage context as a resource, not an afterthought.

### Personal Stories & Experiences
- References to real-world agent failures when exceeding tool/context limits, motivating the shift to retrieval-based approaches.
- Evolution from static context inclusion to dynamic, programmatic context management as agent complexity increased.

### Metrics & Examples
- Performance degradation after ~30 tools; complete failure at ~100 tools (citing a specific paper).

## Resources & Links

- [https://blog.langchain.com/context-engineering-for-agents/](https://blog.langchain.com/context-engineering-for-agents/)
- [https://mirror-feeling-d80.notion.site/Context-Engineering-for-Agents-21f808527b17802db4b1c84a068a0976?source=copy_link](https://mirror-feeling-d80.notion.site/Context-Engineering-for-Agents-21f808527b17802db4b1c84a068a0976?source=copy_link)
- [Video URL](https://www.youtube.com/watch?v=4GiqzUHD5AA)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

