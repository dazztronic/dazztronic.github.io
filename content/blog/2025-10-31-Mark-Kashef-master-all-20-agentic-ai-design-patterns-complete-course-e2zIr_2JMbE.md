+++
title = "Master ALL 20 Agentic AI Design Patterns [Complete Course]"
date = 2025-10-31
draft = false

[taxonomies]
author = ["Mark Kashef"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Multi-agent systems"]
tags = ["Agentic design patterns","Prompt chaining","Shared memory","Coordinator pattern","Mermaid","Claude","Cursor","Jira","Asana"]

[extra]
excerpt = "Mark Kashef distills a 400-page Google engineer-authored book on agentic AI design patterns into a practical, jargon-free video course. The focus is on actionable workflows, real-world analogies, and step-by-step breakdowns of all 20 patterns, empowering practitioners to immediately apply agentic architectures to solve concrete problems."
video_url = "https://www.youtube.com/watch?v=e2zIr_2JMbE"
video_id = "e2zIr_2JMbE"
cover = "https://img.youtube.com/vi/e2zIr_2JMbE/maxresdefault.jpg"
+++

## Overview

Mark Kashef distills a 400-page Google engineer-authored book on agentic AI design patterns into a practical, jargon-free video course. The focus is on actionable workflows, real-world analogies, and step-by-step breakdowns of all 20 patterns, empowering practitioners to immediately apply agentic architectures to solve concrete problems.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Kashef's approach is defined by radical simplification: stripping away academic jargon and theory to deliver each pattern in plain English, with annotated visuals and workflow diagrams. He emphasizes practical application over theory, providing TLDDR (Too Long, Didn't Read) summaries, pros/cons, and use cases for each pattern, and encourages viewers to use the transcript as a reference for AI agents like Claude or Cursor to select the right pattern for a given problem.

### The Core Problem
The main challenge addressed is the overwhelming complexity and inaccessibility of agentic AI design patterns for practitioners who need to build robust, multi-agent systems. Many resources are dense, theoretical, or lack actionable guidance, leaving developers unable to implement these patterns effectively in real-world projects.

### The Solution Approach
Kashef systematically breaks down each of the 20 agentic patterns using a repeatable structure: TLDDR summary, when/where to use, pros and cons, and concrete applications. He uses relatable analogies (e.g., film crew for multi-agent coordination), workflow diagrams (often in Mermaid), and focuses on how memory, coordination, and task assignment work in practice. He advocates for feeding the transcript to AI tools to automate pattern selection for specific problems.

### Key Insights
- Prompt chaining is powerful because it introduces multiple validation points, allowing failures to be caught early and outputs to be checked stepwise before progressing.
- Shared memory in multi-agent systems must be carefully structured to avoid overlap and ensure only the necessary memories persist, likened to a film crew sharing a script and timeline.
- The coordinator/orchestrator pattern mirrors project management tools like Jira or Asana, where tasks (tickets) are dynamically assigned to specialist agents, each with clear acceptance criteria and contract completion checks.

### Concepts & Definitions
- Prompt chaining: breaking a large task into smaller, sequential steps where each step validates the previous output before proceeding.
- Shared memory: a persistent storage mechanism accessible by multiple agents, requiring careful management to avoid memory overlap.
- Coordinator/orchestrator: a central agent or protocol that assigns tasks, manages flow, and enforces acceptance criteria across specialist agents.

### Technical Details & Implementation
- Agentic workflows are visualized using Mermaid diagrams for clarity and reproducibility.
- Shared memory implementations require careful configuration, such as using MCP servers or artifact/version control systems, to ensure proper memory isolation and persistence.
- Task orchestration is modeled after ticket-based project management, with coordinators assigning tasks to agents and enforcing contract-based handoffs.

### Tools & Technologies
- Claude (for transcript ingestion and pattern selection)
- Cursor (as an AI coding assistant)
- Mermaid (for diagramming workflows)
- Jira/Asana (as analogies for agent task management)

### Contrarian Takes & Different Approaches
- Rejects the prevailing trend of over-theorizing agentic design, instead advocating for immediate, practical application and plain-language explanations.
- Challenges the notion that agentic patterns are only for advanced practitioners, arguing that anyone can master them with the right framing.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Use the transcript as a reference dataset for AI coding assistants to automate agentic pattern selection.
- Implement prompt chaining for complex tasks to introduce stepwise validation and error catching.
- Adopt a coordinator pattern with shared memory and contract-based task handoffs to manage multi-agent workflows effectively.

### What to Avoid
- Failing to structure shared memory can result in memory overlap and data leakage between agents.
- Skipping validation steps in prompt chaining increases the risk of propagating errors through the workflow.
- Neglecting clear acceptance criteria for agent tasks leads to ambiguous handoffs and unreliable outcomes.

### Best Practices
- Annotate each workflow with plain-English labels to ensure clarity and ease of onboarding for new team members.
- Model agent coordination after proven project management paradigms, using tickets and contracts for task assignment and completion.
- Leverage visual workflow diagrams to communicate and debug agentic architectures.

### Personal Stories & Experiences
- Annotate each workflow with plain-English labels to ensure clarity and ease of onboarding for new team members.
- Model agent coordination after proven project management paradigms, using tickets and contracts for task assignment and completion.
- Leverage visual workflow diagrams to communicate and debug agentic architectures.

### Metrics & Examples
- References a 400-page book as the source material, underscoring the depth condensed into the video.
- Uses the analogy of project management tickets (e.g., Jira/Asana) to quantify and structure agent task assignments.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=e2zIr_2JMbE)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
