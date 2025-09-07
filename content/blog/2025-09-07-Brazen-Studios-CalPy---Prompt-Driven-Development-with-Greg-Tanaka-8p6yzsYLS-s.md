+++
title = "CalPy - Prompt Driven Development with Greg Tanaka"
date = 2025-09-07
draft = false

[taxonomies]
author = ["Brazen Studios"]
categories = ["Software engineering--Artificial intelligence"]
tags = ["Software engineering--Artificial intelligence", "Prompt engineering", "Software testing"]

[extra]
excerpt = "Greg Tanaka and Brazen Studios champion 'Prompt Driven Development'—a hands-on, pragmatic approach to leveraging AI coding tools like CalPy and Cloud Code for rapid prototyping and iterative software creation. Their perspective stands out for its insistence on controlling AI-generated code randomness and integrating prompt engineering directly into the developer workflow, making AI a reliable coding partner rather than a black box."
video_url = "https://www.youtube.com/watch?v=8p6yzsYLS-s"
video_id = "8p6yzsYLS-s"
cover = "https://img.youtube.com/vi/8p6yzsYLS-s/maxresdefault.jpg"
+++

## Overview

Greg Tanaka and Brazen Studios champion 'Prompt Driven Development'—a hands-on, pragmatic approach to leveraging AI coding tools like CalPy and Cloud Code for rapid prototyping and iterative software creation. Their perspective stands out for its insistence on controlling AI-generated code randomness and integrating prompt engineering directly into the developer workflow, making AI a reliable coding partner rather than a black box.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Their distinctive approach is the rigorous, side-by-side evaluation of AI coding tools using real-world prompts, with a focus on transparency, reproducibility, and minimizing unpredictability in generated code. They treat prompts as first-class citizens in the development process, emphasizing the need for deterministic, testable outputs and integrating prompt logs as a core part of the codebase.

### The Core Problem
The main problem addressed is the unpredictability and potential chaos of AI-generated code ('grenade code') in production environments. This is critical as AI coding assistants become more prevalent, and teams need reliable, auditable, and maintainable code rather than opaque, one-off generations.

### The Solution Approach
They advocate for a workflow where prompts are explicitly versioned and logged, tests are separated from code regeneration, and outputs are compared across tools in live demos. Their methodology involves crafting precise prompts, running them through multiple AI coding tools, and analyzing both the code and the process for determinism and reliability. They stress the importance of treating prompt logs like log files—growing, auditable artifacts that document the evolution of the codebase.

### Key Insights
- Prompt engineering is not just about getting code to work—it's about making AI outputs reproducible and safe for production.
- Contrarian take: Most developers treat AI code as disposable; they argue it must be versioned and tested like any other artifact.
- Personal lesson: Live demos reveal the brittleness of AI tools and the necessity of robust prompt and output management.

### Concepts & Definitions
- Prompt Driven Development: Treating prompts as primary development artifacts, not just ephemeral queries.
- Grenade code: Unpredictable, untested AI-generated code that can destabilize a codebase.
- Prompt log: An append-only record of prompts and their generated outputs, serving as an audit trail.

### Technical Details & Implementation
- Implementation involves copying prompts directly into tools like Cloud Code and CalPy, then comparing outputs for consistency.
- They recommend separating test files from code generation to ensure only code is regenerated, while tests serve as a persistent audit trail.
- Code patterns: Use prompt logs as append-only records, similar to log files, to track the evolution of code and prompts.

### Tools & Technologies
- CalPy (for prompt-driven code generation and workflow management)
- Cloud Code (as a benchmark for AI coding tools)
- Cursor and Windsurf (other AI coding tools, compared for quality)

### Contrarian Takes & Different Approaches
- Disagrees with the view that AI-generated code is inherently disposable; insists it must be managed like any other code artifact.
- Challenges the trend of integrating AI code without audit trails or prompt versioning.
- Advocates for prompt logs as essential, not optional, in professional AI development.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Always log and version your prompts alongside your code to ensure reproducibility.
- Separate test artifacts from code generation to maintain a clear audit trail.
- Perform head-to-head tool comparisons with real prompts to evaluate reliability and output quality.

### What to Avoid
- Do not allow AI-generated code to enter production without deterministic prompts and output validation.
- Avoid treating AI code as a black box—lack of prompt/version control leads to chaos.
- Beware of regenerating tests alongside code, which can erase your audit trail.

### Best Practices
- Maintain an append-only prompt log for every code generation session.
- Use live demos and real prompts to stress-test AI coding tools before adoption.
- Treat prompt engineering as a core software engineering discipline, not an afterthought.

### Personal Stories & Experiences
- Greg shares the anxiety of live demos, highlighting the unpredictability of AI tools and the importance of robust workflows.
- They recount being in meetings all day and not having time to test, underscoring the need for reliable, repeatable AI outputs.
- Evolution: Moved from ad-hoc prompt usage to systematic prompt logging and output comparison after encountering brittle AI code.

### Metrics & Examples
- Compares tools like Cloud Code, Cursor, and Windsurf, stating Cloud Code is 'the best one out there' for prompt-driven coding.
- References Python list insertion quiz as a micro-example of code boundary testing.

## Resources & Links

- [https://pypi.org/project/pdd-cli/](https://pypi.org/project/pdd-cli/)
- [https://github.com/promptdriven/pdd](https://github.com/promptdriven/pdd)
- [https://www.youtube.com/@PromptDrivenDevelopment](https://www.youtube.com/@PromptDrivenDevelopment)
- [https://x.com/gregtanaka](https://x.com/gregtanaka)
- [http://calpy.org](http://calpy.org)
- [https://www.facebook.com/CaliforniaPython](https://www.facebook.com/CaliforniaPython)
- [https://www.facebook.com/groups/calpy](https://www.facebook.com/groups/calpy)
- [https://www.meetup.com/californiapython](https://www.meetup.com/californiapython)
- [https://www.x.com/__CalPy__](https://www.x.com/__CalPy__)
- [https://woodyhooten.com](https://woodyhooten.com)
- [Video URL](https://www.youtube.com/watch?v=8p6yzsYLS-s)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

