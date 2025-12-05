+++
title = "Exposing Agents as MCP servers with mcp-agent: Sarmad Qadri"
date = 2025-12-05
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Computer software--Interoperability","Workflow management systems"]
tags = ["Model Context Protocol (MCP)","MCP-agent","Language Server Protocol (LSP)","Temporal","Airflow","Claude Desktop","Augmented LLM","Microservices","Workflow orchestration","Multi-agent systems"]

[extra]
excerpt = "This talk presents a forward-looking, protocol-first approach to agent development, arguing that the Model Context Protocol (MCP) will become the backbone for scalable, composable, and platform-agnostic agent systems. By exposing agents themselves as MCP servers and modeling them as asynchronous workflows, the methodology unlocks multi-agent collaboration, robust orchestration, and seamless integration across the AI ecosystem. The perspective is rooted in lessons from protocol standardization (LSP) and a conviction that the agent landscape is about to shift from monolithic frameworks to lightweight, interoperable services."
video_url = "https://www.youtube.com/watch?v=uFPAtKIN-FQ"
video_id = "uFPAtKIN-FQ"
cover = "https://img.youtube.com/vi/uFPAtKIN-FQ/maxresdefault.jpg"
+++

## Overview

This talk presents a forward-looking, protocol-first approach to agent development, arguing that the Model Context Protocol (MCP) will become the backbone for scalable, composable, and platform-agnostic agent systems. By exposing agents themselves as MCP servers and modeling them as asynchronous workflows, the methodology unlocks multi-agent collaboration, robust orchestration, and seamless integration across the AI ecosystem. The perspective is rooted in lessons from protocol standardization (LSP) and a conviction that the agent landscape is about to shift from monolithic frameworks to lightweight, interoperable services.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Sarmad Qadri draws a direct parallel between the standardization impact of the Language Server Protocol (LSP) in developer tooling and the transformative potential of MCP for agents. He uniquely advocates for agents not just as clients of MCP servers, but as first-class MCP servers themselves—enabling agents to be invoked, composed, and orchestrated just like any other service. This protocol-native, microservices-inspired view is a departure from monolithic agent frameworks and positions agents as modular, reusable, and infrastructure-agnostic components.

### The Core Problem
The fragmentation and complexity of building production-grade agents—where tool integration, orchestration, and workflow management are brittle, non-standardized, and often locked into heavyweight frameworks—has stalled enterprise adoption and limited scalability. The lack of a universal protocol for connecting LLMs to tools, data, and other agents has made multi-agent collaboration and robust workflow orchestration difficult.

### The Solution Approach
The methodology centers on adopting MCP as the universal interface for agent-tool-data connectivity, treating agents themselves as MCP servers. Agents are architected as asynchronous workflows (using orchestration tools like Temporal or Airflow), which allows for pausing, resuming, retrying, and human-in-the-loop steps. The approach involves implementing canonical agent patterns (augmented LLM, evaluator/generator loops, planner/sub-agent orchestration) as MCP-native microservices, enabling composability and platform independence. The MCP-agent library operationalizes these patterns, making it easy to deploy agents as scalable, reusable services.

### Key Insights
- Moving agent logic from monolithic frameworks to protocol-native microservices (MCP servers) dramatically simplifies integration, scaling, and reuse.
- Agent workflows should be modeled as asynchronous, orchestrated processes—enabling features like pause/resume, retries, and human feedback, which are essential for robust production systems.
- Standardization (as seen with LSP) is a force multiplier: once a protocol like MCP reaches critical mass, both clients and servers can be developed independently, accelerating ecosystem growth.

### Concepts & Definitions
- Model Context Protocol (MCP): A standardized interface for connecting LLMs to tools, data, and resources, enabling interoperability across platforms.
- Augmented LLM: An LLM with access to external tools, data, or resources, forming the base building block for agentic workflows.
- Agent as MCP server: Treating an agent as a service that exposes its capabilities via the MCP protocol, making it invocable and composable like any other API.
- Asynchronous workflow: A process that can be paused, resumed, retried, or await external input, managed by orchestration infrastructure.

### Technical Details & Implementation
- Agents are implemented as MCP servers, exposing their workflows as endpoints that can be invoked by any MCP-compatible client (e.g., Claude Desktop).
- Workflow orchestration is handled by tools like Temporal, which manages execution, retries, failure handling, and state persistence.
- Canonical agent patterns (e.g., planner/sub-agent, evaluator/generator) are encoded as reusable workflow graphs, typically in ~100 lines of code per agent.
- Multi-agent collaboration is enabled by chaining MCP agent servers—one agent can invoke another over MCP, forming a network of composable services.
- Separation of execution environments: agent compute runs independently from the client, allowing for long-running, asynchronous jobs.

### Tools & Technologies
- MCP-agent (open-source library for MCP-native agents)
- Temporal (workflow orchestration)
- Airflow (workflow orchestration, mentioned)
- Claude Desktop (MCP client)
- GitHub, Slack, Linear (as examples of MCP servers)
- Anthropic's 'Building Effective Agents' blog (reference for agent patterns)

### Contrarian Takes & Different Approaches
- Contrary to the prevailing focus on monolithic agent frameworks, the talk argues for lightweight, protocol-native microservices as the future.
- Challenges the assumption that agent orchestration must be tightly coupled to the client or chat session—advocates for asynchronous, infrastructure-managed workflows.
- Predicts that every SaaS product will soon expose itself as an MCP server, and that every agent should do the same.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Design agents as MCP servers to maximize composability and platform independence—start by exposing your agent's workflow as an MCP endpoint.
- Leverage workflow orchestration tools (e.g., Temporal) to manage agent execution, retries, and human-in-the-loop steps.
- Implement canonical agent patterns (augmented LLM, planner/evaluator) as reusable workflows, using the MCP-agent library as a template.
- Separate agent compute from client invocation to enable scalable, asynchronous processing and improve reliability.

### What to Avoid
- Avoid building agents as monolithic, tightly coupled frameworks—this limits reuse, scalability, and integration.
- Do not assume synchronous, in-proc agent execution; production agents must handle asynchrony, failures, and long-running tasks.
- Relying on platform-specific connectors or APIs will lead to fragmentation and maintenance headaches as the ecosystem evolves.

### Best Practices
- Standardize on MCP for all agent-tool-data interactions to future-proof your architecture.
- Model agents as microservices with clear, protocol-defined interfaces, enabling independent deployment and scaling.
- Use workflow orchestration infrastructure to manage agent state, retries, and human feedback loops.

### Personal Stories & Experiences
- Standardize on MCP for all agent-tool-data interactions to future-proof your architecture.
- Model agents as microservices with clear, protocol-defined interfaces, enabling independent deployment and scaling.
- Use workflow orchestration infrastructure to manage agent state, retries, and human feedback loops.

### Metrics & Examples
- Agent workflows demonstrated in the talk are implemented in about 100 lines of code, yet handle sophisticated multi-step tasks.
- Case study: A grading agent orchestrates multiple sub-agents (finder, proofreader, fact checker, style enforcer, writer) to process and evaluate a student short story, with full asynchrony and state management.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=uFPAtKIN-FQ)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
