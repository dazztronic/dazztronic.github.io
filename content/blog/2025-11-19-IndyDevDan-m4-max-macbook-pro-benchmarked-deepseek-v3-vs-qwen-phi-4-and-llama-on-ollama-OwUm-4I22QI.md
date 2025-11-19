+++
title = "M4 MAX MacBook Pro BENCHMARKED: Deepseek v3 vs Qwen, Phi-4 and Llama on Ollama"
date = 2025-11-19
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Artificial intelligence","Machine learning","Computer engineering--Benchmarking","Software engineering--Artificial intelligence"]
tags = ["Ollama","Beni","PromptFu","Llama 3","Falcon 3","Qwen 2.5 Coder","Deepseek V3","MacBook Pro M4 Max","Local LLMs","Benchmarking","Tokens per second","Pass/fail executable evaluation"]

[extra]
excerpt = "IndyDevDan delivers a practitioner-focused, hands-on benchmarking of local LLMs on the M4 Max MacBook Pro, comparing real-world performance and accuracy against cloud models. He introduces a custom benchmarking tool and workflow that enables pass/fail, code-executable evaluation, surfacing practical trade-offs between speed, accuracy, and model size for local AI development."
video_url = "https://www.youtube.com/watch?v=OwUm-4I22QI"
video_id = "OwUm-4I22QI"
cover = "https://img.youtube.com/vi/OwUm-4I22QI/maxresdefault.jpg"
+++

## Overview

IndyDevDan delivers a practitioner-focused, hands-on benchmarking of local LLMs on the M4 Max MacBook Pro, comparing real-world performance and accuracy against cloud models. He introduces a custom benchmarking tool and workflow that enables pass/fail, code-executable evaluation, surfacing practical trade-offs between speed, accuracy, and model size for local AI development.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The approach is distinguished by its developer-centric, empirical benchmarking methodology using a self-built tool (Beni) that emphasizes executable, pass/fail code outputs for evaluating LLMs. Instead of generic benchmarks, the workflow is designed for real-world coding tasks, enabling direct, automated, and repeatable comparisons across hardware and model scales. There's a strong focus on actionable, measurable outcomes rather than theoretical performance.

### The Core Problem
The central challenge addressed is determining whether top-tier local LLMs on consumer hardware (specifically the M4 Max MacBook Pro) can approach or match the capabilities of cloud-based models, and how to reliably measure this in a way that reflects actual developer needs—namely, speed (tokens per second) and functional accuracy in code generation.

### The Solution Approach
The methodology involves side-by-side, prompt-controlled benchmarking of various LLMs (local and cloud) using a custom tool that automates prompt execution and result evaluation. Prompts are crafted to be self-contained and executable, allowing for pass/fail grading via code execution. The process starts with simple, controlled prompts and scales up in complexity and model size, always comparing against a cloud model as a control. The workflow is iterative: prompts are refined to work with larger models, then adapted for smaller ones, with clear recognition of where model size limits prompt complexity.

### Key Insights
- Tokens per second and executable accuracy are the two most critical metrics for local LLM benchmarking; both must be measured to understand practical utility.
- Pass/fail, code-executable benchmarks provide a uniquely objective and automatable way to assess LLM outputs, reducing subjective grading.
- Model size scaling reveals diminishing returns: above 10-14B parameters, accuracy plateaus, while below 10B, adding prompt complexity doesn't help—smaller models simply can't handle it.
- Upgrading from M2 Max to M4 Max yields a consistent 20-25% speed increase on LLM inference, but the advantage narrows as model size increases.
- Cloud models remain the gold standard for accuracy, but local models are rapidly closing the gap for many practical coding tasks.

### Concepts & Definitions
- "Tokens per second" is defined as the primary speed metric for LLM inference, directly reflecting user experience in local development.
- "Pass/fail executable benchmark" refers to a prompt/output pair where the model's output can be run as code and automatically graded for correctness.
- "Control group" in benchmarking is a powerful cloud model used as a reference point to contextualize local model performance.
- Prompt complexity is explained as the amount of instruction and example detail included; larger models can handle more, smaller models cannot.

### Technical Details & Implementation
- Benchmarks are run using Ollama for local model inference and a custom tool (Beni) for orchestrating prompts and evaluating outputs.
- Prompts are structured to be self-contained and evaluatable (e.g., function definitions with explicit arguments and expected outputs), enabling automated code execution for pass/fail results.
- Side-by-side hardware benchmarking is performed by running identical prompts simultaneously on M2 Max and M4 Max MacBook Pros, measuring tokens per second and output accuracy.
- Model lineup includes Llama 3 (various sizes), Falcon 3 (10B, 14B), Qwen 2.5 Coder (14B, 32B), and Deepseek V3 (cloud, 100B+), with Deepseek serving as the accuracy control.
- Benchmarking framework supports dynamic prompt variables, concise instruction levels, and can be extended with examples for more complex tasks.

### Tools & Technologies
- Ollama (for local LLM inference)
- Beni (custom benchmarking tool for automated, code-executable evaluation)
- PromptFu (alternative benchmarking framework, referenced for out-of-the-box use)
- Deepseek V3 (cloud LLM for control group)
- Llama 3, Falcon 3, Qwen 2.5 Coder (various parameter sizes)

### Contrarian Takes & Different Approaches
- Challenges the assumption that bigger models are always better; for many tasks, 14B parameter models are sufficient, and smaller models can be preferable for speed if some accuracy loss is acceptable.
- Argues that prompt complexity is wasted on small models, counter to the common belief that more detailed instructions always help.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- If benchmarking local LLMs, use pass/fail, code-executable prompts to automate and objectify evaluation.
- For most coding tasks, a 14B parameter local model offers an optimal balance of speed and accuracy; only use larger models if accuracy is critical.
- Upgrade to M4 Max only if the 20-25% speed boost in local LLM inference is worth the investment for your workflow.
- Iteratively refine prompts: start with cloud models, then adapt for smaller local models by simplifying instructions and removing complexity as needed.
- Use a cloud model as a control group to calibrate expectations and measure local model progress.

### What to Avoid
- Do not assume prompt complexity will help with models under 10B parameters—smaller models cannot process detailed instructions effectively.
- Avoid subjective, manual grading of LLM outputs; rely on executable, pass/fail benchmarks for consistency.
- Be wary of over-investing in large local models if your hardware or use-case doesn't require their marginal accuracy gains.

### Best Practices
- Always benchmark with both speed (tokens per second) and accuracy (pass/fail code execution) to get a full picture of model utility.
- Maintain a cloud model as a control group in all benchmarks to contextualize local model performance.
- Structure prompts for benchmarking to be self-contained, executable, and evaluatable for automation.
- Iteratively adapt prompts for model size: start with maximal detail for large models, then simplify for smaller ones.

### Personal Stories & Experiences
- Always benchmark with both speed (tokens per second) and accuracy (pass/fail code execution) to get a full picture of model utility.
- Maintain a cloud model as a control group in all benchmarks to contextualize local model performance.
- Structure prompts for benchmarking to be self-contained, executable, and evaluatable for automation.
- Iteratively adapt prompts for model size: start with maximal detail for large models, then simplify for smaller ones.

### Metrics & Examples
- M4 Max achieves 200 tokens/sec on Llama 3 2.1B vs. 160 tokens/sec on M2 Max (20-25% faster).
- On Falcon 3 10B, M4 Max gets 55 tokens/sec, M2 Max 41-42 tokens/sec.
- 14B parameter models (Qwen 2.5 Coder, Falcon 3) match or nearly match cloud model accuracy for many coding prompts.
- 3B parameter models offer 4x speed but drop to ~77% accuracy.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=OwUm-4I22QI)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
