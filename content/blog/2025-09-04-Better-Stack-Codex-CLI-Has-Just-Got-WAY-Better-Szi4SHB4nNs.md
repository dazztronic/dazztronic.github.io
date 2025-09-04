+++
title = "Codex CLI Has Just Got WAY Better!"
date = 2025-09-04
draft = false

[taxonomies]
author = ["Better Stack"]
categories = ["Software engineering--Artificial intelligence"]
tags = ["Software engineering--Artificial intelligence", "Computer security", "Programming tools"]

[extra]
excerpt = "Better Stack delivers a hands-on, skeptical yet hopeful review of Codex CLI's major overhaul, focusing on real-world usability, security, and developer workflow friction. Their perspective stands out for its candid critique, deep dive into security configurations, and practical advice for maximizing Codex CLI's new capabilities while avoiding its pitfalls."
video_url = "https://www.youtube.com/watch?v=Szi4SHB4nNs"
video_id = "Szi4SHB4nNs"
cover = "https://img.youtube.com/vi/Szi4SHB4nNs/maxresdefault.jpg"
+++

## Overview

Better Stack delivers a hands-on, skeptical yet hopeful review of Codex CLI's major overhaul, focusing on real-world usability, security, and developer workflow friction. Their perspective stands out for its candid critique, deep dive into security configurations, and practical advice for maximizing Codex CLI's new capabilities while avoiding its pitfalls.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
This creator approaches Codex CLI not as a fan but as a power user who previously avoided it due to bugginess and subpar coding models compared to Claude. Their methodology is rooted in rigorous, experience-driven testing, emphasizing security, minimalism, and developer autonomy. They uniquely dissect the tool's sandboxing and approval mechanics, offering nuanced, scenario-based recommendations rather than blanket endorsements.

### The Core Problem
The core problem addressed is the historical unreliability, clunky UX, and security ambiguity of Codex CLI, which previously made it a poor fit for serious coding workflows. This matters as developers increasingly rely on terminal-based AI coding assistants, and need tools that are both powerful and safe by default.

### The Solution Approach
Their approach is to methodically test the new Codex CLI update, focusing on speed (from Rust rewrite), UI minimalism, and especially the granular sandbox and approval settings. They advocate for configuring Codex CLI to match your risk tolerance and workflow, using custom profiles and explicit config settings to avoid constant interruptions and maximize productivity.

### Key Insights
- The Rust rewrite (using Ratatouille) delivers tangible speed, security, and dependency improvements over the original TypeScript/Ink version.
- Codex CLI's security model is more robust than competitors, running in a sandbox by default and offering granular control over file and command permissions.
- The approval and sandbox settings, while powerful, can be confusing and disruptive if not proactively configured—requiring a deliberate setup for smooth use.

### Concepts & Definitions
- "Sandbox": An isolated environment restricting Codex CLI's access to files, processes, and network outside the project workspace.
- "Approval flag": A setting that determines when Codex CLI must prompt the user for permission to execute edits or commands.
- "Minimalist UI": A user interface stripped of decorative elements (like ASCII art), focusing solely on text and function.

### Technical Details & Implementation
- Codex CLI now supports login via ChatGPT plan or API key, with a minimalist text-only UI (no ASCII art).
- Sandbox flag options: 'workspace,write' (read/edit files in current dir), 'read only' (read files, ask for edits/commands), 'danger' (full access).
- Approval flag options: 'on request', 'never', 'on failure', 'untrusted'. These can be combined with sandbox settings for fine-grained control.
- Configuration is managed via a TOML file, supporting custom profiles (-p flag) for different workflows.
- Transcript view (Esc Esc or Ctrl+T) reveals all commands, file reads, and model reasoning for transparency.

### Tools & Technologies
- Codex CLI (OpenAI's terminal-based coding assistant)
- Claude (as a coding model benchmark)
- VS Code and Cursor (as alternative AI coding environments, not used by the creator)
- Ratatouille (Rust library for TUI)
- Ink (previous TypeScript TUI library)

### Contrarian Takes & Different Approaches
- Codex CLI is not yet a full replacement for Claude Code, despite improvements—contrary to hype.
- Minimalist UI is preferable to flashy interfaces for productivity.
- Security-by-default should be the norm, not an afterthought, even if it adds initial setup complexity.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Immediately configure your preferred sandbox and approval settings in the TOML config to avoid disruptive prompts.
- Use the 'status' command to verify your current security posture before running commands.
- Create custom profiles for different risk scenarios (e.g., 'read-only' for audits, 'danger' for trusted scripts) and switch with -p.

### What to Avoid
- Failing to set sandbox/approval flags leads to constant login and permission prompts, breaking workflow.
- Misunderstanding the approval model can result in either excessive interruptions or unintentional over-permissioning.
- Windows users are not officially supported yet—expect issues.

### Best Practices
- Proactively set up config profiles tailored to your workflow and security needs.
- Leverage the transcript feature to audit all actions Codex CLI takes in your environment.
- Keep Codex CLI updated to benefit from ongoing security and UX improvements.

### Personal Stories & Experiences
- The creator avoided Codex CLI for a long time due to bugs and inferior models, only reconsidering after the Rust rewrite and major update.
- They express annoyance at repetitive login prompts and complex approval options, reflecting real-world friction.
- Their thinking evolved from skepticism to cautious optimism as the tool matured.

### Metrics & Examples
- Codex CLI now ships with 11 default commands.
- No specific performance numbers, but the Rust version is described as 'faster' and 'more secure' than the TypeScript predecessor.

## Resources & Links

- [https://betterstack.com/docs/getting-started/integrations/mcp/](https://betterstack.com/docs/getting-started/integrations/mcp/)
- [https://betterstack.com/](https://betterstack.com/)
- [https://betterstack.com/community/](https://betterstack.com/community/)
- [https://github.com/BetterStackHQ](https://github.com/BetterStackHQ)
- [https://twitter.com/betterstackhq](https://twitter.com/betterstackhq)
- [https://www.instagram.com/betterstackhq/](https://www.instagram.com/betterstackhq/)
- [https://www.tiktok.com/@betterstack](https://www.tiktok.com/@betterstack)
- [https://www.linkedin.com/company/betterstack](https://www.linkedin.com/company/betterstack)
- [Video URL](https://www.youtube.com/watch?v=Szi4SHB4nNs)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Fresh Perspective

