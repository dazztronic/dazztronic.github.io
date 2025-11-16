+++
title = "A2A & MCP Workshop: Automating Business Processes with LLMs — Damien Murphy, Bench"
date = 2025-11-16
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Business process automation"]
tags = ["A2A","MCP","Genkit XMCP","Zapier","Slack","GitHub","Agent orchestration","Webhooks","Context management","Human-in-the-loop"]

[extra]
excerpt = "Damien Murphy presents a practical, code-level walkthrough of integrating Google's A2A protocol and the Model Context Protocol (MCP) to build multi-agent LLM systems that automate complex business processes. The session uniquely bridges the gap between theoretical agent interoperability and hands-on implementation, revealing real-world integration challenges and solutions not yet documented elsewhere. This matters because it enables practitioners to orchestrate autonomous agents across tools like Slack and GitHub, moving beyond simple voice agents to robust, enterprise-ready automation."
video_url = "https://www.youtube.com/watch?v=wXVvfFMTyzY"
video_id = "wXVvfFMTyzY"
cover = "https://img.youtube.com/vi/wXVvfFMTyzY/maxresdefault.jpg"
+++

## Overview

Damien Murphy presents a practical, code-level walkthrough of integrating Google's A2A protocol and the Model Context Protocol (MCP) to build multi-agent LLM systems that automate complex business processes. The session uniquely bridges the gap between theoretical agent interoperability and hands-on implementation, revealing real-world integration challenges and solutions not yet documented elsewhere. This matters because it enables practitioners to orchestrate autonomous agents across tools like Slack and GitHub, moving beyond simple voice agents to robust, enterprise-ready automation.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Murphy's approach is distinctive for its deep, practical focus on wiring together A2A and MCP—two emerging but sparsely documented protocols—for real, parallelized agent orchestration. He surfaces hard-won lessons from being one of the first to get these protocols working together, including the use of Genkit XMCP as a critical workaround. The methodology is grounded in actual code, local orchestration, and pragmatic tool chaining, rather than high-level conceptual talk.

### The Core Problem
The core challenge addressed is enabling autonomous agents to collaborate and automate multi-step, cross-platform business processes—moving beyond trivial agent demos to production-grade, parallel task execution. This is especially relevant as most current agent frameworks lack robust, interoperable standards for context and tool sharing, making real-world automation brittle or siloed.

### The Solution Approach
The solution involves building a multi-agent system where each agent communicates over the A2A protocol and shares context/tools via MCP. The workshop demonstrates triggering agents via webhooks, orchestrating them locally, and integrating with external services (Slack, GitHub) through Zapier and MCP tools. Murphy emphasizes the need for staging areas for human confirmation and state persistence, and details the necessity of custom wrappers and Genkit XMCP to bridge protocol gaps.

### Key Insights
- True agent interoperability requires both communication (A2A) and shared context/tooling (MCP)—most public examples only implement one or the other.
- Despite claims of full MCP support in A2A, real-world integration is not straightforward; custom workarounds like Genkit XMCP are currently necessary.
- Parallel execution of sub-agents is achievable, but orchestration and state management (especially for human-in-the-loop steps) require explicit design.

### Concepts & Definitions
- A2A: A Google-released protocol enabling agents to communicate over the web, designed for agent-to-agent interoperability.
- MCP (Model Context Protocol): Framed as 'the USB-C for agents,' MCP standardizes how agents consume context, tools, and resources.
- Staging area: A workflow step where actions are drafted and await human confirmation, often implemented via Slack messages with action buttons.

### Technical Details & Implementation
- Agents run locally, orchestrated via codebase with agent logs for debugging and traceability.
- Slack and GitHub agents are connected through MCP tools, leveraging Zapier for external integrations.
- Webhooks are used to trigger agent workflows; state persistence is recommended for multi-step/human-confirmation flows.
- Genkit XMCP is used as a bridge to enable A2A and MCP to function together, due to lack of native support.

### Tools & Technologies
- A2A (Google protocol)
- MCP (Model Context Protocol)
- Genkit XMCP (integration bridge)
- Zapier (external service integration)
- Slack (communication platform)
- GitHub (code repository platform)

### Contrarian Takes & Different Approaches
- Contradicts the narrative that A2A and MCP are plug-and-play; asserts that real-world integration is still bleeding edge and under-documented.
- Challenges the assumption that agent orchestration is solved—emphasizes the ongoing need for custom engineering and state management.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- When building multi-agent systems, explicitly design for both communication (A2A) and context/tool sharing (MCP); do not assume out-of-the-box compatibility.
- Use webhooks to trigger agent workflows and consider implementing a staging area for human-in-the-loop confirmations.
- Leverage Genkit XMCP or similar bridging tools to overcome current protocol gaps between A2A and MCP.

### What to Avoid
- Do not assume that A2A and MCP will work together seamlessly—expect to write custom wrappers or use bridging tools.
- Neglecting state persistence for human confirmation steps can lead to workflow failures or lost actions.
- Security must be explicitly managed for endpoints; exposing everything for demos is not production-safe.

### Best Practices
- Orchestrate agents locally for full control and traceability during development.
- Draft actions and require explicit human confirmation for critical workflow steps, using Slack or similar tools.
- Log all agent interactions for debugging and auditability.

### Personal Stories & Experiences
- Orchestrate agents locally for full control and traceability during development.
- Draft actions and require explicit human confirmation for critical workflow steps, using Slack or similar tools.
- Log all agent interactions for debugging and auditability.

### Metrics & Examples
- Bench is a pre-revenue startup backed by Sutter Hill Ventures, launching in two weeks (from the talk date).
- Voice agent creation is now 'standard' and can be done in five minutes, but complex agent orchestration remains non-trivial.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=wXVvfFMTyzY)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
