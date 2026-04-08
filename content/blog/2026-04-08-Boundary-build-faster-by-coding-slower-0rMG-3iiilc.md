+++
title = "Build Faster by Coding Slower"
date = 2026-04-08
draft = false

[taxonomies]
author = ["Boundary"]
categories = ["Software engineering--Artificial intelligence","Programming languages--Testing","Software testing","Compilers (Computer programs)"]
tags = ["Agentic coding","Claude","Long context prompting","Design documents","Specification-driven development","Snapshot testing","Regression testing","Test case generation","Production data testing","Aggregation metrics","Scenario grouping","Assertion library design","Diff rendering","BAML","Rust","Closures (Computer science)","Lambda expressions","Compiler development","Avoiding magic globals","Test registries","Prompt steering","Restart heuristic"]

[extra]
excerpt = "The video argues that the fastest way to ship high-quality code with coding agents is to “code slower” up front: invest heavily in design docs, explicit decision-making, and test/eval scaffolding so implementation can be close to a one-shot. The distinctive workflow treats long-context models as partners for exploring options and reflecting intent back, while the human retains the role of decision-maker and uses tests (including snapshot outputs) as the final bug-finding microscope."
video_url = "https://www.youtube.com/watch?v=0rMG-3iiilc"
video_id = "0rMG-3iiilc"
cover = "https://img.youtube.com/vi/0rMG-3iiilc/maxresdefault.jpg"
+++

## Overview

The video argues that the fastest way to ship high-quality code with coding agents is to “code slower” up front: invest heavily in design docs, explicit decision-making, and test/eval scaffolding so implementation can be close to a one-shot. The distinctive workflow treats long-context models as partners for exploring options and reflecting intent back, while the human retains the role of decision-maker and uses tests (including snapshot outputs) as the final bug-finding microscope.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
A deliberate “design-first, one-shot implementation” workflow for agentic coding: push as much ambiguity resolution as possible into a markdown design/spec phase where the model dumps its reasoning, then convert that into a tight ticket that can produce 5,000–10,000+ line changes with minimal iteration. The contrarian twist is operational: if the implementation is materially off-course (≈30% wrong), it is faster to delete the branch and restart from a better spec than to keep steering a drifting model.

### The Core Problem
Coding agents can generate lots of code quickly, but they also introduce “slop”: hidden magic, unexamined decisions, brittle tests, and long steering loops once the model commits to a wrong architecture. The problem is how to reliably ship large, high-quality changes (compiler/language features, testing frameworks) without drowning in incremental fixes and misalignment.

### The Solution Approach
1) Start with a markdown design doc that forces explicitness: syntax, package surface area, invariants, and examples—not just implementation notes.
2) Use long-context prompting to have the model enumerate options and patterns from the codebase; keep prompts small and surgical, but require the model to “dump what it’s thinking” at a high level so you can perform ‘brain surgery’ (re-steer) before code exists.
3) Do not outsource decisions: treat the model as a generator of alternatives and codebase recall; the human chooses tradeoffs.
4) Convert the design into an executable ticket: clear acceptance criteria, non-goals, and concrete API examples.
5) Implement with an expectation of near one-shot after design; if the model starts introducing ‘magic’ or architectural drift, update the design and restart rather than patch endlessly.
6) Validate via richer-than-boolean testing: scenario grouping, aggregation metrics, production-data-driven dynamic test cases.
7) Use snapshot tests that print serialized outputs and internal representations; manually read snapshots to catch subtle bugs.
8) Apply a restart heuristic: if ~5% wrong, iterate; if ~30% wrong, nuke the branch and redo the design/ticket because tokens are cheaper than human steering time.

### Key Insights
- Markdown design docs are not documentation—they are an alignment instrument: forcing the model to externalize its reasoning creates multiple ‘re-steer points’ before it hardens into code.
- High-quality evaluation requires more than pass/fail asserts: you need scenario taxonomies (grouping), aggregation metrics, and the ability to generate tests dynamically from real production datasets.
- Snapshot testing is used as a ‘bug microscope’: printing serialized outputs and internal model representations lets a human spot inconsistencies that ordinary asserts miss, especially in compilers/language tooling.
- A practical steering heuristic: if the implementation is slightly off (≈5%), riff with the model; if it’s substantially off (≈30%), restarting from a corrected spec is faster than incremental correction because the model’s trajectory becomes expensive to re-steer.
- Avoid ‘magic’ language features (implicit globals/singletons, injected test registries) because they break discoverability (can’t command-click to source) and violate the language’s own rules, making both humans and agents less effective.
- Prefer assertion APIs that capture operands (equals/contains with structured diff) over boolean asserts; diffs are more agent-friendly and reduce debugging bandwidth by showing exactly what changed (e.g., array elements 5 and 6 differ).

### Concepts & Definitions
- “Do not outsource the thinking”: models should propose options and recall patterns, but letting them make architectural decisions is ‘rolling the dice’ because they optimize for helpfulness, not correctness in your system.
- “Snapshot test” (as framed here): a test that writes the output of serialization and internal data-model representations to text files so you can review exact structures and catch subtle regressions.
- “Coding slower to build faster”: spending more time on design/spec alignment and eval scaffolding reduces downstream iteration and makes large PRs feasible with near one-shot implementation.
- “Magic” (language/tooling): behavior that is implicitly injected (e.g., global variables/singletons in a test runner) rather than expressed as normal language constructs; it harms understandability and tooling navigation.

### Technical Details & Implementation
- Testing feature criteria called out explicitly: (1) break tests into groups of scenarios, (2) use aggregation metrics rather than only boolean pass/fail, (3) load data from production databases/datasets to dynamically define test cases.
- Workflow pattern: long-context for broad design discussion + short, minimal prompts for incremental clarifications; require the model to summarize/describe back large changes because the human is not reading every line.
- Anti-magic implementation preference: implement testing constructs as regular language/package functions rather than Rust-only intrinsics or injected singletons; keep behavior consistent with the rest of the language rules.
- Assertion design choice: TypeScript-style assertion functions (e.g., equals/contains) rather than Python-style `assert expr`; enables automatic diff rendering and better control over evaluation/logging semantics.
- Quality loop after implementation: read test cases, inspect snapshot outputs (serialization + internal representations), fix bugs iteratively; foundational bugs should be rare if design was done well.
- Large-change operating mode: 5,000+ LOC tasks follow the same pipeline; example mentioned of ~16,000 lines for a closures/lambdas feature in BAML.

### Tools & Technologies
- Claude (used for long-context design discussion, option enumeration, and implementation generation)
- Rust (implementation language referenced for compiler/testing package internals)
- BAML (the programming language being developed)
- Production databases/datasets (as sources for dynamic test case generation)
- Custom script to pull feedback/comments from language models/coding agents and summarize them for PR review

### Contrarian Takes & Different Approaches
- Speed comes from slowing down: investing heavily in design/spec and evals beats rapid iterative coding when using coding agents.
- Restarting is not wasteful; for large misalignment it is the optimal strategy because model steering costs more than regeneration.
- Avoiding ‘magic’ is worth the friction: even if implicit registries/globals are convenient, they degrade tooling ergonomics and long-term comprehension.
- Boolean `assert` is a weak default; assertion APIs should be designed around diffs and semantic operators to serve both humans and agentic debugging.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Before writing code, create a markdown design doc that includes concrete language/API examples (not just implementation notes) and explicitly lists decisions and non-goals.
- Prompt the model to enumerate options and then to restate its intended architecture at a high level; use that as a checkpoint to re-steer early (‘brain surgery’) rather than debugging later.
- Adopt the 5%/30% rule: minor drift → iterate; major drift → delete the branch, rewrite the ticket/spec, and regenerate—optimize for total time, not sunk cost.
- Build tests as an evaluation system: define scenario groups, compute aggregate metrics, and generate cases from real production data to avoid toy coverage.
- Add snapshot tests that print serialized outputs and internal representations; schedule time to read snapshots manually—treat it as a first-class debugging tool.
- Design assertion APIs to produce structured diffs by default (equals/contains) so both humans and agents can localize failures quickly.

### What to Avoid
- Letting the model make key decisions leads to architecture roulette; models try to be helpful and may choose ‘magic’ shortcuts that don’t fit your language/tooling philosophy.
- Over-relying on boolean asserts hides useful failure information; you end up manually adding logging/diffing after the fact.
- Continuing to steer a model after it has committed to a wrong path can be slower than restarting; sunk-cost iteration creates long context chains and compounding misalignment.
- Introducing implicit globals/singletons in testing frameworks creates ‘invisible dependencies’ and harms discoverability and maintainability (the JavaScript test-runner ‘describe without import’ problem).

### Best Practices
- Treat design docs as executable alignment artifacts: force the model to expose reasoning, list patterns to follow, and provide multiple checkpoints for human correction.
- Keep language features consistent with the language’s normal rules; avoid special-case magic even if it’s easier to implement in the compiler/runtime.
- Use snapshot outputs as a regression contract for compilers/serializers: store text representations of internal structures and review them during development.
- When changes feel large, ask the model to explain complexity and structure back to you; use that explanation to decide whether to proceed, refactor, or restart.
- Prefer assertion libraries that can render diffs automatically; make the default failure mode informative and agent-consumable.

### Personal Stories & Experiences
- After completing implementations, the workflow involves reading snapshot outputs and repeatedly discovering bugs; each bug triggers fixes, but foundational bugs are rare when the upfront design was strong.
- When foundational issues do appear, the ‘absurd’ but effective move is to nuke the branch and restart from scratch with a clearer ticket—learned as a time-saving tactic rather than a failure.
- Experience shipping multiple 10,000+ line pull requests by converting design discussions into tickets, enabling near one-shot implementation.
- A concrete scale example: ~16,000 lines written for a closures/lambdas feature in BAML, used to illustrate the viability of the approach.

### Metrics & Examples
- “Multiple 10,000+ line PRs” achieved using the design-to-ticket workflow.
- ~16,000 lines of code mentioned for implementing closures/lambdas in BAML.
- Heuristic thresholds: ~5% wrong → iterate; ~30% wrong → restart from scratch.
- Mention of sending ~15 messages in a steering thread before deciding on next steps (illustrating context-chain cost).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=0rMG-3iiilc)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** contrarian wisdom
