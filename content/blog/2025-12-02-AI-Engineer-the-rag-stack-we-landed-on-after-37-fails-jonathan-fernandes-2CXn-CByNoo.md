+++
title = "The RAG Stack We Landed On After 37 Fails - Jonathan Fernandes"
date = 2025-12-02
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Machine learning","Software engineering--Artificial intelligence"]
tags = ["RAG","Docker","LlamaIndex","LangGraph","Quadrant","Olama","Hugging Face","LangSmith","Arize Phoenix","Cohere","Nvidia","RAGAS","Cross-encoder","Bi-encoder","Vector database","Monitoring","Re-ranking","Evaluation"]

[extra]
excerpt = "Jonathan Fernandes delivers a brutally practical, battle-tested RAG stack distilled from 37 failed attempts, emphasizing what actually works in production—especially for regulated, on-premise environments. His approach is refreshingly actionable, mapping every RAG component to specific tools and workflows, and sharing the nuanced tradeoffs and lessons that only come from repeated real-world deployment."
video_url = "https://www.youtube.com/watch?v=2CXn-CByNoo"
video_id = "2CXn-CByNoo"
cover = "https://img.youtube.com/vi/2CXn-CByNoo/maxresdefault.jpg"
+++

## Overview

Jonathan Fernandes delivers a brutally practical, battle-tested RAG stack distilled from 37 failed attempts, emphasizing what actually works in production—especially for regulated, on-premise environments. His approach is refreshingly actionable, mapping every RAG component to specific tools and workflows, and sharing the nuanced tradeoffs and lessons that only come from repeated real-world deployment.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
What sets this approach apart is its relentless focus on production-readiness after extensive trial and error, with a clear bifurcation between prototyping and production stacks. Fernandes prioritizes practical deployment constraints (like on-premise requirements for financial institutions), and shares a modular, tool-agnostic methodology that adapts to both open and closed-source solutions, always with monitoring and evaluation baked in.

### The Core Problem
The challenge addressed is building a robust, scalable, and maintainable Retrieval Augmented Generation (RAG) stack that survives real-world production demands—especially where data privacy, scalability, and traceability are non-negotiable, such as in financial services. The problem is compounded by the overwhelming number of tool choices and the high failure rate of naive or poorly integrated RAG solutions.

### The Solution Approach
The methodology is to prototype rapidly in Google Colab using flexible, API-driven tools, then transition to a Dockerized production stack for on-premise or cloud deployment. Each RAG component—embedding, vector storage, orchestration, LLM, monitoring, re-ranking, and evaluation—is mapped to a specific, proven tool, with clear reasoning for open vs closed-source choices. The stack is modular, allowing for easy swapping of components, and emphasizes traceability and evaluation at every stage. The workflow includes: (1) data ingestion with LlamaIndex, (2) embeddings via closed or open models depending on environment, (3) Quadrant for vector DB due to its scalability, (4) LLMs served via Olama or Hugging Face TGI, (5) monitoring with LangSmith or Arize Phoenix, (6) re-ranking with Cohere or Nvidia models, and (7) evaluation with RAGAS.

### Key Insights
- Separation of prototyping and production environments is critical—Google Colab accelerates prototyping, while Docker ensures production reproducibility and compliance.
- Quadrant is uniquely scalable for vector storage, handling both small and massive document sets with equal reliability.
- Monitoring and tracing are non-negotiable for troubleshooting and performance optimization; skipping this step leads to opaque failures and wasted debugging cycles.

### Concepts & Definitions
- Retrieval Augmented Generation (RAG): A pipeline where a user query is semantically searched against a vector database, retrieved documents are combined with the query as context, and passed to an LLM for generation.
- Cross-encoder: A model that jointly encodes query and document for semantic similarity, yielding high accuracy but poor scalability.
- Bi-encoder: Separate encoders for query and document, enabling fast, scalable retrieval via vector similarity (e.g., cosine similarity).

### Technical Details & Implementation
- Prototyping stack: Google Colab + LlamaIndex (or LangGraph) for orchestration, closed embedding models via API, Quadrant vector DB, closed LLM APIs, LangSmith or Phoenix for tracing, Cohere for re-ranking, RAGAS for eval.
- Production stack: Docker Compose orchestrates containers for data ingestion (LlamaIndex), Quadrant (vector DB), Olama or Hugging Face TGI (LLM serving), Arize Phoenix (monitoring), Nvidia open embedding/reranking models, RAGAS for evaluation.
- Uses LlamaIndex's SimpleDirectoryReader to ingest HTML files and metadata, storing in an in-memory vector DB for prototyping.
- Recommends cross-encoder for post-retrieval re-ranking (high accuracy, low scalability), and bi-encoder for initial retrieval (high scalability, lower accuracy).

### Tools & Technologies
- Google Colab (prototyping environment)
- Docker (production orchestration)
- LlamaIndex (data ingestion/orchestration)
- LangGraph (alternative orchestration)
- Quadrant (vector database)
- Olama (LLM serving)
- Hugging Face Text Generation Inference
- LangSmith (monitoring/tracing)
- Arize Phoenix (monitoring/tracing, Docker-ready)
- Cohere (closed-source re-ranking)
- Nvidia (open-source embedding and re-ranking)
- RAGAS (evaluation framework)

### Contrarian Takes & Different Approaches
- Contrary to the hype around end-to-end closed solutions, Fernandes argues for modular, tool-agnostic stacks that can be swapped out as requirements change.
- Advocates for open-source models in production, especially for on-premise deployments, even when closed models are easier to prototype with.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with a single, well-defined knowledge base and a concrete user question to validate your RAG pipeline end-to-end before scaling.
- Always implement monitoring and tracing from the outset using tools like LangSmith or Arize Phoenix to avoid blind spots in debugging.
- Leverage Docker Compose to modularize each RAG component, making it easy to swap tools and scale up or down as needed.

### What to Avoid
- Naive RAG solutions without query processing or re-ranking often yield unsatisfactory results—always add post-retrieval processing for accuracy.
- Cross-encoders are tempting for accuracy but quickly become bottlenecks at scale; use them only for re-ranking a small set of retrieved docs.
- Skipping monitoring/tracing leads to opaque failures and wasted time—always instrument your stack.

### Best Practices
- Prototype in Google Colab for speed, then port to Docker for production to ensure reproducibility and compliance.
- Use open-source models for on-premise deployments to meet data privacy requirements, especially in regulated industries.
- Employ modular architecture via Docker Compose, with each RAG component in its own container for easy maintenance and upgrades.

### Personal Stories & Experiences
- Prototype in Google Colab for speed, then port to Docker for production to ensure reproducibility and compliance.
- Use open-source models for on-premise deployments to meet data privacy requirements, especially in regulated industries.
- Employ modular architecture via Docker Compose, with each RAG component in its own container for easy maintenance and upgrades.

### Metrics & Examples
- Stack proven to scale from a handful to hundreds of thousands of documents using Quadrant.
- Typical knowledge base example: 32 HTML documents for a London railway operator, used to answer real user queries.
- Performance bottlenecks identified and resolved via tracing tools, leading to measurable improvements in response time.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=2CXn-CByNoo)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
