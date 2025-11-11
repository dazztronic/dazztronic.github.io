+++
title = "The BIG Problem with MCP Servers (and the Solution!)"
date = 2025-11-11
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Natural language processing"]
tags = ["MCP","Anthropic Claude","Skills framework","Code execution","API integration","Token efficiency","Archon"]

[extra]
excerpt = "Cole Medin delivers a sharp critique of MCP servers, highlighting their crippling token inefficiency and rigidity when scaling agent capabilities. He demonstrates, with real numbers and hands-on workflow, how code execution and Anthropic's new 'skills' framework offer a radically more flexible and efficient alternative, fundamentally shifting how agent capabilities are provisioned and discovered."
video_url = "https://www.youtube.com/watch?v=1_z3h2r93OY"
video_id = "1_z3h2r93OY"
cover = "https://img.youtube.com/vi/1_z3h2r93OY/maxresdefault.jpg"
+++

## Overview

Cole Medin delivers a sharp critique of MCP servers, highlighting their crippling token inefficiency and rigidity when scaling agent capabilities. He demonstrates, with real numbers and hands-on workflow, how code execution and Anthropic's new 'skills' framework offer a radically more flexible and efficient alternative, fundamentally shifting how agent capabilities are provisioned and discovered.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's approach is grounded in practical experimentation—he quantifies the token bloat of MCP servers in real-world setups and personally migrates his own open-source Archon project from MCP to Anthropic's skills, proving the efficiency gains. He uniquely frames the trade-off between control (MCP) and flexibility (skills/code execution), advocating for dynamic, on-demand capability discovery as the future.

### The Core Problem
MCP servers require all tool definitions and parameters to be loaded into the agent's context up front, leading to massive token consumption ('context rot') and inflexible workflows. This severely limits the number of capabilities that can be provided to an agent, even with large context windows, and risks overwhelming both the LLM and the user.

### The Solution Approach
The recommended methodology is to shift from static, up-front tool loading (MCP) to real-time, on-demand capability discovery via code execution or Anthropic's skills. Instead of preloading thousands of tokens worth of tool definitions, agents receive minimal skill descriptors and dynamically load or generate code/scripts only when a capability is needed, drastically reducing token usage and increasing flexibility. Medin demonstrates converting an MCP server into a skill, showing the agent can generate and reuse code to interact with APIs as required.

### Key Insights
- Token inefficiency is not just a theoretical issue—real setups with five MCP servers can consume nearly 100,000 tokens, almost half of Claude Sonnet 4.5's context window, before any user input.
- Dynamic, code-based capability discovery is not only more efficient but also leverages modern LLMs' strength in code generation, making agents more autonomous and scalable.
- There is a critical trade-off: MCP offers control and predictability, while code execution/skills provide flexibility and efficiency but introduce security and complexity concerns.

### Concepts & Definitions
- "Context rot": the phenomenon where an agent's context window is filled with static tool definitions, reducing space for actual conversation or task-relevant data.
- "Skills" (Anthropic): lightweight descriptors that enable agents to dynamically load or generate code/instructions for capabilities only when needed.
- "Code execution": allowing agents to write, execute, and reuse scripts to interact with APIs or perform tasks, rather than relying on pre-defined tool wrappers.

### Technical Details & Implementation
- Measuring token consumption in a live agent setup using /context command, revealing 97,000 tokens used by MCP tools alone.
- Migrating an MCP server (Archon) to an Anthropic skill, reducing upfront token usage from thousands to a few hundred.
- Skills framework: only a brief descriptor is loaded at session start; full instructions and code are loaded on demand, typically reducing upfront token cost to 2-3% of MCP.
- Agents can generate and reuse scripts for API interactions, storing instructions for future use.

### Tools & Technologies
- MCP servers (general protocol for agent-tool connections)
- Anthropic Claude Sonnet 4.5 (LLM with large context window)
- Archon (open-source project, both as MCP server and skill)
- Anthropic skills framework

### Contrarian Takes & Different Approaches
- Contrary to the trend of maximizing agent capabilities via MCP, Medin argues that more is not always better—overloading context is counterproductive.
- He predicts that flexibility (skills/code execution) will eventually win out over control (MCP), as LLMs become more capable and trustworthy.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Audit your agent's context consumption using diagnostic commands (e.g., /context) to identify token bloat.
- Transition from MCP servers to skills or code execution where possible to minimize upfront token usage.
- When building new agent capabilities, provide only minimal descriptors up front and load/generate code as needed based on user queries.
- Consider the trade-off between control (MCP) and flexibility (skills/code execution) based on your application's security and workflow needs.

### What to Avoid
- Avoid loading all possible MCP tools up front—this can overwhelm even large-context LLMs and degrade agent performance.
- Relying solely on code execution/skills introduces new risks: security (sandboxing), complexity, and potential for missed capabilities if discovery fails.
- Credential and environment variable management is less mature in skills/code execution setups compared to MCP.

### Best Practices
- Use real-time capability discovery to keep agent context lean and responsive.
- Leverage LLMs' code generation abilities to dynamically create and reuse scripts for API interactions.
- Pair skills-based workflows with careful security controls and sandboxing for code execution.

### Personal Stories & Experiences
- Use real-time capability discovery to keep agent context lean and responsive.
- Leverage LLMs' code generation abilities to dynamically create and reuse scripts for API interactions.
- Pair skills-based workflows with careful security controls and sandboxing for code execution.

### Metrics & Examples
- Five MCP servers for coding assistants consumed 97,000 tokens—48% of Claude Sonnet 4.5's context window.
- Skills-based approach reduced upfront token usage to just a few hundred tokens (2-3% of MCP's cost).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=1_z3h2r93OY)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
