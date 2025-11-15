+++
title = "Python RAG Tutorial (with Local LLMs): AI For Your PDFs"
date = 2025-11-15
draft = false

[taxonomies]
author = ["pixegami"]
categories = ["Artificial intelligence","Machine learning","Information retrieval","Software engineering--Artificial intelligence"]
tags = ["RAG","Python","ChromaDB","Langchain","Ollama","PDF document processing","Vector database","Local LLM","Automated LLM evaluation","Incremental ingestion"]

[extra]
excerpt = "This tutorial demonstrates how to build a Python-based Retrieval Augmented Generation (RAG) application that leverages local open-source LLMs to answer natural language questions about PDF documents, with a focus on efficient, incremental updates to the vector database and robust answer quality evaluation. The approach is hands-on, practical, and addresses real-world workflow needs such as updating document sources without full re-indexing and validating LLM outputs. This matters for practitioners seeking privacy, control, and reproducibility in AI-powered document Q&A systems."
video_url = "https://www.youtube.com/watch?v=2TJxpyO3ei4"
video_id = "2TJxpyO3ei4"
cover = "https://img.youtube.com/vi/2TJxpyO3ei4/maxresdefault.jpg"
+++

## Overview

This tutorial demonstrates how to build a Python-based Retrieval Augmented Generation (RAG) application that leverages local open-source LLMs to answer natural language questions about PDF documents, with a focus on efficient, incremental updates to the vector database and robust answer quality evaluation. The approach is hands-on, practical, and addresses real-world workflow needs such as updating document sources without full re-indexing and validating LLM outputs. This matters for practitioners seeking privacy, control, and reproducibility in AI-powered document Q&A systems.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Distinctively, the tutorial emphasizes running the entire RAG pipeline locally using open-source LLMs (via Ollama) and ChromaDB, avoiding reliance on cloud APIs for privacy and reproducibility. It introduces a robust, deterministic chunk-ID system for incremental database updates, enabling seamless addition of new documents or sections without full re-ingestion—a workflow pain point rarely addressed in standard RAG tutorials. The video also integrates automated LLM-based answer evaluation, blending practical engineering with test-driven development for LLM apps.

### The Core Problem
The main challenge addressed is enabling users to query their own PDF data with natural language using local LLMs, while supporting efficient updates to the underlying vector database as documents change or are added. This is critical for real-world deployments where data evolves and privacy or offline requirements preclude cloud-based solutions.

### The Solution Approach
The workflow begins by loading PDFs using Langchain's document loaders, chunking content into manageable sections, and generating embeddings (either locally or via online models) for storage in ChromaDB. Each chunk receives a unique, deterministic ID based on file path, page number, and chunk index, allowing for precise detection of new or modified content during incremental updates. When querying, user questions are embedded and relevant chunks retrieved, then passed to a local LLM (via Ollama) to generate a natural language answer with source attribution. Automated tests, including both positive and negative cases, are run using LLM-based evaluation to ensure answer quality after any code or data change.

### Key Insights
- Incremental vector database updates are enabled by deterministic chunk IDs, preventing duplicate entries and unnecessary reprocessing—a major usability improvement over naive full re-ingestion.
- Automated LLM-based evaluation of generated answers (including negative test cases and pass thresholds) provides a practical framework for test-driven LLM app development.
- Hybrid embedding strategies (local for privacy, online for quality) can be mixed and matched, depending on user needs and hardware constraints.

### Concepts & Definitions
- Retrieval Augmented Generation (RAG): Indexing external data sources and combining them with LLMs to enable context-aware question answering.
- Vector database: A database that stores high-dimensional embeddings (vectors) for efficient similarity search and retrieval.
- Chunk ID: A deterministic, unique identifier for each document section, constructed from source path, page, and chunk index.

### Technical Details & Implementation
- PDFs are loaded and chunked using Langchain's PDF loader; chunking granularity is managed to balance context size and retrieval precision.
- ChromaDB is used as the vector database, with explicit assignment of chunk IDs combining file path, page number, and chunk index.
- Ollama serves as the local LLM backend for answer generation; embeddings can be generated locally or via online services.
- Code patterns include: iterating over existing DB IDs to filter new/changed chunks, explicit ID management to avoid UUID-based duplication, and integration of LLM-based test assertions.

### Tools & Technologies
- Python (core language for scripting and orchestration)
- Langchain (for document loading and chunking)
- ChromaDB (vector database for embeddings)
- Ollama (local LLM server for answer generation)
- Online embedding models (optional, for higher quality embeddings)

### Contrarian Takes & Different Approaches
- Advocates for local LLM and embedding workflows over cloud APIs, prioritizing privacy and reproducibility even at the cost of some model quality.
- Challenges the assumption that full database re-ingestion is necessary for document updates, demonstrating a more efficient incremental approach.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Assign deterministic IDs to document chunks using source path, page, and chunk index to enable efficient incremental updates.
- Use LLM-based automated tests with both positive and negative cases to validate answer quality after any data or code change.
- Mix local and online embedding models as needed, balancing privacy and quality based on your deployment context.

### What to Avoid
- Relying on auto-generated UUIDs for chunk IDs in ChromaDB leads to duplicate entries and inability to detect updates—always manage IDs explicitly.
- Editing existing PDF content without updating chunk IDs will not trigger database updates; a more advanced change-detection mechanism may be needed for full robustness.
- Skipping negative test cases in LLM evaluation can mask subtle answer quality regressions.

### Best Practices
- Maintain explicit, deterministic chunk IDs for all document sections to support incremental ingestion.
- Automate answer quality checks using LLM-based assertions, including both expected successes and failures.
- Organize source PDFs in a dedicated data folder and script ingestion to be repeatable and idempotent.

### Personal Stories & Experiences
- Maintain explicit, deterministic chunk IDs for all document sections to support incremental ingestion.
- Automate answer quality checks using LLM-based assertions, including both expected successes and failures.
- Organize source PDFs in a dedicated data folder and script ingestion to be repeatable and idempotent.

### Metrics & Examples
- Example: Adding a new PDF resulted in 27 new chunks being detected and ingested, while re-running ingestion with unchanged data resulted in zero new entries—demonstrating correct incremental behavior.
- Test suite includes both positive and negative cases, with the option to set a pass threshold (e.g., 80-90%) rather than requiring 100% success.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=2TJxpyO3ei4)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
