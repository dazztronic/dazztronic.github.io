+++
title = "Unlock Multimodal RAG Agents in n8n (Images, Tables & Text)"
date = 2025-12-09
draft = false

[taxonomies]
author = ["The AI Automators"]
categories = ["Artificial intelligence","Information retrieval","Software engineering--Automation","Computer vision"]
tags = ["RAG","Multimodal","n8n","Superbase","Mistral OCR","OpenAI embeddings","Vector database","PDF parsing","AI vision models","Workflow automation"]

[extra]
excerpt = "This video details a hands-on, production-grade workflow for building multimodal Retrieval-Augmented Generation (RAG) agents in n8n that can index, analyze, and query not just text but also images and tables from complex PDFs. The approach leverages advanced OCR, AI vision models, and vector databases to enable agents to deeply understand and respond with rich media, making knowledge extraction from documents far more actionable and contextually relevant."
video_url = "https://www.youtube.com/watch?v=5aCi42dVOTA"
video_id = "5aCi42dVOTA"
cover = "https://img.youtube.com/vi/5aCi42dVOTA/maxresdefault.jpg"
+++

## Overview

This video details a hands-on, production-grade workflow for building multimodal Retrieval-Augmented Generation (RAG) agents in n8n that can index, analyze, and query not just text but also images and tables from complex PDFs. The approach leverages advanced OCR, AI vision models, and vector databases to enable agents to deeply understand and respond with rich media, making knowledge extraction from documents far more actionable and contextually relevant.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Unlike typical RAG pipelines that focus solely on text, this method integrates multimodal data (text, images, tables) by annotating and embedding visual content using AI vision models, then tightly coupling those annotations with markdown and vector storage. The workflow is deeply pragmatic, emphasizing automation, granular chunking, and inline enrichment of media so that agents can deliver context-rich, actionable responses—including images and tables—directly in chat. The use of n8n for orchestration and Superbase for both storage and vector search is a distinctive, low-code, highly modular approach.

### The Core Problem
Traditional RAG systems struggle to extract and utilize non-textual information from complex documents like product manuals, leading to incomplete answers and missed context. There is a need for scalable, automated pipelines that can ingest, annotate, and retrieve multimodal data—especially images and tables—so that agents can provide richer, more accurate responses.

### The Solution Approach
The workflow begins by ingesting PDFs (machine-readable or scanned) and running them through Mistral's OCR API, which extracts markdown-formatted text, inline media references, and an array of images/tables. AI vision models are prompted to generate granular annotations for each image, which are then programmatically inserted inline into the markdown using custom JavaScript nodes in n8n. Both the enriched markdown and the actual image files (uploaded to Superbase storage) are chunked and embedded using OpenAI's embedding models, then stored in a Superbase vector database. At query time, user questions are embedded, matched against the vector store, and the top results—including annotated images—are passed to a large language model (e.g., GPT-4.1), which is specifically prompted to render images and tables in its responses.

### Key Insights
- Embedding image annotations directly into markdown before vectorization dramatically improves retrieval quality and context for multimodal queries.
- Automating the entire pipeline in n8n enables rapid iteration and modularity, making it easy to swap out components (e.g., OCR provider, embedding model) as needed.
- Prompting the vision model for annotation granularity allows for tailored context depth, which is critical for complex documents.

### Concepts & Definitions
- Multimodal RAG: A retrieval-augmented generation system that indexes and retrieves not only text but also images and tables, providing richer context for LLMs.
- OCR (Optical Character Recognition): Technology that extracts text and media from scanned or image-based documents.
- Vector database: A database optimized for storing and searching embedding vectors, enabling semantic search over unstructured data.

### Technical Details & Implementation
- Uses Mistral OCR API for extracting markdown, images, and tables from PDFs; supports both machine-readable and scanned documents.
- Images are annotated by an AI vision model and uploaded to Superbase storage; markdown is programmatically updated to include Superbase URLs and annotations inline.
- Data is chunked using a recursive text splitter (chunk size: 800, overlap: 200) and embedded with OpenAI's text-embedding-3-small model.
- Superbase is used both for file storage and as a vector database (with langchain integration for table setup).
- n8n orchestrates the entire workflow with HTTP, code, and vector store nodes; JavaScript code nodes are used to manipulate and enrich markdown.

### Tools & Technologies
- n8n (workflow automation/orchestration)
- Mistral OCR API (document parsing and vision annotation)
- Superbase (file storage and vector database)
- OpenAI Embedding Models (text-embedding-3-small)
- GPT-4.1 (LLM for chat responses)

### Contrarian Takes & Different Approaches
- Contrasts with the common text-only RAG approach by asserting that true document understanding requires multimodal indexing and retrieval.
- Advocates for low-code orchestration (n8n) over custom code pipelines, arguing it accelerates prototyping and productionization.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with a simple PDF ingestion pipeline using n8n, Mistral OCR, and Superbase before scaling to more complex ingestion flows.
- Always enrich markdown with inline image annotations and URLs before embedding to maximize retrieval relevance.
- Leverage code nodes in n8n (with LLM-generated JavaScript) to automate data transformation and enrichment steps.

### What to Avoid
- Failing to insert image annotations inline with markdown leads to loss of context and suboptimal retrieval results.
- Uploading binary images without proper URL mapping in markdown prevents agents from rendering images in responses.
- Running code nodes in the wrong execution mode (e.g., 'run once for all items' instead of 'run once for each item') can cause data duplication or processing errors.

### Best Practices
- Chunk data into manageable segments before embedding to ensure high-quality vector search.
- Use a recursive text splitter with overlap to preserve context across chunks.
- Prompt vision models for the desired annotation granularity to match the complexity of your documents.

### Personal Stories & Experiences
- Chunk data into manageable segments before embedding to ensure high-quality vector search.
- Use a recursive text splitter with overlap to preserve context across chunks.
- Prompt vision models for the desired annotation granularity to match the complexity of your documents.

### Metrics & Examples
- Mistral OCR pricing: $1 per 1,000 pages for document AI/OCR, $3 per 1,000 pages for annotations.
- Example: Processing a washing machine manual, the agent retrieves and displays relevant images in response to troubleshooting queries.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=5aCi42dVOTA)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
