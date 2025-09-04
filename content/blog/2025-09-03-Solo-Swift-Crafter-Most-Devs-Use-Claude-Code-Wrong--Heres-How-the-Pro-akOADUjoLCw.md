+++
title = "Most Devs Use Claude Code Wrong — Here’s How the Pros Actually Do It"
date = 2025-09-03
draft = false

[taxonomies]
author = ["Solo Swift Crafter"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering", "Automation", "Programming", "Personal productivity"]

[extra]
excerpt = "Solo Swift Crafter (Daniel) reframes Claude Code from a generic AI tool into a deeply personalized coding partner, emphasizing the power of teaching it your unique workflows, quirks, and preferences. His approach is rooted in indie iOS development, focusing on evolving a collaborative relationship with Claude that saves time, reduces friction, and amplifies creativity. This perspective matters because it transforms AI from a transactional tool into an adaptive teammate, unlocking compounding productivity gains for solo and indie developers."
video_url = "https://www.youtube.com/watch?v=akOADUjoLCw"
video_id = "akOADUjoLCw"
cover = "https://img.youtube.com/vi/akOADUjoLCw/maxresdefault.jpg"
+++

## Overview

Solo Swift Crafter (Daniel) reframes Claude Code from a generic AI tool into a deeply personalized coding partner, emphasizing the power of teaching it your unique workflows, quirks, and preferences. His approach is rooted in indie iOS development, focusing on evolving a collaborative relationship with Claude that saves time, reduces friction, and amplifies creativity. This perspective matters because it transforms AI from a transactional tool into an adaptive teammate, unlocking compounding productivity gains for solo and indie developers.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Daniel's methodology centers on treating Claude Code as a new team member rather than a vending machine—one that learns, adapts, and remembers your specific coding style and project context. He advocates for a living, evolving setup (like the claude.md file) that onboards Claude to your world, and leverages custom workflows, sub-agents, and parameterized commands to create a tailored, automation-rich environment. His indie dev lens prioritizes flexibility, minimal friction, and continuous refinement over rigid, one-size-fits-all AI usage.

### The Core Problem
Most developers use Claude Code superficially, treating it as a black-box prompt generator and missing out on its potential for deep, context-aware collaboration. This leads to generic outputs, frustration, and underutilization—especially problematic for solo and indie developers who need every edge in productivity and code quality.

### The Solution Approach
Daniel's approach is to 'onboard' Claude like a human teammate by documenting project-specific quirks, workflows, and preferences in a claude.md file, checked into the repo or stored globally. He builds reusable, parameterized slash commands for frequent tasks, integrates external tools via MCP, and structures work into explicit 'explore-plan-code-commit' flows with sub-agents for complex tasks. He emphasizes iterative refinement: start small, observe results, and evolve the setup based on real-world feedback, always prioritizing clarity and context for Claude.

### Key Insights
- Claude Code's power compounds when you teach it your project's quirks and your personal coding style, not just generic prompts.
- Explicitly separating planning and coding phases (e.g., 'explore-plan-code-commit') yields better results than jumping straight to code generation.
- Investing in reusable, parameterized commands and onboarding docs pays off in saved time and reduced friction, especially for solo devs juggling multiple projects.

### Concepts & Definitions
- "claude.md": A living onboarding file for Claude, containing all the contextual knowledge, scripts, and preferences you'd share with a new human teammate.
- "MCP": A protocol for connecting Claude to external servers/tools, enabling workflow automation beyond code generation.
- "Sub-agents": Separate Claude subprocesses tasked with investigating specific questions or sections, keeping the main session focused.
- "Explore-plan-code-commit": A workflow where Claude first researches and plans before generating code, then commits changes.

### Technical Details & Implementation
- Use a claude.md file (format-free, markdown) in the repo root or home directory to document scripts, style rules, test commands, and known gotchas.
- Leverage MCP protocol to connect Claude to external tools like Puppeteer (browser automation) or Sentry (error reporting), configured per project or globally.
- Create custom slash commands by storing prompt templates in a cloud/commands directory, supporting parameterization for tasks like fixing GitHub issues or updating dependencies.
- Adopt sub-agents for multi-step or complex tasks to keep context focused and parallelize investigation.

### Tools & Technologies
- Claude Code (Anthropic's AI shell sidekick)
- MCP (for tool integrations like Puppeteer, Sentry)
- GitHub (for PR management)
- Custom Swift build wrappers
- cloud/commands (for slash command templates)

### Contrarian Takes & Different Approaches
- Rejects the idea of AI as a vending machine; insists on treating it as a collaborative, evolving teammate.
- Pushes back against rigid, official best practices—advocates for building a workflow that fits your unique habits and stack.
- Challenges the notion that AI should be used 'out of the box'—argues for investing in onboarding and customization.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by creating a claude.md file for your next project, documenting anything you'd tell a new teammate.
- Build one or two custom slash commands for your most repetitive tasks and parameterize them for flexibility.
- Adopt the 'explore-plan-code-commit' workflow: have Claude research and plan before writing code, and sanity-check its own output.
- Iterate and evolve your setup—observe what works, refine your onboarding docs, and expand automation as you go.

### What to Avoid
- Don't treat Claude as a magic box—generic prompts lead to generic, sometimes incorrect results.
- Avoid letting Claude write code before you've agreed on a plan; skipping the research phase results in half-baked fixes.
- Beware of overfitting tests when using Claude for TDD—use sub-agents to check for edge cases.

### Best Practices
- Onboard Claude with a claude.md file tailored to your project's quirks and your coding style.
- Use parameterized slash commands for repeatable workflows, stored in a dedicated commands directory.
- Separate planning and coding phases, explicitly instructing Claude to research before generating code.
- Leverage sub-agents for complex or multi-step tasks to maintain clarity and focus.

### Personal Stories & Experiences
- Daniel shares that onboarding Claude with project-specific context has repeatedly saved him from bugs and confusion.
- He recounts how the 'are you sure' sanity-check step has prevented half-baked fixes from making it into production.
- His transition from freelance to full-time indie dev led him to refine these workflows out of necessity, not theory.

### Metrics & Examples
- "...a little automation that saves you 10 minutes every time you code. That adds up."
- No specific quantitative case studies, but repeated emphasis on cumulative time savings and reduced friction.

## Resources & Links

- [https://www.anthropic.com/engineering/claude-code-best-practices](https://www.anthropic.com/engineering/claude-code-best-practices)
- [Video URL](https://www.youtube.com/watch?v=akOADUjoLCw)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Fresh Perspective

