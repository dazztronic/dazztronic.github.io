+++
title = "The BIG Problem with MCP Servers (and the Solution!)"
date = 2025-11-11
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = []
tags = []

[extra]
excerpt = "Cole Medin exposes a critical scalability flaw in the MCP protocol for AI agent tool integration: massive token inefficiency and context bloat. He demonstrates, with real numbers and hands-on workflow, how code execution and 'skills' (as per Anthropic's new approach) enable dramatically more efficient, flexible, and scalable agent architectures."
video_url = "https://www.youtube.com/watch?v=1_z3h2r93OY"
video_id = "1_z3h2r93OY"
cover = "https://img.youtube.com/vi/1_z3h2r93OY/maxresdefault.jpg"
+++

## Overview

Cole Medin exposes a critical scalability flaw in the MCP protocol for AI agent tool integration: massive token inefficiency and context bloat. He demonstrates, with real numbers and hands-on workflow, how code execution and 'skills' (as per Anthropic's new approach) enable dramatically more efficient, flexible, and scalable agent architectures.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's perspective is grounded in practitioner experience—he not only diagnoses MCP's inefficiency with hard data from his own setups, but also prototypes and validates the new 'skills' paradigm by porting his own open-source Archon MCP server. His approach is both empirical and experimental, emphasizing real-world agent development pain points and hands-on migration to cutting-edge solutions.

### The Core Problem
MCP servers, as currently implemented, are extremely token-inefficient and rigid: every tool definition and invocation is loaded into the LLM's context up front, quickly consuming 50% or more of available tokens and overwhelming even modern large context models. This severely limits the number of capabilities that can be exposed to agents, stifling scalability and flexibility.

### The Solution Approach
The proposed solution is to shift from static, up-front tool loading (MCP) to dynamic, on-demand capability discovery and code execution ('skills'). Instead of pre-loading all tool definitions, agents receive only minimal skill descriptors at session start, and load full instructions/code only when a capability is actually needed. This leverages LLMs' code-writing prowess, enabling agents to generate, execute, and reuse code for API interactions as needed, massively reducing token usage and increasing flexibility.

### Key Insights
- Token bloat from MCP servers is not just a theoretical issue—real setups can consume nearly 100,000 tokens (48% of context) before any user input, crippling agent effectiveness.
- Dynamic code execution and real-time skill discovery allow agents to scale to dozens of capabilities with only a fraction of the token cost, unlocking new levels of autonomy.
- There's a fundamental trade-off: MCP offers control and predictability, while code execution/skills offer flexibility and efficiency—but also increased complexity and security risk.

### Concepts & Definitions
- "Token inefficiency": The phenomenon where tool definitions and instructions consume a disproportionate share of the LLM's context window, limiting usable space for actual conversation and reasoning.
- "Context rot": The degradation of agent performance as context windows fill with static, rarely-used tool definitions, making it harder for the LLM to reason effectively.
- "Skills" (Anthropic): Minimal descriptors for agent capabilities, with full code/instructions loaded only when needed, enabling dynamic, efficient agent behavior.
- "Code execution": Allowing agents to generate and run code on the fly to interact with APIs, rather than relying on pre-defined tool wrappers.

### Technical Details & Implementation
- In a real-world coding assistant setup, five standard MCP servers consumed 97,000 tokens (48% of Claude Sonnet 4.5's context window) just for tool definitions.
- Migrating to skills: Only a short skill description (a few sentences) is loaded at session start; full code/instructions are loaded on-demand, reducing up-front token use to 2-3% of MCP.
- Agents can generate code to interact directly with API endpoints (e.g., Archon API), save and reuse scripts, and combine workflows dynamically.
- Skills architecture: Agents search a folder of skill descriptors in real time, loading and executing code as user queries require specific capabilities.

### Tools & Technologies
- MCP servers (general protocol for tool integration)
- Claude Sonnet 4.5 (LLM with large context window)
- Archon (open-source project, both as MCP server and skill)
- Anthropic skills (new capability system for agents)

### Contrarian Takes & Different Approaches
- Despite the hype around code execution and skills, MCP is not obsolete—its up-front, explicit tool definitions offer unmatched control and predictability, which remain valuable in many scenarios.
- Flexibility (via code execution/skills) will increasingly win out over control as LLMs become more capable, but the trade-off is real and context-dependent.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Audit your agent setups for token bloat: use context inspection tools (e.g., /context in Cloud Code) to measure how much context is consumed by MCP tool definitions.
- Begin migrating MCP servers to skills: create minimal skill descriptors and enable agents to generate and execute code for API interactions on demand.
- Leverage LLMs' code-writing abilities to dynamically create and reuse scripts for API calls, rather than pre-defining every tool.
- Balance control and flexibility: use MCP for predictable, controlled integrations; use skills/code execution for scalable, flexible agent capabilities.

### What to Avoid
- Do not overload agents with dozens of MCP servers up front—token bloat will cripple performance, even on large-context models.
- Code execution introduces new security risks and complexity: sandboxing, credential management, and environment variables require careful handling.
- Relying solely on code execution may lead to missed capabilities if agents fail to discover relevant skills at runtime.

### Best Practices
- Use skills for capabilities that benefit from dynamic, on-demand loading and code generation; reserve MCP for cases where strict control and predictability are paramount.
- Encourage agents to save and reuse generated code/scripts to optimize for both efficiency and performance.
- Continuously monitor context usage and agent performance as you scale up capabilities.

### Personal Stories & Experiences
- Use skills for capabilities that benefit from dynamic, on-demand loading and code generation; reserve MCP for cases where strict control and predictability are paramount.
- Encourage agents to save and reuse generated code/scripts to optimize for both efficiency and performance.
- Continuously monitor context usage and agent performance as you scale up capabilities.

### Metrics & Examples
- Five MCP servers for coding assistants consumed 97,000 tokens (48% of Claude Sonnet 4.5's context window).
- Switching to skills reduced up-front token usage to just a couple hundred tokens—a 2-3% footprint compared to MCP.
- Modern LLMs can handle up to 1-2 million tokens, but overwhelming them with up-front tool definitions still degrades performance.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=1_z3h2r93OY)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
