+++
title = "Agentic GraphRAG: Simplifying Retrieval Across Structured & Unstructured Data — Zach Blumenfeld"
date = 2025-12-10
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Knowledge representation (Information theory)","Information retrieval","Software engineering--Graph databases"]
tags = ["GraphRAG","Neo4j","LangChain","Pydantic","Google ADK","MCP server","Entity extraction","Knowledge graph","Agentic workflows","Cypher"]

[extra]
excerpt = "This presentation demonstrates how integrating a knowledge graph into Retrieval-Augmented Generation (RAG) workflows enables agents to reason across both structured and unstructured data, unlocking richer analytics and more precise answers. By evolving from simple document embeddings to an expressive, entity-centric graph model, the approach allows for flexible, scalable, and auditable data retrieval and relationship analysis—crucial for agentic workflows that demand more than basic vector search."
video_url = "https://www.youtube.com/watch?v=CzM3cW6FdBs"
video_id = "CzM3cW6FdBs"
cover = "https://img.youtube.com/vi/CzM3cW6FdBs/maxresdefault.jpg"
+++

## Overview

This presentation demonstrates how integrating a knowledge graph into Retrieval-Augmented Generation (RAG) workflows enables agents to reason across both structured and unstructured data, unlocking richer analytics and more precise answers. By evolving from simple document embeddings to an expressive, entity-centric graph model, the approach allows for flexible, scalable, and auditable data retrieval and relationship analysis—crucial for agentic workflows that demand more than basic vector search.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The methodology stands out by embedding a knowledge graph at the core of the RAG pipeline, bridging structured ETL data and unstructured document extraction. Rather than relying solely on vector search, it leverages entity extraction and graph modeling to enable agents to decompose queries, perform aggregations, and reason about relationships—capabilities that are difficult or brittle with flat document stores or traditional RAG setups.

### The Core Problem
How to enable agentic systems to retrieve, aggregate, and reason over both structured and unstructured data sources, especially when queries require analytics, relationship mapping, or data model evolution—tasks that are poorly served by basic vector search or flat document storage.

### The Solution Approach
The workflow begins with ingesting unstructured data (e.g., PDFs of résumés) into a graph database (Neo4j), initially as simple document nodes with embeddings. Recognizing the limitations of this approach for analytics and relationship queries, the process evolves to extract entities (people, skills, accomplishments) using Pydantic classes and LangChain, constructing a rich, extensible graph schema. Agents (built with Google's ADK) are then equipped with tools to query the graph using Cypher, with schema-awareness provided by an MCP server, enabling complex queries, aggregations, and reasoning. The graph model is iteratively refined to support new relationships (e.g., many-to-many collaborations) without costly data model refactoring.

### Key Insights
- A knowledge graph enables agents to move beyond semantic similarity search, supporting decomposed queries, aggregations, and relationship reasoning.
- Expressive data modeling (entities, relationships, domains) is crucial for analytics and explainability in agentic workflows.
- Graph databases allow rapid schema evolution and flexible relationship modeling, avoiding the rigidity and overhead of RDBMS join tables.

### Concepts & Definitions
- "Agentic workflows": Agent-driven processes where agents decompose queries, reason, and interact with multiple data sources.
- "Knowledge graph": A data model representing entities (people, skills, projects) and their relationships, supporting flexible querying and reasoning.
- "Entity extraction": Process of identifying structured entities (e.g., skills, accomplishments) from unstructured text for graph modeling.
- "Aggregation": Querying for summary statistics (e.g., skill distributions) across the graph.
- "Schema evolution": The ability to flexibly add new node/relationship types to the graph model as requirements change.

### Technical Details & Implementation
- Initial ingestion: PDFs loaded into Neo4j as document nodes with metadata and embeddings.
- Entity extraction: Pydantic classes define enumerations for accomplishments, domains, and work types; LangChain decomposes documents into structured JSON.
- Graph construction: Nodes for people, skills, accomplishments; relationships for 'has skill', 'did thing', 'collaborated on'.
- Agent setup: Google's ADK framework, with tools for document search and Cypher querying; schema-awareness via MCP server (open-source on GitHub).
- Querying: Agents generate Cypher queries to perform aggregations (e.g., count Python developers), similarity (overlap of skills/accomplishments), and collaboration analysis.

### Tools & Technologies
- Neo4j (graph database for storage and querying)
- Pydantic (for entity schema definitions and enumerations)
- LangChain (for document decomposition and entity extraction)
- Google's ADK (agent framework for tool orchestration)
- MCP server (enables schema-aware Cypher query generation by agents)

### Contrarian Takes & Different Approaches
- Contradicts the common practice of relying solely on vector search for RAG—argues that knowledge graphs are essential for agentic reasoning and analytics.
- Challenges the assumption that structured and unstructured data must be handled separately—demonstrates unified retrieval via graph modeling.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with a simple graph model (people, skills, accomplishments) and expand iteratively as analytics needs grow.
- Use entity extraction workflows (e.g., LangChain + Pydantic) to convert unstructured documents into graph-ready data.
- Leverage graph databases for rapid schema evolution—add new relationships or nodes as agentic requirements change.
- Equip agents with schema-aware querying tools (e.g., MCP server) to enable complex, explainable analytics.

### What to Avoid
- Relying solely on document embeddings and vector search limits the ability to perform analytics, aggregations, and relationship queries.
- Flat document storage makes it hard to evolve the data model or support many-to-many relationships without costly refactoring.
- Failing to provide agents with a clear data model or schema awareness leads to brittle, inaccurate answers.

### Best Practices
- Define a minimal but expressive graph schema upfront, focusing on entities and relationships relevant to core queries.
- Iteratively refine the graph model as new analytics or relationship needs emerge—avoid over-engineering at the start.
- Use open-source tools (e.g., MCP server) to enable agents to read schemas and generate precise queries.
- Audit and adjust the graph as new data or corrections are needed—maintain explainability and control.

### Personal Stories & Experiences
- Define a minimal but expressive graph schema upfront, focusing on entities and relationships relevant to core queries.
- Iteratively refine the graph model as new analytics or relationship needs emerge—avoid over-engineering at the start.
- Use open-source tools (e.g., MCP server) to enable agents to read schemas and generate precise queries.
- Audit and adjust the graph as new data or corrections are needed—maintain explainability and control.

### Metrics & Examples
- Initial vector search returned a hardcoded five Python developers (due to K=5), while the graph model correctly identified 28.
- Similarity queries in the graph model explained overlap calculations and reasoning, providing transparency.
- Collaboration queries identified specific individuals (e.g., Sarah and Amanda) who worked together on AI projects.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=CzM3cW6FdBs)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
