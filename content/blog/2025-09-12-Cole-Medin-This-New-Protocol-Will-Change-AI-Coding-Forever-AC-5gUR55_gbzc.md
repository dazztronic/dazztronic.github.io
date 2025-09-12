+++
title = "This New Protocol Will Change AI Coding Forever (ACP)"
date = 2025-09-12
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Programming environments", "Computer software--Interoperability", "Open source software"]

[extra]
excerpt = "Cole Medin delivers a hands-on, systems-level breakdown of the Agent Client Protocol (ACP), positioning it as a transformative standard for integrating any AI coding assistant with any code editor. His perspective stands out for its practical, developer-centric focus—demystifying ACP's architecture, showing real-world workflows, and emphasizing the protocol's potential to unlock modular, customizable AI coding environments."
video_url = "https://www.youtube.com/watch?v=5gUR55_gbzc"
video_id = "5gUR55_gbzc"
cover = "https://img.youtube.com/vi/5gUR55_gbzc/maxresdefault.jpg"
+++

## Overview

Cole Medin delivers a hands-on, systems-level breakdown of the Agent Client Protocol (ACP), positioning it as a transformative standard for integrating any AI coding assistant with any code editor. His perspective stands out for its practical, developer-centric focus—demystifying ACP's architecture, showing real-world workflows, and emphasizing the protocol's potential to unlock modular, customizable AI coding environments.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Cole's approach is deeply pragmatic and technical: he doesn't just announce ACP, he demonstrates its live integration in Zed, walks through JSON-RPC message flows, and frames ACP as the missing interoperability layer for AI coding agents. He uniquely emphasizes the power of open standards to enable user-driven customization—encouraging viewers to build their own agents and tools, not just consume prebuilt solutions.

### The Core Problem
The fragmentation of AI coding assistants and code editors—each with proprietary integrations—creates silos, limits user choice, and stifles innovation. Cole highlights the urgent need for a universal protocol that allows any coding agent to work with any editor, mirroring the impact of language server protocols in the past.

### The Solution Approach
Cole advocates adopting ACP as a universal, JSON-RPC-based protocol for agent-editor communication. He demonstrates step-by-step how ACP sessions are established, how live updates and granular change acceptance/rejection work, and how developers can leverage ACP to create custom agents or tools that plug into any compliant editor. His mental model: treat AI coding agents as modular, swappable components—ACP is the interface that makes this ecosystem possible.

### Key Insights
- Live, granular code updates with accept/reject functionality dramatically improve the developer experience compared to monolithic code suggestions.
- Open standards like ACP are the key to breaking vendor lock-in and enabling a flourishing ecosystem of AI coding tools.
- Building your own agents or tools on ACP is not just possible, but encouraged—Cole sees this as the next wave of developer empowerment.

### Concepts & Definitions
- "Agent Client Protocol (ACP)": A universal, JSON-RPC-based protocol standardizing communication between coding assistants and code editors.
- "Session": The initial handshake and ongoing communication channel between an agent and an editor, enabling stateful interaction.
- "Live updates": Real-time, incremental code changes surfaced in the editor as the agent works, with user control to accept or reject each change.

### Technical Details & Implementation
- ACP uses JSON-RPC for communication, mirroring the structure of the Message Client Protocol (MCP) but tailored for coding assistants.
- Integration demonstrated with Zed editor in beta, supporting both Cloud Code and Gemini CLI threads, with instant switching between them.
- Session establishment involves a handshake; subsequent communication includes tool calls, permission requests, and chunked text edits, all as JSON events.
- ACP supports passing images, resources, and file references in user messages, enabling rich context for agents.

### Tools & Technologies
- Zed (code editor, beta ACP integration)
- Cloud Code (AI coding assistant)
- Gemini CLI (AI coding assistant, thread-based interaction)
- Archon (experimental project for custom agent workflows)
- VS Code, Windsurf, Cursor (other editors for context/comparison)

### Contrarian Takes & Different Approaches
- Cole challenges the status quo of proprietary agent-editor integrations, arguing that open protocols are essential for progress.
- He pushes back against the notion that only vendors can build effective coding assistants—he believes users should (and now can) build their own.
- He sees the future of AI coding as user-driven and modular, not vendor-locked or monolithic.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Try ACP now by enabling the beta integration in Zed and connecting to Cloud Code or Gemini CLI.
- Experiment with building your own ACP-compliant agent or tool—Cole suggests this is accessible and powerful.
- Monitor emerging ACP integrations in other editors to stay ahead of the curve.

### What to Avoid
- Don't rely on proprietary, closed integrations—these limit flexibility and future-proofing.
- Beware of assuming all editors or agents are ACP-ready; check for compatibility and expect rapid evolution.
- Avoid monolithic agent workflows—embrace modularity and user control via ACP's granular update model.

### Best Practices
- Adopt open standards (like ACP) early to maximize interoperability and future options.
- Leverage live update and accept/reject features for safer, more controlled code changes.
- Design agents and tools as modular components that can be swapped or combined as needs evolve.

### Personal Stories & Experiences
- Cole shares his long-standing desire for granular change control in Cloud Code, now realized through ACP.
- He recounts his excitement discovering Zed's ACP support and his hands-on exploration of its implementation.
- He hints at ongoing experiments with Archon, reflecting his commitment to pushing ACP's boundaries.

### Metrics & Examples
- No specific quantitative metrics provided, but concrete examples include live switching between Cloud Code and Gemini CLI in Zed, and JSON event structures for ACP communication.

## Resources & Links

- [https://bit.ly/4mW6IFJ](https://bit.ly/4mW6IFJ)
- [https://dynamous.ai/ai-coding-workshop](https://dynamous.ai/ai-coding-workshop)
- [https://www.youtube.com/watch?v=69B3htkGMwc](https://www.youtube.com/watch?v=69B3htkGMwc)
- [https://zed.dev/blog/claude-code-via-acp](https://zed.dev/blog/claude-code-via-acp)
- [https://agentclientprotocol.com/overview/introduction](https://agentclientprotocol.com/overview/introduction)
- [https://scoop.sh/#/apps?q=zed-nightly](https://scoop.sh/#/apps?q=zed-nightly)
- [https://zed.dev/download](https://zed.dev/download)
- [https://github.com/zed-industries/agent-client-protocol/tree/main/typescript/examples](https://github.com/zed-industries/agent-client-protocol/tree/main/typescript/examples)
- [Video URL](https://www.youtube.com/watch?v=5gUR55_gbzc)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

