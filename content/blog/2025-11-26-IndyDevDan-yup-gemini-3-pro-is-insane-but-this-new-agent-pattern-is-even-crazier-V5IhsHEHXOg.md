+++
title = "Yup, Gemini 3 Pro Is Insane… But This NEW Agent Pattern Is Even CRAZIER"
date = 2025-11-26
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Computer programming--Automation"]
tags = ["Gemini 3 Pro","E2B","Agentic workflows","Agent sandbox","Best-of-n pattern","Custom CLI","Prompt engineering","Parallelism","Nano Banana Pro","Cursor","Claude","Codeex"]

[extra]
excerpt = "IndyDevDan demonstrates a radical agent pattern: giving each AI agent its own dedicated compute sandbox, massively scaling parallelism and enabling complex, agentic workflows that go far beyond typical single-agent demos. This approach reframes the bottleneck from model capability to how much compute and orchestration engineers can leverage, unlocking new levels of productivity and creativity. The video is a hands-on, technical exploration of how to reprogram agents with custom skills and orchestrate dozens of parallel agent sandboxes for real engineering impact."
video_url = "https://www.youtube.com/watch?v=V5IhsHEHXOg"
video_id = "V5IhsHEHXOg"
cover = "https://img.youtube.com/vi/V5IhsHEHXOg/maxresdefault.jpg"
+++

## Overview

IndyDevDan demonstrates a radical agent pattern: giving each AI agent its own dedicated compute sandbox, massively scaling parallelism and enabling complex, agentic workflows that go far beyond typical single-agent demos. This approach reframes the bottleneck from model capability to how much compute and orchestration engineers can leverage, unlocking new levels of productivity and creativity. The video is a hands-on, technical exploration of how to reprogram agents with custom skills and orchestrate dozens of parallel agent sandboxes for real engineering impact.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The standout methodology is the 'agent sandbox' pattern: spinning up multiple, isolated compute environments (via E2B) for each agent, allowing them to operate independently, run complex workflows, and even compete against each other ('best-of-n' selection). Dan also shows how to reprogram agent command syntax (custom backslash commands) to inject shared skills and workflows, making agents extensible and composable. The perspective is deeply pragmatic: model quality matters less than how creatively and aggressively you scale and orchestrate agent compute.

### The Core Problem
Most engineers underutilize the potential of state-of-the-art language models by running them in single-threaded, one-shot interfaces, missing out on the scale and parallelism possible with modern agentic architectures. The challenge is to break out of this limited paradigm and harness the full power of these models by orchestrating many agents, each with their own compute and skillset.

### The Solution Approach
The workflow involves launching multiple agent sandboxes (using E2B) where each agent runs on its own dedicated VM or container, executing complex prompts or workflows (e.g., plan-build-host-test for full stack apps). Agents are reprogrammed to recognize custom backslash commands, which map to shared skill files—enabling nested, reusable, and agentic prompts. This setup allows for rapid experimentation, parallel execution, and 'best-of-n' selection, where the most successful agent output is chosen. The mental model is: scale your compute to scale your impact, and treat agent orchestration as the new engineering leverage point.

### Key Insights
- Scaling agent compute—by giving each agent its own sandboxed environment—unlocks orders of magnitude more productivity than simply upgrading to the latest model.
- Contrarian take: Model performance is no longer the main bottleneck; the real constraint is how much compute and orchestration you deploy.
- Personal lesson: Many agent runs will fail or stall, but with parallel sandboxes, you can simply discard failures and select the best outputs, making reliability less of a concern.

### Concepts & Definitions
- 'Agent sandbox': An isolated compute environment (VM/container) where an agent runs independently, executing prompts or workflows without interfering with others.
- 'Best-of-n' pattern: Launching multiple agents in parallel and selecting the best result from the set, mitigating individual agent failures.
- 'Agent skills': Modular, reusable prompt files or code that can be invoked by any agent via custom command syntax, enabling extensibility and shared functionality.

### Technical Details & Implementation
- Uses E2B to provision and manage multiple agent sandboxes (VMs/containers), each running a Gemini 3 Pro, Claude, or Codeex agent.
- Implements custom backslash commands in the agent CLI, mapped to skill files (e.g., agent_sandbox_skill), enabling agents to execute complex, multi-step workflows.
- Workflows like 'plan-build-host-test' are encoded as 170-line prompts, broken into modular steps and invoked via the agent's skill system.
- Demonstrates running 15+ agent sandboxes in parallel, each with their own compute, and selecting outputs from the best-performing agent.

### Tools & Technologies
- Gemini 3 Pro (Google's latest LLM, used as primary agent model)
- E2B (service for provisioning agent sandboxes/compute environments)
- Nano Banana Pro (image generation tool, used as a high-signal example)
- OpenAI GPT 5.1 Codeex Max Premium XL (competing LLM agent)
- Claude Code Running 4.5 Sonnet (Anthropic's agent model)
- Cursor (opinionated AI coding editor, contrasted with Google's Antigravity IDE)
- VS Code (reference point for IDEs)
- Custom CLI (G3PY) for orchestrating agent workflows

### Contrarian Takes & Different Approaches
- Model quality is now less important than orchestration and compute scaling; the field is moving from model-centric to system-centric engineering.
- Big tech IDEs (like Google's Antigravity) are unlikely to outcompete focused startups (like Cursor) in specialized domains.
- The real engineering leverage is not in prompt engineering, but in agent orchestration and compute management.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Stop running single-agent, one-shot prompts—spin up multiple agent sandboxes and parallelize your workflows.
- Reprogram your agents to recognize custom command syntax (e.g., backslash commands) mapped to shared skill files for modular, extensible workflows.
- Adopt the 'best-of-n' pattern: let many agents attempt a task in parallel, then select the best output, rather than relying on a single agent run.
- Use E2B or similar services to provision dedicated compute for each agent, enabling true parallelism and isolation.

### What to Avoid
- Relying on a single agent run is fragile—many agent executions will fail or stall, so parallelism is essential.
- Don't get distracted by flashy new IDEs or tools that try to do everything; focus on specialized, high-signal tools that excel at one thing.
- Avoid underutilizing compute—most engineers are not using enough parallelism or agent orchestration to fully leverage modern LLMs.

### Best Practices
- Modularize agent skills as reusable prompt files, and use custom command syntax to invoke them across agents.
- Structure workflows as multi-step prompts (plan-build-host-test) to enable agents to handle complex, full-stack tasks autonomously.
- Continuously scale up the number of agent sandboxes to maximize throughput and resilience.

### Personal Stories & Experiences
- Modularize agent skills as reusable prompt files, and use custom command syntax to invoke them across agents.
- Structure workflows as multi-step prompts (plan-build-host-test) to enable agents to handle complex, full-stack tasks autonomously.
- Continuously scale up the number of agent sandboxes to maximize throughput and resilience.

### Metrics & Examples
- Demonstrates running 15 agent sandboxes in parallel, each executing a full-stack application or creative task.
- Compares SVG outputs from Gemini, Codeex, and Claude agents for tasks like generating Pokémon cards and a pelican on a skateboard, showing qualitative differences.
- Notes that many agent runs will stall or fail, but parallelism ensures successful outputs are always available.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=V5IhsHEHXOg)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
