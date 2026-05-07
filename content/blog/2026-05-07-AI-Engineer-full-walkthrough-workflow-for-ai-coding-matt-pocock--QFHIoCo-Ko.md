+++
title = "Full Walkthrough: Workflow for AI Coding — Matt Pocock"
date = 2026-05-07
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Software engineering--Artificial intelligence","Software architecture","Software testing","Agile software development","Human-computer interaction"]
tags = ["Claude Code","Anthropic Claude Sonnet","Anthropic Claude Opus","prompt engineering","context window","token budgeting","smart zone","dumb zone","compacting","sub-agents","Kanban","directed acyclic graph","vertical slice","traceable bullets","product requirements document","user stories","test-driven development","red-green-refactor","TypeScript","Node.js","npm","Vitest","Docker sandbox","Git worktree","GitHub Issues","code review","quality assurance","John Ousterhout","deep modules","shallow modules","Frederick P. Brooks","The Pragmatic Programmer","Martin Fowler","refactoring","Sandcastle"]

[extra]
excerpt = "A practical end-to-end workflow for using large language models as coding agents without losing software engineering rigor: align first, then delegate implementation, then aggressively QA. The key idea is to design work so it stays in the model’s “smart zone,” uses strong feedback loops (tests/types), and produces reviewable vertical slices rather than big horizontal phases."
video_url = "https://www.youtube.com/watch?v=-QFHIoCo-Ko"
video_id = "-QFHIoCo-Ko"
cover = "https://img.youtube.com/vi/-QFHIoCo-Ko/maxresdefault.jpg"
+++

## Overview

A practical end-to-end workflow for using large language models as coding agents without losing software engineering rigor: align first, then delegate implementation, then aggressively QA. The key idea is to design work so it stays in the model’s “smart zone,” uses strong feedback loops (tests/types), and produces reviewable vertical slices rather than big horizontal phases.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Treat large language models as powerful but constrained collaborators: they get “dumber” as context grows and they effectively “reset” like Memento—so optimize for short, repeatable sessions with minimal system prompts. The distinctive methodology is a human-in-the-loop alignment phase (“Grill Me” to build a shared design concept) followed by AFK implementation via a Kanban-style DAG of vertical-slice issues, enforced by test-driven development and automated feedback loops.

### The Core Problem
Teams are frustrated because coding agents degrade over long contexts, forget decisions, and encourage a misleading “specifications-to-code compiler” workflow where developers stop engaging with the code. This leads to dumb-zone behavior, poor architecture, weak tests, doc rot, and ultimately low-quality output that is expensive to review and hard to trust.

### The Solution Approach
1) Model constraints first: assume a “smart zone” early in a session and a “dumb zone” after sustained context growth; keep the system prompt tiny to avoid starting dumb.
2) Start every feature with alignment, not a plan: invoke a short meta-prompt (“Grill Me”) that interviews you one question at a time, walking decision-tree branches and offering recommended answers. Goal: reach a shared design concept (Frederick P. Brooks framing) rather than produce a verbose plan.
3) Convert alignment into a destination document: generate a PRD that summarizes problem, solution, user stories, implementation decisions, and testing decisions. Keep code in mind by explicitly listing proposed modules to modify—this is the bridge from product intent to code reality.
4) Split the PRD into a journey: generate a Kanban board of independently grabbable issues with blocking relationships (a DAG), explicitly favoring vertical slices (traceable bullets) over horizontal layers. Review this split quickly because it determines feedback speed and parallelizability.
5) Execute implementation AFK: run an agent loop (“Ralph”) that selects the next AFK-eligible issue, explores the repo, implements with TDD (red-green-refactor), runs feedback loops (tests + typecheck), and produces a reviewable summary/commit.
6) QA as the taste/quality gate: manual QA is where human judgment and product taste re-enter; QA findings become new issues added back onto the Kanban board.
7) Improve the codebase to improve the agent: refactor toward deep modules (John Ousterhout) with small interfaces and rich internals so tests can wrap meaningful behavior; better feedback loops raise the ceiling of agent performance.
8) Scale up with parallelization: once issues are a DAG, run multiple sandboxes/agents in parallel, then run an automated review and a merge agent to integrate branches and fix conflicts/tests.

### Key Insights
- Context length is not a free lunch: regardless of 200K vs 1M context windows, performance degrades after sustained accumulation; the practical “smart zone” marker given is ~100K tokens, after which decisions get noticeably worse.
- Alignment beats planning: the real asset is a shared design concept with the model, not a multi-phase plan; relentless questioning prevents the model from prematurely ‘poofing’ a plan and surfaces hidden requirements (e.g., retroactive backfill).
- Vertical slices are the antidote to agent ‘horizontal coding’: agents naturally implement layer-by-layer (schema → API → UI), which delays end-to-end feedback; traceable bullets force integrated, testable increments that expose errors earlier and reduce blind coding.
- Feedback loops define the ceiling of agent quality: without strong automated tests/type checks, the agent is coding blind; improving testability and module boundaries directly improves agent output.
- Documentation can harm you via doc rot: keeping old PRDs in-repo can mislead agents later when code diverges; prefer closing issues (or otherwise marking docs as historical) rather than leaving stale specs in the working tree.
- Use push vs pull for standards: let implementers pull conventions/skills when needed, but push coding standards into automated reviewers so they can enforce consistency against produced diffs.
- Sub-agents are a token-efficiency hack: delegate exploration to isolated-context sub-agents that burn tokens privately and return summaries, keeping the main session in the smart zone.

### Concepts & Definitions
- Smart zone / dumb zone: early-session context where attention relationships are least strained vs later-session degradation as token interactions scale quadratically; long contexts become error-prone even if the window is huge.
- Memento model of sessions: clearing context returns you to a stable base state (system prompt); compacting creates a summarized ‘history’ but can accumulate sediment and drift—prefer resettable workflows.
- Compacting: compressing a long conversation into a shorter summary to keep going; framed as popular but disliked here because it changes state and can introduce drift.
- Sub-agent: a delegated secondary model call with an isolated context window that explores/does work and reports a summary back to the parent agent.
- Ralph Wiggum practice: specify the destination (e.g., PRD) and repeatedly ask the agent to make small changes toward it; used as a loop concept but augmented with more structure (Kanban + vertical slices).
- Traceable bullets / vertical slices: thin end-to-end increments across layers that provide fast feedback, analogous to tracer rounds that show where you’re aiming.
- Human-in-the-loop vs AFK tasks: planning/alignment requires active human decisions; implementation can be delegated away-from-keyboard when tasks are well-scoped and feedback loops exist.
- Deep modules vs shallow modules (Ousterhout): deep modules expose small interfaces with substantial internal functionality (easy to test at boundaries); shallow modules fragment behavior across many tiny pieces, creating dependency tangles and poor test boundaries.

### Technical Details & Implementation
- Claude Code used as the interactive coding agent; token usage is monitored via a visible status line and treated as essential observability for staying in the smart zone.
- Custom ‘skills’ invoked via slash commands (e.g., /grill-me, /write-a-prd, PRD-to-issues, improve-codebase-architecture) stored in-repo as short prompt templates.
- Grill Me skill prompt: ‘Interview me relentlessly… walk down each branch of the decision tree… ask questions one at a time… provide recommended answer.’ Used to prevent premature planning and force requirement discovery.
- PRD template includes: problem statements, solution, user stories, implementation decisions, testing decisions, and out-of-scope items to preserve negative decisions/rationales.
- PRD-to-issues step explicitly requests ‘independently grabbable issues’ using vertical slices/traceable bullets and blocking relationships to enable parallel execution.
- AFK agent runner (once.sh): bash script concatenates local markdown issues into a variable, includes last five commits for context, then runs Claude Code with permission mode ‘accept edits’; designed as a single iteration of a larger loop.
- Sandboxing: AFK runs are executed in a Docker sandbox to isolate changes and reduce risk while allowing automated loops.
- TDD enforcement: agent writes a failing test first (red), then implements to pass (green), then refactors; reduces test-cheating and improves reliability of generated tests.
- Feedback loops executed by the agent: npm test and npm typecheck (TypeScript) are run; type errors are fixed before completion.
- Kanban DAG enables parallelization: multiple agents can work on non-blocked issues simultaneously, then merge later.
- Sandcastle (TypeScript library) described: creates worktrees/branches, runs prompts in Docker sandboxes, supports parallel issue execution, automated review (often using a stronger model), and a merge agent that integrates branches and fixes conflicts/tests.
- Model selection strategy: Sonnet for implementation, Opus for review (review is treated as higher-leverage/needs more capability).

### Tools & Technologies
- Claude Code
- Anthropic Claude (Sonnet, Opus)
- HumanLayer (Dex Hardy’s smart/dumb zone framing)
- Slido (async Q&A voting)
- GitHub Issues (as PRD/issue store)
- Docker (sandbox execution)
- Bash scripting
- Node.js / npm
- TypeScript
- Vitest (via npx vitest)
- SQLite (mentioned via migration/table error)
- TLDraw (infinite canvas style presentation)
- Sandcastle (custom agent orchestration library)

### Contrarian Takes & Different Approaches
- ‘More context’ is not the main win for coding: 1M-token windows mostly expand the dumb zone; retrieval improves, but coding quality still hinges on staying in the smart zone.
- Compacting is overrated: many developers love it, but resetting context is preferable because it returns to a known-good base state and avoids drift.
- Do not obsessively read/review PRDs generated after a good grilling session: if alignment is achieved, you’re mostly testing summarization ability, not product correctness.
- Documentation should often be deleted/closed rather than preserved in-repo due to doc rot and negative influence on future agent behavior.
- Front-end agent automation is not ready for ‘tasteful’ UI in mature systems; prototypes are useful, but humans must choose and refine.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Add token observability to every coding session and treat ~100K tokens as a practical smart-zone limit; reset context instead of dragging long threads forward.
- Start features with a ‘Grill Me’ interview prompt that asks one question at a time and forces decisions (retroactivity, point sources, UI placement, etc.) before any implementation plan.
- Write a PRD as a destination artifact, but explicitly include ‘proposed modules to modify’ so code structure stays central and you avoid specs-to-code detachment.
- Convert PRDs into a Kanban DAG of vertical-slice issues; ensure the first issue produces an end-to-end visible result (e.g., points on dashboard) rather than only schema/service groundwork.
- Classify tasks as human-in-the-loop (alignment) vs AFK (implementation) and only delegate AFK work once issues are small, testable, and independently grabbable.
- Force TDD in agent prompts (red-green-refactor) and require running tests + type checks before the agent can declare completion.
- Use Docker sandboxes/worktrees for AFK agents so they can run freely without risking the main working directory; merge only after review/QA.
- Refactor toward deep modules with clear interfaces and boundary tests; better module depth makes both humans and agents faster and improves test quality.

### What to Avoid
- Specs-to-code ‘compiler’ workflow fails: editing specs while ignoring code leads to loss of control; the code is the battleground and must stay in view.
- Overlong system prompts (e.g., 250K tokens) push you into the dumb zone immediately; keep always-on context minimal.
- Compacting can create ‘sediment’ and drift: summaries may distort decisions and accumulate errors; prefer clearing context and relying on stable artifacts (PRD/issues).
- Horizontal slicing (schema first, UI last) delays feedback and makes agents code blind; it increases rework when integration finally happens.
- Weak feedback loops guarantee weak agent output; if the agent is producing garbage, the ceiling is often your tests/types, not the model.
- AI-generated documentation left in-repo can rot and mislead future agents; stale PRDs become a hidden source of incorrect assumptions.
- Front-end automation is still brittle: multimodal/browser-agent setups often fail to produce tasteful UI in mature codebases; use prototypes for options, then bring humans back in.
- Expect more code review load: delegating implementation increases review/QA burden; there is no solved answer yet for reducing this overhead.

### Best Practices
- Keep tasks small enough to stay in the smart zone; treat long-running threads as a reliability hazard.
- Use relentless interviewing to reach shared understanding (design concept) before planning; recommendations from the model can accelerate decision-making but require human acceptance.
- Maintain a module map during planning: explicitly name which services/routes/files will change; this anchors the agent and prevents architecture drift.
- Prefer Kanban/DAG planning over sequential phase plans to enable parallelization and reduce idle time.
- Enforce red-green-refactor with automated test/type feedback loops; require passing checks as the definition of ‘done’ for AFK tasks.
- Design deep modules with small interfaces and test at module boundaries; delegate internals to agents while humans own interfaces and behavior contracts.
- Use push/pull control: keep standards available for implementers to pull, but push standards into reviewers for consistent enforcement.
- Treat QA as the taste gate and as a generator of new issues; continuously feed discoveries back into the backlog.

### Personal Stories & Experiences
- Shift in approach: used multi-phase plans until December, then moved to loop-based execution with stronger structure (grilling → PRD → Kanban DAG → AFK).
- Tried the specs-to-code approach (‘vibe coding by another name’) and found it ‘sucks’ because it disconnects developers from the codebase.
- Recorded a Claude Code course on a 200K context window; when 1M launched, concluded it mostly adds more ‘dumb zone’ rather than solving coding quality.
- Built/uses a personal ‘work repo’ with hundreds of closed issues (744 mentioned) as a living PRD/implementation log; prefers closing issues over keeping docs in-tree.
- Created Sandcastle after dissatisfaction with existing AFK agent runners; uses it to sandbox, parallelize, review, and merge agent work.
- Noted practical pain: as delegation increases, personal familiarity with the codebase decreases; mitigates by owning module interfaces while delegating internals.

### Metrics & Examples
- Smart zone heuristic: performance starts degrading around ~40% of context; practical marker given as ~100K tokens even with 200K–1M windows.
- Sub-agent exploration example: ~93.7K tokens spent on Opus by an explore sub-agent while the main session token usage stayed relatively low.
- Grilling sessions can run 40, 80, even 100 questions; can take about an hour of human-in-the-loop alignment.
- Example session token usage: ~25K tokens accumulated before converting to PRD.
- GitHub work repo example: 744 closed issues used as PRDs/implementation records; claimed ~1,000 videos recorded in that repo.
- Test suite size after agent work: 284 tests mentioned in the repo.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=-QFHIoCo-Ko)

## Value Assessment

- **Practical Value:** requires setup
- **Uniqueness Factor:** fresh perspective
