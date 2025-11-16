+++
title = "RAG Evaluation Is Broken! Here's Why (And How to Fix It) - Yuval Belfer and Niv Granot"
date = 2025-11-16
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Machine learning","Information retrieval","Database management"]
tags = ["RAG","LangChain","LlamaIndex","SQL","Text-to-SQL","Schema extraction","LLM pipelines","Benchmarking","Data normalization"]

[extra]
excerpt = "RAG evaluation is fundamentally flawed because current benchmarks are overly simplistic, focusing on local questions with local answers and failing to reflect real-world complexity. The presenters argue for a paradigm shift: instead of optimizing for these benchmarks, RAG pipelines should be adapted to the actual structure and demands of the data, sometimes requiring transformation of unstructured corpora into structured data for more effective querying. This matters because optimizing for flawed metrics leads to systems that perform poorly in practical, user-facing scenarios."
video_url = "https://www.youtube.com/watch?v=Ywl4LsvHKzU"
video_id = "Ywl4LsvHKzU"
cover = "https://img.youtube.com/vi/Ywl4LsvHKzU/maxresdefault.jpg"
+++

## Overview

RAG evaluation is fundamentally flawed because current benchmarks are overly simplistic, focusing on local questions with local answers and failing to reflect real-world complexity. The presenters argue for a paradigm shift: instead of optimizing for these benchmarks, RAG pipelines should be adapted to the actual structure and demands of the data, sometimes requiring transformation of unstructured corpora into structured data for more effective querying. This matters because optimizing for flawed metrics leads to systems that perform poorly in practical, user-facing scenarios.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The team from A21 Labs challenges the prevailing assumption that RAG evaluation is a solved problem, exposing the disconnect between benchmark performance and real-world utility. Their distinctive methodology involves converting unstructured document corpora into structured schemas (e.g., SQL tables) during ingestion, enabling precise, aggregation-style queries that standard RAG pipelines fail to handle. This structured RAG approach is positioned as a targeted fix for domains where questions are inherently aggregative or relational.

### The Core Problem
Most RAG benchmarks are built around the assumption that answers are found in isolated data chunks, which does not reflect the messy, aggregative, or cross-referential queries encountered in real-world applications. As a result, RAG systems optimized for these benchmarks underperform when deployed on actual client data, leading to a cycle of creating new, yet similarly flawed, benchmarks.

### The Solution Approach
Their solution is a two-phase pipeline: during ingestion, documents are clustered into sub-corpora, schemas are inferred and populated (using LLMs and pipelines), and the structured data is stored in an SQL database. At inference, queries are mapped to the relevant schema and executed as text-to-SQL queries, yielding accurate answers for aggregative or relational questions. This approach invests computational resources upfront (ingestion) to enable fast, precise inference, and is especially suited for domains where data can be normalized into structured form.

### Key Insights
- Benchmarks that focus on local answer retrieval do not generalize to real-world, aggregative, or cross-document queries.
- Optimizing RAG systems for flawed benchmarks creates a vicious cycle where improvements are illusory and do not benefit end users.
- Transforming unstructured data into structured schemas enables RAG systems to answer complex, aggregative questions that would otherwise be impossible or unreliable.

### Concepts & Definitions
- "Local questions with local answers": queries where the answer is found in a single chunk of data, as opposed to aggregative or cross-referential queries.
- "Structured RAG": a methodology where unstructured corpora are transformed into structured data (schemas/tables) to enable more powerful querying.
- "Text-to-SQL": mapping natural language queries to SQL statements for execution on structured data.

### Technical Details & Implementation
- Documents are clustered into sub-corpora based on domain (e.g., financial, sports).
- Schema inference and population is performed using LLM-based pipelines, extracting attributes like year, winner, top scorer, etc.
- Structured data is stored in an SQL database; at inference, queries are mapped to schemas and executed as text-to-SQL.
- Standard RAG frameworks like LangChain and LlamaIndex were tested and shown to fail on these aggregative queries (5%-11% accuracy).

### Tools & Technologies
- LangChain (for standard RAG pipeline baseline)
- LlamaIndex (for standard RAG pipeline baseline)
- LLMs (for schema inference and population)
- SQL databases (for storing and querying structured data)
- WikiData and Kaggle (as knowledge bases for evaluation)

### Contrarian Takes & Different Approaches
- The widespread belief that RAG evaluation is a solved problem is challenged; the presenters argue that most benchmarks are fundamentally misaligned with real-world needs.
- They advocate moving beyond the standard chunking-embedding-retrieval pipeline for many use cases, which is contrary to prevailing industry practices.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- For domains with aggregative or relational queries, invest in transforming unstructured corpora into structured schemas during ingestion.
- Do not rely solely on standard RAG benchmarks for evaluation; test on real-world, client-specific data and aggregative questions.
- Be mindful of normalization challenges (e.g., ambiguous entity names, schema heterogeneity) when designing structured RAG pipelines.

### What to Avoid
- Avoid optimizing for benchmarks that do not reflect your real-world use cases—this leads to misleading improvements.
- Not all corpora are suitable for schema extraction; forcing structure onto heterogeneous or schema-less data can backfire.
- Normalization and ambiguity (e.g., entity aliases, multi-valued fields) are major challenges in schema design and must be handled carefully.

### Best Practices
- Cluster documents by domain before schema extraction to ensure schema relevance and manageability.
- Leverage LLMs for attribute extraction but validate schema population rigorously, especially in ambiguous cases.
- Invest compute in ingestion for better inference performance—front-load the complexity where possible.

### Personal Stories & Experiences
- Cluster documents by domain before schema extraction to ensure schema relevance and manageability.
- Leverage LLMs for attribute extraction but validate schema population rigorously, especially in ambiguous cases.
- Invest compute in ingestion for better inference performance—front-load the complexity where possible.

### Metrics & Examples
- On a set of aggregative questions about FIFA World Cup history, standard RAG pipelines achieved only 5% and 11% accuracy, despite answers being present in local segments.
- The structured RAG approach was able to answer complex queries (e.g., 'Which team has won the FIFA World Cup the most times?') via simple SQL queries.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=Ywl4LsvHKzU)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
