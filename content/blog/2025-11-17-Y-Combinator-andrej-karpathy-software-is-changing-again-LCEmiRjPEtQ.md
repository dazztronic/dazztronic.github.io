+++
title = "Andrej Karpathy: Software Is Changing (Again)"
date = 2025-11-17
draft = false

[taxonomies]
author = ["Y Combinator"]
categories = ["Software engineering--Artificial intelligence","Natural language processing","Human-computer interaction"]
tags = ["Large language models","Prompt engineering","Software 3.0","Hugging Face","GitHub","Model Atlas","Context window","Prompt injection","Deep wiki"]

[extra]
excerpt = "Andrej Karpathy presents a paradigm-shifting view of software evolution, arguing that we are entering a new era—Software 3.0—where programming is done in natural language via large language models (LLMs). This matters because it fundamentally redefines what it means to write software, democratizing access and requiring a rethinking of infrastructure, workflows, and mental models for both new and experienced engineers."
video_url = "https://www.youtube.com/watch?v=LCEmiRjPEtQ"
video_id = "LCEmiRjPEtQ"
cover = "https://img.youtube.com/vi/LCEmiRjPEtQ/maxresdefault.jpg"
+++

## Overview

Andrej Karpathy presents a paradigm-shifting view of software evolution, arguing that we are entering a new era—Software 3.0—where programming is done in natural language via large language models (LLMs). This matters because it fundamentally redefines what it means to write software, democratizing access and requiring a rethinking of infrastructure, workflows, and mental models for both new and experienced engineers.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Karpathy's distinctive framework segments software history into three eras: Software 1.0 (explicit code), Software 2.0 (neural network weights), and now Software 3.0 (prompt-based programming in English). He uniquely frames LLMs as 'programmable computers' where prompts are the new code, and emphasizes the psychological analogy—LLMs as 'people spirits' with humanlike strengths and deficits. He also flips the standard technology adoption curve, noting that LLMs reached consumers before governments or corporations.

### The Core Problem
The central challenge is adapting to the rapid, foundational shift in how software is created and operated, as LLMs become ubiquitous and programmable by anyone with natural language. This creates a need to rewrite vast amounts of legacy code and retool infrastructure to accommodate new programming paradigms and the unique quirks of LLMs.

### The Solution Approach
Karpathy advocates for meeting LLMs 'halfway' by restructuring digital resources (e.g., code repositories, documentation) to be more accessible to LLMs, leveraging tools that transform codebases into LLM-friendly formats. He recommends rapid iteration cycles—building partial, tunnelled products and quickly spinning feedback loops between human and LLM. He also stresses the importance of understanding LLMs' cognitive limitations (e.g., context window, amnesia) and designing workflows that compensate for these, rather than expecting LLMs to behave like traditional software or human collaborators.

### Key Insights
- Software is undergoing its most fundamental change in 70 years, with LLMs enabling programming in natural language.
- LLMs are not just classifiers or static models; they are programmable computers, and prompts are now the primary programming interface.
- Unlike previous technology waves, LLMs reached consumers first, reversing the typical government/corporate-first adoption pattern.
- LLMs have superhuman memory and knowledge but suffer from cognitive deficits like hallucination, jagged intelligence, and lack of persistent learning.
- Infrastructure and workflows must be rethought to accommodate LLMs' unique strengths and weaknesses.

### Concepts & Definitions
- Software 1.0: Traditional code written by humans for computers.
- Software 2.0: Neural network weights trained via data and optimizers, not directly coded.
- Software 3.0: Programming computers via natural language prompts to LLMs.
- LLMs as 'people spirits': Stochastic simulations of human psychology, with both superhuman and subhuman traits.
- Context window: The working memory of an LLM, analogous to short-term memory in humans.

### Technical Details & Implementation
- Using tools like 'map of GitHub' and Hugging Face Model Atlas to visualize and manage the new landscape of code and models.
- Transforming code repositories for LLM consumption by concatenating files and generating structured documentation (e.g., via 'get ingest' or 'deep wiki').
- Prompt engineering as the new programming—using few-shot prompts and English instructions to direct LLM behavior.
- Recognizing the context window as LLMs' working memory and explicitly managing it in application design.

### Tools & Technologies
- Map of GitHub (for visualizing codebases)
- Hugging Face (model repository for Software 2.0/3.0)
- Model Atlas
- get ingest (for transforming GitHub repos for LLM input)
- deep wiki (for generating LLM-friendly documentation)

### Contrarian Takes & Different Approaches
- Contradicts the standard technology diffusion model by showing LLMs reached consumers before institutions.
- Challenges the notion that LLMs are just better classifiers, arguing they are a fundamentally new kind of computer.
- Advocates for embracing LLM quirks rather than forcing them into old software paradigms.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Restructure code and documentation to be easily ingestible by LLMs using tools that concatenate and analyze repositories.
- Adopt prompt engineering as a core skill—experiment with few-shot and English-language prompts to program LLMs.
- Design applications and workflows that explicitly manage LLM context windows and compensate for their lack of persistent learning.
- Rapidly iterate on LLM-powered products by spinning tight feedback loops between human input and LLM output.

### What to Avoid
- Do not assume LLMs will learn or adapt over time like human collaborators; they lack persistent memory and require explicit context management.
- Beware of LLM hallucinations and jagged intelligence—always validate outputs, especially in critical applications.
- Security risks: LLMs are susceptible to prompt injection and data leakage; handle sensitive information with care.

### Best Practices
- Meet LLMs halfway by making digital resources (code, docs) LLM-friendly.
- Leverage tools that automate the transformation of repositories for LLM consumption.
- Treat LLMs as fallible collaborators—design systems that monitor, validate, and supplement their outputs.
- Iterate quickly with partial products and tight feedback cycles.

### Personal Stories & Experiences
- Meet LLMs halfway by making digital resources (code, docs) LLM-friendly.
- Leverage tools that automate the transformation of repositories for LLM consumption.
- Treat LLMs as fallible collaborators—design systems that monitor, validate, and supplement their outputs.
- Iterate quickly with partial products and tight feedback cycles.

### Metrics & Examples
- No specific quantitative metrics provided, but references to the scale of code/model repositories (e.g., GitHub, Hugging Face) and the rapid, global adoption of LLMs.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=LCEmiRjPEtQ)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
