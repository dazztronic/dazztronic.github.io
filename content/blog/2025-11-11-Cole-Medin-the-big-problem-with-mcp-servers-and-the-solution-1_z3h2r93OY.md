+++
title = "The BIG Problem with MCP Servers (and the Solution!)"
date = 2025-11-11
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Application programming interfaces"]
tags = ["MCP protocol","Claude skills","Token efficiency","Context window","API integration","Code execution","Archon","Anthropic","Agent capabilities"]

[extra]
excerpt = "Cole Medin exposes a fundamental flaw in the MCP protocol for AI agent-tool integration: severe token inefficiency and context bloat, especially as agents are given more capabilities. He demonstrates, with real numbers and hands-on examples, how this leads to unmanageable context windows and proposes a shift to real-time, code-execution-based skills as a dramatically more efficient and flexible alternative."
video_url = "https://www.youtube.com/watch?v=1_z3h2r93OY"
video_id = "1_z3h2r93OY"
cover = "https://img.youtube.com/vi/1_z3h2r93OY/maxresdefault.jpg"
+++

## Overview

Cole Medin exposes a fundamental flaw in the MCP protocol for AI agent-tool integration: severe token inefficiency and context bloat, especially as agents are given more capabilities. He demonstrates, with real numbers and hands-on examples, how this leads to unmanageable context windows and proposes a shift to real-time, code-execution-based skills as a dramatically more efficient and flexible alternative.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's approach is uniquely grounded in practical experimentation—he quantifies token usage with live examples, transforms his own open-source MCP server (Archon) into a Claude skill, and directly contrasts the trade-offs between up-front tool loading and dynamic, code-driven capability discovery. He advocates for leveraging LLMs' code-writing strengths to enable agents to generate and reuse API-interacting scripts on demand, rather than preloading exhaustive tool definitions.

### The Core Problem
MCP servers, while popular for connecting agents to tools, are extremely token-inefficient and rigid. Each tool definition and invocation consumes thousands of tokens, quickly overwhelming the context window—even with modern large language models—making it impractical to provide agents with many capabilities simultaneously.

### The Solution Approach
The recommended solution is to shift from static, up-front tool loading (MCP) to real-time, on-demand skill discovery and code execution. Instead of predefining all tools, agents dynamically generate and execute scripts to interact with APIs as needed, loading only minimal skill descriptions at session start. This approach leverages recent advances in LLM code generation and is exemplified by Anthropic's Claude skills, which allow agents to discover, generate, and reuse code for capabilities only when required, slashing token usage and boosting flexibility.

### Key Insights
- Token inefficiency in MCP scales linearly with the number of tools, quickly consuming nearly half (or more) of available context even on advanced models.
- Real-time skill discovery and code execution allow agents to remain lightweight and flexible, loading only what is needed when it is needed.
- There is a fundamental trade-off: MCP offers control and predictability, while code execution and skills offer flexibility and efficiency—Medin predicts flexibility will win as LLMs improve.

### Concepts & Definitions
- "Token inefficiency": The excessive consumption of context window tokens due to verbose tool definitions and instructions loaded at session start.
- "Context rot": The degradation of agent performance as context windows are filled with redundant or unnecessary information.
- "Skills" (in Claude/Anthropic context): Lightweight, on-demand capabilities described minimally at session start, with full code/instructions loaded only when needed.

### Technical Details & Implementation
- Live demonstration shows 5 MCP servers consuming 97,000 tokens (48% of Claude Sonnet 4.5's context window).
- Archon MCP server was converted into a Claude skill, reducing up-front token usage from thousands to a few hundred.
- Skill descriptions are just a couple of sentences; full instructions and code are loaded only when invoked.
- Agents can generate and reuse code scripts for API interaction, rather than relying on pre-defined tool wrappers.

### Tools & Technologies
- MCP servers (general protocol for agent-tool integration)
- Claude skills (Anthropic)
- Archon (open-source project for API endpoints, demonstrated as both MCP server and Claude skill)
- Claude Sonnet 4.5 (LLM model used for token context demonstration)
- Cloud Code (environment used to inspect context usage)

### Contrarian Takes & Different Approaches
- Challenges the assumption that more context is always better—argues that overwhelming agents with capabilities is counterproductive.
- Advocates for trusting LLMs with code execution and dynamic discovery, predicting this will outpace rigid tool definitions as models improve.
- Pushes back against the idea that MCP is obsolete, noting its ongoing value for control and predictability in certain scenarios.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Audit your agent's context usage with real numbers—use tools like /context to see token consumption by capability.
- Convert existing MCP servers into Claude skills or similar dynamic code-execution frameworks to reduce up-front token load.
- Design agents to discover and load capabilities in real time, only as needed, rather than preloading all possible tools.
- Take advantage of LLMs' code generation abilities to create reusable scripts for API interaction on the fly.

### What to Avoid
- Avoid overwhelming agents with too many up-front capabilities—this leads to context bloat and degraded performance.
- Code execution introduces new risks: security concerns, sandboxing requirements, and complexity in managing credentials/environment variables.
- Relying solely on dynamic discovery may cause agents to miss capabilities if search or invocation logic is insufficient.

### Best Practices
- Pair minimal skill descriptions with on-demand code loading for maximal token efficiency.
- Reuse generated code scripts across agent sessions to avoid redundant code generation.
- Balance control (MCP) and flexibility (skills/code execution) based on security and predictability needs.

### Personal Stories & Experiences
- Pair minimal skill descriptions with on-demand code loading for maximal token efficiency.
- Reuse generated code scripts across agent sessions to avoid redundant code generation.
- Balance control (MCP) and flexibility (skills/code execution) based on security and predictability needs.

### Metrics & Examples
- Five MCP servers consume 97,000 tokens (48% of Claude Sonnet 4.5's context window).
- Claude skills reduce up-front token usage to 2-3% of what MCP requires.
- Converted Archon skill uses only a couple hundred tokens up front, compared to tens of thousands with MCP.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=1_z3h2r93OY)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
