+++
title = "My Framework for LLM Use Cases and AI Tooling (With Phi-4, Gemini 2.0, Llama 3.3)"
date = 2025-11-19
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Artificial intelligence","Machine learning","Software engineering--Artificial intelligence"]
tags = ["Large language models","Prompt engineering","Agentic workflows","Gemini 2.0","Llama 3.3","Phi-4","RAG","Tool calling","Summarization","NL-to-SQL"]

[extra]
excerpt = "IndyDevDan introduces a six-category framework for classifying large language model (LLM) use cases, enabling engineers to rapidly navigate the fast-evolving generative AI landscape. By mapping prompts and tooling to specific categories—expansion, compression, conversion, seeker, action, and reasoning—he provides a mental model that accelerates prompt engineering, agentic design, and benchmarking. This approach is actionable, making LLM integration systematic and scalable."
video_url = "https://www.youtube.com/watch?v=pytSbBRoFw8"
video_id = "pytSbBRoFw8"
cover = "https://img.youtube.com/vi/pytSbBRoFw8/maxresdefault.jpg"
+++

## Overview

IndyDevDan introduces a six-category framework for classifying large language model (LLM) use cases, enabling engineers to rapidly navigate the fast-evolving generative AI landscape. By mapping prompts and tooling to specific categories—expansion, compression, conversion, seeker, action, and reasoning—he provides a mental model that accelerates prompt engineering, agentic design, and benchmarking. This approach is actionable, making LLM integration systematic and scalable.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The distinctive contribution is a simple, memorable six-category taxonomy for LLM prompts, directly tied to practical engineering workflows and agent design. Unlike generic prompt engineering advice, this framework explicitly links prompt types to tooling, benchmarking, and agentic workflow construction, making it a reusable, modular foundation for building advanced AI systems.

### The Core Problem
With the proliferation of new LLM releases and AI tools, engineers face decision fatigue and inefficiency in prompt engineering and agent design. The lack of a structured approach leads to ad hoc solutions, making it hard to benchmark, reuse, or scale generative AI workflows.

### The Solution Approach
The methodology is to classify every LLM use case into one of six categories: expansion, compression, conversion, seeker, action, and reasoning. Each category has distinct prompt structures, required tooling, and success metrics. By mapping prompts and workflows to these categories, engineers can quickly select the right tools, design reusable benchmarks, and chain prompt types to architect robust agentic systems. The framework is used both for individual prompt design and for structuring multi-step AI agents.

### Key Insights
- Categorizing prompts accelerates engineering by reducing cognitive load—engineers immediately know which tools and benchmarks to apply.
- Agentic workflows become easier to design by chaining prompt categories, enabling modular, maintainable AI agents.
- Each prompt category requires distinct success metrics and tooling, so reusing benchmarks and evaluation strategies is only effective within categories.

### Concepts & Definitions
- Expansion: prompts that grow small inputs into larger outputs (content generation, ideation).
- Compression: distilling large inputs into concise outputs (summarization, key point extraction).
- Conversion: transforming data between formats (text-to-code, language translation).
- Seeker: extracting specific information from data (Q&A, retrieval).
- Action: prompts that trigger tool calls or real-world side effects.
- Reasoning: prompts that provide judgments, conclusions, or drive decision-making.

### Technical Details & Implementation
- Demonstrates use of Gemini 2.0 Flash, Llama 3.3 (via Fireworks), and Phi-4 (54) models side-by-side for each prompt category.
- Phi-4 (54) is highlighted for running locally with high performance at only 14B parameters, making it suitable for edge or private deployments.
- Shows prompt examples for each category: blog post intro (expansion), release summary (compression), NL-to-SQL (conversion), document Q&A (seeker), and tool command generation (action).

### Tools & Technologies
- Gemini 2.0 Flash: used for fast, multimodal prompting.
- Llama 3.3 (Fireworks): 70B parameter model for high-quality outputs.
- Phi-4 (54): 14B parameter model running locally, highlighted for efficiency.
- OpenAI GPT-4o and ChatGPT Pro: referenced as benchmarks and for API integration.

### Contrarian Takes & Different Approaches
- Challenges the notion that prompt engineering is a one-size-fits-all discipline—insists on category-specific approaches.
- Argues that tool-calling and action prompts are underutilized in developer and agent workflows, despite their transformative potential.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Classify every prompt or workflow into one of the six categories before engineering—this guides tool selection and prompt structure.
- Reuse benchmarks and evaluation strategies within each category for rapid iteration.
- Design agentic workflows by chaining prompt categories (e.g., seek → reason → act) to build modular, maintainable AI agents.

### What to Avoid
- Avoid mixing benchmarks and tooling across categories—what works for expansion may fail for seeker or action prompts.
- Do not treat all prompts as generic; lack of categorization leads to inefficient, brittle workflows.
- Underutilizing tool-calling and action prompts limits the real-world impact of LLMs in agentic systems.

### Best Practices
- Adopt the six-category framework as a mental model for all LLM engineering tasks.
- Benchmark and tune models within the context of their prompt category.
- Build agentic workflows by explicitly mapping steps to prompt categories for clarity and maintainability.

### Personal Stories & Experiences
- Adopt the six-category framework as a mental model for all LLM engineering tasks.
- Benchmark and tune models within the context of their prompt category.
- Build agentic workflows by explicitly mapping steps to prompt categories for clarity and maintainability.

### Metrics & Examples
- Phi-4 (54) is a 14B parameter model performing at GPT-4o+ levels, running locally.
- Llama 3.3 is a 70B parameter model used via Fireworks for high-quality outputs.
- Benchmarks for expansion, compression, and seeker prompts are demonstrated live with model outputs.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=pytSbBRoFw8)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
