+++
title = "Yup, QwQ is CRACKED: Prompt Chaining with Qwen and QwQ reasoning model (Ollama + LLM)"
date = 2025-11-18
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Artificial intelligence","Natural language processing","Software engineering--Prompt engineering"]
tags = ["QwQ","Qwen 2.5","Ollama","Prompt chaining","Chain of thought","LLM orchestration","TypeScript","Python","Bun","OpenAI","01 Mini","GPT-4","Extraction prompts"]

[extra]
excerpt = "This video introduces a practical, hands-on methodology for making local reasoning LLMs like Qwen/QwQ (Quinn with Questions) actually useful, despite their verbose and sometimes unwieldy outputs. By chaining prompts across multiple models—using a reasoning model to generate rich, detailed outputs and a second, faster model to extract actionable results—the workflow unlocks the power of local reasoning models for real-world tasks today, not just in theory."
video_url = "https://www.youtube.com/watch?v=YoeNwp9je6E"
video_id = "YoeNwp9je6E"
cover = "https://img.youtube.com/vi/YoeNwp9je6E/maxresdefault.jpg"
+++

## Overview

This video introduces a practical, hands-on methodology for making local reasoning LLMs like Qwen/QwQ (Quinn with Questions) actually useful, despite their verbose and sometimes unwieldy outputs. By chaining prompts across multiple models—using a reasoning model to generate rich, detailed outputs and a second, faster model to extract actionable results—the workflow unlocks the power of local reasoning models for real-world tasks today, not just in theory.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The distinctive approach is a two-model prompt chaining pattern: first, leverage QwQ's deep reasoning and chain-of-thought capabilities to generate comprehensive outputs, then use a high-quality base model (local or cloud) to extract and clean the final answer. This workflow sidesteps QwQ's verbosity and recursive loops, making it practical for automation and agent workflows. The method is presented with working scripts in both TypeScript and Python, emphasizing immediate applicability.

### The Core Problem
QwQ and similar local reasoning models produce outputs entangled with internal thought processes, often verbose, slow, and sometimes in mixed languages, making them impractical for direct use in pipelines or automation. The challenge is extracting clean, actionable results from these models without manual intervention.

### The Solution Approach
The solution is prompt chaining: run the original prompt through QwQ to leverage its reasoning, then pass the output to a second model (e.g., Qwen 2.5, 01 Mini, or GPT-4) with an extraction prompt that isolates the desired final answer. This is implemented via a script that loops through a list of prompts and models, dynamically passing outputs as inputs, and supports both local (Ollama) and cloud (OpenAI) models. The approach is modular, scalable, and language-agnostic.

### Key Insights
- Prompt chaining can compensate for the verbosity and chain-of-thought outputs of reasoning models, making them usable for automation.
- Contrary to the hype, QwQ is not plug-and-play; it requires orchestration with other models to be practical.
- Hard-won lesson: chaining models is an under-discussed but essential pattern for leveraging the strengths and mitigating the weaknesses of modern LLMs, especially locally.

### Concepts & Definitions
- "Prompt chaining": a workflow where the output of one model/prompt is fed as the input to another, allowing for staged processing and output refinement.
- "Chain of Thought Loop": the phenomenon where a reasoning model outputs its internal reasoning steps, often recursively, entangling the final answer.
- "Extraction model": a secondary model used to parse and clean the output from a reasoning model, isolating the actionable result.

### Technical Details & Implementation
- Implements prompt chaining via scripts in both TypeScript and Python, using Bun or Python's UV for execution.
- Uses Ollama to run local models (QwQ, Qwen 2.5, 01 Mini) and the LLM CLI for cloud models (OpenAI's 01 Reasoning, GPT-4).
- The script supports dynamic prompt templates with variable injection and can chain any number of prompts/models.
- Extraction prompts are specifically designed to parse out final answers from verbose, chain-of-thought outputs.

### Tools & Technologies
- QwQ (Qwen with Questions) for local reasoning
- Qwen 2.5 for extraction or secondary reasoning
- 01 Mini (OpenAI) for fast, clean outputs
- Ollama for local model orchestration
- LLM CLI for cloud model access
- Bun and Python's UV for script execution

### Contrarian Takes & Different Approaches
- Challenges the notion that local reasoning models are ready for mainstream use out-of-the-box; insists orchestration is required.
- Argues that prompt chaining is underutilized and under-discussed in the generative AI community, despite its critical importance.
- Finds QwQ more interesting than some high-profile releases like Anthropic's context provider, due to its reasoning transparency.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Set up a prompt chaining script to pair QwQ with a cleaner extraction model for any task requiring deep reasoning and clean outputs.
- Prefix prompts with 'English' to mitigate QwQ's tendency to output in Chinese.
- Use modular prompt templates with dynamic variables to maximize reuse and flexibility in chaining.

### What to Avoid
- Do not use QwQ outputs directly in production pipelines—its chain-of-thought verbosity and language mixing can break downstream processes.
- Beware of recursive loops in QwQ; always use an extraction step to ensure clean results.
- Avoid relying solely on a single model for both reasoning and output formatting; separation of concerns is key.

### Best Practices
- Always pair a verbose reasoning model with a fast, clean extraction model in prompt chains.
- Design extraction prompts with explicit formatting instructions and example outputs.
- Use prompt chaining scripts that are agnostic to model type and number of stages for maximum flexibility.

### Personal Stories & Experiences
- Always pair a verbose reasoning model with a fast, clean extraction model in prompt chains.
- Design extraction prompts with explicit formatting instructions and example outputs.
- Use prompt chaining scripts that are agnostic to model type and number of stages for maximum flexibility.

### Metrics & Examples
- QwQ running on a MacBook M2 Pro is significantly slower than cloud models like 01 Mini on OpenAI's servers.
- Demonstrates prompt chains of arbitrary length (up to 10 stages) to show scalability.
- Shows concrete examples of content generation (SEO titles) where QwQ's reasoning is extracted and cleaned by a secondary model.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=YoeNwp9je6E)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
