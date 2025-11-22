+++
title = "The spelled-out intro to neural networks and backpropagation: building micrograd"
date = 2025-11-22
draft = false

[taxonomies]
author = ["Andrej Karpathy"]
categories = ["Artificial intelligence","Machine learning","Software engineering--Artificial intelligence"]
tags = ["automatic differentiation","backpropagation","micrograd","computation graph","gradient descent","PyTorch","Jupyter Notebook","neural networks","scalar autograd"]

[extra]
excerpt = "This video offers a transparent, ground-up walkthrough of neural network training by building an automatic differentiation engine (micrograd) from scratch, exposing every detail of forward and backward passes. By eschewing black-box abstractions, it demystifies backpropagation and neural network internals, making the mechanics and intuition accessible to practitioners and learners alike."
video_url = "https://www.youtube.com/watch?v=VMj-3S1tku0"
video_id = "VMj-3S1tku0"
cover = "https://img.youtube.com/vi/VMj-3S1tku0/maxresdefault.jpg"
+++

## Overview

This video offers a transparent, ground-up walkthrough of neural network training by building an automatic differentiation engine (micrograd) from scratch, exposing every detail of forward and backward passes. By eschewing black-box abstractions, it demystifies backpropagation and neural network internals, making the mechanics and intuition accessible to practitioners and learners alike.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Karpathy's approach is radically hands-on: he constructs an autograd engine (micrograd) in a blank Jupyter notebook, narrating every step and decision. Unlike most tutorials, he avoids prebuilt frameworks, instead exposing the raw mechanics of computation graphs, chain rule application, and gradient flow at the scalar level. This 'from first principles' methodology emphasizes intuition and transparency over convenience.

### The Core Problem
Most deep learning practitioners rely on high-level libraries (like PyTorch or TensorFlow) that obscure the underlying mechanics of backpropagation and autograd. This opacity can hinder true understanding and debugging. The video addresses the need for a clear, intuitive grasp of how gradients are computed and how neural networks learn at the most granular level.

### The Solution Approach
The methodology involves incrementally building a minimalistic autograd engine (micrograd) that supports scalar-valued operations and constructs a computation graph dynamically as mathematical expressions are composed. Each Value object tracks its data, gradient, and pointers to its parents, enabling both forward evaluation and recursive backward propagation via the chain rule. Manual backpropagation is demonstrated step-by-step, including gradient nudging and verification. The approach then scales up to model a single neuron and, by extension, multilayer perceptrons, always keeping the mechanics explicit.

### Key Insights
- Neural networks are just mathematical expressions—backpropagation is a general-purpose algorithm for computing gradients through any computation graph, not just neural nets.
- Building autograd at the scalar level (rather than tensor level) exposes the atomic mechanics of gradient flow, making the chain rule's application fully transparent.
- Manual verification of gradients by finite differences (nudging inputs and observing output changes) is a powerful tool for debugging and intuition-building.

### Concepts & Definitions
- "Autograd" is defined as an engine for automatic differentiation, specifically for computing gradients via backpropagation.
- "Backpropagation" is framed as a recursive application of the chain rule through a dynamically constructed computation graph.
- A "computation graph" is described as a set of Value objects connected by operations, each maintaining pointers to its parents and children.
- "Neuron" is modeled as a weighted sum of inputs plus bias, passed through a nonlinearity (e.g., tanh), with all operations tracked for gradient computation.

### Technical Details & Implementation
- Each scalar value is wrapped in a Value object that stores its data, gradient, and references to its parents and the operation that produced it.
- The computation graph is constructed dynamically as Value objects are combined via supported operations (add, multiply, power, etc.), with each operation defining its local derivative.
- Backward propagation is implemented as a recursive traversal of the computation graph, multiplying local gradients (from each operation) by the upstream gradient, in accordance with the chain rule.
- The engine is scalar-based (not vectorized), which simplifies the logic and makes each step of gradient computation explicit and debuggable.

### Tools & Technologies
- micrograd (custom autograd engine built from scratch)
- Jupyter Notebook (for interactive development and demonstration)
- PyTorch (referenced for comparison and for showing how to register custom functions)

### Contrarian Takes & Different Approaches
- Contrasts with the common practice of teaching neural networks through high-level abstractions, advocating for a 'first principles' approach.
- Challenges the notion that autograd engines must be complex or opaque—demonstrates that a minimal, scalar-based system can be both educational and powerful.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- To deeply understand backpropagation, implement a scalar-based autograd engine from scratch and manually verify gradients via finite differences.
- When debugging neural network training, inspect the computation graph and gradients at the most granular level to catch subtle errors.
- Register custom operations in PyTorch by subclassing and defining both forward and backward methods, using the same principles demonstrated in micrograd.

### What to Avoid
- Relying solely on high-level frameworks can obscure critical bugs or misunderstandings about gradient flow and computation graph construction.
- Attempting to vectorize or optimize too early can hide the core mechanics and make debugging more difficult.
- Real-world frameworks (like PyTorch) have complex, device-specific backward kernels that are much harder to trace than a minimalistic engine.

### Best Practices
- Start with scalar-level implementations to build intuition before moving to tensor-based or production-grade frameworks.
- Always verify gradients numerically (finite differences) when building or modifying autograd systems.
- Build computation graphs dynamically and ensure each operation tracks its parents and local gradients for full traceability.

### Personal Stories & Experiences
- Start with scalar-level implementations to build intuition before moving to tensor-based or production-grade frameworks.
- Always verify gradients numerically (finite differences) when building or modifying autograd systems.
- Build computation graphs dynamically and ensure each operation tracks its parents and local gradients for full traceability.

### Metrics & Examples
- Demonstrates that the derivative of output g with respect to input a is 138, and with respect to b is 645, showing how small nudges in inputs affect outputs.
- Manual gradient verification: nudging a by h and observing the change in output matches the computed gradient.
- Shows a single optimization step (nudging inputs in the direction of the gradient) increases the target value as expected.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=VMj-3S1tku0)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
