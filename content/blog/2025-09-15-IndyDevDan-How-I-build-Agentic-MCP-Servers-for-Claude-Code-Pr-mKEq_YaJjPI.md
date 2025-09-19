+++
title = "How I build Agentic MCP Servers for Claude Code (Prompts CHANGE Everything)"
date = 2025-09-15
draft = false

[taxonomies]
author = ["IndyDevDan"]
categories = ["Artificial intelligence"]
tags = ["Artificial intelligence", "Software engineering--Artificial intelligence", "Prompt engineering", "Automation--Workflow"]

[extra]
excerpt = "IndyDevDan radically reframes how to build agentic MCP servers by elevating prompts—not tools—as the true power primitive. His approach shows that most engineers are stuck at the tool layer, missing out on the exponential leverage that prompt-driven workflows unlock for Claude Code and other MCP clients. This perspective matters because it transforms AI coding from a series of manual tool calls into guided, reusable, and domain-specific agentic workflows that scale engineering velocity."
video_url = "https://www.youtube.com/watch?v=mKEq_YaJjPI"
video_id = "mKEq_YaJjPI"
cover = "https://img.youtube.com/vi/mKEq_YaJjPI/maxresdefault.jpg"
+++

## Overview

IndyDevDan radically reframes how to build agentic MCP servers by elevating prompts—not tools—as the true power primitive. His approach shows that most engineers are stuck at the tool layer, missing out on the exponential leverage that prompt-driven workflows unlock for Claude Code and other MCP clients. This perspective matters because it transforms AI coding from a series of manual tool calls into guided, reusable, and domain-specific agentic workflows that scale engineering velocity.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Dan's distinctive methodology is a tiered framework for MCP primitives: Resources (lowest), Tools (middle), and Prompts (highest leverage). He insists that prompts are not just for priming models, but are the core mechanism for orchestrating tool composition, guiding user experience, and embedding reusable developer workflows directly into the MCP server. He challenges the prevailing tool-centric mindset and demonstrates, with hands-on code, how prompt-centric design 10x's agentic engineering.

### The Core Problem
Most engineers building MCP servers focus exclusively on tool calling, which leads to clunky, manual, and non-scalable workflows. This leaves the vast majority of agentic potential untapped, especially as model intelligence is no longer the bottleneck—capability engineering is.

### The Solution Approach
Dan's methodology is to architect MCP servers around prompt-driven workflows. He structures MCP servers so that prompts guide every step: priming the agent, suggesting next actions, composing tool sequences, and embedding domain-specific logic. He advocates for thinking from the agent's perspective—context, model, prompt—and using prompts as the glue that transforms tool calls into seamless, guided engineering experiences. His step-by-step: 1) Identify domain-specific workflows, 2) Encode them as prompt templates, 3) Use prompts to suggest, compose, and automate tool usage, 4) Provide reusable AI developer workflows (ADWs) within the MCP server.

### Key Insights
- Prompts are the highest-leverage primitive in MCP servers, enabling rapid priming, guided discovery, and automatic tool composition.
- Contrarian take: Tool calling is just the beginning—real agentic engineering happens when prompts orchestrate the entire workflow.
- Personal lesson: Embedding next-step suggestions and workflow guidance directly into prompts keeps engineers in flow and eliminates context-switching.

### Concepts & Definitions
- "Agentic engineering": Building systems where the agent (AI) is guided by prompts to perform complex, multi-step workflows autonomously.
- "MCP primitives": The foundational building blocks of an MCP server—resources, tools, and prompts—ranked by leverage.
- "AI Developer Workflow (ADW)": A reusable, prompt-driven workflow embedded in the MCP server for domain-specific automation.

### Technical Details & Implementation
- Implements a tiered MCP primitive structure: resources < tools < prompts.
- Uses Quick Data MCP server as a concrete example, with prompt templates that guide data loading, analysis, and visualization.
- MCP server code is structured so that every major action is driven by a prompt, not a manual tool call.
- Recommends using tight, information-dense keyword prompts (e.g., 'load ecom') with context-aware priming for Claude Code.
- Provides a public MCP.json configuration for rapid bootstrapping.

### Tools & Technologies
- Claude Code (Anthropic)—as the agentic coding model
- Quick Data MCP server—for data analysis workflows
- Deepseek R1.1—for advanced model intelligence
- MCP Clients (modelcontextprotocol.io)—for interfacing with MCP servers

### Contrarian Takes & Different Approaches
- Dan argues that the industry obsession with tool calling is misplaced—true agentic workflows require prompt orchestration.
- He challenges the idea that resources or tools are the main value in MCP servers, insisting prompts are the real multiplier.
- Advocates for treating prompts as reusable, composable workflow primitives, not just static instructions.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Stop at tool calls only as a starting point; architect your MCP server so that prompts drive the workflow and suggest next actions.
- Embed reusable prompt templates for common engineering tasks (e.g., data loading, correlation analysis, visualization) directly in your MCP server.
- Think from the agent's perspective: always consider context, model, and prompt when designing workflows.
- Leverage the provided MCP.json and Quick Data repo to experiment with prompt-driven MCP server design.

### What to Avoid
- Mistake: Building MCP servers that only expose tools leads to manual, fragmented workflows and underutilizes agentic potential.
- Anti-pattern: Relying on documentation lookups and context-switching instead of embedding guidance in prompts.
- Trap: Ignoring the agent's perspective—failing to provide the right context and prompt structure results in poor automation.

### Best Practices
- Always structure MCP servers so that prompts guide the user and the agent, not just tools.
- Use information-dense, context-aware prompts to maximize automation and minimize manual intervention.
- Continuously refine prompt templates based on real workflow bottlenecks and user feedback.

### Personal Stories & Experiences
- Dan shares how shifting from tool-centric to prompt-centric MCP design dramatically increased his and his team's engineering velocity.
- He recounts the frustration of jumping between documentation and manual tool calls before embedding workflow guidance in prompts.
- Describes the evolution of his thinking: from seeing prompts as a minor detail to recognizing them as the core of agentic engineering.

### Metrics & Examples
- Demonstrates that using prompt-driven workflows allows engineers to prime agents and execute multi-step tasks in seconds, compared to minutes of manual tool invocation.
- Shows that with prompt-centric design, engineering velocity is 'dramatically increased'—implying at least a 10x improvement in workflow speed.

## Resources & Links

- [https://agenticengineer.com/principled-ai-coding?y=mKEq_YaJjPI](https://agenticengineer.com/principled-ai-coding?y=mKEq_YaJjPI)
- [https://youtu.be/f8RnRuaxee8](https://youtu.be/f8RnRuaxee8)
- [https://github.com/disler/quick-data-mcp](https://github.com/disler/quick-data-mcp)
- [https://www.anthropic.com/solutions/coding](https://www.anthropic.com/solutions/coding)
- [https://modelcontextprotocol.io/clients](https://modelcontextprotocol.io/clients)
- [https://api-docs.deepseek.com/zh-cn/news/news250528](https://api-docs.deepseek.com/zh-cn/news/news250528)
- [Video URL](https://www.youtube.com/watch?v=mKEq_YaJjPI)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Cutting-Edge Insight

