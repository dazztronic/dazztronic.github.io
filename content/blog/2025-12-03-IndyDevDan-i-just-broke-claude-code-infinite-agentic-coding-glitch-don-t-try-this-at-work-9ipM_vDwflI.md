+++
title = "I just BROKE Claude Code: Infinite Agentic Coding GLITCH (Don’t try this at work)"
date = 2025-12-03
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Software engineering--Artificial intelligence","Prompt engineering","Human-computer interaction"]
tags = ["Claude Code","Agentic coding","Prompt composition","Parallel agents","Infinite agentic loop","Spec-driven development","UI generation","Opus model"]

[extra]
excerpt = "IndyDevDan unveils a breakthrough agentic coding pattern using Claude Code, leveraging a two-prompt 'infinite agentic loop' to generate endless, self-improving solutions—demonstrated by spawning unique UI variants in parallel. This approach radically amplifies the creative and computational output from a single prompt, challenging assumptions about prompt engineering and agent orchestration. The method matters because it unlocks scalable, parallelized solution generation for complex problems, pushing the boundaries of automated software creation."
video_url = "https://www.youtube.com/watch?v=9ipM_vDwflI"
video_id = "9ipM_vDwflI"
cover = "https://img.youtube.com/vi/9ipM_vDwflI/maxresdefault.jpg"
+++

## Overview

IndyDevDan unveils a breakthrough agentic coding pattern using Claude Code, leveraging a two-prompt 'infinite agentic loop' to generate endless, self-improving solutions—demonstrated by spawning unique UI variants in parallel. This approach radically amplifies the creative and computational output from a single prompt, challenging assumptions about prompt engineering and agent orchestration. The method matters because it unlocks scalable, parallelized solution generation for complex problems, pushing the boundaries of automated software creation.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The distinctive methodology centers on treating prompts and specs as first-class, composable artifacts—passing them as variables into other prompts to recursively spawn and coordinate sub-agents. The 'infinite agentic loop' is fueled by just two prompts: a high-level spec/plan and an 'infinite' command, enabling virtually unbounded, parallelized generation. This pattern breaks with conventional, linear agent workflows by orchestrating waves of agents that self-improve and diversify outputs indefinitely, until system or resource limits are reached.

### The Core Problem
The core challenge addressed is the bottleneck of limited solution diversity and throughput in agentic coding workflows—where traditional approaches are constrained by sequential execution and finite prompt scope. In the current landscape of AI-assisted coding, there's a pressing need to scale both the quantity and quality of generated solutions, especially for exploratory or creative tasks like UI design.

### The Solution Approach
The method involves constructing a two-prompt system: (1) a spec/plan prompt that defines the problem and desired outputs, and (2) an 'infinite agentic loop' prompt that orchestrates the spawning of parallel sub-agents. Each sub-agent receives its own iteration number, uniqueness directive, and output directory, ensuring outputs are both parallelized and differentiated. The process is initiated via custom slash commands in Claude Code, passing variables such as the spec path, output directory, and the special 'infinite' keyword to trigger perpetual execution. The system reads the spec, parses arguments, and launches waves of five agents at a time, each generating unique, self-contained solutions (e.g., UI files), and continues until context or resource limits are hit.

### Key Insights
- Passing prompts/specs as variables into other prompts enables recursive, composable agent workflows, vastly increasing flexibility and power.
- The real value of infinite agentic loops is realized when pointed at problems requiring a wide array of potential solutions, not just single answers.
- Great planning is great prompting—investing in detailed, modular specs multiplies the effectiveness of agentic coding patterns.

### Concepts & Definitions
- "Infinite agentic loop": A pattern where an agent recursively spawns parallel sub-agents, each generating a unique solution, continuing indefinitely or until system limits are reached.
- "Spec as first-class citizen": Treating the specification or plan as a modular, passable input to prompts, enabling dynamic and reusable workflows.
- "Uniqueness directive": An instruction given to each sub-agent to ensure its output differs from others, fostering diversity in generated solutions.

### Technical Details & Implementation
- Uses Claude Code's custom slash commands (e.g., /infinite) to launch agentic loops with parameters: spec path, output directory, and count/infinite keyword.
- Runs agents in parallel batches of five, each assigned a unique iteration and output directory (e.g., source_infinite), with outputs as self-contained files.
- Prompts are written to be composable, with variables for spec, directory, and iteration injected at runtime by Claude Code's argument parsing.

### Tools & Technologies
- Claude Code (with Opus model) for agent orchestration and code generation
- Custom slash commands in Claude Code for dynamic agent launching
- Git work trees (referenced from a previous video) for parallel agent workflows

### Contrarian Takes & Different Approaches
- Challenges the notion that prompt engineering is a one-shot or linear process, advocating for recursive, composable prompt systems.
- Argues that maximizing compute and parallelization is the key to scaling impact in AI coding, contrary to the focus on single, optimal outputs.
- Suggests that embracing a certain level of output 'garbage' is acceptable and even necessary to discover novel, valuable solutions at scale.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by writing modular, detailed spec files that can be passed as variables into prompts.
- Use Claude Code's custom command system to launch infinite agentic loops with the 'infinite' keyword for tasks needing diverse outputs.
- Iteratively refine prompts to maximize both uniqueness and quality of generated solutions; treat prompt-writing as a recursive, composable process.

### What to Avoid
- The infinite agentic loop will eventually hit context window or compute credit limits—true infinity is constrained by system resources.
- Running too many agents in parallel can quickly exhaust compute credits or overwhelm the system; monitor resource usage closely.
- Not all generated outputs will be valuable—expect a mix of high-quality and low-quality results; filtering and evaluation are necessary.

### Best Practices
- Compose prompts to be modular and parameterized, enabling reuse and recursion.
- Batch agent launches in manageable waves (e.g., groups of five) to balance throughput and system stability.
- Use detailed, well-structured spec files to guide agent behavior and ensure alignment with desired outcomes.

### Personal Stories & Experiences
- Compose prompts to be modular and parameterized, enabling reuse and recursion.
- Batch agent launches in manageable waves (e.g., groups of five) to balance throughput and system stability.
- Use detailed, well-structured spec files to guide agent behavior and ensure alignment with desired outcomes.

### Metrics & Examples
- Demonstrates generating 1,000 lines per agent, with 20-50+ unique UI files created in a single session.
- Runs two infinite agentic loops in parallel, each spawning waves of five agents, with jobs ranging from 2 minutes to 30+ minutes.
- Highlights the rapid consumption of Opus credits and the need to stop agents to preserve resources for other work.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=9ipM_vDwflI)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
