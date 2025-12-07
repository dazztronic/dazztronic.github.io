+++
title = "AI Code That Fixes Itself (An MCP You Can Try Now)"
date = 2025-12-07
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Knowledge representation (Information theory)","Automation"]
tags = ["Knowledge graph","Neo4j","Retrieval-augmented generation (RAG)","Hallucination detection","MCP server","Archon","Pyantic AI","Windsurf","Stage Hand","Director","Playwright","Claude Code","Open source"]

[extra]
excerpt = "Cole Medin introduces a groundbreaking approach to AI coding assistants by integrating knowledge graphs with retrieval-augmented generation (RAG) and hallucination detection, enabling AI code that can identify and correct its own mistakes. This methodology directly addresses the persistent unreliability and hallucination issues in current AI coding tools, making them vastly more dependable and actionable for real-world software development."
video_url = "https://www.youtube.com/watch?v=8Mib-hb6Fcg"
video_id = "8Mib-hb6Fcg"
cover = "https://img.youtube.com/vi/8Mib-hb6Fcg/maxresdefault.jpg"
+++

## Overview

Cole Medin introduces a groundbreaking approach to AI coding assistants by integrating knowledge graphs with retrieval-augmented generation (RAG) and hallucination detection, enabling AI code that can identify and correct its own mistakes. This methodology directly addresses the persistent unreliability and hallucination issues in current AI coding tools, making them vastly more dependable and actionable for real-world software development.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's distinctive methodology centers on transforming entire code repositories into queryable knowledge graphs (using Neo4j), which are then leveraged by AI coding assistants to validate code generation in real time. By coupling deterministic hallucination detection scripts with agentic workflows, he enables self-correcting AI code—a leap beyond standard RAG or documentation-based approaches. His commitment to open source and rapid iteration, plus the integration of these techniques into his MCP server and Archon agent builder, sets his work apart.

### The Core Problem
AI coding assistants frequently hallucinate functions, attributes, or code patterns that don't exist, leading to brittle, unreliable code and wasted developer time. This is especially problematic when building with complex frameworks or automating browser interactions, where documentation alone is insufficient and hallucinations are hard to catch.

### The Solution Approach
Medin ingests entire GitHub repositories into a Neo4j knowledge graph, mapping repositories, files, classes, functions, and attributes as nodes and relationships. AI coding assistants query this graph to validate generated code, while a deterministic hallucination detector script cross-references code against the graph to flag and correct non-existent elements. This feedback loop enables the assistant to self-correct, reducing hallucination rates to zero. The approach is modular, open source, and integrates with his MCP server and Archon agent builder, allowing for dynamic tool injection and project/task management.

### Key Insights
- Storing codebases as knowledge graphs enables precise, automated validation of AI-generated code, catching hallucinations that documentation-based RAG misses.
- Deterministic scripts (not LLMs) can efficiently detect and report hallucinated code elements by traversing the knowledge graph, providing a robust feedback mechanism.
- Iterative refinement of system prompts (e.g., claw.md) and knowledge sources is crucial—poorly specified prompts can mislead even advanced agents, as seen in confidence score anomalies.

### Concepts & Definitions
- Knowledge graph: A structured, relational representation of a codebase, where entities (repos, files, classes, functions, attributes) are nodes connected by meaningful edges, enabling semantic queries.
- Hallucination (in AI coding): The generation of code elements (functions, methods, attributes) that do not exist in the target codebase or framework.
- Deterministic hallucination detection: Using non-LLM, rule-based scripts to compare code against a canonical knowledge graph, identifying mismatches with certainty.

### Technical Details & Implementation
- Neo4j is used to store codebase graphs, with nodes for repositories, files, classes, functions, and attributes, color-coded for visualization.
- The MCP server is configured via environment variables to enable knowledge graph usage (USE_KNOWLEDGE_GRAPH=true) and connect to a Neo4j instance (credentials required).
- The hallucination detector script operates deterministically, not via LLMs, by traversing the knowledge graph and matching code usage to actual class/function definitions.
- Integration with Claude Code and other AI agents is achieved by exposing graph query tools and hallucination detection as callable tools within the agent workflow.
- Browser automation is handled via Stage Hand (built on Playwright), with Director providing a platform for natural language-driven automation and self-correction.

### Tools & Technologies
- Neo4j (knowledge graph database for code structure)
- MCP server (AI agent orchestration with RAG and knowledge graph integration)
- Archon (AI agent builder, soon to integrate knowledge graph strategies)
- Pyantic AI (open source AI agent framework, used as a case study)
- Windsurf (AI coding assistant tested in the workflow)
- Stage Hand (open source browser automation framework built on Playwright)
- Director (platform for natural language-driven browser automation)

### Contrarian Takes & Different Approaches
- Contrary to the prevailing belief that LLMs plus RAG are sufficient for reliable coding, Medin argues that only knowledge graph-driven, deterministic validation can truly eliminate hallucinations.
- He challenges the idea that browser automation is best handled by hand-coded scripts, advocating for agentic, self-correcting workflows powered by Director and Stage Hand.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- To enable hallucination-free AI coding, ingest your codebase into Neo4j, configure the MCP server to use the knowledge graph, and integrate the hallucination detector into your agent workflow.
- When building AI agents, always validate generated code against the knowledge graph before execution to catch and correct hallucinations automatically.
- Invest time refining your system prompts and documentation (e.g., claw.md) to ensure agents interpret instructions correctly and confidence scores are meaningful.

### What to Avoid
- Relying solely on documentation-based RAG is insufficient—AI assistants will still hallucinate valid-looking but non-existent code.
- Neglecting to update or accurately map the knowledge graph can lead to false negatives or missed hallucinations.
- Poorly specified prompts or system instructions can cause agents to misinterpret validation goals, skewing confidence metrics.

### Best Practices
- Automate hallucination detection by integrating deterministic scripts with your AI coding pipeline, using knowledge graphs as the source of truth.
- Modularize your agent workflows to allow dynamic injection of tools (e.g., hallucination detector, graph query) for flexible, robust coding assistance.
- Keep your knowledge graphs and RAG sources in sync with your codebase to maintain high validation accuracy.

### Personal Stories & Experiences
- Automate hallucination detection by integrating deterministic scripts with your AI coding pipeline, using knowledge graphs as the source of truth.
- Modularize your agent workflows to allow dynamic injection of tools (e.g., hallucination detector, graph query) for flexible, robust coding assistance.
- Keep your knowledge graphs and RAG sources in sync with your codebase to maintain high validation accuracy.

### Metrics & Examples
- Initial hallucination detection found 7 valid uses and 1 hallucination; after correction, 8 valid uses and 0% hallucination rate.
- In a more complex agent generation (over 300 lines), first-try success with zero hallucinations was achieved using the knowledge graph pipeline.
- Manual runs of the hallucination detector confirmed 12 valid uses and zero hallucinations in the final agent script.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=8Mib-hb6Fcg)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
