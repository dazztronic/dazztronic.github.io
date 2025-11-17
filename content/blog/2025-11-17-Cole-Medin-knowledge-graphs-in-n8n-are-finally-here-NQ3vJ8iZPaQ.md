+++
title = "Knowledge Graphs in n8n are FINALLY Here!"
date = 2025-11-17
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence","Knowledge representation (Information theory)","Software engineering--Workflow automation"]
tags = ["n8n","RAG","Knowledge graphs","Neo4j","Graffiti MCP","Docker Compose","OpenAI","Vector database","Agentic RAG"]

[extra]
excerpt = "Cole Medin introduces a practical, hacky, and highly actionable way to integrate knowledge graphs into n8n RAG workflows, leveraging Graffiti MCP and Neo4j alongside traditional vector databases. This dual-storage approach empowers agents to handle both unstructured semantic search and complex relational queries, addressing a core limitation of vector-only RAG systems."
video_url = "https://www.youtube.com/watch?v=NQ3vJ8iZPaQ"
video_id = "NQ3vJ8iZPaQ"
cover = "https://img.youtube.com/vi/NQ3vJ8iZPaQ/maxresdefault.jpg"
+++

## Overview

Cole Medin introduces a practical, hacky, and highly actionable way to integrate knowledge graphs into n8n RAG workflows, leveraging Graffiti MCP and Neo4j alongside traditional vector databases. This dual-storage approach empowers agents to handle both unstructured semantic search and complex relational queries, addressing a core limitation of vector-only RAG systems.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
What sets this methodology apart is its pragmatic, workflow-centric fusion of knowledge graphs and vector databases within n8n, using only two additional nodes and open-source tools. Instead of replacing vectors, the approach layers knowledge graphs on top, enabling agents to dynamically choose the optimal search modality based on query type—an 'agentic RAG' paradigm that adapts to real-world data complexity.

### The Core Problem
Traditional RAG pipelines using only vector databases (e.g., PGVector, Pinecone) fail to capture and navigate relationships between entities, making it hard for agents to answer relational or multi-entity questions. This is especially problematic as datasets grow in complexity and size, leading to agents 'getting lost' in flat, chunked data.

### The Solution Approach
The workflow augments the RAG pipeline by simultaneously populating a vector database and a knowledge graph (Neo4j) via Graffiti MCP during data ingestion. Graffiti uses LLMs (OpenAI by default) to extract entities and relationships from raw text, storing them in Neo4j. Two n8n nodes are added: one for inserting documents into the knowledge graph, and another for enabling the agent to query it. The agent's system prompt is tuned to route queries to vectors or the knowledge graph depending on whether the question is semantic or relational. Docker Compose is used for orchestration, and careful attention is paid to container networking and environment variables for seamless integration.

### Key Insights
- Storing the same data in both vector and graph form allows agents to leverage the strengths of each—semantic similarity for single-entity queries, and graph traversal for relational questions.
- Knowledge graphs are slower and more expensive due to LLM-based extraction, so they should only be used when relational querying is needed; otherwise, vectors suffice.
- A tiny but critical Docker networking tweak (using host.docker.internal and correct service names) is required for n8n to communicate with the Graffiti MCP server—a detail that can easily trip up practitioners.

### Concepts & Definitions
- Knowledge graph: A data structure that stores entities (nodes) and their relationships (edges), enabling relational queries and navigation.
- Vector database: A database optimized for storing and searching high-dimensional embeddings, used for semantic similarity search.
- Agentic RAG: A retrieval-augmented generation pipeline where the agent dynamically chooses between different retrieval tools (vector search, knowledge graph) based on the query type.

### Technical Details & Implementation
- Docker Compose setup includes n8n, Neo4j, and Graffiti MCP containers; environment variables must specify OpenAI API keys and reference Neo4j by service name.
- Two n8n nodes are added: one for inserting documents into the knowledge graph (specifying document name and body), and one for querying the graph (passing the query as a parameter, letting the agent/LLM decide the query structure).
- Firewall and Docker networking must be configured to expose the MCP server port to n8n, including editing docker-compose files and possibly remapping ports if conflicts exist.
- Graffiti MCP uses LLMs (OpenAI by default) for entity/relation extraction, but can be configured for other providers.

### Tools & Technologies
- n8n (workflow automation platform)
- Neo4j (graph database)
- Graffiti MCP (LLM-powered entity/relation extraction and graph API server)
- Docker Compose (container orchestration)
- OpenAI API (LLM provider)
- PGVector, Pinecone, Quadrant (vector databases, referenced for context)

### Contrarian Takes & Different Approaches
- Contrary to the trend of replacing vectors with graphs, this approach advocates for a hybrid model, using both in tandem and letting the agent choose.
- Warns against blindly adopting knowledge graphs for all RAG use cases, emphasizing that vectors alone are often sufficient and more efficient.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by self-hosting n8n, Neo4j, and Graffiti MCP on a cloud VM (e.g., DigitalOcean), using provided Docker Compose files.
- Set up environment variables for Graffiti MCP, including OpenAI API keys and correct Neo4j service references.
- Add two nodes to your n8n workflow: one for inserting documents into the knowledge graph, and one for querying it.
- Tune your agent's system prompt to specify when to use vector search versus knowledge graph search, based on query type.
- Carefully check Docker networking and firewall settings to ensure all services can communicate.

### What to Avoid
- Failing to reference Neo4j by service name in environment variables will break container communication.
- Not exposing the MCP server port or misconfiguring Docker networking will prevent n8n from accessing the knowledge graph.
- Knowledge graphs introduce latency and cost due to LLM extraction—avoid them for non-relational or high-throughput use cases.

### Best Practices
- Store data in both vector and graph formats to maximize retrieval flexibility.
- Let the agent/LLM decide the query structure for knowledge graph search, rather than hardcoding queries.
- Keep the workflow modular—add only the minimal nodes needed to extend functionality.

### Personal Stories & Experiences
- Store data in both vector and graph formats to maximize retrieval flexibility.
- Let the agent/LLM decide the query structure for knowledge graph search, rather than hardcoding queries.
- Keep the workflow modular—add only the minimal nodes needed to extend functionality.

### Metrics & Examples
- No explicit quantitative metrics provided, but qualitative examples include agents handling thousands of entities and relationships, and the practical demonstration of querying both single and multi-entity data.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=NQ3vJ8iZPaQ)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
