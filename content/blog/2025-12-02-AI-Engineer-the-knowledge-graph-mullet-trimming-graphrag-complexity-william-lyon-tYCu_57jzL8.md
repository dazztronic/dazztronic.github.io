+++
title = "The Knowledge Graph Mullet: Trimming GraphRAG Complexity - William Lyon"
date = 2025-12-02
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Knowledge representation (Information retrieval)","Artificial intelligence--Software engineering","Database management systems--Graph databases"]
tags = ["GraphRAG","Dgraph","Property graph","RDF","Vector search","Model Context Protocol (MCP)","Hypermode agents","DQL","Embeddings","Geospatial queries"]

[extra]
excerpt = "William Lyon introduces the 'knowledge graph mullet'—a hybrid approach combining property graphs and RDF triples—to simplify and supercharge GraphRAG workflows. By leveraging Dgraph's unique architecture, he demonstrates how to gain the query flexibility of property graphs with the scalability and interoperability of RDF, enabling more powerful, context-rich AI agent applications. This perspective matters because it bridges two traditionally siloed graph paradigms, unlocking new efficiencies and capabilities for knowledge-driven AI systems."
video_url = "https://www.youtube.com/watch?v=tYCu_57jzL8"
video_id = "tYCu_57jzL8"
cover = "https://img.youtube.com/vi/tYCu_57jzL8/maxresdefault.jpg"
+++

## Overview

William Lyon introduces the 'knowledge graph mullet'—a hybrid approach combining property graphs and RDF triples—to simplify and supercharge GraphRAG workflows. By leveraging Dgraph's unique architecture, he demonstrates how to gain the query flexibility of property graphs with the scalability and interoperability of RDF, enabling more powerful, context-rich AI agent applications. This perspective matters because it bridges two traditionally siloed graph paradigms, unlocking new efficiencies and capabilities for knowledge-driven AI systems.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Lyon's 'knowledge graph mullet' analogy encapsulates a deliberate fusion: 'business in the front' (property graph for modeling and querying) and 'party in the back' (RDF triples for storage and interchange). This hybrid methodology is distinctive in its pragmatic embrace of both paradigms, using Dgraph to expose a property graph interface while leveraging RDF's scalable triple store under the hood—sidestepping the dogmatic split between property graph and semantic web communities.

### The Core Problem
GraphRAG implementations often suffer from complexity and inefficiency due to rigid adherence to either property graph or RDF approaches, limiting scalability, interoperability, or ease of use. The challenge is to build knowledge graphs that are both easy to query and maintain (property graph benefits) and scalable/interoperable (RDF benefits), especially for AI agent workflows that demand rich, traversable context.

### The Solution Approach
The methodology involves modeling data using the property graph paradigm (nodes, labels, relationships, properties) for intuitive querying and traversal, while storing and exchanging data as RDF triples for performance and interoperability. Dgraph serves as the backbone, mapping property graph constructs to triples, using optimizations like posting lists for fast traversal, and exposing a GraphQL-inspired query language (DQL). Embeddings (vector representations) are stored as node properties, enabling vector search as a flexible entry point into the graph, which is then traversed for richer context. The Model Context Protocol (MCP) is layered on top to allow AI agents to interact with the graph via standardized tool interfaces.

### Key Insights
- Combining property graph and RDF models yields a system that's both easy to work with and highly scalable—mirroring the mullet's 'business in the front, party in the back' versatility.
- Contrary to prevailing wisdom, you don't have to choose between property graphs and RDF; hybridizing both unlocks best-of-both-worlds capabilities.
- A major lesson: entry points like vector search, geospatial queries, or image similarity should be seen as flexible starting nodes for deeper graph traversals, not as the sole retrieval mechanism.

### Concepts & Definitions
- Knowledge graph: framed as an instance of a property graph—nodes with labels, relationships with types and direction, and arbitrary key-value properties.
- Property graph: nodes (with labels), relationships (typed, directed), and properties (key-value pairs) as the core modeling primitives.
- RDF triple: subject-predicate-object structure, where subject is always a node (unique ID), predicate is a relationship or property, and object is another node or property value.
- Posting list: an optimization grouping predicates and maintaining lists of connected node IDs for efficient traversal.
- Model Context Protocol (MCP): a protocol for exposing database tools to AI models, enabling agentic workflows.

### Technical Details & Implementation
- Dgraph is used to model data as property graphs, but stores data as RDF triples, with unique node IDs mapping to disk offsets for efficient traversal.
- Posting lists in Dgraph group predicates and maintain lists of connected node IDs, optimizing relationship traversal.
- Embeddings (e.g., from chunked documents) are stored as node properties, enabling vector similarity search as an entry point.
- DQL (Dgraph Query Language) is inspired by GraphQL and supports complex traversals, filtering, and aggregation.
- The Model Context Protocol (MCP) server exposes Dgraph to AI agents, supporting readonly and mutation endpoints for querying, schema inspection, and data manipulation.

### Tools & Technologies
- Dgraph: hybrid property graph/RDF graph database used for modeling, storage, and querying.
- Rattell: Dgraph query workbench for executing and visualizing DQL queries.
- Model Context Protocol (MCP) server: exposes Dgraph to AI agents for querying and schema manipulation.
- Hypermode agents: agentic framework leveraging MCP for tool access and code ejection.
- Notion MCP server: enables agents to interact with Notion workspaces.
- GitHub MCP server: allows agents to interact with GitHub repositories.

### Contrarian Takes & Different Approaches
- Challenges the conventional wisdom that property graphs and RDF are mutually exclusive, advocating for a pragmatic hybrid approach.
- Argues that vector search should not be the sole retrieval mechanism in RAG workflows, but rather a starting point for deeper, graph-based context gathering.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Model your knowledge graph using property graph constructs for intuitive querying, but store and exchange data as RDF triples for scalability.
- Use vector embeddings as node properties to enable flexible vector search entry points, then traverse the graph for richer, multi-hop context.
- Leverage Dgraph's MCP server to expose your graph to AI agents, enabling automated code generation, data analysis, and workflow integration.

### What to Avoid
- Avoid rigidly adhering to only property graph or only RDF paradigms—doing so limits scalability or usability.
- Don't treat vector search as the end of retrieval; use it as an entry point for deeper graph traversal to unlock richer context.
- Beware of neglecting unique node IDs and efficient indexing, as this undermines traversal performance in large-scale graphs.

### Best Practices
- Hybridize property graph modeling with RDF storage for maximum flexibility and scalability.
- Chunk documents and compute embeddings for each chunk, storing them as node properties to enable semantic search.
- Expose graph databases to AI agents using standardized protocols (like MCP) for seamless tool integration and automation.

### Personal Stories & Experiences
- Hybridize property graph modeling with RDF storage for maximum flexibility and scalability.
- Chunk documents and compute embeddings for each chunk, storing them as node properties to enable semantic search.
- Expose graph databases to AI agents using standardized protocols (like MCP) for seamless tool integration and automation.

### Metrics & Examples
- Demonstrates traversing news articles within 50 kilometers of New York City using geospatial queries.
- Shows vector search for articles semantically similar to 'money laundering', then expands context via graph traversal to related topics and organizations.
- Mentions Dgraph's open-sourcing of all enterprise features, making advanced capabilities accessible without licensing barriers.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=tYCu_57jzL8)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
