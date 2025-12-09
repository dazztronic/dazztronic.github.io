+++
title = "RFT, DPO, SFT: Fine-tuning with OpenAI — Ilan Bigio, OpenAI"
date = 2025-12-09
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Machine learning","Natural language processing","Software engineering--Artificial intelligence"]
tags = ["Fine-tuning","Prompt engineering","OpenAI API","GPT-4.0","JSONL","Reasoning models","Agents SDK","Overfitting"]

[extra]
excerpt = "This session demystifies OpenAI's fine-tuning landscape (RFT, SFT, DPO) by blending hands-on implementation with candid discussion of trade-offs, failures, and nuanced decision-making. The presenter, deeply embedded in OpenAI's developer experience, offers a practitioner's lens on when and how to fine-tune versus prompt engineer, emphasizing practical workflows, real-world pitfalls, and the evolving nature of these tools."
video_url = "https://www.youtube.com/watch?v=JfaLQqfXqPA"
video_id = "JfaLQqfXqPA"
cover = "https://img.youtube.com/vi/JfaLQqfXqPA/maxresdefault.jpg"
+++

## Overview

This session demystifies OpenAI's fine-tuning landscape (RFT, SFT, DPO) by blending hands-on implementation with candid discussion of trade-offs, failures, and nuanced decision-making. The presenter, deeply embedded in OpenAI's developer experience, offers a practitioner's lens on when and how to fine-tune versus prompt engineer, emphasizing practical workflows, real-world pitfalls, and the evolving nature of these tools.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The approach stands out for its raw, practitioner-first perspective: live coding, real datasets, and unfiltered stories of both success and failure. Rather than evangelizing fine-tuning, the talk is refreshingly honest about its costs, complexity, and when not to use it. The methodology is grounded in rapid experimentation, empirical comparison (prompting vs. fine-tuning), and leveraging reasoning models to extract meta-insights from model behavior.

### The Core Problem
The central challenge is optimizing LLM performance for specific tasks—deciding when to use prompting, when to invest in fine-tuning, and how to navigate the practical hurdles (data formatting, overfitting, iteration speed) that arise in real-world deployments.

### The Solution Approach
The workflow begins with baseline evaluation using prompting, followed by structured fine-tuning experiments with varying dataset sizes and models (e.g., GPT-4.0 vs. 4.0 mini). Data is prepared in JSONL format with explicit message arrays, uploaded via the OpenAI API, and fine-tuning jobs are launched with clear separation of training and validation files. The process is iterative: results are compared, overfitting is monitored visually (not automatically), and reasoning models are used to analyze both successes and failures, extracting actionable notes to improve prompts or data.

### Key Insights
- Fine-tuning is best viewed as a high-investment, high-reward tool—akin to a CNC machine—whereas prompting is a low-barrier, flexible toolkit suitable for most jobs.
- Contrary to hype, fine-tuning does not solve all problems and is often unnecessary unless you have clean, sufficient data and a well-defined domain need.
- Personal lesson: Iteration cycles are much slower with fine-tuning; never start a fine-tuning job right before a deadline or live demo.
- Using reasoning models to analyze model errors can surface missing data or prompt gaps, offering a meta-optimization layer even if the fine-tune fails.

### Concepts & Definitions
- Fine-tuning: Continued training of a pre-trained model on domain-specific data to optimize weights for a targeted task.
- Prompting: Crafting input prompts to steer model behavior without changing model weights; likened to using hand tools.
- RFT (Reasoning Fine-Tuning): Using reasoning models to analyze model outputs, extract insights, and potentially inform further prompt or data improvements.
- Overfitting: When a model performs well on training data but poorly on unseen data; not automatically detected in OpenAI fine-tuning jobs.

### Technical Details & Implementation
- Data for fine-tuning must be in JSONL format with a 'messages' array; the last assistant message is the learning target.
- Files must be uploaded to OpenAI's API with 'purpose' set to 'fine-tune'; jobs are launched specifying base model (full snapshot, not alias), training file, validation file, and epochs.
- Fine-tuning jobs on OpenAI can take 30 minutes to 24 hours; monitoring for overfitting is manual via loss curves.
- Empirical results: GPT-4.0 mini with 500 examples outperformed GPT-4.0 base on a classification task (accuracy: 90% vs. 83%).

### Tools & Technologies
- OpenAI API for file upload and fine-tuning job management
- JSONL data format for training/validation sets
- Agents SDK (TypeScript) for broader OpenAI integration
- Jupyter notebook for workflow demonstration

### Contrarian Takes & Different Approaches
- Challenges the notion that fine-tuning is a universal solution; advocates for prompt engineering as the default starting point.
- Argues that failures in fine-tuning are valuable—using reasoning models to analyze errors can be more informative than blindly tuning.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with prompt engineering—it's faster, cheaper, and sufficient for most use cases.
- If fine-tuning, ensure your data is clean, well-formatted, and sufficient in size; use JSONL with explicit message arrays.
- Always separate training and validation files to monitor for overfitting.
- Use reasoning models to analyze both successful and failed outputs, extracting notes to refine future prompts or data.

### What to Avoid
- Do not expect fine-tuning to automatically check or prevent overfitting; manual monitoring is required.
- Avoid launching fine-tuning jobs immediately before important deadlines due to unpredictable job durations.
- Noisy or subjective data can undermine fine-tuning effectiveness, especially for reasoning-based tasks.

### Best Practices
- Iterate quickly with prompt engineering before committing to fine-tuning.
- Prepare datasets with clear, unambiguous examples; include both successes and failures for richer learning.
- Leverage validation sets and monitor loss curves to detect overfitting early.
- Document and analyze failures—use them to inform prompt or data improvements.

### Personal Stories & Experiences
- Iterate quickly with prompt engineering before committing to fine-tuning.
- Prepare datasets with clear, unambiguous examples; include both successes and failures for richer learning.
- Leverage validation sets and monitor loss curves to detect overfitting early.
- Document and analyze failures—use them to inform prompt or data improvements.

### Metrics & Examples
- Baseline accuracy: 83% (GPT-4.0), 75% (GPT-4.0 mini) with prompting.
- Fine-tuned accuracy: 90% (GPT-4.0 mini with 500 examples), outperforming base models.
- Fine-tuning job durations: 30 minutes to 24 hours on OpenAI API.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=JfaLQqfXqPA)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
