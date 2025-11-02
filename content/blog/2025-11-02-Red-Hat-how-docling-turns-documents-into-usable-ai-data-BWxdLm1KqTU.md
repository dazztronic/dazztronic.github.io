+++
title = "How Docling turns documents into usable AI data"
date = 2025-11-02
draft = false

[taxonomies]
author = ["Red Hat"]
categories = ["Artificial intelligence","Machine learning","Natural language processing","Information retrieval"]
tags = ["Docling","LlamaIndex","Retrieval Augmented Generation (RAG)","PDF parsing","Markdown","JSON","OCR","EasyOCR","Tesseract","HuggingFace","Mistral","InstrucLab","Vector database","LangChain"]

[extra]
excerpt = "This video demonstrates how Docling, an open source IBM project, bridges the gap between complex, unstructured document formats (like PDFs and DOCX) and AI-ready data by converting them into structured markdown and JSON. The walkthrough highlights Docling's superior performance, practical integration into RAG pipelines, and unique ability to preserve document integrity, making organizational data truly usable for large language models. The perspective is hands-on, performance-driven, and focused on real-world AI workflow integration."
video_url = "https://www.youtube.com/watch?v=BWxdLm1KqTU"
video_id = "BWxdLm1KqTU"
cover = "https://img.youtube.com/vi/BWxdLm1KqTU/maxresdefault.jpg"
+++

## Overview

This video demonstrates how Docling, an open source IBM project, bridges the gap between complex, unstructured document formats (like PDFs and DOCX) and AI-ready data by converting them into structured markdown and JSON. The walkthrough highlights Docling's superior performance, practical integration into RAG pipelines, and unique ability to preserve document integrity, making organizational data truly usable for large language models. The perspective is hands-on, performance-driven, and focused on real-world AI workflow integration.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The approach is distinctive in its focus on operationalizing organizational data for AI by tackling the hardest part: extracting structured, context-rich data from notoriously difficult formats (PDF, DOCX, PPTX, XLSX) using open source, high-performance tooling. The methodology is not just about parsing, but about preserving layout, tables, and context for downstream AI applications, with a strong emphasis on reproducible benchmarks and direct integration into modern RAG and fine-tuning pipelines.

### The Core Problem
The central challenge addressed is the extraction of usable, context-aware data from complex, semi-structured document formats that are ubiquitous in enterprises but difficult for AI models to process directly. Traditional approaches are hampered by poor standardization, licensing costs, and the inability to preserve document structure, which limits the value of organizational knowledge in AI workflows.

### The Solution Approach
The solution leverages Docling's context-aware parsing pipeline, which combines OCR, object recognition, and layout analysis to convert documents into markdown/JSON while retaining tables, figures, and hierarchical structure. The workflow involves benchmarking against other open source tools, direct CLI and Python API usage, and seamless integration with vector databases and RAG frameworks (LlamaIndex, LangChain) for Q&A and fine-tuning tasks. The mental model is: 'Extract once, structure well, and unlock for any downstream AI use-case.'

### Key Insights
- Performance matters: Docling processes pages significantly faster than alternatives (3.1s/page on x86, 1.2s/page on M3 ARM) and is robust across architectures, making it viable for both server and local workflows.
- Preserving document integrity—especially tables and figures—is essential for meaningful AI retrieval and generation; naive parsing loses critical context.
- Open source, local processing avoids licensing costs and privacy concerns inherent in cloud LLM-based document parsing.

### Concepts & Definitions
- Retrieval Augmented Generation (RAG): A framework where external data is retrieved and fed into a language model to improve relevance and accuracy.
- Node parsing: The process of breaking structured documents into logical sections or paragraphs for embedding and retrieval.
- Embedding model: A model that converts text into vector representations for similarity search.

### Technical Details & Implementation
- Docling can be installed via pip and used both as a CLI and a Python library, supporting batch conversion from folders or URLs.
- Supports multiple OCR backends (EasyOCR, Tesseract) or can skip OCR for text-based PDFs.
- Integration pattern: Docling parses documents to markdown, which is then chunked into nodes and embedded using HuggingFace models within LlamaIndex; vector search enables similarity-based Q&A.
- Images are converted to base64 within markdown, and tables are preserved in markdown table format.

### Tools & Technologies
- Docling (IBM open source document parser)
- LlamaIndex (RAG framework)
- LangChain (alternative RAG framework)
- HuggingFace (embedding models)
- Mistral (open source LLM for generation)
- InstrucLab (open source fine-tuning toolkit)
- EasyOCR, Tesseract (OCR engines)

### Contrarian Takes & Different Approaches
- Challenges the assumption that LLMs or cloud-based APIs are required for document parsing, advocating for open source, local-first solutions.
- Argues that investing in high-fidelity document structure preservation is not optional but foundational for successful AI applications.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Install Docling via pip and experiment with converting your own PDFs to markdown to evaluate structure preservation.
- Integrate Docling output into a RAG pipeline using LlamaIndex for immediate Q&A capabilities on your unique data.
- Benchmark Docling against other tools on your hardware to validate performance claims and select the best fit.

### What to Avoid
- Relying on naive PDF-to-text tools often results in loss of tables, figures, and context, leading to poor AI retrieval results.
- Some open source parsers (e.g., Marker) are significantly slower and may not scale for large document sets.
- MinorU, while competitive in speed, failed to run on ARM architectures—cross-platform compatibility matters.

### Best Practices
- Always preserve document structure (headings, tables, images) when preparing data for AI ingestion.
- Use open source, local tools to avoid licensing and privacy issues with proprietary cloud-based parsers.
- Chunk parsed documents into logical nodes for more effective embedding and retrieval in vector databases.

### Personal Stories & Experiences
- Always preserve document structure (headings, tables, images) when preparing data for AI ingestion.
- Use open source, local tools to avoid licensing and privacy issues with proprietary cloud-based parsers.
- Chunk parsed documents into logical nodes for more effective embedding and retrieval in vector databases.

### Metrics & Examples
- Docling processes at 3.1 seconds per page on x86 and 1.2 seconds per page on M3 ARM, outperforming Marker (16s/page) and Unstructured.
- MinorU could not complete runs on M3 ARM, highlighting Docling's cross-platform robustness.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=BWxdLm1KqTU)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
