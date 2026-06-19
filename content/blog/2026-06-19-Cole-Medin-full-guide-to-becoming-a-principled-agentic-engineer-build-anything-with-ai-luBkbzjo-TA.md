+++
title = "FULL Guide to Becoming a Principled Agentic Engineer (Build Anything with AI)"
date = 2026-06-19
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Software engineering--Artificial intelligence","Software project management","Product management","Human-computer interaction"]
tags = ["Claude Code","Large language models","Agentic workflows","PRD","User stories","Acceptance criteria","Jira","Confluence","Atlassian MCP server","Model Context Protocol","MCP.json","GitHub Copilot","OpenAI Codex","Linear","GitHub Issues","GitHub CLI","Speech-to-text","Sub-agents","Context window management","Prompt engineering","Plan.md","Commands and skills","Human-in-the-loop","Continuous improvement","Code review","Testing strategy","Linting","Type checking","Unit testing","End-to-end testing","Browser automation","Git commits","Branching strategy"]

[extra]
excerpt = "A practical, low-bloat system for using coding agents to ship reliable production work by shifting the engineer’s role from “writing code” to “planning + validating.” The video’s core value is a repeatable workflow—ideate → generate structured artifacts (PRD, tickets, plans) → implement in a fresh session → evolve your agent layer—so results become consistent across tickets and teams."
video_url = "https://www.youtube.com/watch?v=luBkbzjo-TA"
video_id = "luBkbzjo-TA"
cover = "https://img.youtube.com/vi/luBkbzjo-TA/maxresdefault.jpg"
+++

## Overview

A practical, low-bloat system for using coding agents to ship reliable production work by shifting the engineer’s role from “writing code” to “planning + validating.” The video’s core value is a repeatable workflow—ideate → generate structured artifacts (PRD, tickets, plans) → implement in a fresh session → evolve your agent layer—so results become consistent across tickets and teams.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
A deliberately “foundational, moldable” alternative to heavyweight open-source agent frameworks: instead of adopting bloated harnesses (BMAD/GSD/etc.), build a thin AI layer (global rules + reusable commands/skills) that fits your existing software development life cycle. The distinctive move is treating prompts as version-controlled operational procedures (PRD/story/plan/implement/prime) and using every ticket as feedback to evolve that AI layer, not just fix code.

### The Core Problem
Teams are overengineering agentic coding with complex frameworks and still getting unreliable outcomes because agents make hidden assumptions and drift from intent. The real bottleneck is not code generation; it’s unclear requirements, lack of structured artifacts, and weak validation—leading to non-repeatable results and “vibe coding” that can’t scale in organizations.

### The Solution Approach
1) Reframe the engineer’s job: delegate code generation to agents; keep humans in the driver’s seat for planning and validation.
2) Phase 1 — Ideation (project-level planning):
   - Start unstructured: do a “brain dump” (often via speech-to-text) describing the app/sprint goals as specifically as possible.
   - Force clarification: explicitly instruct the agent to ask clarifying questions one at a time to reduce assumptions (misalignment is the common failure mode).
   - Convert conversation → PRD via a reusable command that enforces a consistent template (executive summary, mission, target users, in-scope/out-of-scope, etc.).
   - Review the PRD (human-in-the-loop) before downstream automation.
   - Convert PRD → work items (Jira tickets/GitHub issues/Linear tasks) via another command; optionally auto-create them through an MCP integration.
3) Phase 2 — PIV loop (ticket-level execution):
   - Two-layer planning mental model: project plan (PRD/tickets) vs task plan (per-ticket implementation plan).
   - Prime a fresh session: run a “prime” command to load only the right context (ticket + key codebase files/routes + recent git commits as long-term memory).
   - Explore unstructured: discuss solution options; use sub-agents for research to avoid overwhelming the main context window.
   - Structure it: generate a single plan artifact (plan.md) containing decisions, files to touch, ordered task list, and self-validation steps.
   - Implement in a new session: start fresh to reduce bias and keep the agent focused; run an “implement” command that reads the plan and executes it (branching, coding, validation, and admin updates).
   - Human review + manual testing before merge/production.
4) Phase 3 — System evolution (outer loop):
   - When something goes wrong, don’t just patch the code—patch the system that allowed it: update global rules, commands, templates, validation steps, or on-demand context (e.g., Confluence docs).
   - Treat AI layer assets like code: version control, pull requests, code review, team-wide reuse.
Reasoning/mental models emphasized:
- Reliability comes from structured artifacts + reduced assumptions, not from more agents.
- Context is a scarce resource; manage it intentionally (sub-agents, prime scope, fresh sessions).
- Separate “thinking” (planning) from “doing” (implementation) to prevent drift and bias.

### Key Insights
- Misalignment—not broken code—is the dominant failure mode: agents often ‘do a bad job’ because they filled gaps with assumptions; the fix is to force clarifying questions and lock decisions into artifacts before coding.
- Unstructured → structured is the repeatability engine: start with a free-form brain dump, then crystallize into a PRD, then tickets, then a per-ticket plan; each step produces a single source-of-truth document that downstream steps consume.
- Commands/skills are prompts promoted into procedures: if you prompt something more than ~3 times, turn it into a reusable command with arguments so the workflow becomes standardized and shareable across a team.
- Fresh sessions are a focus tool: do planning in one context window, then implement from the plan in a brand-new session to reduce accumulated bias and keep the agent constrained to the agreed approach.
- System evolution is the compounding advantage: every ticket can improve the AI layer (rules/commands/validation/templates), and those improvements save future engineering hours across the whole team.
- Context window size is not a license to stuff everything in: even with ~1M token contexts, models get ‘overwhelmed like people’; sub-agents plus summaries beat dumping raw research into the main thread.
- Use git history as long-term memory: recent commits encode patterns and conventions; loading them during ‘prime’ helps the agent follow existing style/architecture without reinventing approaches.

### Concepts & Definitions
- Principled agentic engineering: delegating code generation while keeping humans responsible for planning and validation, producing reliable and repeatable outcomes rather than ‘vibe coding.’
- AI layer: a project’s reusable agent configuration—global rules (always-on conventions) plus commands/skills (on-demand procedures) that encode the team’s software development life cycle.
- Commands vs skills (framing used here): both are reusable workflows/prompts; commands are invoked like CLI procedures (often with arguments), and skills are reusable playbooks the agent can load to perform standardized tasks.
- PIV loop: a repeatable per-ticket cycle that moves from exploration (unstructured) → plan artifact (structured) → implementation + validation, with human review at the end.
- Two-layer planning: project-level planning (PRD + sprint scope) vs task-level planning (file-level implementation plan for a single ticket).
- System evolution (outer loop): a retroactive improvement cycle where failures trigger updates to rules/templates/validation so the same class of mistake is less likely to recur.

### Technical Details & Implementation
- Toolchain pattern: one system to manage work (Jira/GitHub/Linear) + one system to code with a large language model (Claude Code); everything else is optional.
- Atlassian MCP server integration: configured via an MCP.json file to let the agent create Jira issues, comment with technical notes, update ticket status, and access Confluence pages as context.
- Create-PRD command: generates a markdown PRD from the conversation using a fixed template (executive summary, mission, target users, scope, etc.) and writes it to a specified path via arguments.
- Create-stories command: parses the PRD into individual stories with acceptance criteria, saves markdown artifacts, and (when Jira integration is present) creates issues in a specified project/epic; includes self-checking/validation to ensure phases are fully extracted.
- Prime command: loads external context (e.g., Jira issue via MCP), scans codebase routes/features, and pulls recent git commits to align with existing patterns; accepts a comma-separated list of issue IDs as an argument.
- Sub-agent research workflow: spawn multiple sub-agents to inspect codebase or research implementation options, then return only summaries to the main agent to control context bloat.
- Plan command output: plan.md includes locked decisions, file-by-file change list, ordered task checklist, and explicit self-validation steps (type checking, linting, unit tests; optionally end-to-end via browser automation).
- Implement command: reads plan.md in a fresh session, creates a branch, executes tasks, runs validation, compares implementation to plan to detect drift, and performs admin updates (e.g., Jira comments/status).
- Agent-driven admin work: automate CRUD operations in Jira (create/assign/update/comment) so developers avoid ‘backstage work’ and stay focused on review/validation.
- Practical demo nuance: QR code work initially implemented ‘piping’ without a UI consumer; the workflow then quickly added a demo page—illustrating why human review and artifact checks matter even with structured plans.

### Tools & Technologies
- Claude Code
- Jira
- Atlassian MCP server
- Confluence
- GitHub
- GitHub Issues
- GitHub Copilot
- OpenAI Codex
- Linear
- Jira MCP server
- GitHub CLI
- MCP.json
- Speech-to-text tools
- Agent Browser (browser automation skill/CLI)
- Git (git log/commits as context)
- Confluence MCP/Atlassian MCP integration

### Contrarian Takes & Different Approaches
- You don’t need fancy agent harnesses or specialized multi-agent frameworks to do real work at scale; a thin layer of rules + reusable commands is often more effective and adaptable.
- ‘Vibe coding’ is framed as the wrong goal; the right posture is principled delegation where humans own planning/validation and agents own execution/admin.
- Even with million-token contexts, more context is not better; models can be overwhelmed, so context management (sub-agents, summaries, fresh sessions) is a core engineering skill.
- The highest leverage isn’t just faster code generation—it’s eliminating the administrative and planning overhead (ticket creation, documentation, updates) through agent automation.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Stop adopting bloated agent frameworks by default; instead, build a minimal AI layer (rules + commands) that matches your existing software development life cycle and iterate from there.
- Run a ‘brain dump’ prompt first, then explicitly instruct the agent: ‘Ask me clarifying questions one at a time’ to eliminate assumptions before any planning artifacts are generated.
- Create a PRD from the conversation using a fixed template, then review it manually before generating tickets—don’t chain PRD → tickets without a human checkpoint.
- Turn repeated prompts into commands/skills (rule of thumb: if you’ve typed it 3+ times, promote it) and add arguments so procedures are reusable across projects and tickets.
- Adopt two-layer planning: PRD/tickets for scope, then a per-ticket plan.md that names files to touch, task order, and validation steps.
- Always implement from a plan artifact in a fresh session; treat the plan as the contract and keep the implementation context focused.
- Use sub-agents for research-heavy steps (codebase scanning, web research) and only bring back summaries to protect the main context window.
- After each ticket, run a mini-retro: if something went wrong, update global rules/commands/validation templates so the same failure mode is less likely next time; commit those changes like code.

### What to Avoid
- Overengineering with off-the-shelf agent frameworks can make it hard to adapt to real team conventions; bloat reduces ownership and adoption.
- Skipping the clarifying-question phase causes agents to ‘successfully’ build the wrong thing—misalignment is more common than outright broken code.
- Don’t blindly auto-generate tickets and start coding; review the PRD/tickets first to catch misunderstood answers or missing requirements.
- Avoid stuffing massive research into the main session even if the model supports huge contexts; too much context degrades focus and reasoning quality.
- Don’t implement in the same session where you debated options heavily; accumulated bias and wandering context increases drift from the final decision.
- Letting agents ship directly to production without human review is treated as an anti-pattern for serious work; validation and code review remain essential.
- Agent outputs can look complete while missing a ‘consumer’ integration (e.g., backend piping without UI usage); require explicit validation steps that confirm end-to-end behavior.

### Best Practices
- Encode your organization’s conventions into global rules (style, testing, logging) so the agent follows the same standards every time.
- Standardize artifacts: PRD template, story format with acceptance criteria, and plan.md structure; consistency is what makes delegation safe.
- Separate planning and implementation into different sessions; use the plan artifact as the handoff boundary.
- Automate administrative overhead (ticket creation, updates, comments, assignment) via MCP integrations so humans spend time on high-leverage review and validation.
- Use git history as a pattern library: load recent commits during priming to keep new code consistent with existing architecture.
- Build validation into the plan: lint/typecheck/unit tests (and optionally end-to-end browser automation) before handing back to a human reviewer.
- Treat the AI layer as a first-class codebase: version control, pull requests, and team-wide reuse of commands/skills.

### Personal Stories & Experiences
- Corporate training experience: the workflow is intentionally simplified from a longer (multi-hour) organizational training to focus on foundations that teams can mold rather than replace their entire process.
- Meta-setup lesson: the environment and integrations (e.g., Atlassian MCP server, repo scaffolding) were largely configured by the coding agent itself by pointing it at an existing command/skill repository—showing how setup work can be delegated too.
- Live demo correction: after implementing QR code ‘piping,’ the missing UI consumer was caught and quickly patched with a demo page—used to reinforce the need for human oversight and iterative refinement.

### Metrics & Examples
- Workshop format: condensed from a typical ~4-hour organizational training into a ~1-hour session.
- Clarifying phase can run 20–30+ minutes when done thoroughly.
- Context usage example shown: ~32,000 tokens loaded during priming; overall session mentions exceeding 100,000 tokens; references availability of ~1,000,000 token context with Claude Opus.
- Tool calls example: Atlassian MCP invoked multiple times (e.g., ‘calling Atlassian seven times’) to create/update issues.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=luBkbzjo-TA)

## Value Assessment

- **Practical Value:** requires setup
- **Uniqueness Factor:** fresh perspective
