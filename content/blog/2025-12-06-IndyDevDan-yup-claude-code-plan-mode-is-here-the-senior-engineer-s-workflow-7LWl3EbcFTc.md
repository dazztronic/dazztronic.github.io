+++
title = "Yup, Claude Code Plan Mode is here: The Senior Engineer's Workflow"
date = 2025-12-06
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Software engineering--Artificial intelligence","Computer programming","Human-computer interaction"]
tags = ["Claude Code","Plan Mode","Agentic coding","Opus 4","Prompt engineering","Infinite agentic loop","Specs directory","Context window","Prime command"]

[extra]
excerpt = "This video delivers a senior engineer's workflow for leveraging Claude Code's new Plan Mode, emphasizing a deliberate separation between planning and execution that mirrors expert engineering practices. The approach is all about maximizing agentic coding tools by priming context windows, validating assumptions, and pushing more ambitious, multi-step tasks to AI agents, resulting in higher velocity and safer, more reliable code changes."
video_url = "https://www.youtube.com/watch?v=7LWl3EbcFTc"
video_id = "7LWl3EbcFTc"
cover = "https://img.youtube.com/vi/7LWl3EbcFTc/maxresdefault.jpg"
+++

## Overview

This video delivers a senior engineer's workflow for leveraging Claude Code's new Plan Mode, emphasizing a deliberate separation between planning and execution that mirrors expert engineering practices. The approach is all about maximizing agentic coding tools by priming context windows, validating assumptions, and pushing more ambitious, multi-step tasks to AI agents, resulting in higher velocity and safer, more reliable code changes.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
IndyDevDan frames Plan Mode not just as a feature, but as a paradigm shift: treating AI agents as junior engineers who require clear, staged instructions, context priming, and explicit plans before execution. The methodology borrows from senior engineering habits—research, plan, then build—while exploiting Plan Mode's safety (no mutations) to iterate and validate plans collaboratively with the agent before any code is touched.

### The Core Problem
Modern AI coding tools often blur planning and execution, leading to context loss, unreviewed changes, and brittle workflows. The challenge is enabling AI agents to handle complex, multi-step engineering tasks safely and efficiently, without sacrificing control or clarity.

### The Solution Approach
The workflow is: enter Plan Mode (Shift+Tab+Tab), use concise prompts to load the agent's context window with relevant codebase details, ask explicit, even 'stupid', questions to validate understanding, and have the agent generate a detailed plan (ideally written to a spec file). Only after plan approval does the workflow exit Plan Mode and move to execution, often using 'think hard' triggers to invoke deeper reasoning. This mirrors the senior engineer's process of architecting before building, and leverages the agent's statelessness by persisting plans for review and iteration.

### Key Insights
- Plan Mode's strict read-only context gathering is a superpower: it prevents accidental mutations and lets engineers safely iterate on plans with the agent.
- Contrary to the 'move fast and break things' ethos, the most effective agentic workflows slow down up front—planning and validating before any code is generated.
- A critical lesson: always persist plans to disk (spec files) before execution, since agent context is ephemeral and can be lost, undermining traceability and review.

### Concepts & Definitions
- Plan Mode: a Claude Code operating mode where the agent only reads, analyzes, and plans—no code mutations—mirroring the research and design phase of engineering.
- Context Window: the set of files and information loaded into the agent's working memory, critical for accurate planning and execution.
- Agentic Coding: a workflow where AI agents are treated as collaborators, given explicit plans and context, and expected to execute multi-step tasks.
- Ephemeral Agents: AI agents whose context and state are temporary; persisting plans/specs to disk is necessary for traceability.

### Technical Details & Implementation
- Plan Mode is toggled with Shift+Tab+Tab in Claude Code; it restricts the agent to reading files and building context, with no file creation, modification, or deletion allowed.
- The recommended workflow uses the 'prime' command (e.g., 'get ls files') to load key files into the context window, followed by explicit planning prompts.
- For mid-to-large features, the process involves writing the plan to a spec file in a dedicated specs directory, then having the agent execute against that spec.
- The 'think hard' keyword in prompts triggers the reasoning model in Claude 4 Opus, yielding more thoughtful, information-dense plans.
- Infinite agentic loop architecture is used to generate multiple solution variants in parallel, each in its own directory with modular file separation.

### Tools & Technologies
- Claude Code (with Plan Mode and Opus 4 model)
- Cursor (editor integration)
- Prime command (custom slash command for context loading)
- Infinite agentic loop codebase
- Specs directory for plan persistence

### Contrarian Takes & Different Approaches
- Challenges the notion that speed comes from immediate code generation; instead, advocates for deliberate planning as the real velocity multiplier.
- Argues that agents should be treated as junior engineers needing explicit, staged instructions—not as magical black boxes.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Always start with Plan Mode before any code changes—prime the agent's context, validate assumptions, and get a plan approved.
- For substantial features, have the agent write the plan to a spec file, review and iterate on it, then execute only after approval.
- Use explicit, even redundant prompts and questions to ensure the agent's understanding; don't assume implicit context.
- Leverage the 'think hard' keyword to get deeper reasoning from the model when planning complex changes.

### What to Avoid
- Avoid jumping straight to code generation without a validated plan—context loss and unreviewed changes are common failure modes.
- Don't trust the agent's first answer blindly; always use 'correct me if I'm wrong' to reduce model bias and surface misunderstandings.
- Failing to persist plans/specs means losing the ability to review, iterate, or recover from agent context resets.

### Best Practices
- Mirror senior engineering habits: research, plan, then build—never conflate planning and execution.
- Prime the agent's context window with only the most relevant files and details for concise, focused planning.
- Persist all plans/specs to disk for traceability, review, and future iteration.
- Push for larger, more ambitious agentic tasks—modern models and compute can handle more than you think.

### Personal Stories & Experiences
- Mirror senior engineering habits: research, plan, then build—never conflate planning and execution.
- Prime the agent's context window with only the most relevant files and details for concise, focused planning.
- Persist all plans/specs to disk for traceability, review, and future iteration.
- Push for larger, more ambitious agentic tasks—modern models and compute can handle more than you think.

### Metrics & Examples
- Each agent consumed about 40k Opus tokens and completed tasks in roughly 3 minutes.
- Top-level agent ran for 400 seconds and used 5.2k tokens.
- Multiple UI variants generated in parallel, each with its own modular file structure.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=7LWl3EbcFTc)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
