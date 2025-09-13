+++
title = "Is Docker Building the Best AI Stack?"
date = 2025-09-13
draft = false

[taxonomies]
author = ["Bret Fisher Agentic DevOps"]
categories = ["Software engineering--Artificial intelligence"]
tags = ["Software engineering--Artificial intelligence", "DevOps", "Cloud computing", "Containerization (Computer science)"]

[extra]
excerpt = "Bret Fisher's approach demystifies Docker's rapidly evolving AI stack by breaking down each new feature into practical, developer-centric workflows. His perspective is rooted in hands-on DevOps experience, emphasizing how Docker's AI integrations can be leveraged immediately without heavy SaaS dependencies. This episode uniquely maps the interconnectedness of Docker's AI tools, focusing on real-world agentic development and extensibility."
video_url = "https://www.youtube.com/watch?v=dUmSsnc33O0"
video_id = "dUmSsnc33O0"
cover = "https://img.youtube.com/vi/dUmSsnc33O0/maxresdefault.jpg"
+++

## Overview

Bret Fisher's approach demystifies Docker's rapidly evolving AI stack by breaking down each new feature into practical, developer-centric workflows. His perspective is rooted in hands-on DevOps experience, emphasizing how Docker's AI integrations can be leveraged immediately without heavy SaaS dependencies. This episode uniquely maps the interconnectedness of Docker's AI tools, focusing on real-world agentic development and extensibility.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Bret Fisher's methodology is to systematically dissect Docker's AI ecosystem from a practitioner's lens, prioritizing actionable integration over theoretical discussion. He uniquely emphasizes the modularity and interoperability of Docker's AI features, showing how they can be composed, extended, and run both locally and in the cloud, all while minimizing vendor lock-in. His contrarian stance is to focus on open standards (like MCP) and local-first workflows, challenging the SaaS-heavy direction of most AI tooling.

### The Core Problem
Developers face fragmentation and complexity when trying to build, run, and extend AI-powered applications, especially with the proliferation of proprietary tools and cloud dependencies. The challenge is to create a unified, developer-friendly stack that enables agentic workflows, secure tool orchestration, and seamless model management—without being locked into closed ecosystems.

### The Solution Approach
Fisher and his guests advocate for a composable, containerized AI stack using Docker's new features: Model Runner for local/remote model hosting, MCP Toolkit and Gateway for standardized tool orchestration, and Docker Compose for declarative agentic setups. Their mental model is to treat models and tools as first-class, OCI-compliant resources, managed through familiar Docker workflows. They recommend leveraging open protocols (MCP), container lifecycle management, and Compose extensibility to build secure, portable, and extensible AI environments.

### Key Insights
- Docker's Model Runner and MCP Gateway enable developers to run and orchestrate open models and tools locally or remotely, reducing reliance on SaaS.
- The adoption of the MCP protocol as a standard for agentic tool integration is a game-changer, enabling interoperability across AI platforms.
- Compose's evolution to support models and agentic tools as top-level resources signals a shift toward declarative, extensible AI infrastructure.
- Open sourcing the MCP Gateway empowers developers to audit, extend, and self-host their agentic toolchains.
- Most of Docker's new AI features are free and integrate directly into existing workflows, lowering the barrier to experimentation.

### Concepts & Definitions
- "MCP (Model-Component Protocol)" is framed as the emerging open standard for agentic tool interoperability, replacing proprietary integrations.
- "MCP Gateway" is described as a proxy MCP server that manages the lifecycle, security, and orchestration of agentic tool containers.
- "Model Runner" is defined as a Docker-native way to package, run, and manage open-source models as OCI containers.
- "Agentic applications" are explained as AI-powered workflows that combine models and tools to perform complex, multi-step tasks.

### Technical Details & Implementation
- Docker Model Runner encapsulates models (GGUF, etc.) into OCI-compliant containers, managed via Docker CLI.
- MCP Toolkit GUI in Docker Desktop enables discovery and activation of 140+ agentic tools, each containerized for secure, isolated execution.
- MCP Gateway acts as a proxy MCP server, spinning up tool containers on demand, injecting credentials, and inspecting prompt traffic for security.
- Compose files now support models and MCP tools as top-level resources, allowing declarative agentic setups that can run locally or on Google Cloud Run.
- Docker Offload (formerly Docker Cloud) enables seamless toggling between local and remote execution of models and containers via the Docker UI.

### Tools & Technologies
- Docker Model Runner (for model hosting and management)
- Docker Hub Model Catalog (for model discovery and distribution)
- Gordon AI (Docker-focused AI chatbot in Docker Desktop/CLI)
- MCP Toolkit (GUI for agentic tool management)
- MCP Gateway (open-source proxy for MCP tools)
- Docker Compose (now supporting models and agentic tools)
- Docker Offload (cloud-based container/model execution)
- Google Cloud Run (for running Compose YAMLs)

### Contrarian Takes & Different Approaches
- Fisher challenges the SaaS-first mentality of most AI tooling, advocating for local-first, open-standard, and self-hosted approaches.
- He questions the sustainability of proprietary agentic tool integrations, arguing that open protocols like MCP are the future.
- He suggests that Compose YAML is the most universal configuration format in the AI/DevOps space, contrary to the trend toward bespoke cloud-native formats.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Explore the MCP Toolkit beta in Docker Desktop to activate and experiment with agentic tools in a secure, containerized way.
- Use Docker Model Runner to package and run open models locally, leveraging the Docker CLI for lifecycle management.
- Adopt the MCP protocol for tool integration to future-proof agentic workflows and avoid vendor lock-in.
- Leverage Compose's new capabilities to declaratively define agentic stacks—including models and tools—for reproducible development and deployment.
- Try Docker Offload to seamlessly shift workloads between local and cloud environments without changing code or configuration.

### What to Avoid
- Beware of relying on proprietary tool integrations (e.g., pre-MCP era) that may limit interoperability and transparency.
- Do not assume all agentic tools are secure by default—use MCP Gateway's prompt inspection and credential injection features to mitigate risks.
- Avoid hard-coding environment variables or secrets in Compose files; use Docker's secure injection mechanisms instead.
- Recognize that the MCP protocol is still evolving—future-proof by following open standards and monitoring community adoption.

### Best Practices
- Treat models and agentic tools as OCI-compliant, containerized resources for maximum portability and reproducibility.
- Use Docker Compose to declaratively manage the full AI stack, including models, tools, and supporting infrastructure.
- Leverage open-source components (like MCP Gateway) to maintain transparency and extensibility in agentic workflows.
- Regularly update and audit tool containers to ensure security and compatibility with evolving standards.

### Personal Stories & Experiences
- Fisher recounts the evolution from proprietary, opaque tool integrations to the open, standardized MCP ecosystem, highlighting the increased developer empowerment.
- He shares excitement about Docker's rapid feature releases, noting the challenge (and opportunity) of keeping up with the pace of innovation.
- The discussion reflects a decade-long relationship with Docker and its community, emphasizing the value of long-term practitioner insight.

### Metrics & Examples
- MCP Toolkit currently offers 141 agentic tools and is rapidly growing.
- Compose YAMLs can now be deployed directly to Google Cloud Run, with other platforms likely to follow.
- Most new Docker AI features are available at no additional cost, emphasizing accessibility.

## Resources & Links

- [https://podcast.bretfisher.com/episodes/is-docker-building-the-best-ai-stack](https://podcast.bretfisher.com/episodes/is-docker-building-the-best-ai-stack)
- [https://youtube.com/live/MnFyZlbXNLc](https://youtube.com/live/MnFyZlbXNLc)
- [https://courses.bretfisher.com/waitlist](https://courses.bretfisher.com/waitlist)
- [https://www.docker.com/products/model-runner/](https://www.docker.com/products/model-runner/)
- [https://www.docker.com/blog/meet-gordon-an-ai-agent-for-docker/](https://www.docker.com/blog/meet-gordon-an-ai-agent-for-docker/)
- [https://www.docker.com/products/docker-offload/](https://www.docker.com/products/docker-offload/)
- [https://hub.docker.com/catalogs/gen-ai](https://hub.docker.com/catalogs/gen-ai)
- [https://www.docker.com/products/mcp-catalog-and-toolkit/](https://www.docker.com/products/mcp-catalog-and-toolkit/)
- [https://github.com/docker/mcp-gateway](https://github.com/docker/mcp-gateway)
- [https://www.bretfisher.com/newsletter/](https://www.bretfisher.com/newsletter/)
- [https://www.linkedin.com/in/mikesir87/](https://www.linkedin.com/in/mikesir87/)
- [https://www.linkedin.com/in/nirmalkmehta/](https://www.linkedin.com/in/nirmalkmehta/)
- [https://bsky.app/profile/bretfisher.com](https://bsky.app/profile/bretfisher.com)
- [https://www.linkedin.com/in/bretefisher/](https://www.linkedin.com/in/bretefisher/)
- [https://x.com/BretFisher](https://x.com/BretFisher)
- [https://www.bretfisher.com](https://www.bretfisher.com)
- [https://www.bretfisher.com/courses/](https://www.bretfisher.com/courses/)
- [https://discord.com/invite/devops](https://discord.com/invite/devops)
- [https://www.bretfisher.com/podcast/](https://www.bretfisher.com/podcast/)
- [Video URL](https://www.youtube.com/watch?v=dUmSsnc33O0)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

