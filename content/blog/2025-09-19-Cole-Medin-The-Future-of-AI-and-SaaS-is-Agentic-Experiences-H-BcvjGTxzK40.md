+++
title = "The Future of AI and SaaS is Agentic Experiences (Here's How to Build Them)"
date = 2025-09-19
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Application software", "Human-computer interaction", "Software engineering--Protocols"]

[extra]
excerpt = "Cole Medin reframes the future of AI in SaaS as being about deeply embedding agents into product experiences, not building standalone agent apps. His perspective matters because he provides a practical, protocol-driven workflow for rapidly integrating agentic capabilities into real applications, emphasizing human-in-the-loop design and seamless frontend-backend state sync. Medin's approach is both technically actionable and strategically contrarian, offering a clear path for developers to build resilient, differentiated AI-powered products."
video_url = "https://www.youtube.com/watch?v=BcvjGTxzK40"
video_id = "BcvjGTxzK40"
cover = "https://img.youtube.com/vi/BcvjGTxzK40/maxresdefault.jpg"
+++

## Overview

Cole Medin reframes the future of AI in SaaS as being about deeply embedding agents into product experiences, not building standalone agent apps. His perspective matters because he provides a practical, protocol-driven workflow for rapidly integrating agentic capabilities into real applications, emphasizing human-in-the-loop design and seamless frontend-backend state sync. Medin's approach is both technically actionable and strategically contrarian, offering a clear path for developers to build resilient, differentiated AI-powered products.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's distinctive approach is his focus on 'agentic experiences'—where AI agents are not the product, but are woven into the fabric of the application to enhance its unique value. He champions AG-UI as a protocol to standardize agent-app integration, enabling rapid, modular development across any frontend or agent framework. He rejects the hype of agent-as-product, instead advocating for invisible, utility-driven agent integration that survives beyond the AI hype cycle.

### The Core Problem
The problem is that most AI SaaS builders are stuck creating standalone agent apps, which are likely to be rendered obsolete by general-purpose agents (like ChatGPT) as they improve. The real challenge is making agents a natural, value-adding part of existing products, which is technically and architecturally more complex but crucial for long-term product survival.

### The Solution Approach
Medin's methodology is to use AG-UI as a protocol layer that decouples agent logic from frontend implementation, allowing any agent framework (like Pydantic AI) to connect with any frontend (like CopilotKit). He demonstrates a workflow: scaffold a CopilotKit app, connect it to a Pydantic AI agent via AG-UI, and use frontend tools to pass commands and sync state. His mental model is that agentic experiences require standardized communication, human-in-the-loop controls, and seamless state management between UI and agent.

### Key Insights
- Embedding agents as invisible, utility-driven features within products creates lasting value, while standalone agent apps are vulnerable to commoditization.
- Contrarian take: The future isn't agent marketplaces or agent-first SaaS, but SaaS with deeply integrated, protocol-driven agentic experiences.
- Lesson: Building agentic experiences is harder than chatbots, but AG-UI and modular frameworks make it dramatically easier and faster.

### Concepts & Definitions
- 'Agentic experiences': Applications where AI agents are deeply embedded as part of the product's core functionality, not as standalone features.
- 'AG-UI': A protocol that standardizes how AI agents connect to applications, decoupling frontend and backend agent logic.
- 'Human-in-the-loop': Keeping users in control by exposing agent tools and state in the frontend, not ceding full autonomy to the agent.

### Technical Details & Implementation
- Uses AG-UI protocol to standardize agent-app communication, enabling plug-and-play agent integration.
- Combines CopilotKit (frontend), AG-UI (protocol), and Pydantic AI (agent framework) for rapid prototyping.
- Recommends scaffolding with CopilotKit CLI, connecting to a Pydantic AI backend via AG-UI, and leveraging frontend tools for state sync and command passing.
- Demonstrates local development with minimal setup: 'literally built this out in like a half hour after I brought in my existing agent.'

### Tools & Technologies
- AG-UI (protocol for agent-app integration)
- CopilotKit (frontend/client framework supporting AG-UI)
- Pydantic AI (agent framework, especially for RAG agents)
- CopilotKit Cloud (optional hosting for agent backends)

### Contrarian Takes & Different Approaches
- Disagrees with the trend of building agent-first SaaS or agent marketplaces, arguing these will be obsolete.
- Advocates for invisible agent integration over agent-centric product design.
- Challenges the idea that agentic experiences are too complex for rapid development—shows it's possible with the right stack.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by scaffolding a CopilotKit app and connecting it to your agent backend via AG-UI for instant agentic capabilities.
- Expose agent tools and state in the frontend to enable human-in-the-loop workflows.
- Use AG-UI's quickstart and modularity to rapidly prototype and iterate on agentic features.

### What to Avoid
- Don't build standalone agent apps—these are likely to be outcompeted by general-purpose agents.
- Avoid tightly coupling agent logic to frontend code; use protocols like AG-UI to keep architecture modular.
- Neglecting human-in-the-loop controls leads to brittle, less usable agentic experiences.

### Best Practices
- Standardize agent-app communication with AG-UI for flexibility and speed.
- Leverage modular toolchains (CopilotKit + AG-UI + Pydantic AI) for rapid iteration.
- Prioritize frontend tools and state sync to keep users in control and experiences fluid.

### Personal Stories & Experiences
- Medin shares that after experimenting with isolated chatbots, he found building agentic experiences much harder, but AG-UI made it 'so easy' to integrate existing agents into full apps.
- He recounts building a full agentic app in under an hour using his workflow, highlighting the productivity boost from standardized protocols.

### Metrics & Examples
- Built a full agentic application in 'like a half hour' after integrating an existing agent.
- Demonstrates instant state sync and tool invocation between frontend and agent using AG-UI.

## Resources & Links

- [https://github.com/CopilotKit/CopilotKit](https://github.com/CopilotKit/CopilotKit)
- [https://dynamous.ai/ai-coding-workshop](https://dynamous.ai/ai-coding-workshop)
- [https://github.com/ag-ui-protocol/ag-ui](https://github.com/ag-ui-protocol/ag-ui)
- [https://github.com/coleam00/ottomator-agents/tree/main/ag-ui-rag-agent](https://github.com/coleam00/ottomator-agents/tree/main/ag-ui-rag-agent)
- [https://dojo.ag-ui.com/pydantic-ai](https://dojo.ag-ui.com/pydantic-ai)
- [https://ai.pydantic.dev/ag-ui/](https://ai.pydantic.dev/ag-ui/)
- [Video URL](https://www.youtube.com/watch?v=BcvjGTxzK40)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

