+++
title = "Building Multimodal AI Agents From Scratch — Apoorva Joshi, MongoDB"
date = 2025-12-10
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Machine learning","Software engineering--Artificial intelligence"]
tags = ["Multimodal agents","Large language models","RAG","Python","Jupyter Notebooks","Memory management","Tool schema","Embedding models","MongoDB"]

[extra]
excerpt = "This workshop demystifies the process of building multimodal AI agents from scratch, focusing on hands-on, minimal-abstraction construction using Python. By breaking down agent architecture and multimodality into actionable components, it empowers practitioners to deeply understand and implement agents that handle both text and image data. The session stands out for its practical, stepwise methodology and candid discussion of trade-offs, memory management, and real-world applicability."
video_url = "https://www.youtube.com/watch?v=640KMYtxCeI"
video_id = "640KMYtxCeI"
cover = "https://img.youtube.com/vi/640KMYtxCeI/maxresdefault.jpg"
+++

## Overview

This workshop demystifies the process of building multimodal AI agents from scratch, focusing on hands-on, minimal-abstraction construction using Python. By breaking down agent architecture and multimodality into actionable components, it empowers practitioners to deeply understand and implement agents that handle both text and image data. The session stands out for its practical, stepwise methodology and candid discussion of trade-offs, memory management, and real-world applicability.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Apoorva Joshi's approach is distinctive in its insistence on stripping away abstractions to expose the core mechanics of agent construction, prioritizing direct, from-scratch implementation over reliance on high-level frameworks. She emphasizes understanding the 'why' behind each architectural decision, especially regarding memory, tool integration, and multimodal reasoning, rather than just assembling prebuilt components.

### The Core Problem
The main challenge addressed is enabling AI systems to handle complex, multi-step tasks that require reasoning across multiple data modalities (text and images), while maintaining coherent, context-aware conversations. This is critical as real-world data and user expectations increasingly demand agents that can process and synthesize heterogeneous information sources.

### The Solution Approach
The methodology involves decomposing the agent into modular components: LLM-powered reasoning, tool schemas for external actions (e.g., API calls), and explicit memory management (short-term for the workshop). The workflow starts with user queries, leverages LLMs to select and invoke tools, processes results, and iteratively refines responses, all while maintaining conversational context via session-based memory. Multimodality is achieved by integrating both text and image data handling, with clear separation of embedding-based retrieval and generative multimodal LLMs.

### Key Insights
- Agents should only be used when task complexity or personalization justifies their higher cost and latency—simple prompting or retrieval-augmented generation (RAG) suffice for less demanding use cases.
- Short-term memory (session-based chat history) is often sufficient for many agent applications; long-term memory adds complexity and should be implemented only as needed.
- Directly exposing the agent's tool schema and memory mechanisms enables fine-grained control and deeper understanding, which is invaluable for debugging and extending agent capabilities.

### Concepts & Definitions
- AI Agent: A system using an LLM to reason, plan, and execute actions via tools, iteratively refining its approach based on results and memory.
- Simple Prompting: Directly querying an LLM, limited to its pre-trained (parametric) knowledge.
- RAG (Retrieval-Augmented Generation): Enhancing LLMs with external data retrieval for more accurate, personalized responses.
- Multimodality: The capability of models to process, understand, and generate multiple data types (e.g., text, images, audio).
- Short-term Memory: Storage and retrieval of conversational context within a single session; contrasted with long-term memory spanning multiple sessions.

### Technical Details & Implementation
- Agent architecture consists of a Python-based orchestrator, an LLM (with tool access), a tool schema (name, description, input types), and a memory component (session-based chat history stored in a database).
- Tools are defined with explicit schemas (name, description, input parameters) and invoked via code that parses LLM outputs and executes API calls (e.g., weather API).
- Short-term memory is managed by associating each user query with a session ID, retrieving and updating conversation history in a database for each turn.
- Two classes of multimodal models are leveraged: embedding models for unified retrieval across modalities, and multimodal LLMs for reasoning and generation.
- Hands-on implementation is provided via Jupyter notebooks (lab.ipb for coding, solutions.ipb for reference), with in-line documentation and modular code patterns.

### Tools & Technologies
- Python (core implementation language)
- Large Language Models (LLMs, e.g., OpenAI, Claude)
- Weather API (example tool integration)
- Jupyter Notebooks (lab.ipb, solutions.ipb)
- MongoDB (implied for session/memory storage)

### Contrarian Takes & Different Approaches
- Contrary to the hype, agents are not always the right solution—use them judiciously and only when their advanced capabilities are truly needed.
- Long-term memory is often overemphasized; many practical applications function well with just short-term, session-based memory.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by building agents with minimal abstractions to gain a deep understanding before adopting higher-level frameworks.
- Define tool schemas explicitly, including parameter types and descriptions, to streamline LLM-tool interactions.
- Implement session-based short-term memory for conversational coherence; log both user queries and LLM responses for each session.
- Use embedding models for unified multimodal retrieval and multimodal LLMs for reasoning/generation when handling text-image data.
- Leverage provided notebooks for hands-on practice, choosing between code-completion (lab.ipb) and reference (solutions.ipb) modes.

### What to Avoid
- Avoid using agents for simple tasks—overengineering leads to unnecessary complexity, cost, and latency.
- Do not neglect explicit memory management; lack of session context results in incoherent multi-turn conversations.
- Relying solely on LLM parametric knowledge limits the agent's ability to answer up-to-date or personalized queries.

### Best Practices
- Modularize agent components (reasoning, tools, memory) for clarity and extensibility.
- Log all user queries and LLM responses to enable debugging and future personalization.
- Start with short-term memory and expand to long-term only if application requirements demand it.

### Personal Stories & Experiences
- Modularize agent components (reasoning, tools, memory) for clarity and extensibility.
- Log all user queries and LLM responses to enable debugging and future personalization.
- Start with short-term memory and expand to long-term only if application requirements demand it.

### Metrics & Examples
- Workshop allocates 55-60 minutes for hands-on agent coding, emphasizing practical understanding over theoretical coverage.
- Agent example: answering questions about a large document corpus and analyzing charts/diagrams, demonstrating real-world multimodal use cases.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=640KMYtxCeI)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
