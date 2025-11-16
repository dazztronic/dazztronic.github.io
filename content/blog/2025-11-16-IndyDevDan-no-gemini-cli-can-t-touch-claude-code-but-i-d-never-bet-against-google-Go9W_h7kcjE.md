+++
title = "No, Gemini CLI CAN’T touch Claude Code BUT I’d NEVER bet against Google"
date = 2025-11-16
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Software engineering--Artificial intelligence","Machine learning--Natural language processing","Computer programming--Automation"]
tags = ["Agentic coding","Gemini CLI","Claude Code","Opus model","Gemini 2.5 Pro","Bun","Git worktree","Slash commands","Vue.js","Parallel agent workflows"]

[extra]
excerpt = "IndyDevDan delivers a hands-on, side-by-side battle between Google's new Gemini CLI and Anthropic's Claude Code, dissecting their agentic coding capabilities in real-world workflows. While Gemini CLI can't yet match Claude Code's agentic depth, its speed, memory features, and Google's relentless innovation pipeline make it a future contender that shouldn't be underestimated."
video_url = "https://www.youtube.com/watch?v=Go9W_h7kcjE"
video_id = "Go9W_h7kcjE"
cover = "https://img.youtube.com/vi/Go9W_h7kcjE/maxresdefault.jpg"
+++

## Overview

IndyDevDan delivers a hands-on, side-by-side battle between Google's new Gemini CLI and Anthropic's Claude Code, dissecting their agentic coding capabilities in real-world workflows. While Gemini CLI can't yet match Claude Code's agentic depth, its speed, memory features, and Google's relentless innovation pipeline make it a future contender that shouldn't be underestimated.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The approach is a live, technical bake-off using identical prompts and isolated git worktrees to rigorously compare agentic coding tools in practical, multi-step front-end development tasks. Dan's methodology is rooted in agentic evaluation, leveraging custom slash commands and parallel environments to expose nuanced strengths and weaknesses, rather than relying on abstract benchmarks or marketing claims.

### The Core Problem
Evaluating whether Google's Gemini CLI introduces genuinely new agentic coding capabilities that can challenge or surpass the current leader, Claude Code, in practical, developer-centric workflows. This matters because the agentic coding landscape is rapidly evolving, and developers need clear, experience-driven guidance on which tools deliver real productivity and code quality gains.

### The Solution Approach
Dan sets up isolated git worktrees for each agent, using custom slash commands to automate environment duplication and variable propagation. Each tool is given identical prompts across escalating UI component complexity, with outputs compared on speed, planning, memory, and code quality. The evaluation is grounded in real project tasks (e.g., creating hero banners, carousels, data tables, multi-step forms) and emphasizes both agentic reasoning and raw execution.

### Key Insights
- Gemini CLI is significantly faster than Claude Code but lacks true agentic planning and parallelization, making it less precise for complex, multi-step tasks.
- Gemini's automatic memory feature (retaining user instructions without explicit memory commands) is unique and powerful, but could introduce subtle bugs if not carefully managed.
- Agentic frameworks like Claude Code's Opus model excel in stepwise planning and subtask management, leading to cleaner, more reliable code, especially as task complexity increases.
- The real competitive advantage for Google is not current feature parity, but its access to massive training data (e.g., YouTube), engineering talent, and the ability to iterate rapidly—making it unwise to bet against their long-term prospects.
- Front-end framework choice is becoming irrelevant for these models; both can handle Vue.js and similar stacks with ease.

### Concepts & Definitions
- "Agentic coding" is defined as coding workflows where AI agents autonomously plan, execute, and manage subtasks, often in parallel, to accomplish complex development objectives.
- "Git worktree" is explained as a method to create multiple working directories from a single repository, allowing isolated environments for each agent or workflow.
- "Memory feature" in this context refers to the AI tool's ability to persist user instructions across tasks without explicit user intervention.

### Technical Details & Implementation
- Isolated git worktrees are used for each agent, set up via custom slash commands embedded in a trees.md file, ensuring clean environments and reproducible tests.
- Both Gemini CLI (Gemini 2.5 Pro) and Claude Code (Opus model) are run in their own directories with environment variables copied for parity.
- Gemini CLI operates in 'YOLO mode' (full access), while Claude Code is run in 'dangerous mode' for maximum capability.
- Evaluation tasks include installing dependencies with Bun, updating HTML titles, and incrementally building UI components (hero banner, carousel, data table, multi-step form).
- Gemini CLI's memory feature automatically persists user instructions (e.g., not to auto-run dev servers), unlike Claude Code which requires explicit memory management.

### Tools & Technologies
- Gemini CLI (Google's agentic coding tool, evaluated with Gemini 2.5 Pro)
- Claude Code (Anthropic's agentic coding tool, evaluated with Opus model)
- Bun (JavaScript runtime for installing dependencies)
- Git worktree (for isolated codebase environments)
- Custom slash commands (for automating environment setup and reporting)

### Contrarian Takes & Different Approaches
- It's a mistake to bet against Google in the long run, despite their current product lagging behind Anthropic's Claude Code in agentic sophistication.
- The real battle is not about feature parity today, but about who can leverage data, talent, and iteration speed to dominate agentic coding in the future.
- Framework and language choice is becoming moot for these models—agentic coding tools are rapidly abstracting away such distinctions.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Use isolated git worktrees for each AI agent to ensure clean, reproducible testing and prevent cross-contamination of code changes.
- Leverage custom slash commands to automate environment setup and task orchestration when evaluating or using agentic coding tools.
- Explicitly instruct agentic tools not to perform undesired actions (e.g., auto-starting dev servers) and verify if the tool persists such instructions automatically.
- Monitor both speed and quality—Gemini CLI may be faster, but Claude Code's stepwise planning often yields cleaner, more reliable code for complex tasks.
- Stay tool-agnostic and monitor rapid developments; don't lock into a single agentic coding tool given the pace of innovation.

### What to Avoid
- Running agentic tools in 'dangerous' or 'YOLO' modes can lead to unintended destructive actions—only do so if you fully understand the risks.
- Relying solely on speed (as with Gemini CLI) may sacrifice code quality and introduce subtle bugs, especially in multi-step or stateful workflows.
- Automatic memory features can be double-edged: while convenient, they may cause unexpected behavior if prior instructions are unintentionally retained.

### Best Practices
- Always isolate agentic agents in separate git worktrees to maintain clean environments and facilitate parallel experimentation.
- Evaluate agentic coding tools using real-world, incrementally complex tasks to surface strengths and weaknesses that benchmarks may miss.
- Favor agentic frameworks with explicit planning and subtask management for complex, multi-component development.

### Personal Stories & Experiences
- Always isolate agentic agents in separate git worktrees to maintain clean environments and facilitate parallel experimentation.
- Evaluate agentic coding tools using real-world, incrementally complex tasks to surface strengths and weaknesses that benchmarks may miss.
- Favor agentic frameworks with explicit planning and subtask management for complex, multi-component development.

### Metrics & Examples
- Gemini CLI is more than twice as fast as Claude Code (Opus 4) in multi-step form generation tasks.
- Gemini CLI's open-source repo has 67 contributors, 119 pull requests, and 500 issues, indicating strong early community interest.
- Both tools successfully generate hero banners, carousels, and data tables, but differ in code cleanliness and feature completeness.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=Go9W_h7kcjE)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
