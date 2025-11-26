+++
title = "The spelled-out intro to language modeling: building makemore"
date = 2025-11-26
draft = false

[taxonomies]
author = ["Andrej Karpathy"]
categories = ["Artificial intelligence","Machine learning","Natural language processing","Software engineering--Artificial intelligence"]
tags = ["Language modeling","Character-level models","Bi-gram models","PyTorch","Jupyter Notebook","Neural networks","Negative log likelihood","Broadcasting","Sampling","Data preprocessing"]

[extra]
excerpt = "This video delivers a hands-on, step-by-step construction of a character-level language model from scratch, demystifying the inner workings of models like GPT-2 by starting with the simplest possible bi-gram model and gradually increasing complexity. The approach is uniquely transparent: every line of code and mathematical operation is explained, with a focus on intuition, pitfalls, and the reasoning behind each design choice. The result is a rare, ground-up mental model of language modeling that empowers practitioners to truly understand, not just use, modern neural architectures."
video_url = "https://www.youtube.com/watch?v=PaCmpygFfXo"
video_id = "PaCmpygFfXo"
cover = "https://img.youtube.com/vi/PaCmpygFfXo/maxresdefault.jpg"
+++

## Overview

This video delivers a hands-on, step-by-step construction of a character-level language model from scratch, demystifying the inner workings of models like GPT-2 by starting with the simplest possible bi-gram model and gradually increasing complexity. The approach is uniquely transparent: every line of code and mathematical operation is explained, with a focus on intuition, pitfalls, and the reasoning behind each design choice. The result is a rare, ground-up mental model of language modeling that empowers practitioners to truly understand, not just use, modern neural architectures.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Karpathy's methodology is radically explicit and incremental: he builds language models from a blank notebook, spelling out every step, from data loading to matrix broadcasting, and insists on deep understanding of each operation before moving forward. Unlike most tutorials that rely on high-level libraries or pre-built models, this approach reconstructs the entire modeling pipeline, including manual count-based models and neural network equivalents, to reveal their equivalence and the underlying statistical logic.

### The Core Problem
How can one truly understand and implement language models—not just use them as black boxes—by reconstructing their logic from the ground up? In an era where most practitioners rely on opaque, pre-trained models, this approach addresses the gap in foundational intuition and practical skills needed to build, debug, and extend language models for novel applications.

### The Solution Approach
The process begins with loading a dataset of 32,000 names, treating each as a sequence of characters, and extracting statistical relationships (bi-grams) between characters. The methodology involves first building a count-based bi-gram model, then translating this into a neural network framework, and finally demonstrating their equivalence both in output and in loss minimization. Every transformation—such as normalization via broadcasting—is dissected, and the reasoning behind each operation is explained, including the mathematical and programming nuances (e.g., PyTorch broadcasting rules). The approach is iterative: start simple, validate understanding, then incrementally add complexity (eventually reaching transformers).

### Key Insights
- A single word in the dataset encodes multiple training examples: every character transition (and the end-of-word signal) is a data point for the model.
- Count-based models and neural network models can be mathematically equivalent at the bi-gram level, but neural networks offer extensibility for more complex patterns.
- Broadcasting in tensor operations is powerful but dangerous; understanding its semantics is essential to avoid subtle bugs.

### Concepts & Definitions
- Character-level language model: a model that predicts the next character in a sequence, treating text as sequences of individual characters.
- Bi-gram model: a statistical model that predicts the next character based solely on the previous character.
- Broadcasting (in PyTorch): a set of rules for performing element-wise operations on tensors of different shapes by automatically expanding dimensions as needed.
- Negative log likelihood loss: a loss function measuring how well the predicted probability distribution matches the observed data, commonly used in classification tasks.

### Technical Details & Implementation
- Dataset is loaded as a list of strings via Python, split by lines.
- Bi-gram statistics are computed using a 27x27 count matrix (for 26 letters plus end-of-word), normalized row-wise to yield transition probabilities.
- PyTorch broadcasting is used to normalize matrices; explicit attention is paid to tensor shapes (27x27 vs 27x1 vs 27) and the implications for division.
- Sampling from the model involves starting at a special start token, then iteratively sampling next characters from the learned probability distribution until the end token is reached.
- Two training approaches are implemented: direct frequency counting and gradient-based optimization using negative log likelihood loss.

### Tools & Technologies
- Python (for data loading and manipulation)
- Jupyter Notebook (for interactive development)
- PyTorch (for tensor operations and neural network implementation)

### Contrarian Takes & Different Approaches
- Contradicts the common practice of jumping straight to deep neural networks by advocating for starting with explicit statistical models.
- Challenges the notion that neural networks are always more powerful or fundamentally different than classical models at the basic level.
- Defends the value of manual, step-by-step construction over reliance on high-level abstractions and pre-built libraries.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with the simplest possible model (bi-gram counts) to build intuition before moving to neural networks.
- Always check tensor shapes before performing operations like division; use explicit shape manipulations (e.g., keepdim=True) to ensure correct broadcasting.
- Validate model outputs at each step—sampling from the model is a practical way to check if the statistical logic is working as intended.

### What to Avoid
- Misunderstanding broadcasting rules in PyTorch can lead to silent, hard-to-detect bugs; always verify shapes and consult documentation.
- Assuming that neural network models are fundamentally different from count-based models at the simplest level is a misconception; they can be equivalent if not extended.
- Skipping the foundational steps (like manual counting and normalization) leads to fragile intuition and difficulty debugging more complex models.

### Best Practices
- Build models incrementally, validating each layer of abstraction before adding complexity.
- Use explicit, readable code to clarify each mathematical operation and data transformation.
- Treat every word in the dataset as a rich source of multiple training examples by extracting all possible character transitions.

### Personal Stories & Experiences
- Build models incrementally, validating each layer of abstraction before adding complexity.
- Use explicit, readable code to clarify each mathematical operation and data transformation.
- Treat every word in the dataset as a rich source of multiple training examples by extracting all possible character transitions.

### Metrics & Examples
- Dataset contains approximately 32,000 names, with shortest word length 2 and longest 15 characters.
- Bi-gram count matrix is 27x27, representing all possible character transitions including start and end tokens.
- Model evaluation uses negative log likelihood loss to quantify prediction quality.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=PaCmpygFfXo)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** fresh perspective
