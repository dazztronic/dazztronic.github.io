+++
title = "Best LLM for Parallel Function Calling: 14 LLM, 420 Prompt, 1 Winner Benchmark"
date = 2025-11-18
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Artificial intelligence","Machine learning","Software engineering--Artificial intelligence"]
tags = ["Large language models","Function calling","Benchmarking","Gemini 1.5 Flash","Claude 3.5 Sonnet","Prompt engineering","Agentic workflows","JSON schema","Tool chaining"]

[extra]
excerpt = "This video delivers a rigorous, hands-on benchmark of 14 leading large language models (LLMs) for parallel function (tool) calling, focusing on their ability to execute long, ordered chains of tool invocations reliably, quickly, and cheaply. The findings challenge hype-driven model selection and spotlight an underappreciated LLM—Gemini 1.5 Flash—as the clear winner for agentic, multi-step workflows. The approach is deeply practical, data-driven, and exposes real-world strengths and weaknesses that are invisible in surface-level model comparisons."
video_url = "https://www.youtube.com/watch?v=ZlljCLhq814"
video_id = "ZlljCLhq814"
cover = "https://img.youtube.com/vi/ZlljCLhq814/maxresdefault.jpg"
+++

## Overview

This video delivers a rigorous, hands-on benchmark of 14 leading large language models (LLMs) for parallel function (tool) calling, focusing on their ability to execute long, ordered chains of tool invocations reliably, quickly, and cheaply. The findings challenge hype-driven model selection and spotlight an underappreciated LLM—Gemini 1.5 Flash—as the clear winner for agentic, multi-step workflows. The approach is deeply practical, data-driven, and exposes real-world strengths and weaknesses that are invisible in surface-level model comparisons.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The methodology is uniquely centered on live, iterative benchmarking of LLMs using a custom tool that simulates real-world, multi-agent, multi-tool workflows, rather than relying on synthetic or one-off tests. The focus is on agentic engineering—building systems where specialized AI agents autonomously execute complex, long-running tasks via reliable tool chaining. This perspective is contrarian in its rejection of hype and marketing claims, advocating for relentless, empirical evaluation and exposing unexpected winners and losers.

### The Core Problem
The central challenge addressed is reliably orchestrating long sequences of tool calls (function calls) using LLMs—critical for building robust, long-running agentic workflows and multi-agent systems. In practice, many LLMs fail to maintain accuracy, order, and cost-effectiveness as tool chains grow, undermining the viability of advanced AI automation.

### The Solution Approach
The approach involves constructing a live benchmarking tool where prompts are crafted to trigger multiple, ordered tool calls. Each LLM is tested repeatedly (across 10s to 100s of runs) with incrementally longer tool chains, measuring not just correctness but also execution time and cost. For models lacking native function calling, a JSON schema hack is used to simulate structured outputs, ensuring fair comparison. The process emphasizes empirical iteration, variance analysis, and real-world scenario simulation, with results visualized in sortable columns for actionable insights.

### Key Insights
- Gemini 1.5 Flash outperforms all other LLMs in both speed and cost for long, ordered tool chains—despite being largely ignored by the community.
- Many hyped models (e.g., Claude 3.5 Sonnet) perform poorly in real-world tool chaining, with high costs and low accuracy, contrary to expectations.
- Non-determinism in LLM outputs demands repeated, high-volume benchmarking to reveal true performance characteristics—single-run tests are misleading.

### Concepts & Definitions
- "Tool calling" is defined as the LLM's ability to output a sequence of function calls (with parameters) that trigger domain-specific agents to perform tasks.
- "Agentic workflows" are described as autonomous, long-running systems where specialized AI agents execute complex plans via orchestrated tool calls.
- "Relative cost" is introduced as a normalized metric for comparing LLM efficiency across different pricing models.

### Technical Details & Implementation
- A custom benchmarking tool is used, allowing users to define expected tool call sequences and prompts, then run these across multiple LLMs in parallel.
- Metrics tracked per run include execution time, total time, per-call and total cost, number and percentage correct, and relative cost.
- For LLMs without function calling support, structured JSON output is enforced via prompt engineering and schema definition.
- Models are tested with both native function calling and JSON schema hacks, enabling apples-to-apples comparison.
- Prompts are incrementally extended from single tool calls up to chains of 15+ calls, including repeated tools to test model robustness.

### Tools & Technologies
- Gemini 1.5 Flash (Google) – highlighted as the top performer for function calling.
- Claude 3.5 Sonnet (Anthropic) – tested and found lacking in this use case.
- GPT-4, GPT-4o, GPT-3.5 (OpenAI) – included in benchmarks.
- 01 Mini, 40 Mini, 40 JSON (various vendors) – compared for cost and accuracy.
- Custom live benchmarking tool – enables real-time, multi-model evaluation.

### Contrarian Takes & Different Approaches
- Rejects the notion that the most popular or expensive LLMs are best for complex workflows.
- Advocates for 'sleeping on Google' (i.e., undervaluing Google models) as a mistake—empirical results matter more than brand.
- Argues that structured JSON prompting can be as effective as native function calling for many models.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Always benchmark LLMs in your actual workflow context—do not rely on marketing or general benchmarks.
- Use structured JSON schema prompting to enable tool calling with models lacking native support.
- Run benchmarks repeatedly (10s to 100s of times) to account for LLM non-determinism and surface real performance.
- Sort results by execution time, cost, and accuracy to identify the true best-fit model for your needs.

### What to Avoid
- Do not assume top-tier or hyped models will perform best for tool chaining—empirical testing often reveals the opposite.
- Single-run or synthetic benchmarks are misleading due to LLM variability; always use multiple runs.
- Relying on function calling support alone is insufficient—prompt engineering and output validation are critical for reliability.

### Best Practices
- Incrementally build up tool call chains in benchmarks to test model robustness as complexity grows.
- Use a live, interactive benchmarking tool to visualize and compare model performance in real time.
- Adopt a data-driven, skeptical mindset—trust results, not reputations.

### Personal Stories & Experiences
- Incrementally build up tool call chains in benchmarks to test model robustness as complexity grows.
- Use a live, interactive benchmarking tool to visualize and compare model performance in real time.
- Adopt a data-driven, skeptical mindset—trust results, not reputations.

### Metrics & Examples
- Gemini 1.5 Flash achieved 100% accuracy across 30 test cases with tool chains up to length 15, at a cost of less than one-tenth of a cent.
- Claude 3.5 Sonnet delivered only 27% accuracy at 14 cents for the same benchmark.
- Execution time for Gemini 1.5 Flash was fastest by nearly 20 seconds compared to other models.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=ZlljCLhq814)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
