+++
title = "Claude Sonnet 4.5 - The New Coding King? (Sonnet 4.5 vs. GPT 5 Codex)"
date = 2025-11-17
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Software engineering--Artificial intelligence","Machine learning--Applications","Natural language processing","Computer programming--Automation"]
tags = ["Claude Sonnet 4.5","GPT-5 Codex","Claude Code","Codeex","Stripe integration","Agentic applications","PRP workflow","Docker","VS Code extension","RAG","Git"]

[extra]
excerpt = "This video delivers a hands-on, side-by-side live comparison of Claude Sonnet 4.5 and GPT-5 Codex for implementing a Stripe integration into a real-world agentic application. The test exposes not just benchmark numbers but practical, workflow-level differences—most notably, Sonnet 4.5’s dramatic speed and efficiency leap, outperforming both its predecessor and OpenAI’s offering in a complex, non-trivial coding task."
video_url = "https://www.youtube.com/watch?v=P-0fm8ljl0I"
video_id = "P-0fm8ljl0I"
cover = "https://img.youtube.com/vi/P-0fm8ljl0I/maxresdefault.jpg"
+++

## Overview

This video delivers a hands-on, side-by-side live comparison of Claude Sonnet 4.5 and GPT-5 Codex for implementing a Stripe integration into a real-world agentic application. The test exposes not just benchmark numbers but practical, workflow-level differences—most notably, Sonnet 4.5’s dramatic speed and efficiency leap, outperforming both its predecessor and OpenAI’s offering in a complex, non-trivial coding task.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The approach is distinctive for its live, unscripted, real-world coding challenge—executing the exact same requirements in parallel on both models within actual developer tools (Claude Code and Codeex). Rather than relying on synthetic benchmarks, the methodology stresses practical developer experience, iterative debugging, and nuanced workflow observations, surfacing issues and strengths as they unfold in a real project context.

### The Core Problem
Evaluating whether Claude Sonnet 4.5’s benchmark-topping performance translates into meaningful, practical superiority over GPT-5 Codex for real-world coding tasks—specifically, building a Stripe payment integration into an existing, agent-powered application. This matters because developer productivity, code quality, and friction points in LLM-assisted coding are critical differentiators in the current generative AI landscape.

### The Solution Approach
The workflow involves launching both Claude Sonnet 4.5 (via Claude Code) and GPT-5 Codex (via Codeex) on the same feature build: integrating Stripe payments into a chat-based agentic app. Both models receive identical, structured requirements (using a PRP-style instruction set), and are run on separate branches to avoid interference. The process is observed live, with iterative corrections and environment setup handled as needed, and both speed and code quality are assessed through direct usage and UI testing.

### Key Insights
- Claude Sonnet 4.5 completed the Stripe integration in 15 minutes—over 5x faster than GPT-5 Codex (1 hour 20 minutes) and more than twice as fast as its predecessor Opus 4.1 (35 minutes).
- Speed is not the only differentiator: Sonnet 4.5 also produced higher quality code with fewer iterations needed for functional correctness, though minor issues (e.g., token count UI updates) still required quick manual fixes.
- GPT-5 Codex exhibited workflow inefficiencies, such as repeatedly rereading files after edits, which slowed progress and introduced friction—potentially a byproduct of the tool’s Windows environment.
- A single live test cannot fully determine superiority, but the observed workflow differences are stark and meaningful for real developer productivity.
- The PRP (Prompt-Requirement-Plan) structured workflow enables both LLMs to break down complex features into manageable tasks, but Sonnet 4.5 executes these with greater fluidity and fewer missteps.

### Concepts & Definitions
- PRP (Prompt-Requirement-Plan): A structured approach to LLM coding workflows, where the model loads the feature requirement, thinks through the implementation, breaks it into tasks, and executes each task sequentially.
- Agentic application: An app architecture where user interactions are mediated by an intelligent agent (here, a RAG-powered chat interface), often requiring complex, multi-step integrations.

### Technical Details & Implementation
- Both models were run in their respective IDE integrations: Claude Sonnet 4.5 in Claude Code (with the new VS Code extension), GPT-5 Codex in Codeex.
- Each LLM worked on a separate Git branch of the same codebase, starting from a pre-integration state to ensure a fair comparison.
- The PRP workflow loaded feature requirements, decomposed them into tasks, and executed stepwise implementation.
- Environment setup included Docker containers for backend services and Stripe test accounts for payment flows.
- Minor manual corrections were needed for Sonnet 4.5 (URL mismatches), and for Codex (Docker/environment setup and UI tweaks).

### Tools & Technologies
- Claude Sonnet 4.5 (via Claude Code and VS Code extension)
- GPT-5 Codex (via Codeex)
- Stripe (test account for payment integration)
- Docker (for backend environment setup)
- Git (for branch management and code isolation)

### Contrarian Takes & Different Approaches
- Benchmarks alone are insufficient—practical, live coding experience is the real litmus test for LLM coding agents.
- Despite hype around OpenAI’s Codex, Claude Sonnet 4.5 currently delivers a superior developer experience in actual implementation scenarios.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- For rapid, high-quality LLM-assisted coding in real projects, leverage Claude Sonnet 4.5 via Claude Code, especially for complex integrations.
- Adopt a structured PRP-style workflow to maximize LLM effectiveness: clearly define requirements, break down tasks, and iterate as needed.
- Use separate branches and containerized environments to isolate LLM outputs and streamline debugging during parallel model evaluations.

### What to Avoid
- Don’t rely solely on benchmarks—real-world workflow friction (like file rereads or environment-specific quirks) can dramatically affect productivity.
- Expect minor issues even from top-performing models (e.g., UI update bugs, environment mismatches); always verify outputs before deployment.
- Running LLM coding agents on certain platforms (e.g., Windows with Codeex) may introduce unexpected slowdowns or workflow inefficiencies.

### Best Practices
- Iterate quickly: address minor issues as they arise rather than expecting one-shot perfection from LLMs.
- Validate LLM-generated code in a live environment before merging or deploying.
- Benchmark LLMs not only on speed and accuracy, but also on workflow smoothness and developer experience.

### Personal Stories & Experiences
- Iterate quickly: address minor issues as they arise rather than expecting one-shot perfection from LLMs.
- Validate LLM-generated code in a live environment before merging or deploying.
- Benchmark LLMs not only on speed and accuracy, but also on workflow smoothness and developer experience.

### Metrics & Examples
- Claude Sonnet 4.5: 15 minutes to full Stripe integration.
- Opus 4.1: 35 minutes for the same task.
- GPT-5 Codex: 1 hour 20 minutes, with workflow inefficiencies.
- Sonnet 4.5 showed a nearly 20% improvement in agentic tool use benchmarks over Opus 4.1.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=P-0fm8ljl0I)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
