+++
title = "Claude Code Web JUST Dropped but I Already Built Something BETTER (with Codex!)"
date = 2025-11-19
draft = false

[taxonomies]
author = ["Cole Medin"]
categories = ["Software engineering--Artificial intelligence","Artificial intelligence--Automation","Computer programming--Automation"]
tags = ["OpenAI Codeex SDK","Telegram bot","TypeScript","Browserbase","Render","GitHub CLI","MCP server","Human-in-the-loop","Remote agentic coding","Workflow automation"]

[extra]
excerpt = "Cole Medin presents a hands-on, open-source workflow that integrates OpenAI's Codeex coding assistant directly into Telegram, enabling remote, agentic code changes and deployments from any device—including a phone. Unlike out-of-the-box cloud coding tools, this approach prioritizes user-defined workflows, granular control, and seamless integration with personal infrastructure, making agentic coding truly flexible and extensible."
video_url = "https://www.youtube.com/watch?v=injqJTy5Tus"
video_id = "injqJTy5Tus"
cover = "https://img.youtube.com/vi/injqJTy5Tus/maxresdefault.jpg"
+++

## Overview

Cole Medin presents a hands-on, open-source workflow that integrates OpenAI's Codeex coding assistant directly into Telegram, enabling remote, agentic code changes and deployments from any device—including a phone. Unlike out-of-the-box cloud coding tools, this approach prioritizes user-defined workflows, granular control, and seamless integration with personal infrastructure, making agentic coding truly flexible and extensible.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Medin's methodology centers on building a fully customizable, self-hosted agentic coding assistant that operates inside familiar communication platforms (like Telegram), rather than relying on restrictive, vendor-hosted cloud solutions. The workflow is defined by the user in a simple markdown file, allowing for bespoke command chaining, integration with personal MCP servers, and human-in-the-loop validation—features not possible in most commercial offerings.

### The Core Problem
Existing remote agentic coding tools (Claude Code, Codeex Cloud, Jules, etc.) lack flexibility, making it difficult for developers to define custom commands, chain prompts, or connect to their own infrastructure. This rigidity hinders practical adoption for users who want full control, seamless integration with their workflows, and the ability to validate and deploy code changes remotely.

### The Solution Approach
Medin integrates the Codeex SDK into a TypeScript application that communicates with Telegram via the Telegraph library. The workflow is defined in an 'agents.md' file within the repo, specifying each step (clone repo, create branch, make changes, push to staging, validate, deploy to production). The system leverages browser-based MCP servers for automated validation and session replay, ensuring robust human-in-the-loop oversight. The entire setup is open source, deployable on cloud platforms like Render or DigitalOcean, and accessible from any device.

### Key Insights
- Custom agentic coding assistants can be embedded in everyday messaging apps, enabling true remote development and deployment workflows.
- Defining workflows in markdown makes them transparent, version-controlled, and easily modifiable—unlike opaque, vendor-controlled pipelines.
- Human-in-the-loop validation is essential even for advanced agentic coding; automated browser sessions and session replays provide both agent and human assurance.

### Concepts & Definitions
- "Agentic coding" is framed as remote, AI-driven code modification and deployment, orchestrated by user-defined workflows and validated by both agents and humans.
- "MCP server" refers to a modular control point that allows agents to perform browser-based validation and other automated tasks outside the coding environment.
- "Human-in-the-loop" is defined as a workflow step where a human reviews and approves agent actions before production deployment, ensuring safety and correctness.

### Technical Details & Implementation
- Telegram integration is handled via the Telegraph TypeScript library, mapping user messages to Codeex SDK threads.
- The Codeex SDK is used to start/resume threads, run streamed prompts, and manage working directories without restarting containers.
- Workflow logic is stored in 'agents.md', loaded into the container at runtime, and read by the Codeex SDK to orchestrate the coding process.
- Browserbase is used for remote browser sessions, enabling the agent to validate deployed changes and generate session replays.
- Deployments are managed via Render (free tier), with separate staging and production environments triggered by branch merges.

### Tools & Technologies
- OpenAI Codeex SDK (TypeScript)
- Telegram (via Telegraph library)
- Render (cloud deployment platform)
- Browserbase (remote browser sessions)
- GitHub CLI
- DigitalOcean (for remote hosting)

### Contrarian Takes & Different Approaches
- Contrary to the trend of relying on polished, vendor-hosted AI coding assistants, Medin argues that self-hosted, SDK-driven solutions offer unmatched flexibility and control.
- He challenges the notion that agentic coding must be tied to a specific platform or UI, advocating for messaging apps as universal, programmable interfaces.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Fork the open-source repo, set up the Telegram bot, and deploy the container to a cloud platform for instant remote coding capabilities.
- Define your workflow logic in a markdown file within your repo to enable transparent, customizable agentic operations.
- Integrate browser-based validation (via Browserbase or similar) for robust, automated testing and verification before production deployment.

### What to Avoid
- Relying solely on vendor-hosted agentic coding tools can limit flexibility and control, especially for custom workflows or infrastructure integration.
- Skipping human-in-the-loop validation risks deploying faulty or unverified code to production.
- Neglecting to separate staging and production environments can lead to unintended live site changes.

### Best Practices
- Use open-source SDKs and self-hosted infrastructure to maximize flexibility and control over agentic coding workflows.
- Maintain clear separation between staging and production, with automated and human validation steps before live deployment.
- Leverage messaging platforms (Telegram, Slack) as universal interfaces for triggering and monitoring agentic coding tasks.

### Personal Stories & Experiences
- Use open-source SDKs and self-hosted infrastructure to maximize flexibility and control over agentic coding workflows.
- Maintain clear separation between staging and production, with automated and human validation steps before live deployment.
- Leverage messaging platforms (Telegram, Slack) as universal interfaces for triggering and monitoring agentic coding tasks.

### Metrics & Examples
- Demonstrates a full code change and deployment cycle (clone, branch, edit, stage, validate, deploy) executed entirely from Telegram on a phone.
- Uses Render's free tier for both staging and production environments, showing cost-effective deployment.
- Live session replays and logs provide transparent, auditable records of agent actions and validations.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=injqJTy5Tus)

## Value Assessment

- **Practical Value:** immediately actionable
- **Uniqueness Factor:** cutting-edge insight
