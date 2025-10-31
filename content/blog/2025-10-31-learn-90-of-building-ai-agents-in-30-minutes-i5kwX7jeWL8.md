+++
title = "Learn 90% of Building AI Agents in 30 Minutes"
date = 2025-10-31
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Artificial intelligence","Software engineering--Artificial intelligence","Computer programming"]
tags = ["AI agents","System prompt engineering","OpenRouter","Mistral 3.1","Qwen 3","LLM selection","Rapid prototyping","Prompt evaluation","Iterative development"]

[extra]
excerpt = "Cole Medin distills the process of building AI agents down to its essential components, advocating for simplicity and rapid iteration over perfectionism. His approach empowers both beginners and experienced developers to focus on the 90% that matters for proof-of-concept agents, sidestepping common traps of overengineering and analysis paralysis."
video_url = "https://www.youtube.com/watch?v=i5kwX7jeWL8"
video_id = "i5kwX7jeWL8"
cover = "https://img.youtube.com/vi/i5kwX7jeWL8/maxresdefault.jpg"
+++

## Overview

Cole Medin distills the process of building AI agents down to its essential components, advocating for simplicity and rapid iteration over perfectionism. His approach empowers both beginners and experienced developers to focus on the 90% that matters for proof-of-concept agents, sidestepping common traps of overengineering and analysis paralysis.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's distinctive methodology is a ruthless focus on simplicity: he champions building a functional agent quickly by ignoring advanced concerns (like prompt evaluations, split testing, or perfect LLM selection) until after a working prototype exists. His '90% rule' reframes agent development as an iterative, low-friction process, not a quest for initial perfection.

### The Core Problem
Many aspiring agent builders get bogged down by the overwhelming array of choices—LLM selection, prompt engineering, tool integration, security, and deployment—leading to stalled projects and lost momentum. This is especially problematic as the AI landscape evolves rapidly, making early perfectionism counterproductive.

### The Solution Approach
Medin advocates a stepwise, minimalistic workflow: (1) Start with a basic agent using a system prompt template (persona/goals, tool instructions, output format, misc), (2) Use platforms like OpenRouter to easily swap LLMs without commitment, (3) Avoid advanced optimizations or evaluations until the core agent works, (4) Iterate manually, refining only after the agent delivers value. This approach is grounded in his experience building hundreds of agents and observing thousands more.

### Key Insights
- Iterative simplicity trumps initial perfection—most successful agents start basic and evolve based on real feedback.
- Choosing the 'perfect' LLM up front is a waste; platforms like OpenRouter make swapping trivial, so focus on functionality first.
- System prompt overengineering is a common trap; a simple, reusable template covers 90% of use cases.
- Manual testing and high-level refinement are sufficient for early-stage agents; elaborate prompt evaluations can wait.
- RAM is the only local resource needed for most agent prototypes if using third-party LLM APIs—front-end and agent logic remain lightweight.

### Concepts & Definitions
- "System prompt" is framed as the top-level instruction set for the agent, broken into modular categories for clarity and reuse.
- "Proof of concept" is defined as a working agent that demonstrates value without full production polish.
- "Prompt evaluation" and "split testing" are described as advanced optimization steps, not necessary for initial builds.

### Technical Details & Implementation
- System prompt template includes: persona/goals, tool instructions/examples, output format, miscellaneous instructions.
- OpenRouter is recommended for rapid LLM iteration, supporting Grok, Anthropic, Gemini, GPT, Qwen, and open-source models.
- For local models, Mistral 3.1 and Qwen 3 are suggested for privacy or cost-sensitive scenarios.
- No need for complex infrastructure—just enough RAM and API access to LLM providers.
- Manual, high-level prompt refinement replaces automated prompt evaluation in early stages.

### Tools & Technologies
- OpenRouter (for LLM routing and experimentation)
- Mistral 3.1 (local LLM)
- Qwen 3 (local LLM)
- Anthropic, Gemini, Grok, GPT (various LLM providers)

### Contrarian Takes & Different Approaches
- Contradicts the common wisdom that LLM selection and prompt engineering must be perfect from the start.
- Challenges the belief that advanced evaluation and split testing are necessary for early-stage agents.
- Advocates for manual, high-level refinement over automated optimization in the proof-of-concept phase.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start with a basic system prompt template and fill in only essential details.
- Use OpenRouter or similar platforms to iterate on LLM choice without friction.
- Avoid advanced prompt engineering or model evaluations until after the agent works.
- Manually test and refine the agent at a high level before considering automation or scaling.
- Focus on getting a working prototype running with minimal local resources.

### What to Avoid
- Don't get stuck trying to pick the perfect LLM at the outset; it's a premature optimization.
- Avoid overcomplicating system prompts—complexity early on slows progress and adds little value.
- Resist the urge to implement advanced evaluation or split testing before the agent is functional.
- Perfectionism is the enemy of momentum; waiting for the 'perfect' setup leads to stalled projects.

### Best Practices
- Reuse a modular system prompt template for all agents to speed up development.
- Iterate quickly by leveraging LLM routing platforms for model experimentation.
- Keep infrastructure minimal—use cloud LLM APIs and only scale up when necessary.
- Refine agent instructions manually in the early stages, automating only after value is proven.

### Personal Stories & Experiences
- Reuse a modular system prompt template for all agents to speed up development.
- Iterate quickly by leveraging LLM routing platforms for model experimentation.
- Keep infrastructure minimal—use cloud LLM APIs and only scale up when necessary.
- Refine agent instructions manually in the early stages, automating only after value is proven.

### Metrics & Examples
- No specific quantitative metrics are cited, but references to 'hundreds' of personal agent builds and 'thousands' observed provide scale.
- Mentions that RAM is the only local resource needed for most agent prototypes.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=i5kwX7jeWL8)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** contrarian wisdom
