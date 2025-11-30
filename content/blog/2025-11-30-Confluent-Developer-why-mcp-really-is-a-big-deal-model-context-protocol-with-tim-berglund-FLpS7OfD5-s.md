+++
title = "Why MCP really is a big deal | Model Context Protocol with Tim Berglund"
date = 2025-11-30
draft = false

[taxonomies]
author = ["Confluent Developer"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Application software--Development","Microservices"]
tags = ["Model Context Protocol (MCP)","Agentic AI","Retrieval Augmented Generation (RAG)","Kafka","REST API","JSON RPC","Confluent","Claude Desktop"]

[extra]
excerpt = "This video reframes the Model Context Protocol (MCP) as a foundational architecture for building agentic AI applications in professional and enterprise contexts, rather than just enhancing desktop tools. By treating MCP as a pluggable, discoverable, and composable protocol for connecting LLMs to real-world tools and resources, it unlocks scalable, maintainable agentic workflows far beyond simple prompt engineering."
video_url = "https://www.youtube.com/watch?v=FLpS7OfD5-s"
video_id = "FLpS7OfD5-s"
cover = "https://img.youtube.com/vi/FLpS7OfD5-s/maxresdefault.jpg"
+++

## Overview

This video reframes the Model Context Protocol (MCP) as a foundational architecture for building agentic AI applications in professional and enterprise contexts, rather than just enhancing desktop tools. By treating MCP as a pluggable, discoverable, and composable protocol for connecting LLMs to real-world tools and resources, it unlocks scalable, maintainable agentic workflows far beyond simple prompt engineering.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Rather than focusing on consumer-facing enhancements or desktop integrations, the approach positions MCP as the backbone for enterprise-grade agentic AI, emphasizing its role in enabling modular, reusable, and composable access to tools and data sources. The analogy to USB-C is explicitly rejected as misleading; instead, the protocol is framed as a microservices-like architecture for AI agents.

### The Core Problem
LLMs by themselves only generate text and lack the ability to take real-world actions or access up-to-date, organization-specific data. Existing solutions often hardcode integrations, making them brittle, non-reusable, and difficult to scale across teams or use cases.

### The Solution Approach
The methodology involves architecting agentic applications as host applications that use an MCP client library to connect to one or more MCP servers. These servers expose tools, resources, and capabilities via well-defined RESTful endpoints, described by the MCP specification. The workflow is: (1) the client queries the server for available capabilities, (2) the LLM is prompted with both the user input and the list of resources/tools, (3) the LLM recommends which resources to fetch or tools to invoke, (4) the client retrieves data or invokes tools as instructed, and (5) the process is composable, allowing servers to act as clients to other servers, enabling complex, modular workflows.

### Key Insights
- Pluggability and discoverability are core: tools and resources can be added or swapped without modifying agent code, enabling rapid iteration and reuse.
- Composability is a game-changer: MCP servers can themselves be clients, chaining capabilities across organizational boundaries or technology stacks.
- Contrary to hype cycles, RAG (Retrieval Augmented Generation) remains highly relevant in enterprise contexts and integrating it via MCP is both practical and future-proof.

### Concepts & Definitions
- "Agentic AI" is defined as AI that can cause effects in the world by invoking tools and accessing resources, not just generating text.
- "Host application" refers to the microservice or application embedding the MCP client and orchestrating agentic workflows.
- "Resource" is any external data (e.g., calendar, database, Kafka topic) that can be surfaced to the LLM for context.
- "Tool" is any actionable endpoint or API (e.g., calendar booking, restaurant reservation) that the agent can invoke.

### Technical Details & Implementation
- MCP communication supports both standard IO (for local processes) and HTTP/Server Sent Events (for distributed/cloud setups), with JSON RPC as the message format.
- Capabilities are exposed via RESTful endpoints, including a capabilities list endpoint describing available tools, resources, and prompts.
- A typical configuration involves a host application (microservice) with the MCP client library, connecting to one or more MCP servers registered via URLs (often managed in a properties file).
- Tool invocation is handled via structured API calls to LLMs, which return recommended actions and parameters; the client is responsible for executing these actions.

### Tools & Technologies
- MCP client library (for host applications)
- MCP server (can be custom or prebuilt, e.g., Confluent MCP server for Kafka integration)
- Claude Desktop (as an example of a local LLM host application)
- Kafka (as a resource/data source)
- Yelp API (as an example of an external resource)

### Contrarian Takes & Different Approaches
- Dismisses the idea that RAG is obsolete, arguing it is still essential for enterprise data integration.
- Rejects the 'USB-C for AI' analogy as misleading, advocating for an architectural, microservices-based mental model instead.
- Challenges the focus on desktop agentic enhancements, insisting the real value is in scalable, professional, enterprise agentic AI.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- When building agentic applications, design your integrations as MCP servers exposing tools and resources, rather than hardcoding logic into the agent.
- Document and describe resources and tools clearly in the MCP server so LLMs can reason about their use effectively.
- Leverage the composability of MCP by chaining servers, e.g., using a Confluent MCP server to access Kafka topics without duplicating integration code.

### What to Avoid
- Avoid baking integrations directly into agent code; this leads to non-reusable, siloed solutions.
- Do not rely solely on standard IO for communication in distributed or enterprise environments—use HTTP/SSE for scalability.
- Neglecting to provide clear, descriptive metadata for resources/tools in the MCP server can hinder LLM reasoning and degrade agent performance.

### Best Practices
- Treat agentic AI applications as microservices, using MCP for modularity and maintainability.
- Keep the agent logic minimal and delegate discovery and invocation of resources/tools to the MCP protocol.
- Use structured API calls for tool invocation, letting LLMs recommend actions but keeping execution under explicit client control for safety and auditability.

### Personal Stories & Experiences
- Treat agentic AI applications as microservices, using MCP for modularity and maintainability.
- Keep the agent logic minimal and delegate discovery and invocation of resources/tools to the MCP protocol.
- Use structured API calls for tool invocation, letting LLMs recommend actions but keeping execution under explicit client control for safety and auditability.

### Metrics & Examples
- No specific quantitative metrics or case studies with numbers are cited, but practical examples include integrating calendar APIs, restaurant bookings, and Kafka topics via MCP.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=FLpS7OfD5-s)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
