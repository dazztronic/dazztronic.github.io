+++
title = "Making AI Way More Energy Efficient | Extropic CTO"
date = 2025-11-16
draft = false

[taxonomies]
author = ["Extropic"]
categories = ["Artificial intelligence","Machine learning--Energy consumption","Integrated circuits--Design and construction","Probabilistic computing"]
tags = ["Probabilistic circuits","Thermodynamic denoising models","Hybrid algorithms","Generative AI","Energy efficiency","FPGAs","GPUs","Custom hardware","Hardware-software co-design"]

[extra]
excerpt = "Extropic's CTO presents a radical rethinking of AI hardware: building probabilistic integrated circuits that sample from probability distributions instead of performing deterministic logic, enabling generative AI with orders-of-magnitude lower energy use. This approach directly tackles the looming energy bottleneck in scaling AI, proposing a hardware-software co-design paradigm that could make advanced AI both economically and ecologically viable."
video_url = "https://www.youtube.com/watch?v=dRuhl6MLC78"
video_id = "dRuhl6MLC78"
cover = "https://img.youtube.com/vi/dRuhl6MLC78/maxresdefault.jpg"
+++

## Overview

Extropic's CTO presents a radical rethinking of AI hardware: building probabilistic integrated circuits that sample from probability distributions instead of performing deterministic logic, enabling generative AI with orders-of-magnitude lower energy use. This approach directly tackles the looming energy bottleneck in scaling AI, proposing a hardware-software co-design paradigm that could make advanced AI both economically and ecologically viable.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Instead of optimizing existing architectures (CPUs/GPUs), Extropic is inventing a new class of integrated circuits—probabilistic chips—that natively perform stochastic sampling, fundamentally aligning hardware with the probabilistic nature of machine learning. The methodology is not just theoretical: they've built and tested physical chips, integrating them into hybrid systems and developing new algorithms tailored to this hardware. Their contrarian stance is that only such a hardware revolution—rather than incremental improvements—can solve AI's energy crisis.

### The Core Problem
Current generative AI models are so energy-intensive that scaling them to ubiquitous, expert-level assistants would require energy and infrastructure investments on the scale of entire nations or even the global GDP. The energy cost of AI is poised to become the primary bottleneck for progress, threatening both economic feasibility and sustainability.

### The Solution Approach
The team develops integrated circuits that use probabilistic logic: instead of calculating deterministic outputs, these circuits sample from mathematically defined probability distributions. This requires co-designing new generative AI algorithms that exploit this hardware's strengths, moving away from standard neural architectures optimized for GPUs. The approach is validated through lab-built chips, hybrid FPGA integrations, and early benchmarks. They envision scaling by combining these probabilistic modules with traditional neural networks, creating hybrid systems that drastically reduce deterministic computation (and thus energy use) while retaining capability.

### Key Insights
- Energy, not just speed or capability, will soon be the limiting factor in AI scaling—hardware must be reimagined for efficiency, not just performance.
- Probabilistic hardware can, in specific generative tasks, be up to 10,000x more energy efficient than GPUs running state-of-the-art algorithms.
- Hybridizing probabilistic circuits with conventional neural networks offers a promising path to practical, scalable AI systems.
- A major lesson: leveraging physical noise for computation is nontrivial—turning random circuit noise into reliable, useful sampling required significant research and iteration.

### Concepts & Definitions
- "Probabilistic circuits": hardware elements that sample from probability distributions rather than compute fixed logical functions.
- "Thermodynamic denoising models (DTMs)": algorithmic primitives that use physical noise to perform generative sampling, serving as building blocks for larger ML systems.
- "Hybrid algorithms": computational workflows that partition tasks between probabilistic chips (for sampling) and conventional neural nets (for deterministic processing).

### Technical Details & Implementation
- Custom integrated circuits fabricated using standard foundries (e.g., TSMC, Intel), but with novel probabilistic logic elements.
- Chips are packaged and mounted on custom boards, interfaced with FPGAs for hybrid operation and algorithm testing.
- Hybrid algorithms combine thermodynamic denoising models (DTMs) on probabilistic hardware with neural nets on GPUs, reducing deterministic FLOPs.
- Benchmarks show 10,000x efficiency improvement over GPU-based VAEs on simple generative tasks.

### Tools & Technologies
- Custom probabilistic integrated circuits (fabricated via standard semiconductor foundries)
- FPGAs (for system integration and prototyping)
- GPUs (for hybrid algorithm comparison and baseline)

### Contrarian Takes & Different Approaches
- Contradicts the prevailing belief that Moore's Law and incremental GPU/CPU improvements will suffice for AI's future needs.
- Argues that the only viable path to mass-scale, expert-level AI is a hardware revolution—not just software optimization.
- Suggests that energy scaling, not model size or data, will be the ultimate constraint on AI progress.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- When pushing the boundaries of efficiency, consider hardware-software co-design: invent new algorithms tailored to the unique properties of your hardware.
- Prototype early with hybrid systems (e.g., FPGAs + custom chips) to validate both hardware and algorithmic innovations before scaling.
- Benchmark new approaches on simple but representative tasks to quantify efficiency gains and guide further development.

### What to Avoid
- Do not underestimate the challenge of harnessing physical noise for computation—naive designs will fail to produce reliable, useful outputs.
- Avoid assuming that incremental improvements to existing architectures (GPUs/CPUs) can solve the energy scaling crisis; fundamental redesign may be necessary.
- Beware of over-extrapolating from simple benchmarks—real-world ML tasks may expose new scaling challenges.

### Best Practices
- Co-develop hardware and algorithms from the ground up to fully exploit new computational paradigms.
- Integrate early prototypes into real systems (boards, FPGAs) for rapid iteration and feedback.
- Use hybrid models to bridge new hardware with established ML techniques, enabling practical adoption and incremental scaling.

### Personal Stories & Experiences
- Co-develop hardware and algorithms from the ground up to fully exploit new computational paradigms.
- Integrate early prototypes into real systems (boards, FPGAs) for rapid iteration and feedback.
- Use hybrid models to bridge new hardware with established ML techniques, enabling practical adoption and incremental scaling.

### Metrics & Examples
- Simulation of new chips shows ~10,000x energy efficiency over GPU-based VAEs on simple generative benchmarks.
- A single advanced AI assistant at current energy efficiency would consume ~20% of the US grid (100 GW), costing ~$10B per GW in data center buildout.
- Scaling to expert-level AI for all would require 5-10 terawatts—orders of magnitude beyond current global capacity, with infrastructure costs approaching world GDP.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=dRuhl6MLC78)

## Value Assessment

- **Practical Value:** cutting-edge insight
- **Uniqueness Factor:** cutting-edge insight
