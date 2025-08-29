+++
title = "How I ACTUALLY Use Claude Code... My Complete Workflow"
date = 2025-08-27
draft = false

[taxonomies]
author = ["AI LABS"]
categories = ["Claude Code", "Development Workflow"]
tags = ["claude-code", "subagents", "agentic-workflows", "ux", "ui", "nextjs", "testing", "performance", "gitingest"]

[extra]
excerpt = "The video demonstrates a complete, repeatable workflow in Claude Code that builds polished applications by chaining subagents (UX → UI design → implementation → testing → benchmarking), while preserving context and avoiding common failure modes."
video_url = "https://www.youtube.com/watch?v=7Sx0o-41r2k"
video_id = "7Sx0o-41r2k"
cover = "https://img.youtube.com/vi/7Sx0o-41r2k/maxresdefault.jpg"
+++

## 📖 Overview
The video demonstrates a **complete, repeatable workflow in Claude Code** that builds polished applications by chaining **subagents** (UX → UI design → implementation → testing → benchmarking), while preserving context and avoiding common failure modes. The approach emphasizes **context capture (MD docs), proactive agent roles, and parallelism** to produce higher-quality results than single-agent prompting.

![Video Thumbnail](https://img.youtube.com/vi/7Sx0o-41r2k/maxresdefault.jpg)

## 🔍 Key Insights & Learnings

### The Core Problem
- **Single-threaded prompting loses context** and drifts over long builds. Even with a 200k token window per session, complex app builds overflow and earlier reasoning is forgotten. **Result:** brittle prototypes and "cluttered" UIs when agents make product decisions on the fly.
- Existing frameworks (e.g., **BMAD**, **Supercloud**) existed as **slash-command** workflows and weren't yet implemented as Claude Code subagents at recording time—limiting chaining and maintainable context flow.

### The Solution Approach
- **Chain specialized subagents** (UX Researcher → Sprint Prioritizer → UI Designer → Whimsy/Micro-interaction Designer → Rapid Prototyper → Frontend Dev → Test Runner → Performance Benchmarker) and **persist their outputs to Markdown** so downstream agents read from durable, explicit context rather than transient conversation state.
- Use Claude Code's **subagent architecture**: each subagent has its **own context window** (separate from main), and the **main session acts as a controller**, delegating tasks and fanning out work **in parallel** where beneficial.
- **Iterate on prompts and scope early**: supply features from a high-level planning pass (outside the subagents), then constrain the UX agent to **user experience only** (not product scope) to avoid cluttered UIs.

### Technical Details & Implementation

**1) Subagent basics (Claude Code):**  
- Subagents live as Markdown with YAML frontmatter in either **project** (`.claude/agents/`) or **user** (`~/.claude/agents/`) scope; project scope wins on name conflicts. Minimal structure:  
  ```md
  ---
  name: code-reviewer
  description: Expert review; use proactively after changes
  tools: Read, Grep, Glob, Bash
  ---

  You are a senior code reviewer. When invoked:
  1) run git diff
  2) focus on modified files
  3) report findings by priority...
  ```

**2) Project context capture to MD (critical):**

* After generating a draft multi-agent workflow, **persist context** (UX, UI specs, tasks, architecture notes) to **Markdown files** so each downstream agent reads the exact prior conclusions without blowing the chat context.
* The video's 4 phases: **(1) UX & Planning, (2) UI Design, (3) Frontend, (4) Backend**—each with its own prompts & doc folders.

  Example structure:
  ```
  /docs/
    ux/           # research, personas, flows, IA
    ui/           # component plans, states, microinteractions
    impl/
      frontend/   # component checklists, integration notes
      backend/    # endpoints, contracts, perf targets
    qa/           # test plans, issues, perf reports
  .claude/
    agents/       # ux-researcher.md, ui-designer.md, ...
    commands/     # reusable slash commands (optional)
  ```

**3) Bootstrapping with GitIngest + public agent packs:**

* Use **gitingest.com** to convert a GitHub repo (e.g., a **subagent collection organized by department**) into **LLM-readable text**; paste into Claude Code and ask it to **propose a connected agent workflow**, then refine prompts and **write the doc/agent files**.
* Example community list of Claude Code **subagents** for inspiration.

**4) Running & observing agents:**

* Prefer the author's **auto-run startup** (vs. "simple" start) and use **verbose mode** to see what agents do behind the scenes.
* **Checkpointing/branch navigation:** *press `Esc` twice* to open prior prompt branches and **jump back safely**—useful when a run goes off-track.

**5) Results & costs (example from the run):**

* UX research subagent **~7 min / 53k tokens**; Frontend implementation **~18 min / 130k tokens**; high polish with **microinteractions** and smooth transitions; multiple **views (calendar/table/kanban)** for content.
* Heavy multi-agent runs can **exhaust Pro**; author recommends **Claude Max ($100–$200 tiers)** for sustained usage.
* Note: **weekly rate limits** are rolling out as of **Aug 28, 2025** due to "inference whales" usage patterns; plan accordingly.

### Tools & Technologies

* **Claude Code** (CLI + subagents; chaining; headless mode; custom slash commands; hooks).
* **GitIngest** (site + CLI) for repo → text conversion.
* **Community subagent packs** for design/coding/marketing roles.
* **Cursor** (referenced for prior checkpointing UX comparison).

## 💡 Key Takeaways & Actionable Insights

### What You Should Do

1. **Design agents first; code second.** Write subagents with single, clear responsibilities and **save their outputs** to `/docs` for downstream agents.
2. **Generate agent prompts from examples** (Claude docs' chaining patterns), then **refine** to your app.
3. **Pin scope outside UX.** Do a top-down feature breakdown (main session/desktop), then have **UX focus strictly on experience** within that scope to prevent feature creep.
4. **Use `Esc` ×2** for checkpoint/branch jumps when a run derails.
5. **Monitor cost & time.** Big parallel runs are expensive—**Max plan** is often necessary; watch for new **weekly limits**.
6. **Leverage headless mode** for CI or scripted workflows; use `--verbose` during prompt development.

### What to Avoid

* **Letting UX agents choose product features** → leads to cluttered UI and scope drift. Keep product decisions separate.
* **Over-agentifying** small apps (e.g., piling on marketing/testing agents) → slower, costlier runs. Start lean; add only where the workflow demonstrably benefits.
* **Relying on chat context alone** for hand-offs → record and version context in MD files.

### Best Practices

* **Project-scoped agents** in `.claude/agents/` under VCS; keep descriptions **action-oriented** (e.g., "Use *proactively* after changes").
* Maintain a **structured docs tree** (`/docs/ux`, `/docs/ui`, `/docs/impl`, `/docs/qa`) so each step reads from stable artifacts.
* Use **verbose** early to observe tool usage and refine commands; once stable, run quiet.
* Consider a repo **`CLAUDE.md`** with common commands, style, and workflow notes to be auto-pulled into context.

## 🔗 Resources & Links

* **Video:** How I ACTUALLY Use Claude Code... My Complete Workflow. ([YouTube](https://www.youtube.com/watch?v=7Sx0o-41r2k))
* **Claude Code Subagents (docs):** definitions, storage, examples, chaining. ([Anthropic](https://docs.anthropic.com/en/docs/claude-code/sub-agents))
* **Claude Code Best Practices (blog):** `CLAUDE.md`, tool allowlists, headless (`-p`), `--verbose`, custom slash commands. ([Anthropic](https://www.anthropic.com/engineering/claude-code-best-practices))
* **CLI Reference:** commands & flags. ([Anthropic](https://docs.anthropic.com/en/docs/claude-code/cli-reference))
* **Headless Mode (SDK docs):** automate CI/builds. ([Anthropic](https://docs.anthropic.com/en/docs/claude-code/sdk/sdk-headless))
* **Common Workflows (docs):** starter playbooks. ([Anthropic](https://docs.anthropic.com/en/docs/claude-code/common-workflows))
* **Pricing:** Pro & Max plans. ([Anthropic](https://www.anthropic.com/pricing))
* **GitIngest (Site / CLI):** repo → LLM text. ([gitingest.com](https://gitingest.com/), [GitHub](https://github.com/coderamp-labs/gitingest))

## 🔗 Related Concepts & Further Learning

* **Hooks & Slash Commands** to automate workflow steps and standardize prompts.
* **MCP tools & allowlists** to extend Claude's tool access safely.
* **GitHub Actions + headless Claude Code** for PR triage, test-fix loops, or lint-like subjective reviews.

## 📝 Personal Notes

This represents a significant shift from single-agent prompting to orchestrated, multi-agent workflows. The emphasis on persistent context via Markdown files is crucial for maintaining quality across complex builds. The checkpoint navigation feature (Esc ×2) addresses one of the major pain points in iterative AI development.

## ⭐ Value Assessment

* **Practical Value:** Very high for building a repeatable, multi-agent dev workflow with Claude Code; includes concrete scaffolding and prompts.
* **Technical Depth:** Medium-high; assumes comfort with CLI, repo structure, and iterative prompt engineering.
* **Relevance:** High if you're adopting **Claude Code subagents** for real projects or migrating from single-agent prompting to **agentic pipelines**.