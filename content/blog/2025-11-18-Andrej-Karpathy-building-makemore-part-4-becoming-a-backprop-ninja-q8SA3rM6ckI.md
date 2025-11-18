+++
title = "Building makemore Part 4: Becoming a Backprop Ninja"
date = 2025-11-18
draft = false

[taxonomies]
author = ["Andrej Karpathy"]
categories = ["Artificial intelligence","Machine learning","Software engineering--Neural networks"]
tags = ["PyTorch","Backpropagation","Manual gradient computation","Numerical stability","Softmax","Batch normalization","One-hot encoding","Tensor operations"]

[extra]
excerpt = "This lecture dives deep into manual backpropagation at the tensor level, bypassing PyTorch's autograd to demystify neural network training internals. By hand-coding the backward pass, the session exposes the 'leaky abstraction' of backpropagation and builds intuition for debugging and optimizing neural networks. The approach is both a historical throwback and a practical exercise in understanding the mechanics that modern frameworks often obscure."
video_url = "https://www.youtube.com/watch?v=q8SA3rM6ckI"
video_id = "q8SA3rM6ckI"
cover = "https://img.youtube.com/vi/q8SA3rM6ckI/maxresdefault.jpg"
+++

## Overview

This lecture dives deep into manual backpropagation at the tensor level, bypassing PyTorch's autograd to demystify neural network training internals. By hand-coding the backward pass, the session exposes the 'leaky abstraction' of backpropagation and builds intuition for debugging and optimizing neural networks. The approach is both a historical throwback and a practical exercise in understanding the mechanics that modern frameworks often obscure.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Karpathy insists on writing the backward pass by hand—even though modern frameworks automate this—arguing that true mastery requires understanding the mechanics beneath autograd. He frames backpropagation as a 'leaky abstraction,' challenging the notion that stacking differentiable layers and relying on autograd is always safe or sufficient. The methodology is rooted in both historical practice (when everyone wrote backward passes manually) and a desire to cultivate deep intuition for debugging and optimization.

### The Core Problem
The core issue addressed is the over-reliance on autograd systems, which can mask subtle bugs and prevent practitioners from understanding or debugging neural network failures. Without manual understanding, issues like dead neurons, vanishing/exploding gradients, or incorrect gradient flow can go undetected, leading to suboptimal or broken models.

### The Solution Approach
The workflow involves stripping away PyTorch's autograd (loss.backward()) and implementing the backward pass manually for each layer, operating directly on tensors. The process includes careful handling of numerically sensitive operations (e.g., softmax with logit max subtraction), explicit calculation and routing of gradients (using one-hot encoding and scatter operations), and verifying correctness at each step. The reasoning is that making every gradient flow explicit removes hidden complexity, reveals subtle bugs, and cements understanding of how gradients propagate through diverse layers (including batch normalization).

### Key Insights
- Backpropagation is a leaky abstraction: relying blindly on autograd can lead to undetected bugs and poor model performance.
- Manual backward passes expose subtle implementation errors, such as incorrectly clipping the loss instead of the gradients, which can silently zero out important gradient information.
- Historical context matters: ten years ago, hand-written backward passes were the norm, and this practice built a generation of practitioners with deeper intuition for neural network mechanics.

### Concepts & Definitions
- Backpropagation as a 'leaky abstraction': an abstraction that can fail in subtle ways if its internals are not understood.
- Dead neurons: neurons that output zero gradient and thus never update, often due to activation saturation.
- Clipping loss vs. clipping gradients: the distinction between limiting the loss value (which can zero gradients) and limiting gradient magnitude (which preserves learning signal).

### Technical Details & Implementation
- Manual backward pass for a multi-layer perceptron, including explicit gradient computation for each layer (matrix multiplications, biases, softmax, batch normalization).
- Numerical stability in softmax: subtracting the row-wise max from logits before exponentiation, and verifying that gradients with respect to these maxes are (almost) zero.
- Gradient routing via one-hot encoding and scatter operations to ensure correct propagation through max operations.
- PyTorch's torch.no_grad() context is used to disable autograd entirely during manual gradient computation, improving efficiency.

### Tools & Technologies
- PyTorch (used for tensor operations, but autograd is disabled for this exercise).
- Matlab (historical reference for early deep learning work and manual backward passes).

### Contrarian Takes & Different Approaches
- Contradicts the modern norm by advocating for manual backward pass implementation as a learning tool.
- Challenges the belief that autograd makes neural network training 'just work'—arguing that it can obscure critical errors.
- Suggests that the loss of manual backward pass writing has diminished practitioners' ability to debug and optimize models.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Implement the backward pass by hand at least once to build intuition and debugging skills.
- Use torch.no_grad() when manually computing gradients to avoid unnecessary autograd overhead.
- Verify gradients at each step, especially for numerically sensitive operations, to catch subtle bugs early.

### What to Avoid
- Clipping the loss instead of the gradients can silently zero out gradients for outliers, harming learning.
- Assuming autograd always works correctly can lead to undetected bugs, especially in custom or numerically unstable layers.
- Ignoring the indices returned by max operations in backward passes can result in incorrect gradient routing.

### Best Practices
- Break down each layer's backward pass into explicit, verifiable steps.
- Use one-hot encoding and scatter operations to route gradients correctly through selection operations.
- Test manual backward passes against autograd for correctness before deploying in more complex settings.

### Personal Stories & Experiences
- Break down each layer's backward pass into explicit, verifiable steps.
- Use one-hot encoding and scatter operations to route gradients correctly through selection operations.
- Test manual backward passes against autograd for correctness before deploying in more complex settings.

### Metrics & Examples
- Manual backward pass achieves loss values comparable to autograd-based training, demonstrating correctness.
- Gradients with respect to logit maxes are shown to be on the order of 1e-9 or 1e-10, confirming expected numerical behavior.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=q8SA3rM6ckI)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** contrarian wisdom
