+++
title = "This Tiny Model is Insane... (7m Parameters)"
date = 2025-11-16
draft = false

[taxonomies]
author = ["Matthew Berman"]
categories = ["Artificial intelligence","Machine learning","Neural networks--Recursive algorithms"]
tags = ["Tiny Recursive Model (TRM)","Recursive reasoning","Deep supervision","ARC AGI benchmark","Sudoku","Mocha","Scaling laws","Model generalization"]

[extra]
excerpt = "A 7-million-parameter model, the Tiny Recursive Model (TRM), outperforms much larger frontier models on challenging reasoning benchmarks by leveraging recursion and deep supervision rather than sheer scale. This approach challenges the prevailing belief that bigger models are always better, showing that architectural innovations can yield outsized gains in reasoning tasks. The implications are profound: highly capable models could soon run on everyday devices, democratizing advanced AI capabilities."
video_url = "https://www.youtube.com/watch?v=NC9nTxn6aos"
video_id = "NC9nTxn6aos"
cover = "https://img.youtube.com/vi/NC9nTxn6aos/maxresdefault.jpg"
+++

## Overview

A 7-million-parameter model, the Tiny Recursive Model (TRM), outperforms much larger frontier models on challenging reasoning benchmarks by leveraging recursion and deep supervision rather than sheer scale. This approach challenges the prevailing belief that bigger models are always better, showing that architectural innovations can yield outsized gains in reasoning tasks. The implications are profound: highly capable models could soon run on everyday devices, democratizing advanced AI capabilities.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The perspective centers on a radical simplification: instead of mimicking biological hierarchies or stacking complex layers, TRM uses a single, tiny network with recursion to simulate 'virtual depth.' The methodology discards biological analogies and focuses on what actually drives generalization—recursive self-improvement and deep supervision—arguing that recursion, not scale, is the new scaling law.

### The Core Problem
Large language models (LLMs) struggle with hard reasoning tasks because they generate answers autoregressively, making them prone to cascading errors and brittle reasoning traces. Existing solutions like chain-of-thought and pass@k are computationally expensive and don't fundamentally solve the reasoning deficit, especially at smaller scales.

### The Solution Approach
TRM iteratively refines its answers by maintaining two memories: the current guess and its reasoning trace. At each recursion, both are updated, akin to a self-critiquing loop. Deep supervision is applied at every step, passing intermediate 'notes' forward to improve accuracy. Unlike prior hierarchical models, TRM uses just two layers, finding that increasing layers actually harms generalization due to overfitting, while increasing recursion depth simulates greater model capacity.

### Key Insights
- Deep supervision—providing feedback at each intermediate step—doubles accuracy compared to single-step supervision, demonstrating the power of incremental self-improvement.
- Contrary to scaling laws, smaller networks with more recursion generalize better than deeper, larger models; recursion acts as a 'virtual depth' multiplier.
- Biological analogies and complex mathematical justifications are unnecessary; practical ablation shows that recursion alone, not hierarchy or multiple latent features, drives performance.

### Concepts & Definitions
- "Recursive hierarchical reasoning" is reframed as a feedback loop where the model iteratively critiques and refines its own output.
- "Deep supervision" is defined as providing intermediate supervision at every step, not just the final output, to guide learning.
- "Virtual depth" describes the effect of recursion simulating the capacity of a deeper network without actually increasing layer count.

### Technical Details & Implementation
- TRM is implemented as a two-layer network with recursive feedback, updating both the answer and reasoning trace at each step.
- Deep supervision is configured to supervise every recursion, passing latent features forward for iterative refinement.
- Scaling recursion depth (number of loops) is prioritized over increasing network depth (layers), as more layers lead to overfitting.

### Tools & Technologies
- Mocha (AI app builder for rapid prototyping and deployment, used in the video demo context)

### Contrarian Takes & Different Approaches
- Scaling up model size is not always the path to better reasoning; recursion and deep supervision can outperform brute-force scale.
- Biological inspiration is not a sufficient justification for architectural choices in neural networks—empirical results matter more.
- The field may need to rethink scaling laws for reasoning tasks, prioritizing recursion over parameter count.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Experiment with smaller, shallow models and increase recursion depth with deep supervision rather than stacking more layers.
- Implement recursive reasoning by maintaining and updating both the answer and a reasoning trace at each step.
- Use deep supervision at every recursion to maximize incremental learning and generalization.

### What to Avoid
- Avoid overfitting by resisting the urge to add more layers; more depth can degrade generalization in this paradigm.
- Do not rely on biological analogies or complex theoretical justifications without empirical ablation—focus on what actually drives performance.
- Beware of GPU memory limits when scaling recursion depth; excessive recursion can cause out-of-memory errors.

### Best Practices
- Apply deep supervision at every step of recursion for challenging reasoning tasks.
- Use a minimal architecture (two layers) and maximize recursion, leveraging feedback loops for self-improvement.
- Benchmark against reasoning-heavy tasks (e.g., ARC AGI, Sudoku) to validate generalization improvements.

### Personal Stories & Experiences
- Apply deep supervision at every step of recursion for challenging reasoning tasks.
- Use a minimal architecture (two layers) and maximize recursion, leveraging feedback loops for self-improvement.
- Benchmark against reasoning-heavy tasks (e.g., ARC AGI, Sudoku) to validate generalization improvements.

### Metrics & Examples
- TRM (7M parameters) achieves 45% on ARC AGI 1 and 8% on ARC AGI 2, outperforming Gemini 2.5 Pro (4.9%) and Deepseek R1.
- Sudoku Extreme accuracy jumps from 55% (HRM) to 87% (TRM); Maze Hard from 75% to 85%.
- Deep supervision boosts accuracy from 19% to 39%; recursion with two layers outperforms deeper models.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=NC9nTxn6aos)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
