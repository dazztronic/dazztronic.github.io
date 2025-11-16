+++
title = "AI Engineer World's Fair 2025 - Evals"
date = 2025-11-16
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Software engineering--JavaScript","Natural language processing"]
tags = ["LLM evaluation","Synthetic data","Prompt engineering","Bolt Foundry","Chroma","Jupyter","JavaScript","Multimodal"]

[extra]
excerpt = "This session at the AI Engineer World's Fair 2025 dives into the practical realities and evolving methodologies of evaluating large language models (LLMs), with a standout focus on a new JavaScript-centric eval framework inspired by journalistic structure. The conversation surfaces the need for more robust, transparent, and user-friendly evaluation workflows—especially for developers outside Python-centric ecosystems."
video_url = "https://www.youtube.com/watch?v=Vqsfn9rWXR8"
video_id = "Vqsfn9rWXR8"
cover = "https://img.youtube.com/vi/Vqsfn9rWXR8/maxresdefault.jpg"
+++

## Overview

This session at the AI Engineer World's Fair 2025 dives into the practical realities and evolving methodologies of evaluating large language models (LLMs), with a standout focus on a new JavaScript-centric eval framework inspired by journalistic structure. The conversation surfaces the need for more robust, transparent, and user-friendly evaluation workflows—especially for developers outside Python-centric ecosystems.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The distinctive approach here is the application of journalistic principles to prompt and eval design, treating prompt construction like writing a structured news article rather than overwhelming the LLM with unstructured or adversarial inputs. This is operationalized in the Bolt Foundry framework, which targets JavaScript developers and emphasizes reproducibility and clarity in synthetic data creation.

### The Core Problem
Most JavaScript developers lack accessible, effective tools for running LLM evals or generating synthetic data, especially compared to the Python ecosystem. Existing approaches often rely on opaque, ad hoc prompt engineering that makes error analysis and improvement cycles difficult.

### The Solution Approach
The Bolt Foundry framework introduces a journalism-inspired methodology: prompts and evals are structured similarly to news articles—clear, modular, and reproducible. This contrasts with the typical 'scare the LLM' approach, instead focusing on transparency and iterative error correction. The workflow involves identifying precise failure points in model outputs and building a feedback loop for targeted error reduction.

### Key Insights
- Structuring prompts and evals like journalistic writing increases clarity, reproducibility, and debuggability.
- Synthetic data generation and eval workflows should be accessible to JavaScript developers, not just Python specialists.
- Iterative error correction—finding the exact point of failure and looping improvements—is more effective than broad, unfocused testing.

### Concepts & Definitions
- Eval: The process of systematically testing LLM outputs against expected results, often with synthetic data.
- Journalism-inspired prompt design: Building prompts with the clarity, structure, and reproducibility of a news article, rather than ad hoc or adversarial methods.
- Error correction loop: An iterative process of identifying specific model failure points and refining prompts or data to address them.

### Technical Details & Implementation
- Bolt Foundry is a JavaScript framework (live on GitHub) for running evals and creating synthetic data, with a workflow inspired by journalism.
- Prompts are built in a modular, structured way, mirroring the organization of news articles.
- Supports multimodal evals (e.g., images as well as text) as long as labeled input-output pairs are available.
- Integration with Jupyter notebooks for open-source benchmarking; Chroma used for vector, full-text, and metadata search.

### Tools & Technologies
- Bolt Foundry (JavaScript eval framework)
- Chroma (retrieval and search system)
- Jupyter notebooks (for benchmarking and reproducibility)

### Contrarian Takes & Different Approaches
- Challenging the dominance of Python in LLM evaluation tooling, advocating for robust JavaScript-native solutions.
- Rejecting adversarial, unstructured prompt engineering in favor of clarity and reproducibility.
- Arguing that journalism-inspired structure is superior to current best practices in prompt and eval design.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Adopt a structured, journalistic approach to prompt and eval design for greater clarity and reproducibility.
- Focus on finding the exact point where a model fails, then iterate specifically on that failure mode.
- Leverage Bolt Foundry or similar frameworks to bring eval workflows into JavaScript environments.

### What to Avoid
- Avoid overwhelming LLMs with unstructured or adversarial prompts—this leads to less actionable error analysis.
- Don't rely solely on Python-based tools if your stack is JavaScript; this creates unnecessary friction and limits adoption.
- Beware of skipping the error correction loop—broad, unfocused testing rarely leads to meaningful model improvements.

### Best Practices
- Structure prompts and evals modularly, like sections of a news article.
- Use labeled input-output pairs for multimodal evals to maintain clarity.
- Iterate on specific failure points rather than general model weaknesses.

### Personal Stories & Experiences
- Structure prompts and evals modularly, like sections of a news article.
- Use labeled input-output pairs for multimodal evals to maintain clarity.
- Iterate on specific failure points rather than general model weaknesses.

### Metrics & Examples
- No specific quantitative metrics cited, but the framework is positioned as immediately usable (live on GitHub) and supports both text and image evals with labeled pairs.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=Vqsfn9rWXR8)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
