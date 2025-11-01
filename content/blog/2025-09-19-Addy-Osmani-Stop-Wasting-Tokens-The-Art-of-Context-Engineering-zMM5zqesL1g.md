+++
title = "Stop Wasting Tokens: The Art of Context Engineering"
date = 2025-09-19
draft = false

[taxonomies]
author = ["Addy Osmani"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Natural language processing", "Software engineering--Artificial intelligence", "Human-computer interaction"]

[extra]
excerpt = "Addy Osmani reframes prompt engineering as a secondary concern to context engineering, arguing that the real lever for high-performing AI agents is how you curate and manage the context window. His approach is deeply practical, rooted in developer experience, and focuses on maximizing every token's value to reduce hallucinations and improve agent reliability. This perspective matters because it shifts the focus from clever prompt crafting to disciplined, systematic context management—a crucial but often overlooked skill in AI-assisted workflows."
video_url = "https://www.youtube.com/watch?v=zMM5zqesL1g"
video_id = "zMM5zqesL1g"
cover = "https://img.youtube.com/vi/zMM5zqesL1g/maxresdefault.jpg"
+++

## Overview

Addy Osmani reframes prompt engineering as a secondary concern to context engineering, arguing that the real lever for high-performing AI agents is how you curate and manage the context window. His approach is deeply practical, rooted in developer experience, and focuses on maximizing every token's value to reduce hallucinations and improve agent reliability. This perspective matters because it shifts the focus from clever prompt crafting to disciplined, systematic context management—a crucial but often overlooked skill in AI-assisted workflows.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Osmani's distinctive methodology is the systematic decomposition of context engineering into actionable patterns—Write, Select, Compress, Isolate—combined with a developer-centric workflow that treats the AI as a new team member. He advocates for treating the context window as limited RAM, requiring careful, intentional curation of instructions, data, and history. Unlike prompt-centric approaches, he insists that the quality and structure of context, not just the prompt, are what determine agent success.

### The Core Problem
The core problem is that most users waste tokens on irrelevant or poorly structured context, leading to hallucinations, vague answers, and unreliable AI agent behavior. With context windows still limited in size, especially for coding agents and developer tools, maximizing the value of each token is essential for practical, production-grade AI applications.

### The Solution Approach
Osmani's methodology involves: (1) precisely defining what should fill the context window (reference materials, detailed instructions, examples, conversation history, immediate requests); (2) applying context management patterns (Write new info, Select only what's relevant, Compress verbose data, Isolate critical instructions); (3) leveraging tools that automate context optimization; (4) treating the AI like a new hire—providing explicit, filtered, and relevant information while assuming no prior knowledge. His mental model: the LLM is the CPU, the context window is RAM, and your job is to engineer that RAM for maximum utility.

### Key Insights
- The context window is the true bottleneck for LLM performance—every token must be intentional and valuable.
- Prompt engineering fails without disciplined context management; clever prompts can't compensate for irrelevant or noisy context.
- Providing concrete examples and explicit constraints dramatically improves output quality—Osmani has seen this repeatedly in coding workflows.
- Treating the AI like a new hire (not an omniscient agent) leads to better results: assume it knows nothing except what you provide.
- Filtering out irrelevant or outdated information is as important as adding new context—garbage in, garbage out.

### Concepts & Definitions
- "Token": the smallest unit of text the model processes, like colored blocks in a sentence.
- "Context window": the maximum number of tokens (prompt + output) the model can remember and use at once.
- Mental model: LLM as CPU, context window as RAM—engineer the RAM for optimal performance.
- "Context engineering": the art and science of filling the context window with the right mix of instructions, data, and history.

### Technical Details & Implementation
- Use patterns: Write (add new, relevant info), Select (choose only what's needed), Compress (summarize verbose data), Isolate (separate critical instructions).
- Feed the AI full error logs, design docs, database schemas, and PR feedback for richer, more grounded responses.
- Leverage tools like Cursor and Cline to automate context selection and compression for coding agents.
- Explicitly state constraints (e.g., required libraries, coding standards) within the context window.

### Tools & Technologies
- Cursor (for automated context optimization in coding workflows)
- Cline (for context management and compression)

### Contrarian Takes & Different Approaches
- Osmani challenges the prompt engineering hype, arguing that context engineering is the real differentiator.
- He disagrees with the assumption that LLMs can 'figure it out' from minimal prompts—explicit, curated context is essential.
- He advocates for treating LLMs as limited-memory agents, not omniscient assistants.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Be precise: avoid vague requests by sharing specific code, design docs, errors, and schemas.
- Give concrete output examples and state all constraints explicitly.
- Filter out irrelevant or outdated information before submitting to the AI.
- Treat the AI like a new hire—assume it knows only what you provide.
- Start applying Write, Select, Compress, Isolate patterns to every AI interaction.

### What to Avoid
- Don't assume clever prompts alone will yield good results—context quality is critical.
- Avoid overfilling the context window with irrelevant or redundant information.
- Beware of context drift: as the window fills, older (potentially important) info fades and can cause the agent to lose track.
- Garbage in, garbage out: unfiltered or noisy context leads to hallucinations and poor performance.

### Best Practices
- Curate context with intention—every token should serve a purpose.
- Use a spectrum of examples to show desired output structure and format.
- Explicitly state rules, constraints, and task descriptions.
- Continuously filter and update context as the conversation evolves.

### Personal Stories & Experiences
- Osmani shares that providing a spectrum of examples (not just one) has repeatedly improved AI output in his coding workflows.
- He notes success when treating the AI like a new hire, leading to fewer misunderstandings and better results.
- He has seen failures when context was overloaded or not filtered, resulting in hallucinated or irrelevant answers.

### Metrics & Examples
- No specific quantitative metrics are cited, but practical examples include using full error logs, design docs, and PR feedback to improve coding agent reliability.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=zMM5zqesL1g)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

