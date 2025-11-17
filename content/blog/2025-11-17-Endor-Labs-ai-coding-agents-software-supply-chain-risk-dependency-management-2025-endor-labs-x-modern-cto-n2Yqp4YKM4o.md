+++
title = "AI Coding Agents & Software Supply Chain Risk | Dependency Management 2025 (Endor Labs x Modern CTO)"
date = 2025-11-17
draft = false

[taxonomies]
author = ["Endor Labs"]
categories = ["Software engineering--Security measures","Artificial intelligence--Software development","Computer software--Supply chain management"]
tags = ["Dependency management","Reachable vulnerability analysis","AI code generation","Provenance","Artifact signing","MCP servers","Open source software","Static analysis"]

[extra]
excerpt = "This conversation dives deep into the evolving risks and opportunities in software supply chains as AI coding agents become mainstream, focusing on dependency management and the unique security challenges posed by AI-generated code. The discussion stands out for its granular analysis of how AI models introduce new dependencies and versions, and for its actionable prioritization framework that slashes security noise by focusing only on vulnerabilities in actually used code paths."
video_url = "https://www.youtube.com/watch?v=n2Yqp4YKM4o"
video_id = "n2Yqp4YKM4o"
cover = "https://img.youtube.com/vi/n2Yqp4YKM4o/maxresdefault.jpg"
+++

## Overview

This conversation dives deep into the evolving risks and opportunities in software supply chains as AI coding agents become mainstream, focusing on dependency management and the unique security challenges posed by AI-generated code. The discussion stands out for its granular analysis of how AI models introduce new dependencies and versions, and for its actionable prioritization framework that slashes security noise by focusing only on vulnerabilities in actually used code paths.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Endor Labs' approach is distinctive in its laser focus on 'reachable vulnerability' analysis—using deep program analysis to map which parts of third-party dependencies are actually invoked by the application, then prioritizing security issues only in those areas. They uniquely extend this rigor to the AI-generated code context, emphasizing provenance, versioning, and the need to treat AI outputs as untrusted inputs requiring traceability and signing.

### The Core Problem
The proliferation of AI coding agents is accelerating the introduction of new dependencies and versions into software, massively increasing the attack surface and making traditional vulnerability management unmanageable due to sheer volume and lack of context. The core challenge is how to prioritize and secure this expanding, opaque supply chain without overwhelming engineering teams.

### The Solution Approach
Their methodology centers on deep static and program analysis to determine which functions in third-party dependencies are actually called by the application code. Only vulnerabilities in these 'reachable' code paths are prioritized for remediation. For AI-generated code, they advocate treating it as untrusted input, enforcing provenance (traceability of who/what generated code), and requiring artifact signing and attestation. They also recommend reviewing AI-suggested dependency versions and maintaining allow-lists until AI maturity improves.

### Key Insights
- Most vulnerabilities (90-95%) in dependencies are in code paths never actually used by the application—prioritizing only 'reachable' vulnerabilities yields the biggest security payoff.
- AI code generation introduces not just new code, but new dependencies and versions—often in ways not previously studied, making version suggestion a novel risk vector.
- Open-source communities rapidly amplify new trends (e.g., over 10,000 MCP servers released post-Anthropic announcement), creating both innovation and a chaotic, hard-to-secure ecosystem.

### Concepts & Definitions
- 'Reachable vulnerability' is defined as a security issue located in a code path that is actually invoked by the application, as opposed to vulnerabilities in unused parts of dependencies.
- Provenance in this context means the ability to trace who or what generated a piece of code, which repository it originated from, and how it entered the codebase.
- MCP servers refer to a new class of agentic systems (post-Anthropic) that act as middleware for AI agents, rapidly proliferating in open source.

### Technical Details & Implementation
- Deep program analysis maps function calls from first-party code to third-party dependencies, establishing 'reachability' boundaries.
- All vulnerabilities are discovered, but only those in reachable code paths are flagged as critical for remediation.
- For AI-generated artifacts, enforce artifact signing and attestation to ensure provenance and traceability.
- Maintain allow-lists for dependencies and versions, and require human review of AI-generated code until AI reliability improves.

### Tools & Technologies
- Endor Labs platform for application security and dependency analysis
- Integrated developer environments (IDEs) with AI agents
- MCP servers (Middleware for agentic AI systems)
- GitHub (for open source MCP server distribution)

### Contrarian Takes & Different Approaches
- Contrary to the industry norm of chasing every vulnerability, the team argues that only reachable vulnerabilities matter and should be prioritized.
- Rather than defaulting to importing large dependency sets, they advocate for generating small, bespoke code snippets with AI to minimize supply chain exposure.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Prioritize remediation only for vulnerabilities in code paths your application actually uses—implement deep program analysis to determine reachability.
- Treat all AI-generated code as untrusted input: require artifact signing, attestation, and maintain provenance records.
- Review and control dependency and version suggestions from AI agents; use allow-lists and human review until AI maturity increases.
- Consider generating small, needed functions with AI instead of importing large dependency sets, reducing supply chain risk.

### What to Avoid
- Do not attempt to remediate every vulnerability flagged by traditional tools—this leads to unmanageable noise and wasted effort.
- Blindly trusting AI-generated code or dependency suggestions without provenance or review can introduce undetected security risks.
- Neglecting to track who/what generated code (provenance) makes incident response and accountability impossible.

### Best Practices
- Use deep program analysis to establish which third-party code is actually used, and focus security efforts there.
- Enforce artifact signing and attestation for all code (especially AI-generated) to maintain traceability.
- Implement allow-lists for dependencies and versions, and require human review of AI-generated suggestions.

### Personal Stories & Experiences
- Use deep program analysis to establish which third-party code is actually used, and focus security efforts there.
- Enforce artifact signing and attestation for all code (especially AI-generated) to maintain traceability.
- Implement allow-lists for dependencies and versions, and require human review of AI-generated suggestions.

### Metrics & Examples
- In large companies, vulnerability counts can reach tens of thousands, but only 5-10% are in code paths actually used by the application.
- Over 10,000 MCP servers released on GitHub since November (post-Anthropic), with 1,000 new repositories in a single week in March.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=n2Yqp4YKM4o)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
