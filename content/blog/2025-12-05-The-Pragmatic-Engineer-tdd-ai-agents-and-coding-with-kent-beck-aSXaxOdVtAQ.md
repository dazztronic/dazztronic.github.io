+++
title = "TDD, AI agents and coding with Kent Beck"
date = 2025-12-05
draft = false

[taxonomies]
author = ["The Pragmatic Engineer"]
categories = ["Software engineering--Artificial intelligence","Software testing","Agile software development"]
tags = ["Test-Driven Development","AI coding assistants","xUnit","SonarQube","Immutable annotations","Code quality","Extreme Programming"]

[extra]
excerpt = "Kent Beck explores the intersection of Test-Driven Development (TDD) and AI coding agents, revealing how traditional testing philosophies must adapt when collaborating with unpredictable, generative tools. He shares hard-won lessons from decades of software engineering, emphasizing the need for immutable test expectations and a willingness to discard more code as experimentation accelerates. Beck's perspective matters because it bridges foundational software practices with the rapidly evolving landscape of AI-assisted development."
video_url = "https://www.youtube.com/watch?v=aSXaxOdVtAQ"
video_id = "aSXaxOdVtAQ"
cover = "https://img.youtube.com/vi/aSXaxOdVtAQ/maxresdefault.jpg"
+++

## Overview

Kent Beck explores the intersection of Test-Driven Development (TDD) and AI coding agents, revealing how traditional testing philosophies must adapt when collaborating with unpredictable, generative tools. He shares hard-won lessons from decades of software engineering, emphasizing the need for immutable test expectations and a willingness to discard more code as experimentation accelerates. Beck's perspective matters because it bridges foundational software practices with the rapidly evolving landscape of AI-assisted development.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Beck treats AI coding assistants as 'unpredictable genies'—powerful but prone to misunderstanding intent—requiring a rigorous, immutable test suite as a guardrail. His methodology fuses TDD discipline with a high-velocity, experimental workflow enabled by AI, advocating for relentless trial, error, and code disposal. He uniquely frames the AI-human collaboration as a dialogue, not a monologue, and insists on immutable annotations in tests to prevent AI from 'fixing' the test instead of the code.

### The Core Problem
The challenge is maintaining code correctness and intent when working with AI agents that can rapidly generate or modify code but may not fully grasp nuanced requirements. As AI tools accelerate development, the risk of inadvertently breaking or diluting core logic increases, especially if tests are mutable or interpreted loosely.

### The Solution Approach
Beck's approach is to maintain a large, fast-running, and immutable test suite (e.g., 300ms for all tests) that acts as a non-negotiable contract with the AI agent. He advocates for explicit, unchangeable expected values in tests—'immutable annotations'—so that the AI cannot simply alter the test to make the code pass. He treats the AI as a collaborator that must be constrained by clear, enforced boundaries, and he encourages frequent, fearless code disposal as the cost of experimentation drops.

### Key Insights
- Immutable test expectations are critical when working with AI agents; otherwise, the AI may 'fix' the test instead of the code, eroding correctness.
- The velocity of AI-assisted coding means organizations must normalize throwing away far more code—completed experiments should be celebrated, not mourned.
- Physical and social context (e.g., team seating, lighting, acoustics) has outsized leverage on software outcomes—often more than technical optimizations.

### Concepts & Definitions
- TDD (Test-Driven Development): A methodology where tests are written before code, serving as both specification and regression suite.
- Immutable annotation: A test expectation that is explicitly marked as correct and must not be changed, serving as a contract with the AI agent.
- Conversational process: Beck's preferred framing for software development as an ongoing dialogue (not a monologue) between human and system (or AI), iteratively refining outcomes.

### Technical Details & Implementation
- All tests should run in under 300 milliseconds to enable constant feedback and rapid iteration.
- Tests must include immutable annotations—explicit, unchangeable expected values—to prevent AI from mutating test intent.
- Combining TDD frameworks (e.g., xUnit style) with AI coding assistants, ensuring the AI is always checked by a rigorous test harness.

### Tools & Technologies
- AI coding assistants (e.g., GitHub Copilot, Amazon Q Developer, Google Gemini Code Assist)
- TDD frameworks (e.g., xUnit in Smalltalk)
- SonarQube for code quality and assurance

### Contrarian Takes & Different Approaches
- Beck rejects the notion that better up-front specification (waterfall) solves project failure, advocating instead for iterative, conversational development.
- He argues that the dilution of 'Agile' was predictable and that the original intent was a dynamic, conversational process—not rigid methodology.
- He insists that code quality and correctness cannot be delegated to AI alone; immutable human intent must be enforced via tests.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Enforce immutability in your test suite—explicitly annotate expected values and prevent AI or humans from altering them without deep review.
- Optimize your test suite to run in hundreds of milliseconds, enabling constant, rapid feedback during AI-assisted coding.
- Treat code as disposable—run many experiments, keep only what works, and reward teams for completed (even discarded) experiments.

### What to Avoid
- Allowing AI agents to modify tests to fit generated code undermines the purpose of testing and erodes code correctness.
- Neglecting the physical and social environment of teams can sabotage even technically sound projects.
- Failing to adapt to the increased volume of code artifacts generated by AI leads to technical debt and missed opportunities.

### Best Practices
- Maintain a fast, comprehensive, and immutable test suite as a safety net for AI-driven code changes.
- Foster a culture where discarding code is normalized and celebrated as part of the experimental process.
- Pay close attention to team dynamics and workspace setup as high-leverage factors in project success.

### Personal Stories & Experiences
- Maintain a fast, comprehensive, and immutable test suite as a safety net for AI-driven code changes.
- Foster a culture where discarding code is normalized and celebrated as part of the experimental process.
- Pay close attention to team dynamics and workspace setup as high-leverage factors in project success.

### Metrics & Examples
- A full test suite running in 300 milliseconds enables constant feedback loops.
- Teams should expect to generate 10x more code artifacts with AI, but only keep a fraction—celebrating 8 completed experiments in a week, even if only one is retained.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=aSXaxOdVtAQ)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
