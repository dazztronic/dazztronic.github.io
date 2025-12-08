+++
title = "Remote MCPs: What we learned from shipping — John Welsh, Anthropic"
date = 2025-12-08
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Software engineering--Artificial intelligence","Computer networks--Protocols","Application software--Interoperability"]
tags = ["MCP","JSON-RPC","OAuth 2.1","Websockets","gRPC","Centralized gateway","Tool integration","Model context provisioning","SDK"]

[extra]
excerpt = "John Welsh shares Anthropic's hard-won playbook for taming integration chaos in large-scale AI systems by standardizing on the MCP protocol for all model context provisioning. By building a centralized MCP gateway and prioritizing operational simplicity, Anthropic turns integration from a recurring headache into a solved problem, freeing engineers to focus on value-adding features instead of plumbing. The talk is a masterclass in how to make the 'right thing' the default, leveraging protocol standardization for speed, security, and future-proofing."
video_url = "https://www.youtube.com/watch?v=0NHCyq8bBcM"
video_id = "0NHCyq8bBcM"
cover = "https://img.youtube.com/vi/0NHCyq8bBcM/maxresdefault.jpg"
+++

## Overview

John Welsh shares Anthropic's hard-won playbook for taming integration chaos in large-scale AI systems by standardizing on the MCP protocol for all model context provisioning. By building a centralized MCP gateway and prioritizing operational simplicity, Anthropic turns integration from a recurring headache into a solved problem, freeing engineers to focus on value-adding features instead of plumbing. The talk is a masterclass in how to make the 'right thing' the default, leveraging protocol standardization for speed, security, and future-proofing.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Welsh's approach is defined by ruthless pragmatism: standardize on a single protocol (MCP) for all tool/model integrations, not because it's glamorous, but because it's boring and reliable. He champions the 'pit of success'—designing infrastructure so the easiest path is also the correct one—enabling engineers to fall into best practices by default. The methodology is less about technical novelty and more about organizational leverage: centralizing integration logic, credential management, and observability in a single MCP gateway, making future upgrades and security policies trivial to enforce.

### The Core Problem
Rapid proliferation of custom endpoints and ad-hoc integrations in fast-moving AI teams leads to duplicated effort, inconsistent interfaces, security risks, and brittle systems that are hard to maintain or extend. As AI models become more capable at tool calling, organizations face a combinatorial explosion of integration points, each with its own authentication, transport, and context-handling quirks.

### The Solution Approach
Anthropic standardized all model context provisioning on MCP (Model Context Protocol), building a centralized MCP gateway that abstracts away transport, authentication, and routing. Engineers interact with a simple SDK client, regardless of whether the integration is internal or external. The gateway handles credential management, rate limiting, and observability, while the protocol's extensibility ensures future features are adopted organization-wide via package updates. The approach is to make the correct integration path the path of least resistance, minimizing custom code and maximizing reuse.

### Key Insights
- Standardizing on a protocol like MCP for all integrations is not about competitive advantage, but about eliminating undifferentiated heavy lifting so teams can focus on core product value.
- Building a 'pit of success'—where the easiest way is the right way—drives organizational consistency and reduces integration friction.
- Centralizing context flow and credential management via a gateway not only simplifies engineering but also enables robust security policies and auditing, which are otherwise nearly impossible at scale.

### Concepts & Definitions
- "MCP (Model Context Protocol)" is framed as a JSON-RPC-based protocol for standardized message exchange between models and context providers, with a global transport standard for interoperability.
- "Pit of success" is defined as designing systems so that the easiest path for engineers is also the correct, secure, and maintainable path.
- "Integration chaos" refers to the proliferation of custom, inconsistent endpoints and duplicated logic across services, leading to maintenance and security nightmares.

### Technical Details & Implementation
- The MCP gateway exposes a single connect-to-MCP call, returning an SDK client session; engineers pass in a URL, org ID, and account ID, with authentication handled via signed tokens.
- Transport is abstracted: internally, Anthropic uses websockets with JSON-RPC blobs; other options like gRPC or Unix sockets are equally viable as long as they provide read/write streams.
- Credential management is centralized: the gateway injects bearer tokens and manages OAuth, so individual services never handle user credentials directly.
- All message formats are standardized, enabling easy hooking of policy enforcement, content classification, and auditing tools.

### Tools & Technologies
- MCP (Model Context Protocol)
- MCP SDK client libraries (multi-language)
- Websockets (for internal transport)
- gRPC (alternative transport)
- OAuth 2.1 (for authentication)
- Centralized MCP gateway

### Contrarian Takes & Different Approaches
- It's not a competitive advantage to build bespoke integrations for every tool; standardization and operational simplicity are more valuable than custom engineering in this domain.
- Being 'boring' (i.e., using standard protocols and infrastructure) is a virtue, not a vice, for integration work.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Pick a single protocol for all tool/model integrations—if not MCP, then something else—and enforce it organization-wide.
- Build a gateway or shared infrastructure layer that handles authentication, routing, and observability for all integrations.
- Make the integration path as simple as possible for engineers: one SDK call, minimal configuration, and automatic credential handling.
- Leverage protocol extensibility to future-proof your integrations—update packages, not custom code, as new features arrive.

### What to Avoid
- Avoid duplicating integration logic across services; this leads to inconsistent behaviors and massive maintenance overhead.
- Do not allow every service to handle user credentials or external network connectivity—this creates security and auditing nightmares.
- Beware of underestimating the complexity of transport and authentication; centralize these concerns early.

### Best Practices
- Standardize on a protocol and stick to it for all model context and tool integrations.
- Centralize shared concerns (auth, routing, observability) in a gateway layer.
- Design for the 'pit of success'—make the right thing the easiest thing.
- Use standardized message formats to enable policy enforcement and auditing.

### Personal Stories & Experiences
- Standardize on a protocol and stick to it for all model context and tool integrations.
- Centralize shared concerns (auth, routing, observability) in a gateway layer.
- Design for the 'pit of success'—make the right thing the easiest thing.
- Use standardized message formats to enable policy enforcement and auditing.

### Metrics & Examples
- Example: Four products with four different billing models and token limits can all be unified via MCP's sampling primitives, eliminating weeks of custom integration work.
- Anthropic supports multiple languages internally with their MCP SDKs, demonstrating cross-language standardization.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=0NHCyq8bBcM)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
