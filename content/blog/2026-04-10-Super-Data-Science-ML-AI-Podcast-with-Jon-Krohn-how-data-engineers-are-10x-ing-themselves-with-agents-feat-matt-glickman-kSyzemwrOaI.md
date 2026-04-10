+++
title = "How Data Engineers Are “10x’ing” Themselves With Agents, feat. Matt Glickman"
date = 2026-04-10
draft = false

[taxonomies]
author = ["Super Data Science: ML & AI Podcast with Jon Krohn"]
categories = ["Software engineering--Artificial intelligence","Data engineering","Knowledge representation (Information theory)","Business enterprises--Technological innovations","Cloud computing"]
tags = ["Genesis Computing","agents","agentic workflows","data pipelines","data engineering automation","living context graph","knowledge graph","data lineage","semantic search","source-to-target mapping","runbooks","blueprints","confidence scoring","confidence-gated escalation","reasoning models","verification harness","artifacts","pull request","code review","CI/CD","on-premises deployment","enterprise security boundary","Snowflake","decoupled compute and storage","elasticity","cloud migration","Amazon EC2","private cloud","function calling","tool use","vibe coding","agent orchestration","spinning plates","finance","healthcare","media industry","content leakage","institutional knowledge","M&A valuation"]

[extra]
excerpt = "The episode argues that February 2026 was an \"event horizon\" where frontier models became capable of reliably executing long, multi-step data engineering workflows—changing enterprise operating models permanently. Matt Glickman’s distinctive take is that the real unlock isn’t just better models; it’s combining (1) a living context graph of an organization’s data/code/docs and (2) a verification harness that forces agents to prove work with artifacts, escalating only when confidence is low."
video_url = "https://www.youtube.com/watch?v=kSyzemwrOaI"
video_id = "kSyzemwrOaI"
cover = "https://img.youtube.com/vi/kSyzemwrOaI/maxresdefault.jpg"
+++

## Overview

The episode argues that February 2026 was an "event horizon" where frontier models became capable of reliably executing long, multi-step data engineering workflows—changing enterprise operating models permanently. Matt Glickman’s distinctive take is that the real unlock isn’t just better models; it’s combining (1) a living context graph of an organization’s data/code/docs and (2) a verification harness that forces agents to prove work with artifacts, escalating only when confidence is low.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
A data-engineering-first agent platform built around two compounding assets: (1) a "living context graph" created by crawling an enterprise’s internal universe (databases, code repos, docs, spreadsheets, SaaS tools) and (2) a guardrailed execution harness ("blueprints") that makes agents follow runbooks, produce evidence, and escalate on low confidence. The contrarian inversion is moving from "copilot" (human drives step-by-step) to "AI-first" delegation (agents run autonomously; humans answer only the hard unknowns—and those answers are memorialized so the system never asks twice).

### The Core Problem
Enterprise data engineering is a chronic bottleneck: pipelines are complex, under-documented, high-attrition, and only noticed when they fail. The hardest part isn’t generic domain knowledge (models increasingly have that), but organization-specific semantics and tribal logic (how this firm computes metrics, why a transformation exists, what breaks next Thursday when a weird feed changes) that usually lives in people’s heads and disappears when they leave.

### The Solution Approach
1) Treat adoption like onboarding a new employee: connect the system to internal databases, code repositories, document stores, and relevant tools with read credentials.
2) Build a living context graph during onboarding by crawling and extracting relationships across code→tables, APIs→tables, spreadsheets→definitions, dashboards→queries, etc. The graph is not the product; it is the substrate that makes agents effective.
3) Execute work via domain-specific runbooks ("blueprints"): e.g., extraction blueprint = extract → validate → confirm → create monitors; semantic modeling blueprint = field-by-field source-to-target mapping with tie-outs.
4) Invert the copilot loop: agents work for hours autonomously on a mission; they interrupt humans only when confidence is low or a key decision is missing.
5) Force correctness with proof: require artifacts (test outputs, report run logs, PRs, CI evidence). Use a second agent/reviewer to verify completeness (e.g., detect that only 10,000/30,000 reports were actually run).
6) Memorialize every human answer and escalation outcome into the organization-owned knowledge base so future runs compound rather than repeat questions.
7) Deploy inside the customer’s environment (not a shared SaaS) so accumulated knowledge remains the enterprise’s asset and security/telemetry concerns don’t block adoption.

### Key Insights
- "Big data" was often a misdiagnosis; the real scaling pain was a "big user problem"—too many teams needing to operate on one consistent copy of data. Snowflake’s decoupled compute/storage solved that; agents + context graphs aim to solve the analogous "big workflow" problem in data engineering.
- The missing ingredient for enterprise agents is not general model intelligence but organization-specific context that is usually not written down. Building a context graph by crawling internal systems turns tribal knowledge into a navigable substrate.
- Correctness beats novelty in enterprise: consumer products can tolerate creative gap-filling; enterprise data workflows require grounded truth, auditability, and repeatable verification.
- Agents inherit a "laziness" analogue: they may do the minimum to appear done (e.g., sample tests instead of exhaustive runs). The fix is a harness that demands evidence and uses independent verification agents.
- Confidence-aware escalation is a practical breakthrough from reasoning models: repeatedly ask "how confident are you" and require the model to name what it is unsure about; then either retry or escalate precisely.
- AI-first is a forcing function: start projects with "why can’t an agent do this?" rather than "is this an AI use case?"—especially for greenfield firms (e.g., new hedge funds) that can design processes around agents before hiring.
- Institutional knowledge becomes a balance-sheet asset: once captured in a living context graph, it reduces key-person risk and could affect valuation/M&A multiples similarly to how recurring SaaS revenue changes valuation dynamics.

### Concepts & Definitions
- "February 2026 event horizon": the moment frontier models crossed a threshold in handling long, multi-step, high-context workflows (especially in software/data engineering), making the shift irreversible and accelerating enterprise bifurcation.
- "Big user problem": scaling challenge driven by many users/teams needing to run the business on a single consistent data copy—more about concurrency and organizational adoption than raw data volume.
- "Living context graph": a continuously built graph of relationships across an enterprise’s data universe (tables, code, APIs, docs, spreadsheets, dashboards, communications) that agents can navigate to understand what exists, how it’s used, and how changes propagate.
- "Blueprints": domain-specific guardrails/runbooks that constrain agent behavior into auditable steps (extract/validate/monitor; source-to-target mapping; testing and tie-outs) rather than free-form generation.
- "AI-first company": an organization that begins each initiative by assuming agents should do the work unless proven otherwise, using humans primarily for steering, approvals, and resolving true unknowns.
- "Spinning plates": the skill of orchestrating many agents in parallel (a conductor role), managing context switching and delegation at scale.

### Technical Details & Implementation
- Architecture pattern: deploy the agent platform inside the customer’s environment (customer-controlled security boundary) rather than a multi-tenant SaaS; the system self-manages via an embedded "AI engineer" that helps install/operate it.
- Onboarding workflow: connect to databases, code repositories, document repositories, and SaaS/on-prem sources; run an internal crawler to build a relationship graph (code references tables; APIs touch tables; reports depend on models).
- Agent execution loop: mission definition → graph navigation to locate relevant sources/precedents → generate/modify pipelines → run tests in development → produce code review + pull request → integrate with existing CI/CD pipeline.
- Verification harness: require artifacts (logs, outputs, test results) and implement reviewer-agent checks for completeness (e.g., validate that all 30,000 reports were executed, not a subset).
- Semantic search over graph: agents perform semantically similar lookups to find existing fields/reports/pipelines that approximate the requested metric/column, then trace lineage back to sources and propagate forward.
- Operational guardrail: agents behave like "another developer" subject to standard enterprise controls (dev environments, PR review, CI/CD), reducing perceived risk versus uncontrolled autonomous execution.

### Tools & Technologies
- Snowflake (cloud data platform; decoupled compute/storage as scaling solution)
- Amazon EC2 (provisioning example; contrast with slow internal private cloud)
- CI/CD pipelines (agents submit PRs into existing workflows)
- Git repositories / code repositories (crawled for context; PR-based delivery)
- Document repositories (read for tribal context)
- Dashboards / reporting systems (example: 30,000 reports to test during migration)
- Frontier reasoning models (confidence/self-reflection capability)
- Function calling / tool use (early GPT-4 era capability cited as precursor to agents)
- Zoom / Google Meet (remote work contrast; in-person enterprise selling)

### Contrarian Takes & Different Approaches
- The industry over-focused on vertical scaling (bigger models) while the practical enterprise unlock is horizontal compounding: context + verification + knowledge capture that makes agents reliably autonomous in real organizations.
- Humans are not the gold standard for accuracy; they make constant mistakes that are socially excused. Holding models to a higher bar is reasonable, but it should be done with proof-based harnesses rather than vibes.
- Finance and healthcare were late cloud adopters but are early Artificial intelligence adopters; media/gaming were early cloud adopters but are now slower on Artificial intelligence due to content leakage fears.
- Most enterprises shouldn’t build their own agent platforms; they should buy outcomes. Internal builds are structurally disadvantaged versus revenue-driven vendors that iterate faster.
- The real labor impact is not mass firing but a collapse in junior hiring; throughput roles get replaced by scalable agents, while a smaller number of "conductors" may be hired to orchestrate many agents.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Adopt an "AI-first" intake question for every backlog item: "Why can’t an agent do this work?" Use it as a forcing function to redesign processes, not just automate steps.
- When using agents for data work, never accept "looks good" outputs—require artifacts: executed test logs, report run outputs, lineage diffs, and PRs. Add a second verifier agent to audit completeness.
- Start by building (or buying) a context acquisition layer: connect agents to databases, repos, and docs and let them crawl to form a context graph; don’t rely on humans to manually gather context each time.
- Implement confidence-gated escalation: at each step ask the agent to state confidence and identify the single biggest uncertainty; only then involve a human, and store the resolution for reuse.
- For migrations, use agents to run exhaustive validation (e.g., all reports, all fields) instead of sampling; treat token spend as cheaper than business-user testing and post-migration surprises.
- If you’re a new organization (e.g., greenfield fund), delay hiring by first mapping what 10–20 agents can do; hire selectively for "agent conductor" roles rather than traditional junior throughput roles.

### What to Avoid
- "Single-shot YOLO" agent usage: throwing tokens at a task without guardrails leads to plausible but unverified outputs; enterprise workflows need structured runbooks and proof.
- Agent "laziness"/minimum-effort behavior: models may skip exhaustive checks unless forced; sampling 30,000 reports is an attractive failure mode unless you demand evidence.
- Context gathering as hidden tax: if humans must manually assemble docs/repos/tables for every task, you’ve shifted work rather than removed it; automate context acquisition via crawling/graphing.
- Building internal platforms for cost instead of buying revenue-driven products: internal tooling often lags because it lacks the economic pressure that optimizes commercial systems (analogy: EC2 perfection vs slow internal provisioning).
- Over-trusting novelty: consumer-style creativity is a liability in regulated enterprise settings; correctness and auditability must dominate design.

### Best Practices
- Deploy agent systems inside the enterprise security boundary when selling to regulated industries; make the accumulated knowledge explicitly the customer’s asset to reduce adoption friction.
- Use existing software engineering controls (dev environments, PRs, CI/CD) as the safety envelope for agents; position agents as "another developer" rather than a rogue autonomous system.
- Codify domain runbooks as reusable "blueprints" so agents follow deterministic steps (extract→validate→monitor; source-to-target mapping with tie-outs) instead of ad hoc prompting.
- Make escalation outcomes durable: every time a human answers a question, memorialize it so the system compounds knowledge and stops re-asking.
- Treat context graphs as a means, not an end: build them to improve task execution speed/correctness, not as a standalone documentation project.

### Personal Stories & Experiences
- Goldman Sachs crisis-era platform success: a consolidated data platform helped quants manage risk during the financial crisis, but success created demand to run the whole firm on one database—revealing the "big user problem" and scaling limits of pre-cloud architectures.
- Snowflake pitch at Goldman (2013/2014): sitting next to founder Benoît Dageville, hearing the decouple compute/storage thesis; skepticism about cloud adoption was common, but the prediction that Goldman would be in the cloud before on-prem Snowflake landed proved correct—triggering Matt’s jump to Snowflake.
- Bi-coastal Snowflake years: weekly Bay Area engineering + New York customer cadence; highlights New York’s enterprise concentration and the importance of in-person enterprise building post-COVID.
- Private cloud failure anecdote: a quant edited a provisioning form and accidentally took out half of Goldman; used to illustrate why revenue-driven platforms (EC2) get optimized to near-perfection while internal cost-center tooling accumulates risk and slowness.
- Design partner attrition moment: data engineering champion’s last day at a private equity firm—he was relieved; successor looked exhausted trying to absorb undocumented pipeline knowledge—crystallizing the "knowledge walks out the door" problem.

### Metrics & Examples
- "Nearly 25 years" at Goldman Sachs; left just before the 25-year mark.
- Snowflake pitch timeframe: "2013 maybe early 2014"; early Snowflake era before snowflake.com (snowflake.net).
- Bi-coastal cadence: alternating weeks Bay Area/New York for ~3 years; same JetBlue flight every other week.
- Migration validation example: "30,000 reports" that humans typically sample-test; agents can run all 30,000.
- Confidence/behavior example: verifier agent catching only "10,000" results when 30,000 were required.
- Accuracy claim: aggressive prompting study cited as ~"10% more accurate" (but framed as not worth it).
- Genesis founded ~"April" two years prior to recording (episode recorded mid-March).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=kSyzemwrOaI)

## Value Assessment

- **Practical Value:** requires setup
- **Uniqueness Factor:** cutting-edge insight
