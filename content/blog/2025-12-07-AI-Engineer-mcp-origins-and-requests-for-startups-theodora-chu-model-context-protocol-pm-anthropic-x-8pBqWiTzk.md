+++
title = "MCP: Origins and Requests For Startups — Theodora Chu, Model Context Protocol PM, Anthropic"
date = 2025-12-07
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Software engineering--Protocols","Open source software"]
tags = ["Model Context Protocol","LLM tool integration","Agentic AI","Streamable HTTP","OAuth","Inspector","Protocol design","Developer experience","Open-source standards"]

[extra]
excerpt = "Theodora Chu provides a candid, behind-the-scenes account of the Model Context Protocol (MCP), focusing on its origins as a solution to the friction of copying context into LLMs and its evolution into an open-source standard for model agency. The talk emphasizes the importance of model agency, community-driven protocol development, and the practical trade-offs made to optimize for server simplicity and future agent intelligence. Chu's perspective is grounded in real-world product management, highlighting both technical decisions and the messy realities of adoption and iteration."
video_url = "https://www.youtube.com/watch?v=x-8pBqWiTzk"
video_id = "x-8pBqWiTzk"
cover = "https://img.youtube.com/vi/x-8pBqWiTzk/maxresdefault.jpg"
+++

## Overview

Theodora Chu provides a candid, behind-the-scenes account of the Model Context Protocol (MCP), focusing on its origins as a solution to the friction of copying context into LLMs and its evolution into an open-source standard for model agency. The talk emphasizes the importance of model agency, community-driven protocol development, and the practical trade-offs made to optimize for server simplicity and future agent intelligence. Chu's perspective is grounded in real-world product management, highlighting both technical decisions and the messy realities of adoption and iteration.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Chu's approach is distinctive in its focus on model agency as the next frontier for LLM utility, advocating for open-source, standardized protocols as the foundation for scalable tool integration. She emphasizes optimizing for server simplicity (even at the cost of client complexity) and betting on the increasing intelligence of models to eventually automate their own integrations. The methodology is deeply community-driven, with protocol evolution shaped by real-world feedback and contributions.

### The Core Problem
The central challenge addressed is the manual, error-prone process of copying relevant context into LLMs' context windows, which limits model utility and hinders workflow automation. The broader issue is the lack of a standardized, open way for models to interact with external tools and data sources, impeding the development of truly agentic AI systems.

### The Solution Approach
The solution is the Model Context Protocol (MCP), an open-source, standardized protocol that enables LLMs to access and interact with external tools and data sources autonomously. The protocol is designed with the mental model that there will be far more servers (tools) than clients (models), so complexity is intentionally pushed to the client side. Key features include support for streamable HTTP transport for bidirectionality, elicitation for interactive clarification with end users, and a registry API for discoverability. The protocol's evolution is highly iterative, with rapid feedback loops from internal hackathons and external community contributions.

### Key Insights
- Model agency—not just context injection—is the critical unlock for the next generation of LLM applications.
- Open-source, standardized protocols are essential for ecosystem growth; closed, partnership-driven integrations can't scale.
- Optimizing for server simplicity (even at the expense of client complexity) is a deliberate bet on the future landscape, where servers vastly outnumber clients.
- Community contributions are not just welcomed but essential; protocol flaws are rapidly fixed through external PRs and feedback.
- Automated MCP server generation is a moonshot bet, anticipating a future where models write their own integrations in real time.

### Concepts & Definitions
- "Model agency" is defined as the model's ability to autonomously choose actions and interact with the external world, analogous to how humans respond to open-ended tasks.
- "Elicitation" is explained as a protocol feature where the server can ask the end user for more information (e.g., clarifying what "best" means in a flight booking request).
- The "three users" mental model for server builders: end user, client developer, and the model itself, each with unique needs and interface requirements.

### Technical Details & Implementation
- Transitioned transport from SSE to streamable HTTP to enable bidirectional communication, supporting agent-to-agent workflows.
- OAuth integration for identity management was initially flawed but corrected via community-driven updates to the draft spec.
- Inspector tool is highlighted as an underutilized resource for debugging MCP servers.
- Elicitation feature in the draft spec allows servers to request clarifying information from end users and pass it through the protocol.
- Registry API (in progress) will allow models to dynamically discover MCP servers without prior configuration.

### Tools & Technologies
- Cursor (first major adopter of MCP, catalyzing ecosystem momentum)
- VS Code and Sourcegraph (subsequent adopters in the coding tools space)
- Inspector (debugging tool for MCP servers)
- OAuth (for identity management in MCP integrations)
- GitHub (for protocol development and community PRs)

### Contrarian Takes & Different Approaches
- Contrary to some expectations, the protocol intentionally pushes complexity to clients, not servers—a strategic bet on ecosystem structure.
- The belief that automated MCP server generation by models is not just possible but inevitable, even if it's a moonshot today.
- The assertion that open-source standards, not closed partnerships, are the only scalable path for LLM tool integration.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Contribute directly to the MCP GitHub repo—identify protocol mismatches with your mental model and submit PRs.
- Leverage Inspector for debugging MCP server implementations.
- When building MCP servers, design with the "three users" in mind: end user, client developer, and model.
- Explore vertical-specific MCP servers beyond dev tools—opportunities exist in sales, finance, legal, and education.
- Consider building tooling for AI security, observability, and auditing as models gain more external access.

### What to Avoid
- Don't underestimate the challenge of driving adoption—launching a protocol is just the beginning; real traction requires hands-on builder engagement.
- Beware of assuming closed, partnership-driven integrations can scale; open standards are necessary for ecosystem growth.
- Avoid neglecting the model as a user when designing server APIs; failing to do so can limit utility and adoption.

### Best Practices
- Optimize protocol design for server simplicity, anticipating a future with many more servers than clients.
- Iterate rapidly based on real-world builder feedback; treat the protocol as a living standard.
- Use open-source, community-driven development to surface and fix protocol flaws quickly.

### Personal Stories & Experiences
- Optimize protocol design for server simplicity, anticipating a future with many more servers than clients.
- Iterate rapidly based on real-world builder feedback; treat the protocol as a living standard.
- Use open-source, community-driven development to surface and fix protocol flaws quickly.

### Metrics & Examples
- No specific quantitative metrics are cited, but notable adoption milestones include Cursor, VS Code, Sourcegraph, Google, Microsoft, and OpenAI integrating MCP.
- The timeline from internal hack week to open-source release and subsequent ecosystem adoption is highlighted as a case study in rapid protocol evolution.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=x-8pBqWiTzk)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
