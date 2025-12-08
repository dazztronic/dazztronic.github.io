+++
title = "The State of MCP observability: Observable.tools — Alex Volkov and Benjamin Eckel, W&B and Dylibso"
date = 2025-12-08
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Software engineering--Distributed systems","Artificial intelligence--Software tools","Computer software--Quality control"]
tags = ["MCP","OpenTelemetry","Distributed tracing","Observability","Weights & Biases Weave","MCP.Run","Semantic conventions","Python","TypeScript"]

[extra]
excerpt = "This talk exposes a critical blind spot in observability for MCP (Modular Command Protocol) powered AI agents, especially as teams increasingly compose agents from distributed tools and services. By marrying open telemetry standards with MCP, the presenters show how to achieve true end-to-end tracing—even across language and vendor boundaries—while advocating for a community-driven, vendor-neutral approach to observability."
video_url = "https://www.youtube.com/watch?v=Lcqat4iP_lE"
video_id = "Lcqat4iP_lE"
cover = "https://img.youtube.com/vi/Lcqat4iP_lE/maxresdefault.jpg"
+++

## Overview

This talk exposes a critical blind spot in observability for MCP (Modular Command Protocol) powered AI agents, especially as teams increasingly compose agents from distributed tools and services. By marrying open telemetry standards with MCP, the presenters show how to achieve true end-to-end tracing—even across language and vendor boundaries—while advocating for a community-driven, vendor-neutral approach to observability.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The presenters uniquely blend deep production experience running MCP at scale with a pragmatic, hands-on push for open, standardized observability—eschewing vendor lock-in and bespoke integrations. Their approach is both technical (demonstrating cross-language tracing with OpenTelemetry) and community-oriented (launching the Observable.tools manifesto to rally ecosystem-wide alignment).

### The Core Problem
As MCP adoption grows, developers lose visibility into agent behavior due to the distributed, multi-vendor, and multi-language nature of tool composition—creating a dangerous observability blind spot. This undermines reliability, security, and the ability to debug or monitor production systems, especially for enterprises with strict operational requirements.

### The Solution Approach
They advocate instrumenting both MCP clients and servers with OpenTelemetry (otel), propagating trace context through MCP's protocol meta payload—even when crossing language or administrative domains. The approach involves extracting the current span on the client, injecting it into the payload, and having the server inherit and continue the trace, so all spans are stitched together in a unified observability backend. They also push for semantic conventions and higher-level SDKs to make this seamless for developers, regardless of their expertise in observability.

### Key Insights
- MCP agents are fundamentally distributed systems, so established distributed tracing techniques (like OpenTelemetry) are directly applicable.
- Vendor-specific observability integrations (e.g., bespoke Weave SDK support) are a stopgap; true scalability and interoperability require open, standardized protocols.
- Passing trace context via MCP's meta payload is a practical hack that works today, but the ecosystem needs first-class support and tooling to make this robust and accessible.

### Concepts & Definitions
- Trace: An atomic operation in a distributed system, composed of a tree of spans representing each step.
- Span: A timed operation with arbitrary metadata, representing a single step within a trace.
- Sync: The centralized backend or collector that receives spans from instrumented code, enabling aggregation and visualization.
- Semantic conventions: Agreed-upon attribute schemas for spans, allowing observability platforms to interpret and visualize traces meaningfully across tools and vendors.
- Domain: Not just a network domain, but an administrative boundary—whether you control both client and server, or interact with third-party services.

### Technical Details & Implementation
- Set the MCP_TRACE_LIST_OPERATION environment variable on both client and server to enable basic tracing in Weave's Python SDK.
- To achieve cross-language tracing, extract the current OpenTelemetry span in the client (e.g., TypeScript), inject it into the MCP protocol's meta payload, and on the server side, extract and continue the trace before emitting spans to the sync.
- All observability backends (e.g., Weave, Lockfire, etc.) are converging on OpenTelemetry as the wire protocol, enabling plug-and-play backend switching with minimal code changes—often just configuration.
- A working demo and code are available on GitHub, showing how to adapt this approach for your own agents.

### Tools & Technologies
- Weights & Biases Weave (with MCP and OpenTelemetry support)
- MCP.Run (Dylibso's platform for MCP agents)
- OpenTelemetry (otel) for distributed tracing
- Observable.tools (community manifesto and initiative)
- Lockfire (another observability provider mentioned)
- GitHub (for code samples and third-party MCP servers)
- Stripe (example of third-party MCP server)

### Contrarian Takes & Different Approaches
- The insistence that vendor-neutral, open protocols are the only sustainable path for observability in the MCP ecosystem—contrary to the proliferation of proprietary integrations.
- Advocacy for community-driven conventions and tooling over waiting for formal spec adoption or top-down mandates.
- The view that you shouldn't need to be an observability expert to get this working—pushing for higher-level SDKs and conventions.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Instrument both MCP clients and servers with OpenTelemetry, propagating trace context via the protocol's meta payload.
- Adopt semantic conventions for your spans—contribute to or align with the GenAI semantic conventions effort.
- If building platforms or SDKs, prioritize vendor-neutral, open protocol support and join community efforts like Observable.tools.
- Check out the provided GitHub demo to see cross-language, cross-domain tracing in action and adapt it for your own agents.
- If you're an AI engineer, audit your agent's toolchain for observability gaps and push for end-to-end tracing.

### What to Avoid
- Relying solely on bespoke, vendor-specific observability integrations leads to fragmentation and blind spots as your stack grows.
- Neglecting to propagate trace context across administrative domains (e.g., third-party servers) results in black-box spans and lost debugging capability.
- Assuming that observability 'just works' with MCP out of the box is a trap—explicit instrumentation and context propagation are required.

### Best Practices
- Use OpenTelemetry as the standard for distributed tracing in MCP-powered agents, regardless of language or vendor.
- Propagate trace context explicitly through protocol meta payloads to enable end-to-end trace stitching.
- Collaborate on semantic conventions so that all observability platforms can interpret your traces consistently.
- Favor configuration-based backend switching (otel syncs) over code changes for observability integration.

### Personal Stories & Experiences
- Use OpenTelemetry as the standard for distributed tracing in MCP-powered agents, regardless of language or vendor.
- Propagate trace context explicitly through protocol meta payloads to enable end-to-end trace stitching.
- Collaborate on semantic conventions so that all observability platforms can interpret your traces consistently.
- Favor configuration-based backend switching (otel syncs) over code changes for observability integration.

### Metrics & Examples
- A trace example shows an HTTP request taking 350 milliseconds, with sub-operations like markdown generation visualized in the trace.
- The time to adapt a TypeScript agent to send traces to Weave via OpenTelemetry was 'a few minutes,' demonstrating cross-language ease.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=Lcqat4iP_lE)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
