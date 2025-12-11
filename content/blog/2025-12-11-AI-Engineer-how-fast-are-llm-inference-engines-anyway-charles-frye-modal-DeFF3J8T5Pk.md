+++
title = "How fast are LLM inference engines anyway? — Charles Frye, Modal"
date = 2025-12-11
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence","Machine learning--Natural language processing","Software engineering--Performance benchmarking"]
tags = ["Large language models","LLM inference","VLM","SG Lang","Tensor TLM","Modal","Benchmarking","Time-to-first-token","Throughput","Speculative decoding","KV caching","Open source"]

[extra]
excerpt = "Charles Frye delivers a practitioner's deep dive into benchmarking open LLM inference engines, exposing the real-world performance landscape for self-hosted models. By building and open-sourcing a comprehensive benchmarking suite and dataset, he empowers engineers to make data-driven decisions about model hosting, performance tuning, and infrastructure tradeoffs—moving beyond vendor marketing and anecdotal claims."
video_url = "https://www.youtube.com/watch?v=DeFF3J8T5Pk"
video_id = "DeFF3J8T5Pk"
cover = "https://img.youtube.com/vi/DeFF3J8T5Pk/maxresdefault.jpg"
+++

## Overview

Charles Frye delivers a practitioner's deep dive into benchmarking open LLM inference engines, exposing the real-world performance landscape for self-hosted models. By building and open-sourcing a comprehensive benchmarking suite and dataset, he empowers engineers to make data-driven decisions about model hosting, performance tuning, and infrastructure tradeoffs—moving beyond vendor marketing and anecdotal claims.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Frye's approach is hands-on, empirical, and open: he systematically benchmarks multiple open-source LLM inference engines (VLM, SG Lang, Tensor TLM) across diverse models and context lengths, then publishes the raw data and code for community use and extension. He frames the open model landscape as having reached a 'good enough' inflection point, where self-hosting is now practical and competitive, and pushes for a collaborative, transparent benchmarking culture rather than closed, proprietary performance claims.

### The Core Problem
The central challenge is quantifying and comparing the real-world speed and throughput of open LLM inference engines, especially as organizations consider self-hosting for cost, privacy, or customization reasons. With the rapid evolution of open models and inference stacks, reliable, reproducible performance data is scarce, making it hard to choose the right engine or optimize deployments.

### The Solution Approach
Frye's methodology involves automating large-scale benchmarks across engines, models, and configurations, focusing on practical metrics like time-to-first-token and requests per second under realistic loads. He starts with out-of-the-box settings to reflect what users actually experience, then encourages community contributions for optimized configs. The results are organized into an interactive 'almanac'—a living reference for LLM engineers. His benchmarking protocol includes both maximum throughput (flooding the engine with parallel requests) and minimum latency (single-request roundtrips), sweeping the full performance envelope.

### Key Insights
- Open LLMs and inference engines have reached a capability threshold where self-hosting is not just viable but often preferable for many use cases.
- Time-to-first-token is a critical, user-facing metric—300ms is a practical threshold for interactive applications, while 1s is a common SLO.
- Context length (input tokens) is often 'cheaper' than output tokens for latency—shifting workloads from reasoning-heavy to context-heavy can improve performance without sacrificing quality.
- Out-of-the-box performance varies widely between engines and models; optimization is non-trivial and community benchmarking is essential.
- Scaling throughput is best achieved by scaling out (more replicas) rather than scaling up (bigger hardware), especially with GPU-bound workloads.

### Concepts & Definitions
- "Time-to-first-token": The latency between sending a prompt and receiving the first generated token—crucial for perceived responsiveness.
- "Throughput per replica": The number of requests per second a single GPU/server can handle; scaling is achieved by adding more replicas.
- "Speculative decoding" and "multi-token prediction": Advanced inference optimizations that are difficult to implement manually, highlighting the value of mature inference engines.
- "Doerty threshold": A reference to a 300ms latency boundary for interactive systems, borrowed from human-computer interaction research.

### Technical Details & Implementation
- Benchmarks run on single H100 GPUs, measuring both time-to-first-token and requests per second across 10+ models, 3 engines, and 10 context lengths.
- Initial benchmarking required hours of manual setup; automation and a custom benchmarking suite reduced this to ~15-20 minutes per config.
- All benchmarks start with default (out-of-the-box) engine/model settings to reflect real user experience; optimization is left open for community contribution.
- The benchmarking suite and results are open-sourced, with a web interface for querying and downloading raw data.
- Example config: Quen 3 Mixture of Experts on VLM, 128 tokens in, 1024 tokens out, ~1 RPS, first token in <1s.

### Tools & Technologies
- VLM (inference engine)
- SG Lang (inference engine)
- Tensor TLM (inference engine)
- Modal (cloud infrastructure platform)
- Llama, Quen, DeepSeek, Gemma (open LLMs)
- Custom open-source benchmarking suite (available on modal.com/lmalmanac)

### Contrarian Takes & Different Approaches
- It no longer makes sense to default to closed/proprietary models for most use cases—open models are now 'good enough' and offer better properties for many scenarios.
- Rather than obsessing over the absolute best model, focus on whether an open model meets your capability threshold—once 'good enough,' open solutions tend to dominate, as seen in operating systems and databases.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Leverage the open-source benchmarking suite and dataset to evaluate inference engines for your own workloads before committing to a stack.
- Start with out-of-the-box engine/model configs to establish a baseline, then iteratively optimize for your use case—share results with the community.
- For interactive applications, target <300ms time-to-first-token; for batch jobs, focus on maximizing throughput per replica.
- If you need higher throughput, scale horizontally (add more replicas) rather than vertically (bigger GPUs).

### What to Avoid
- Don't assume vendor or engine marketing claims reflect your workload—always benchmark with your own data and settings.
- Avoid over-optimizing for rare edge-case configurations; focus on realistic, production-relevant scenarios.
- Beware that not all engines support all models/configs equally—compatibility and optimization can lag behind headline features.

### Best Practices
- Automate benchmarking to reduce manual effort and ensure reproducibility.
- Publish both methodology and raw results to foster transparency and community improvement.
- Use a standardized set of input/output token lengths to enable apples-to-apples comparisons.

### Personal Stories & Experiences
- Automate benchmarking to reduce manual effort and ensure reproducibility.
- Publish both methodology and raw results to foster transparency and community improvement.
- Use a standardized set of input/output token lengths to enable apples-to-apples comparisons.

### Metrics & Examples
- Quen 3 Mixture of Experts on VLM: ~1 request per second, 128 tokens in, 1024 tokens out, first token <1s.
- Gemma 27B BF16: Similar throughput to Quen 3 despite 10x model size, due to optimization differences.
- Benchmarks run on single H100 GPU; scaling throughput requires more replicas.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=DeFF3J8T5Pk)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
