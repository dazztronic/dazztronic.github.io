+++
title = "Agentic AI Engineering: Complete 4-Hour Workshop feat. MCP, CrewAI and OpenAI Agents SDK"
date = 2025-12-05
draft = false

[taxonomies]
author = ["Jon Krohn"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Machine learning"]
tags = ["Agentic AI","OpenAI Agents SDK","CrewAI","Anthropic MCP","LangGraph","Autogen","Prompt chaining","Routing","Parallelization","Guardrails","Lightning AI Studios"]

[extra]
excerpt = "This workshop delivers a hands-on, deeply practical exploration of agentic AI systems, focusing on building, orchestrating, and deploying multi-agent workflows using cutting-edge tools like OpenAI Agents SDK, CrewAI, and Anthropic's MCP. The presenters emphasize both the technical architectures and the real-world business value, grounding their approach in live coding, concrete use cases, and candid discussion of both the promise and current limitations of agentic AI. Their perspective is uniquely actionable, blending enterprise consulting experience with a practitioner's eye for debugging, workflow design, and tool selection."
video_url = "https://www.youtube.com/watch?v=LSk5KaEGVk4"
video_id = "LSk5KaEGVk4"
cover = "https://img.youtube.com/vi/LSk5KaEGVk4/maxresdefault.jpg"
+++

## Overview

This workshop delivers a hands-on, deeply practical exploration of agentic AI systems, focusing on building, orchestrating, and deploying multi-agent workflows using cutting-edge tools like OpenAI Agents SDK, CrewAI, and Anthropic's MCP. The presenters emphasize both the technical architectures and the real-world business value, grounding their approach in live coding, concrete use cases, and candid discussion of both the promise and current limitations of agentic AI. Their perspective is uniquely actionable, blending enterprise consulting experience with a practitioner's eye for debugging, workflow design, and tool selection.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The methodology is distinguished by its modular, workflow-centric approach to agentic AI, emphasizing explicit orchestration patterns (prompt chaining, routing, parallelization) and the use of specialized agents as 'engineering teams' for complex tasks. The presenters combine live, step-by-step coding with business consulting insights, offering a rare blend of technical depth and enterprise pragmatism. They also foreground the importance of autonomy and guardrails, advocating for granular control and traceability in agentic systems—contrasting with more monolithic or black-box agent approaches.

### The Core Problem
The central challenge addressed is how to reliably design, implement, and scale agentic AI systems that can autonomously handle complex, multi-step workflows in enterprise contexts—where control, auditability, and business value are paramount. This is critical as organizations seek to move beyond simple LLM chatbots to robust, production-grade agentic solutions.

### The Solution Approach
The workshop breaks down agentic system design into modular workflows: prompt chaining (sequential subtasks with checkpoints), routing (specialized agent selection), and parallelization (concurrent agent execution). Each pattern is illustrated with real-world examples (content pipelines, code generation, medical triage, legal document processing). The presenters advocate for explicit orchestration—using code or orchestration frameworks rather than relying solely on LLMs for control logic. They demonstrate how to compose agents into 'engineering teams' using CrewAI, and how to leverage OpenAI Agents SDK and Anthropic MCP for scalable, autonomous task execution. Debugging, guardrails, and traceability are emphasized at every step.

### Key Insights
- Explicitly breaking down complex tasks into modular, auditable subtasks (with LLMs or code as orchestrators) yields more reliable and debuggable agentic systems.
- Contrary to some hype, agentic AI is not a panacea—current LLMs have significant limitations, but rapid progress and careful system design can mitigate many issues.
- In enterprise consulting, agentic solutions generate immediate client engagement and business value, with nearly 100% conversion from exploratory conversations to contracts.
- Guardrails and traceability are not optional; they are essential for safe, maintainable agentic workflows, especially in regulated or high-stakes domains.
- Specialization of agents (e.g., by domain expertise) and explicit routing/coordinating logic enables separation of concerns and higher quality outputs.

### Concepts & Definitions
- Agentic AI: Programs where large language model outputs control the workflow, featuring autonomy, tool use, multi-agent interaction, planning, and environment awareness (Anthropic's framing).
- Prompt chaining: Decomposing a task into sequential LLM-driven subtasks, each with explicit instructions and checkpoints.
- Routing: Using an LLM or code to triage inputs and direct them to specialized agents for handling.
- Parallelization: Running multiple agent/LLM subtasks concurrently, coordinated by code.
- Guardrails: Deterministic or rule-based checks inserted between workflow stages to ensure correctness and safety.

### Technical Details & Implementation
- Prompt chaining: sequential LLM calls, each handling a subtask (e.g., outline generation, draft writing, SEO polishing), with deterministic gates for quality control.
- Routing: an LLM or code-based router directs inputs to specialized LLMs/agents (e.g., medical triage by specialty, legal document categorization).
- Parallelization: coordinator (code, not LLM) launches multiple specialized LLMs/agents in parallel for concurrent subtask processing.
- CrewAI is used to create agent 'engineering teams' that collaborate on complex workflows; OpenAI Agents SDK provides the backbone for agent orchestration; Anthropic MCP is leveraged for autonomous trading simulations.
- Debugging is facilitated by traceable subtask execution and deterministic gates between workflow stages.

### Tools & Technologies
- OpenAI Agents SDK (for agent orchestration and workflow control)
- CrewAI (for building multi-agent engineering teams)
- Anthropic MCP (for autonomous agent development, especially trading simulations)
- LangGraph and Autogen (mentioned as additional frameworks in extended materials)
- Lightning AI Studios (for scalable compute resources)

### Contrarian Takes & Different Approaches
- While some experts (e.g., Andrej Burkov) argue that agentic AI is overhyped, the presenters maintain that—despite limitations—practical, high-value applications are already emerging.
- The insistence on explicit orchestration and guardrails runs counter to the trend of 'end-to-end' LLM solutions, advocating instead for modular, controllable architectures.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by decomposing your problem into modular subtasks and explicitly define agent roles and responsibilities.
- Implement deterministic gates between workflow stages to enforce quality and enable debugging.
- Use orchestration frameworks (CrewAI, OpenAI Agents SDK) to manage agent collaboration and workflow execution.
- Specialize agents by domain expertise and use routing logic to direct tasks appropriately.
- Leverage traceability and logging at each subtask to facilitate debugging and auditing.

### What to Avoid
- Avoid relying on monolithic LLMs to handle all subtasks—this sacrifices control, debuggability, and quality.
- Do not neglect guardrails; skipping deterministic checks can lead to unpredictable or unsafe outputs.
- Beware of overhyping agentic AI—current LLMs have real limitations; design for failure and gradual improvement.
- Failing to specialize agents or implement routing leads to bloated, unfocused systems with lower performance.

### Best Practices
- Adopt modular workflow patterns (prompt chaining, routing, parallelization) to structure agentic systems.
- Use code-based coordinators for orchestration when more control is needed than LLMs can provide.
- Implement traceable, auditable pipelines with checkpoints and logging at each subtask.
- Engage business stakeholders early to align agentic solutions with real enterprise value.

### Personal Stories & Experiences
- Adopt modular workflow patterns (prompt chaining, routing, parallelization) to structure agentic systems.
- Use code-based coordinators for orchestration when more control is needed than LLMs can provide.
- Implement traceable, auditable pipelines with checkpoints and logging at each subtask.
- Engage business stakeholders early to align agentic solutions with real enterprise value.

### Metrics & Examples
- Humanity's Last Exam (HLE): a multimodal benchmark with 2,500 challenging questions across 100+ subjects, curated by 1,000 experts from 500 institutions in 50 countries, used to assess LLM progress and overfitting.
- Consulting conversion: 100% of exploratory conversations with enterprise clients have led to next steps and contracts for agentic AI solutions.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=LSk5KaEGVk4)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
