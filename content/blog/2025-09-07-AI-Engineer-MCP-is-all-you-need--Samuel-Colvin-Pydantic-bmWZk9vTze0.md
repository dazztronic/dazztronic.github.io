+++
title = "MCP is all you need — Samuel Colvin, Pydantic"
date = 2025-09-07
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Protocols", "Software engineering--Agent-based systems", "Python (Computer program language)"]

[extra]
excerpt = "Samuel Colvin, creator of Pydantic, argues that the Model Communication Protocol (MCP) is a powerful, underutilized foundation for agent-to-agent communication in AI systems, challenging the trend of overcomplicating agent architectures. His perspective is grounded in practical experience building widely adopted Python tools and frameworks, emphasizing simplicity, composability, and leveraging existing protocols to streamline AI engineering."
video_url = "https://www.youtube.com/watch?v=bmWZk9vTze0"
video_id = "bmWZk9vTze0"
cover = "https://img.youtube.com/vi/bmWZk9vTze0/maxresdefault.jpg"
+++

## Overview

Samuel Colvin, creator of Pydantic, argues that the Model Communication Protocol (MCP) is a powerful, underutilized foundation for agent-to-agent communication in AI systems, challenging the trend of overcomplicating agent architectures. His perspective is grounded in practical experience building widely adopted Python tools and frameworks, emphasizing simplicity, composability, and leveraging existing protocols to streamline AI engineering.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Colvin's approach is defined by a relentless focus on pragmatic, minimalistic solutions—he advocates for using MCP as a unifying protocol for agent communication, rather than inventing bespoke or overly complex systems. He draws on his experience with Pydantic and its ecosystem, applying the same principles of clarity, validation, and composability to agent frameworks. His methodology is to identify where the community is overengineering and to demonstrate how a single, well-designed protocol can cover most use cases.

### The Core Problem
The proliferation of custom, fragmented agent-to-agent communication methods in AI engineering leads to unnecessary complexity, maintenance burdens, and interoperability issues. Colvin addresses the need for a standardized, robust protocol that simplifies these interactions, especially as agent frameworks become more central in generative AI applications.

### The Solution Approach
Colvin proposes adopting MCP as the backbone for agent communication, leveraging its ability to handle tool calls, LLM interactions, and even recursive agent workflows via 'sampling.' He demonstrates how MCP can be used both client- and server-side, enabling agents to delegate tasks, proxy LLM calls, and maintain a clean separation of concerns. His mental model is to treat agent communication as a protocol problem, not an application-specific hack, and to build on proven, composable primitives.

### Key Insights
- Most agent-to-agent communication needs can be met with MCP, avoiding the need for custom protocols.
- Sampling within MCP allows remote agents to piggyback on the LLM context of the original agent, enabling powerful recursive workflows.
- Overcomplicating agent architectures is a common trap—simplicity and protocol adherence yield more maintainable and interoperable systems.

### Concepts & Definitions
- "Sampling" in MCP: a mechanism where a server can make requests back through the client to the LLM, enabling recursive or delegated agent actions.
- MCP (Model Communication Protocol): a standardized protocol for agent-to-agent and agent-to-tool communication, designed to reduce fragmentation.
- Agent framework: a system for orchestrating LLMs, tools, and workflows, often requiring robust communication primitives.

### Technical Details & Implementation
- Demonstrates MCP 'sampling' where a server can request the client to proxy LLM calls, enabling recursive agent workflows.
- Pydantic AI framework supports MCP sampling both as client (proxying LLM calls) and server (registering as an LLM tool).
- Shows how agent calls within MCP can generate SQL queries, with full traceability and validation.

### Tools & Technologies
- Pydantic (data validation library for Python)
- Pydantic AI (agent framework built on Pydantic principles)
- Pydantic Logfire (observability platform)
- MCP Python SDK

### Contrarian Takes & Different Approaches
- Challenges the notion that each new agent use case requires a bespoke communication protocol.
- Argues that most complexity in agent frameworks is self-inflicted and unnecessary.
- Defends the view that protocol-driven design (MCP) is sufficient for the majority of agent communication needs.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Adopt MCP as the default protocol for agent communication to reduce complexity and improve interoperability.
- Leverage MCP sampling to enable agents to delegate tasks and share LLM context across tool boundaries.
- Use frameworks (like Pydantic AI) that natively support MCP and its advanced features for rapid prototyping.

### What to Avoid
- Beware of inventing new agent communication methods when robust protocols like MCP already exist.
- Overengineering agent frameworks leads to brittle, hard-to-maintain systems.
- Sampling is powerful but not yet widely supported—ensure your stack can handle it before relying on it in production.

### Best Practices
- Build agent workflows on top of standardized protocols (MCP) for future-proofing and composability.
- Instrument agent calls for traceability (e.g., logging generated SQL and LLM responses).
- Iterate on protocol support within your frameworks, contributing back to open standards.

### Personal Stories & Experiences
- Colvin references the evolution of Pydantic from a library to a company, applying its principles to new domains like agent frameworks.
- He candidly shares that sampling support in Pydantic AI is still in PR stage, reflecting a transparent, iterative development process.
- Invites attendees to see live demos and even failures, emphasizing a culture of learning through experimentation.

### Metrics & Examples
- Pydantic is downloaded about 360 million times a month (140 times a second), indicating massive adoption.
- Demonstrates agent-generated SQL queries within MCP, showing real-world traceability and validation.

## Resources & Links

- [https://x.com/samuel_colvin](https://x.com/samuel_colvin)
- [https://www.linkedin.com/in/samuel-colvin/](https://www.linkedin.com/in/samuel-colvin/)
- [https://github.com/samuelcolvin](https://github.com/samuelcolvin)
- [https://pydantic.dev/](https://pydantic.dev/)
- [Video URL](https://www.youtube.com/watch?v=bmWZk9vTze0)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Contrarian Wisdom

