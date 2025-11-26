+++
title = "Ilya Sutskever – We're moving from the age of scaling to the age of research"
date = 2025-11-26
draft = false

[taxonomies]
author = ["Dwarkesh Patel"]
categories = ["Artificial intelligence","Machine learning","Neurosciences--Influence on artificial intelligence","Research--Methodology"]
tags = ["Reinforcement learning","RL fine-tuning","Benchmarks","Generalization","Scaling laws","Research taste","Human learning analogy","Transformer","AlexNet"]

[extra]
excerpt = "Ilya Sutskever argues that the era of brute-force scaling in artificial intelligence is ending, and a new age of research—driven by original ideas and deeper understanding—is emerging. He highlights a disconnect between AI model performance on benchmarks and their real-world economic impact, emphasizing the need for fundamentally new research directions and a return to scientific taste and inspiration from human cognition. This perspective matters because it challenges the prevailing narrative that more compute and data alone will yield transformative progress."
video_url = "https://www.youtube.com/watch?v=aR20FWCCjAs"
video_id = "aR20FWCCjAs"
cover = "https://img.youtube.com/vi/aR20FWCCjAs/maxresdefault.jpg"
+++

## Overview

Ilya Sutskever argues that the era of brute-force scaling in artificial intelligence is ending, and a new age of research—driven by original ideas and deeper understanding—is emerging. He highlights a disconnect between AI model performance on benchmarks and their real-world economic impact, emphasizing the need for fundamentally new research directions and a return to scientific taste and inspiration from human cognition. This perspective matters because it challenges the prevailing narrative that more compute and data alone will yield transformative progress.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Sutskever's approach is distinguished by his insistence on the primacy of research taste, aesthetic judgment, and correct inspiration from the brain, rather than mere scaling of existing architectures. He frames progress as bottlenecked by ideas, not just compute, and advocates for a top-down, beauty-driven methodology that draws from how humans learn and self-correct. His contrarian stance is that the field must move beyond optimizing for benchmarks and instead seek elegant, robust principles akin to those underlying human intelligence.

### The Core Problem
The central issue addressed is the growing gap between AI models' impressive performance on standardized evaluations (evals) and their limited, sometimes brittle, real-world utility. This matters because it reveals fundamental limitations in current training paradigms—especially reinforcement learning (RL) fine-tuning—and suggests that further scaling will not resolve these shortcomings.

### The Solution Approach
Sutskever proposes a shift from scaling to research, focusing on developing new training paradigms inspired by human learning—such as robust, unsupervised, value-driven self-correction. He suggests that researchers should expand beyond optimizing for evals and instead cultivate environments and objectives that foster generalization and taste. The methodology involves top-down reasoning: holding to a multifaceted, beauty-driven belief about what AI should be, and persisting through experimental setbacks based on this conviction.

### Key Insights
- There is a persistent disconnect between AI performance on evals and practical economic impact, likely due to overfitting RL training to benchmarks rather than fostering true generalization.
- The real 'reward hacking' may be occurring at the human level, with researchers inadvertently optimizing models to look good on evals rather than for broader competence.
- Human learning is robust, sample-efficient, and value-driven—qualities current machine learning systems lack, pointing to the need for fundamentally new principles.
- Research progress is now bottlenecked by ideas, not compute; the field has more companies than novel approaches.
- Aesthetic sense, beauty, and correct inspiration from neuroscience are essential for guiding research, especially when empirical results are ambiguous.

### Concepts & Definitions
- "Research taste" is defined as an aesthetic, multifaceted judgment about what constitutes fundamental, beautiful, and brain-inspired AI research.
- "Reward hacking" is reframed as a phenomenon not just of models, but of human researchers who over-optimize for benchmark performance.
- "Top-down belief" is explained as a guiding conviction about how AI should work, which sustains researchers through experimental setbacks.

### Technical Details & Implementation
- Current RL fine-tuning involves creating diverse RL environments, often inspired by evaluation benchmarks, which can lead to overfitting and lack of generalization.
- Historical breakthroughs (AlexNet, Transformer) were achieved with relatively modest compute (e.g., AlexNet on 2 GPUs, Transformer on up to 64 GPUs), suggesting that massive compute is not always necessary for research innovation.
- Human analogy: Unlike current ML, humans learn robustly and quickly with minimal explicit reward signals, implying a need for new ML analogies and architectures.

### Tools & Technologies
- Reinforcement learning (RL) fine-tuning: Used for post-pretraining adjustment, but criticized for its tendency to overfit to benchmarks.
- Benchmarks/evals: Used as targets for RL environments, but their overuse is seen as a limiting factor.

### Contrarian Takes & Different Approaches
- Challenges the Silicon Valley mantra that 'ideas are cheap, execution is everything,' arguing that in AI, ideas are now the true bottleneck.
- Disputes the notion that scaling compute is the primary driver of progress, emphasizing that research breakthroughs often require less compute than assumed.
- Argues that optimizing for evals is a form of reward hacking by researchers, not just models, and that this practice is holding back real-world impact.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Expand the diversity of RL environments beyond benchmarks to encourage broader generalization.
- Adopt a top-down, beauty-driven approach to research, using inspiration from human cognition and neuroscience.
- Persist with promising research directions even when empirical results are ambiguous, provided the top-down reasoning is sound.

### What to Avoid
- Beware of overfitting RL training to evaluation benchmarks, as this can create models that perform well on tests but poorly in real-world applications.
- Avoid conflating compute scaling with genuine research progress; more compute does not necessarily yield better ideas.
- Do not rely solely on empirical results without a guiding top-down belief, as this can lead to abandoning promising directions prematurely.

### Best Practices
- Use multifaceted inspiration from neuroscience—such as distributed representation and learning from experience—to guide AI research.
- Balance empirical data with aesthetic and theoretical judgment to navigate ambiguous experimental outcomes.
- Encourage a diversity of research approaches, especially when dominant paradigms become saturated.

### Personal Stories & Experiences
- Use multifaceted inspiration from neuroscience—such as distributed representation and learning from experience—to guide AI research.
- Balance empirical data with aesthetic and theoretical judgment to navigate ambiguous experimental outcomes.
- Encourage a diversity of research approaches, especially when dominant paradigms become saturated.

### Metrics & Examples
- AlexNet was trained on 2 GPUs; the original Transformer used no more than 64 GPUs—far less than contemporary large-scale models.
- Current models excel at hard evaluation tasks but still exhibit basic failures (e.g., cycling between bugs in code correction tasks).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=aR20FWCCjAs)

## Value Assessment

- **Practical Value:** conceptual framework
- **Uniqueness Factor:** cutting-edge insight
