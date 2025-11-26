+++
title = "Building makemore Part 5: Building a WaveNet"
date = 2025-11-26
draft = false

[taxonomies]
author = ["Andrej Karpathy"]
categories = ["Artificial intelligence","Machine learning","Deep learning","Natural language processing"]
tags = ["WaveNet","Character-level language modeling","Hierarchical neural networks","Dilated causal convolution","PyTorch","Batch normalization","Embedding layers","Jupyter Notebook","VS Code"]

[extra]
excerpt = "This session dives into evolving a basic character-level language model into a hierarchical, WaveNet-inspired architecture, emphasizing progressive information fusion and practical neural network engineering. The perspective is hands-on, demystifying complex concepts like dilated causal convolutions and focusing on debugging, prototyping, and iterative experimentation. The approach is both educational and deeply pragmatic, highlighting the real-world workflow of developing and scaling deep learning models."
video_url = "https://www.youtube.com/watch?v=t3YJ5hKiMQ0"
video_id = "t3YJ5hKiMQ0"
cover = "https://img.youtube.com/vi/t3YJ5hKiMQ0/maxresdefault.jpg"
+++

## Overview

This session dives into evolving a basic character-level language model into a hierarchical, WaveNet-inspired architecture, emphasizing progressive information fusion and practical neural network engineering. The perspective is hands-on, demystifying complex concepts like dilated causal convolutions and focusing on debugging, prototyping, and iterative experimentation. The approach is both educational and deeply pragmatic, highlighting the real-world workflow of developing and scaling deep learning models.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Karpathy's approach stands out by reconstructing advanced architectures (like WaveNet) from first principles, using minimal dependencies and a pedagogical, code-first mindset. He emphasizes understanding tensor shapes, manual layer construction, and progressive architectural complexity, rather than relying on high-level libraries or black-box abstractions. The methodology is rooted in transparency, reproducibility, and hands-on debugging, with a strong focus on the 'why' behind each architectural decision.

### The Core Problem
The main challenge addressed is how to extend a simple character-level language model (multi-layer perceptron with limited context) to handle longer contexts and deeper, more expressive architectures without losing critical information too quickly. This is crucial for generating higher-quality sequences and for exploring the practical implementation of modern sequence models.

### The Solution Approach
The workflow begins by increasing the context window (from 3 to 8 characters) and observing performance gains, then transitions to a hierarchical, tree-like fusion of context—mirroring WaveNet's progressive, dilated convolutions. Each layer fuses pairs of elements (characters, bigrams, four-grams, etc.), enabling deeper models to gradually integrate information. The process is highly iterative: prototyping in Jupyter notebooks, debugging tensor shapes, and only then porting stable code to a main repository for experimentation. Emphasis is placed on inspecting intermediate tensor shapes and understanding the mechanics of each layer.

### Key Insights
- Progressively fusing context at each layer (rather than flattening all input at once) preserves information and enables deeper, more expressive models.
- Simply increasing context length (from 3 to 8) in a shallow model already yields significant validation loss improvements, highlighting the importance of context in sequence modeling.
- Manual prototyping and shape inspection in Jupyter notebooks are invaluable for debugging and understanding model internals before scaling up experiments.

### Concepts & Definitions
- "Dilated causal convolution" is clarified as a fast implementation detail for progressive context fusion, not a fundamentally different modeling approach.
- "Batch normalization" is described as a layer that maintains running mean/variance outside backpropagation, requiring careful mode management (train/eval) and introducing statefulness.
- "Embedding layer" is defined as mapping discrete tokens (characters) to learnable dense vectors.

### Technical Details & Implementation
- Block size is increased from 3 to 8 to provide more context per prediction, resulting in a parameter count increase (e.g., 10,000 more parameters).
- Embedding layer transforms integer character indices into 10-dimensional vectors, producing tensors of shape [batch, context, embedding_dim].
- Flattening concatenates embeddings across the context window, feeding them into a linear layer with input size context*embedding_dim.
- Hierarchical fusion is implemented by fusing pairs of elements at each layer (e.g., characters → bigrams → four-grams), mimicking the tree-like structure of WaveNet.
- Development workflow involves prototyping in Jupyter, verifying tensor shapes, then transferring code to VS Code for full-scale training.

### Tools & Technologies
- PyTorch (for API mimicry and tensor operations)
- Jupyter Notebook (for prototyping and debugging)
- VS Code (for production code and experiment management)

### Contrarian Takes & Different Approaches
- Questions whether a deep, hierarchical network is always superior—suggests that a sufficiently large shallow network might outperform a complex one if tuned well.
- Argues that stateful layers (like batch normalization) can be more trouble than they're worth in some scenarios.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Prototype new layers and architectures in Jupyter, focusing on tensor shape correctness before scaling up.
- Increase context window size as a quick win for improving sequence model performance.
- Maintain a performance log to track the impact of architectural changes and hyperparameter tuning.

### What to Avoid
- Failing to manage batch normalization's train/eval state can introduce subtle bugs.
- Flattening all context into a single hidden layer squashes information too quickly, leading to poor performance.
- Neglecting to inspect tensor shapes at each step can result in hard-to-debug errors.

### Best Practices
- Build neural networks from modular, reusable layer blocks with clear, PyTorch-like APIs.
- Debug and verify all tensor shapes during the forward pass to ensure correct layer connectivity.
- Iteratively experiment and log results, rather than relying on intuition alone.

### Personal Stories & Experiences
- Build neural networks from modular, reusable layer blocks with clear, PyTorch-like APIs.
- Debug and verify all tensor shapes during the forward pass to ensure correct layer connectivity.
- Iteratively experiment and log results, rather than relying on intuition alone.

### Metrics & Examples
- Validation loss improved from 2.10 to 2.02 by increasing context window from 3 to 8.
- Parameter count increased by approximately 10,000 when scaling up context.
- Challenge issued to beat a validation loss of 1.993 with further experimentation.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=t3YJ5hKiMQ0)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
