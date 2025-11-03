+++
title = "How to Build Trustworthy AI — Allie Howe"
date = 2025-11-03
draft = false

[taxonomies]
author = ["AI Engineer"]
categories = ["Artificial intelligence--Security measures","Artificial intelligence--Moral and ethical aspects","Machine learning--Operations","Computer security"]
tags = ["ML SecOps","AI red teaming","Runtime security","ModelScan","Prompt injection","Jailbreaks","Hugging Face","Regulatory compliance","ISO420001","EU AI Act","HIPAA","FDA guidelines","RAG","Python"]

[extra]
excerpt = "This talk delivers a pragmatic, security-first blueprint for building trustworthy AI, emphasizing that responsibility for AI failures falls squarely on implementers, not just vendors. By reframing trustworthy AI as the intersection of AI security (protecting the model from the world) and AI safety (protecting the world from the model), it provides a workflow that blends ML secops, AI red teaming, and runtime security. The approach is grounded in real-world incidents and regulatory shifts, making the advice urgent and actionable."
video_url = "https://www.youtube.com/watch?v=n6wHJDqlS1I"
video_id = "n6wHJDqlS1I"
cover = "https://img.youtube.com/vi/n6wHJDqlS1I/maxresdefault.jpg"
+++

## Overview

This talk delivers a pragmatic, security-first blueprint for building trustworthy AI, emphasizing that responsibility for AI failures falls squarely on implementers, not just vendors. By reframing trustworthy AI as the intersection of AI security (protecting the model from the world) and AI safety (protecting the world from the model), it provides a workflow that blends ML secops, AI red teaming, and runtime security. The approach is grounded in real-world incidents and regulatory shifts, making the advice urgent and actionable.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Howe's perspective is distinctive in its operationalization of trustworthy AI as a dual focus: AI security (external threats) and AI safety (internal harms), with a strong emphasis on runtime security ('shift right') over traditional 'shift left' paradigms. The methodology adapts DevSecOps to the realities of AI/ML workflows (ML SecOps), recognizing that data scientists and ML engineers operate outside classic CI/CD pipelines, and thus require new security models. The approach is deeply practical, advocating for continuous, layered defenses and leveraging open-source tools integrated into both pre-deployment and runtime environments.

### The Core Problem
The central problem is that AI systems are increasingly vulnerable to both adversarial attacks (like prompt injections and jailbreaks) and unintentional harms (biased or unsafe outputs), yet existing security and compliance frameworks are inadequate for the unique, non-deterministic nature of AI. With regulatory pressure mounting and public incidents on the rise, organizations risk reputational, legal, and financial fallout if they fail to proactively secure and monitor their AI deployments.

### The Solution Approach
The solution is a three-stage pipeline: (1) ML SecOps for model scanning and provenance checks during build, (2) AI red teaming for adversarial and safety testing pre-deployment, and (3) AI runtime security for real-time input/output validation and guardrails. This is underpinned by a mental model that separates 'how the world harms the AI' (security) from 'how the AI harms the world' (safety), and prioritizes runtime monitoring due to AI's non-deterministic, rapidly evolving threat landscape. The workflow is collaborative, involving product, engineering, and security teams, and leverages open-source tools like ModelScan and runtime APIs for scalable protection.

### Key Insights
- Responsibility for AI failures almost always falls on the deploying organization, not the model vendor, as evidenced by recent lawsuits and public incidents.
- Traditional DevSecOps is insufficient for AI; ML SecOps must account for unique ML workflows and the fact that data scientists often operate outside CI/CD.
- Runtime security is now critical ('shift right'), as prompt injection and jailbreak threats evolve too quickly for pre-deployment controls alone.
- Continuous AI red teaming not only uncovers vulnerabilities but also informs runtime guardrails and helps detect model backdoors by comparing LLM responses.
- Regulatory compliance (ISO420001, EU AI Act, HIPAA, FDA guidelines) is rapidly becoming non-optional, and trustworthy AI is foundational for unlocking advanced applications in sensitive domains like healthcare.

### Concepts & Definitions
- Trustworthy AI: The combination of AI security (defending the system from external threats) and AI safety (preventing the system from causing harm).
- AI Security: How external actors can harm your AI system (e.g., prompt injection, data leakage).
- AI Safety: How your AI system can harm the world (e.g., biased, unsafe, or inappropriate outputs).
- ML SecOps: Machine Learning Security Operations, an evolution of DevSecOps tailored for ML workflows and tools.
- AI Red Teaming: Systematic adversarial and safety testing of AI systems to uncover vulnerabilities and inform guardrails.

### Technical Details & Implementation
- ModelScan is used for static model scanning to detect unsafe operators or credential leaks before deployment; integrates with Hugging Face for automated checks.
- AI red teaming involves adversarial testing (prompt injections, jailbreaks) and safety testing (bias, inappropriate content), with results feeding into runtime guardrails.
- Runtime security is implemented via API integrations or Python modules that validate both prompts and model outputs, blocking unsafe or off-topic responses in real time.
- Architectural example: In-game AI agents (like Fortnite's Vader NPC) process user audio and context, with security layers to filter and monitor interactions for safety and compliance.

### Tools & Technologies
- ModelScan (static model vulnerability scanner, open source, Hugging Face integration)
- Hugging Face (model hosting and scanning integration)
- Databricks, Jupyter Notebooks (ML engineering environments outside traditional CI/CD)
- Python (for runtime security modules and API integration)

### Contrarian Takes & Different Approaches
- Contradicts the traditional 'shift left' security paradigm, arguing that 'shift right' (runtime security) is now more critical for AI.
- Challenges the notion that DevSecOps is sufficient for AI, advocating for a new ML SecOps model tailored to the unique workflows of data science and ML engineering.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Integrate model scanning tools like ModelScan before deploying any third-party or custom models, especially when pulling from public model zoos.
- Establish a continuous AI red teaming process to test for both adversarial (prompt injection, jailbreak) and safety (bias, inappropriate content) vulnerabilities.
- Prioritize implementing runtime security solutions that validate both inputs and outputs, blocking unsafe prompts or responses before they reach users.
- Stay ahead of emerging regulations (ISO420001, EU AI Act, HIPAA, FDA) by embedding compliance checks into your AI development lifecycle.

### What to Avoid
- Relying solely on pre-deployment security (shift left) is inadequate; AI threats evolve at runtime and require ongoing monitoring.
- Pulling models from public repositories without scanning for vulnerabilities can result in credential leaks or backdoors.
- Ignoring regulatory requirements can lead to substantial fines and reputational damage, as seen in EU AI Act enforcement cases.

### Best Practices
- Adopt a layered defense: combine ML SecOps, AI red teaming, and runtime security for comprehensive protection.
- Continuously update and refine runtime guardrails based on red teaming findings and real-world incidents.
- Collaborate across product, engineering, and security teams to ensure trustworthy AI is a shared responsibility.

### Personal Stories & Experiences
- Adopt a layered defense: combine ML SecOps, AI red teaming, and runtime security for comprehensive protection.
- Continuously update and refine runtime guardrails based on red teaming findings and real-world incidents.
- Collaborate across product, engineering, and security teams to ensure trustworthy AI is a shared responsibility.

### Metrics & Examples
- EU AI Act fine: 20 million euros for unauthorized facial data scraping.
- Healthcare AI models: Example of models trained on 1.3 million cells, highlighting the scale and sensitivity of data involved.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=n6wHJDqlS1I)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
