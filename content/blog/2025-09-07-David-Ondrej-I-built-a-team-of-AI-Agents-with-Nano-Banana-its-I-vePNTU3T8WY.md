+++
title = "I built a team of AI Agents with Nano Banana (it’s I-N-S-A-N-E)"
date = 2025-09-07
draft = false

[taxonomies]
author = ["David Ondrej"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Artificial intelligence", "Image processing--Artificial intelligence", "Multi-agent systems"]

[extra]
excerpt = "David Ondrej reframes Nano Banana not just as a state-of-the-art image model, but as a foundation for building practical, multi-agent AI systems that anyone—even beginners—can deploy. His perspective stands out for its relentless focus on actionable, minimalistic engineering and leveraging the model's agentic capabilities, rather than just its image generation prowess."
video_url = "https://www.youtube.com/watch?v=vePNTU3T8WY"
video_id = "vePNTU3T8WY"
cover = "https://img.youtube.com/vi/vePNTU3T8WY/maxresdefault.jpg"
+++

## Overview

David Ondrej reframes Nano Banana not just as a state-of-the-art image model, but as a foundation for building practical, multi-agent AI systems that anyone—even beginners—can deploy. His perspective stands out for its relentless focus on actionable, minimalistic engineering and leveraging the model's agentic capabilities, rather than just its image generation prowess.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
David's approach is distinctive in that he moves beyond showcasing Nano Banana's image quality, instead demonstrating how to orchestrate teams of AI agents powered by the model for real-world applications. He emphasizes minimal code, raw Python, and agentic workflows, advocating for simplicity and directness over feature bloat or unnecessary dependencies.

### The Core Problem
Most practitioners focus solely on the capabilities of new AI models in isolation, missing the opportunity to build agentic systems that can perform complex, coordinated tasks. David addresses the gap between model demos and deployable, multi-agent solutions that are accessible to non-experts.

### The Solution Approach
David's methodology is to treat Nano Banana as a decision-making agent (not just a generator), leveraging its Gemini heritage for both text and image outputs. He constructs a lightweight Flask-based Python app, orchestrating multiple API calls to create a team of agents, each handling a distinct task. He stresses reducing code complexity by instructing the model to minimize lines of code, resulting in maintainable, modular systems.

### Key Insights
- Nano Banana's true power is in agentic, multi-step workflows, not just image generation.
- Explicitly prompting for minimal code yields cleaner, more robust implementations—AI models tend to over-engineer unless guided.
- You can build production-ready agentic systems with just two code files and an environment file, avoiding dependency sprawl.

### Concepts & Definitions
- "Agentic actions": The model's ability to not only generate outputs but also make decisions and take steps autonomously.
- "Feature bloat": Unnecessary code or dependencies that complicate maintenance and increase failure points.
- "Consistency in image editing": The model's unique ability to make precise, repeatable edits without unintended artifacts.

### Technical Details & Implementation
- Uses Flask as a lightweight Python UI framework for rapid prototyping.
- Runs multiple OpenRouter API calls in parallel, each returning a separate PNG file for agentic task separation.
- Recommends using raw Python due to model training data abundance and simplicity.
- Environment isolation via conda to prevent package conflicts.

### Tools & Technologies
- Nano Banana (Google's image model, Gemini-based)
- Vectal.ai (platform for free Nano Banana access)
- Flask (Python web framework)
- OpenRouter API
- Conda (environment management)

### Contrarian Takes & Different Approaches
- Challenges the norm of focusing on model demos—insists the real value is in building agentic systems.
- Argues that more code is not better; minimalism is often superior for both function and maintainability.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Prompt your AI model to minimize code lines for simpler, more maintainable implementations.
- Use Flask and raw Python to quickly prototype agentic systems without dependency bloat.
- Leverage Vectal.ai for free access to Nano Banana and experiment with multi-agent workflows.

### What to Avoid
- Avoid letting AI models generate unnecessarily verbose or complex code—always specify simplicity.
- Don't overload your project with dependencies; stick to essentials to reduce bugs and maintenance overhead.
- Beware of treating advanced models as mere generators—unlock their agentic potential.

### Best Practices
- Keep codebases minimal (two files plus environment) for clarity and ease of iteration.
- Isolate environments for each project to prevent conflicts.
- Explicitly instruct AI models on desired code characteristics (e.g., brevity, modularity).

### Personal Stories & Experiences
- David shares his surprise at how little code is needed to build a robust agentic system, challenging his own assumptions about necessary complexity.
- He recounts how user feedback (requests for full-screen chat) directly shaped product features, highlighting a user-driven development mindset.

### Metrics & Examples
- Demonstrates four parallel API calls, each producing a separate PNG, as a practical example of multi-agent orchestration.
- Highlights that even the free plan on Vectal.ai allows users to experiment with Nano Banana at no cost.

## Resources & Links

- [https://www.vectal.ai/](https://www.vectal.ai/)
- [https://www.skool.com/new-society](https://www.skool.com/new-society)
- [https://www.instagram.com/davidondrej1/](https://www.instagram.com/davidondrej1/)
- [https://x.com/DavidOndrej1](https://x.com/DavidOndrej1)
- [https://whop.com/davidondrej](https://whop.com/davidondrej)
- [https://www.hostinger.com/david](https://www.hostinger.com/david)
- [Video URL](https://www.youtube.com/watch?v=vePNTU3T8WY)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

