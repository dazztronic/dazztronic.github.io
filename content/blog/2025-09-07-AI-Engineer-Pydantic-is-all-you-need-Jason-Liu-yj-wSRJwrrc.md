+++
title = "Pydantic is all you need: Jason Liu"
date = 2025-09-07
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Natural language processing", "Software engineering--Application software", "Data structures (Computer science)"]

[extra]
excerpt = "Jason Liu argues that Pydantic, when paired with structured prompting, is the linchpin for building robust, maintainable language model applications—far beyond its typical use as a data validation library. His perspective is grounded in the pragmatic realities of integrating language models with legacy systems, emphasizing code quality, developer ergonomics, and the power of schema-driven development."
video_url = "https://www.youtube.com/watch?v=yj-wSRJwrrc"
video_id = "yj-wSRJwrrc"
cover = "https://img.youtube.com/vi/yj-wSRJwrrc/maxresdefault.jpg"
+++

## Overview

Jason Liu argues that Pydantic, when paired with structured prompting, is the linchpin for building robust, maintainable language model applications—far beyond its typical use as a data validation library. His perspective is grounded in the pragmatic realities of integrating language models with legacy systems, emphasizing code quality, developer ergonomics, and the power of schema-driven development.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Liu's distinctive approach is treating Pydantic models as the single source of truth for both data validation and prompt schema, unifying prompt engineering, data contracts, and application logic. He reframes structured prompting as a software engineering discipline, not just a prompt design trick, and demonstrates how Pydantic can bridge the gap between LLM outputs and existing production systems without brittle regexes or manual parsing.

### The Core Problem
The core problem is the unreliable, error-prone process of extracting structured data from language model outputs—especially when integrating with existing APIs or systems that require strict schemas. Most current approaches rely on fragile regex parsing or hope that LLMs will output perfectly formatted JSON, which fails at scale and in production.

### The Solution Approach
Liu's methodology is to define all expected outputs as Pydantic models, using their type hints, docstrings, and validators to generate both the prompt schema and the downstream data contract. He leverages OpenAI function calling and libraries like Instructor and Marvin to automate the translation between LLM outputs and Pydantic objects, ensuring that validation, documentation, and prompt quality are all synchronized. This approach enforces good variable names, field descriptions, and documentation as part of the development process, making code and prompts maintainable and auditable.

### Key Insights
- Treating Pydantic models as the canonical schema for both prompts and application logic eliminates the need for manual parsing and reduces bugs.
- Contrary to the trend of building chatbots, most real-world LLM applications are about structured data extraction and system integration—not conversation.
- Good docstrings and field descriptors in Pydantic models directly improve prompt and output quality, creating a virtuous cycle between code and LLM performance.

### Concepts & Definitions
- "Structured prompting": Using object schemas (like Pydantic models) to define and enforce the expected output format from LLMs, rather than relying on unstructured text or manual parsing.
- "Backwards compatibility": The necessity for LLM outputs to integrate seamlessly with existing software and APIs, which often cannot be changed.
- "Single source of truth": Using Pydantic models to unify prompt schema, data validation, and application logic, reducing duplication and errors.

### Technical Details & Implementation
- Define all LLM output schemas as Pydantic models, including nested classes and validators.
- Use OpenAI function calling to enforce output structure, passing Pydantic-generated JSON schema as the contract.
- Leverage libraries like Instructor and Marvin to streamline the workflow between Pydantic models and LLM prompts.
- Docstrings and field descriptions in Pydantic models are automatically included in the schema sent to the LLM, improving both validation and prompt clarity.

### Tools & Technologies
- Pydantic (core schema and validation engine)
- OpenAI function calling (for structured LLM outputs)
- Instructor (library for integrating Pydantic with LLM prompts)
- Marvin (library for simplifying LLM application development)

### Contrarian Takes & Different Approaches
- The real value of LLMs in production is not chatbots, but structured data extraction and integration with legacy systems.
- You don't need a proliferation of new tools—Pydantic is sufficient for most LLM application needs if used correctly.
- Prompt engineering should be treated as software engineering, with schemas, documentation, and validation—not as a separate, ad-hoc discipline.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start every LLM application by defining the output schema as a Pydantic model, including all fields, types, and docstrings.
- Use OpenAI function calling or similar structured output features to enforce that LLMs return data matching your Pydantic schema.
- Invest in writing clear docstrings and field descriptions—they directly improve both code maintainability and LLM output quality.

### What to Avoid
- Don't rely on regex or manual parsing for extracting structured data from LLM outputs—it's brittle and fails in production.
- Avoid duplicating schemas across prompts, validation, and application logic; this leads to drift and maintenance headaches.
- Neglecting documentation and field descriptions in your models will degrade both code quality and LLM performance.

### Best Practices
- Unify prompt schema, validation, and application logic in a single Pydantic model.
- Use validators in Pydantic to enforce business logic and data integrity before accepting LLM outputs.
- Review and maintain good variable names and documentation as part of the schema definition process.

### Personal Stories & Experiences
- Liu reflects on the pain of parsing LLM outputs with regex and the relief of switching to schema-driven development.
- He shares excitement about future multimodal applications, like extracting bounding boxes from images and instantly building generative UIs, all driven by structured outputs.
- He notes that most LLM applications he's seen in production are not chatbots, but data extraction and system integration tasks.

### Metrics & Examples
- He estimates that 90% of LLM applications in production are about structured data extraction, not chat interfaces.
- Describes use cases like extracting graphs from documents and bounding boxes from images as next-generation structured output applications.

## Resources & Links

- [https://ai.engineer/worlds-fair](https://ai.engineer/worlds-fair)
- [Video URL](https://www.youtube.com/watch?v=yj-wSRJwrrc)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

