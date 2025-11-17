+++
title = "The True Power of AI Coding - Build Your OWN Workflows (Full Guide)"
date = 2025-11-17
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Software engineering--Artificial intelligence","Artificial intelligence--Automation","Knowledge management systems"]
tags = ["Obsidian","Docker","OpenAI API","Slash commands","Sub-agents","PRP framework","BMAD","GitHub Spec Kit","Archon","Cloud Code","Context engineering","RAG"]

[extra]
excerpt = "This guide reframes AI coding assistants from mere prompt tools into customizable, reusable systems, empowering developers to architect their own workflows rather than relying on off-the-shelf frameworks. By demystifying context engineering and integrating tools like slash commands, sub-agents, and custom Dockerized agents within platforms like Obsidian, it provides a blueprint for building adaptable, project-specific AI coding pipelines. The approach is deeply practical, emphasizing mental models and hands-on configuration over generic strategies."
video_url = "https://www.youtube.com/watch?v=mHBk8Z7Exag"
video_id = "mHBk8Z7Exag"
cover = "https://img.youtube.com/vi/mHBk8Z7Exag/maxresdefault.jpg"
+++

## Overview

This guide reframes AI coding assistants from mere prompt tools into customizable, reusable systems, empowering developers to architect their own workflows rather than relying on off-the-shelf frameworks. By demystifying context engineering and integrating tools like slash commands, sub-agents, and custom Dockerized agents within platforms like Obsidian, it provides a blueprint for building adaptable, project-specific AI coding pipelines. The approach is deeply practical, emphasizing mental models and hands-on configuration over generic strategies.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Rejecting the proliferation of rigid, one-size-fits-all frameworks (like PRP, BMAD), the methodology centers on understanding the underlying philosophies of these systems to build bespoke workflows tailored to individual projects. The process is grounded in a three-phase mental model—planning, implementing, validating—augmented by reusable slash commands, sub-agents, and global rules, all orchestrated within a local, extensible environment (Obsidian + Docker). This empowers practitioners to become 'project managers' for their AI assistants, not passive consumers.

### The Core Problem
Developers are overwhelmed by a glut of context engineering frameworks and struggle to adapt them to their unique needs, leading to confusion, inefficiency, and shallow use of AI coding assistants. The lack of a flexible, foundational workflow inhibits the creation of robust, reusable coding systems.

### The Solution Approach
The workflow is built around a three-step mental model: planning (including 'vibe planning' for freeform ideation, requirements gathering, and context curation), implementation (using slash commands to execute tasks and manage code generation), and validation (leveraging both AI and human review, with sub-agents specialized for research and validation but not implementation). The process is exemplified through a live setup: integrating a custom Dockerized AI agent with Obsidian, using primer slash commands to bootstrap context, and creating markdown-based workflows that can be adapted across projects.

### Key Insights
- Understanding the 'why' behind frameworks like PRP and BMAD enables you to remix or replace them, building workflows that fit your actual needs.
- Sub-agents are best reserved for research and validation, not for implementation—this separation of concerns prevents workflow confusion and maintains code quality.
- Reusable slash commands and global rules transform ephemeral prompting into a structured, repeatable system, making AI coding assistants far more powerful.

### Concepts & Definitions
- 'Vibe planning' is defined as an initial, freeform exploration phase to brainstorm and clarify project ideas before formalizing requirements.
- 'Slash commands' are reusable prompt templates that automate and standardize interactions with AI coding assistants.
- 'Global rules' are persistent instructions that guide the assistant's behavior across all project phases, ensuring consistency and adherence to best practices.
- 'Sub-agents' are specialized AI agents with targeted roles (e.g., research, validation), each with its own system prompt and scope.

### Technical Details & Implementation
- Custom AI agent runs locally in Docker, exposing OpenAI API-compatible endpoints for integration with Obsidian.
- Slash commands are implemented as markdown templates that automate context setup, task management, and codebase research.
- Primer slash commands are used at the start of each new conversation to orient the AI assistant to the current project state.
- Sub-agents are configured with specialized system prompts for research and validation, but are deliberately excluded from code implementation tasks.

### Tools & Technologies
- Obsidian (local knowledge management, workflow hub)
- Docker (for running custom AI agents)
- Dynamis Obsidian agent (custom AI agent integration)
- Archon (context engineering, RAG, task management)
- GitHub Spec Kit (command-driven requirements and planning)
- Cloud Code (AI coding assistant, conversation management)
- OpenAI API (for agent compatibility)

### Contrarian Takes & Different Approaches
- Advocates scrapping pre-made frameworks in favor of building custom workflows, challenging the prevailing wisdom of adopting popular context engineering strategies as-is.
- Argues that sub-agents should not be used for implementation, counter to some multi-agent workflow trends.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start every new coding session with a primer slash command to orient your AI assistant to the current project context.
- Design your own planning workflow using markdown-based slash commands, tailored to your project's needs rather than generic frameworks.
- Separate research/validation (sub-agents) from implementation (main agent) to maintain clarity and code quality.
- Establish global rules early in your planning phase to ensure consistent assistant behavior across all tasks.

### What to Avoid
- Relying blindly on existing frameworks (PRP, BMAD, etc.) without understanding their philosophy leads to misapplication and inefficiency.
- Using sub-agents for implementation introduces confusion and can degrade code quality—restrict them to research and validation roles.
- Failing to curate context thoroughly in the planning phase results in poor AI output and wasted effort.

### Best Practices
- Adopt a three-phase workflow (plan, implement, validate) and build reusable slash commands for each phase.
- Use primer commands to bootstrap context at the start of every session, especially when working with large or evolving codebases.
- Perform both AI-driven and manual code review to ensure output quality and avoid 'vibe coding' (unstructured, ad-hoc development).

### Personal Stories & Experiences
- Adopt a three-phase workflow (plan, implement, validate) and build reusable slash commands for each phase.
- Use primer commands to bootstrap context at the start of every session, especially when working with large or evolving codebases.
- Perform both AI-driven and manual code review to ensure output quality and avoid 'vibe coding' (unstructured, ad-hoc development).

### Metrics & Examples
- No specific quantitative metrics are cited, but the workflow is demonstrated through a live example: integrating a Dockerized AI agent with Obsidian and executing a full plan-implement-validate cycle.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=mHBk8Z7Exag)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
