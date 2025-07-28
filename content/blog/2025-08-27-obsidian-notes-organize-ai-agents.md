+++
title = "My Obsidian Notes Organize Themselves with AI Agents (Claude AI + Bases)"
date = 2025-08-27
draft = false

[taxonomies]
categories = ["Productivity", "AI Tools", "claude code"]
tags = ["obsidian", "claude-code", "mcp", "smart-connections", "rest-api", "semantic-search", "youtube-transcript-api", "uv"]

[extra]
excerpt = "A deep-dive on turning an Obsidian vault into a self-organizing system using Claude Code agents plus Obsidian Bases. You'll build reliable slash-command workflows for idea capture, YouTube note ingestion (with transcript + thumbnail), and an orchestrator that routes inputs automatically."
video_url = "https://www.youtube.com/watch?v=OPH4yNvuMr8"
video_id = "OPH4yNvuMr8"
cover = "https://img.youtube.com/vi/OPH4yNvuMr8/maxresdefault.jpg"
+++

## 📖 Overview

A deep-dive on turning an Obsidian vault into a **self-organizing system** using **Claude Code** agents plus **Obsidian Bases**. You'll build reliable slash-command workflows for idea capture, YouTube note ingestion (with transcript + thumbnail), and an orchestrator that routes inputs automatically—then enrich notes via **semantic search** across your vault

![Video Thumbnail](https://img.youtube.com/vi/OPH4yNvuMr8/maxresdefault.jpg)

## 🔍 Key Insights & Learnings

### The Core Problem

* **Friction in note capture & organization**: people spend too much time filing notes and too little engaging with them. The goal is **90% thinking, 10% organizing**
* Folder hierarchy is brittle; **organization should be driven by properties/tags**, not location. Bases lets you **view, filter, and sort notes by properties** so files can live anywhere.

### The Solution Approach

1. **Reliable micro-agents via Claude Code slash commands**
    * Start with a small, deterministic **/idea** command that always produces the same schema (YAML front matter, tags, date). Reliability > cleverness

2. **Richer ingestion for media**
    * A **/youtube-note** command: extract video ID, pull transcript with `youtube-transcript-api`, build a structured note (cover image, sections like description/insights), then **add to a Bases view**

3. **Semantic linking**
    * Use **Smart Connections** + **Local REST API** + **MCP Tools** to query your vault semantically and append "Relevant notes" back into the YouTube note

4. **Single entry point**
    * An **/capture** orchestrator decides (idea vs. YouTube) based on the input pattern and **routes to the correct workflow**. Extensible to tasks, books, articles, etc

### Technical Details & Implementation

#### 1) Claude Code custom slash command: `/idea`

* **Location:** create `.claude/commands/idea.md`.
* **Allowed tools:** `write` (filesystem) and a safe `bash` tool for current date.
* **Behavior:** generate filename, clean up raw text, write a note with YAML front matter (`tags: [idea]`, `date:`), then ask for user approval to write

**Example command file (reconstructed from the video's structure):**

```markdown
---
description: "Capture a fleeting idea into a clean Obsidian note."
tools:
  - write
  - bash:
      name: "now"
      command: "date +%Y-%m-%d"
      description: "Get today's date (YYYY-MM-DD)."
---

# Context
- today: {{bash:now}}

# Task
1. Create a slug from the provided idea (short, kebab-case).
2. Filename: "{{today}}-idea-{{slug}}.md" (in vault root).
3. Clean up filler words; keep the core idea concise.
4. Write this file content:

---
tags: [idea]
date: {{today}}
---

# Idea
{{cleaned_idea}}
```

#### 2) Obsidian Bases integration

* Create a **Base** and **filter by `tag = idea`** to list ideas regardless of folder. Properties (like `date`) become sortable columns. This **decouples organization from location**.

#### 3) Slash command: `/youtube-note`

* **Args:** YouTube URL.
* **Steps:**
    1. Extract the **video ID** from the URL.
    2. Use Python's **`youtube-transcript-api`** (run ad-hoc via **`uv`** for an isolated environment) to fetch transcript.
    3. Generate a note with: title, tags `[video,...]`, `cover` (thumbnail), sections for description, objectives/insights, and **space to study**.
    4. Add it to a **"Videos" Base** (cards view with `image property = cover`)

**Skeleton for the transcript step (as described):**

```bash
# Extract VIDEO_ID from input (pseudo)
VIDEO_ID="$(your_extraction_logic)"

# One-off, isolated run using uv to fetch transcript
uvx python - <<'PY'
from youtube_transcript_api import YouTubeTranscriptApi as YTA
import json, os
vid = os.environ.get("VIDEO_ID")
print(json.dumps(YTA.get_transcript(vid)))
PY
```

**Card view cover:** use `https://img.youtube.com/vi/VIDEO_ID/maxresdefault.jpg` or fall back to `hqdefault.jpg` if rendering fails

#### 4) Semantic search & auto-linking

* Install **Smart Connections**, **MCP Tools**, and **Local REST API**.
* Save the Local REST API key into a **`.env`** in your vault.
* The agent calls the Local REST API endpoint exposed via MCP Tools to run a **semantic search** (keywords + embeddings) and returns **relevance scores** and file names; then it appends a **"Relevant notes"** section with links back into your YouTube note
* Confirm additions via the same **write approval** flow. Finally, inspect the **Local Graph** to visualize connections

#### 5) Orchestrator: `/capture`

* Context points to the paths of `/idea` and `/youtube-note` command files.
* **Routing logic:** If input looks like a **URL → run YouTube workflow**; otherwise **treat as idea**. Extensible to tasks, books, articles with more routes

### Tools & Technologies

* **Claude Code** (Anthropic) for agentic workflows & custom slash commands.
* **Obsidian Bases** (core plugin) for database-like views over note properties.
* **Smart Connections** (plugin) for semantic relevance across notes.
* **Local REST API** (plugin) for programmatic, API-key-protected access to your vault.
* **MCP Tools for Obsidian** to expose search & actions to Claude via MCP.
* **`youtube-transcript-api`** for pulling video transcripts. **`uv`** to run Python deps quickly/isolated.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do

* **Start tiny & reliable:** implement `/idea` first; lock a consistent schema (front matter + tag). This becomes the backbone for Bases
* **Adopt property-driven organization:** filter in Bases by `tags` / `date` instead of moving files.
* **Automate YouTube ingestion:** 1-click transcript → structured note → card in a "Videos" Base
* **Enrich notes semantically:** wire Smart Connections + REST API + MCP Tools; append "Relevant notes" sections automatically
* **Consolidate entry points:** use `/capture` to route inputs to the right workflow

### What to Avoid

* **Over-engineering early:** don't start with the orchestrator; nail a simple, predictable agent first
* **Relying on folder hierarchies:** they increase friction; **let properties + Bases** do the organizing

### Best Practices

* **Least-privilege tools** in slash commands (only `write` and the specific `bash` you need)
* **Approval gates** on writes; keep humans in the loop
* **Restart Claude Code** after adding new commands so it refreshes available workflows
* **Thumbnail robustness:** if `maxresdefault.jpg` fails to render, switch to `hqdefault.jpg`
* **Secure your API key** via `.env`, pass it explicitly in REST calls.

## 🔗 Resources & Links

* **Video:** My Obsidian Notes Organize Themselves with AI Agents ([YouTube](https://www.youtube.com/watch?v=OPH4yNvuMr8))
* **Claude Code:** Overview & setup ([Anthropic](https://docs.anthropic.com/en/docs/claude-code/overview))
* **Obsidian Bases:** Core documentation ([Obsidian Help](https://help.obsidian.md/bases))
* **Smart Connections:** Plugin repository ([GitHub](https://github.com/brianpetro/obsidian-smart-connections))
* **Local REST API:** Plugin repository ([GitHub](https://github.com/coddingtonbear/obsidian-local-rest-api))
* **MCP Tools for Obsidian:** Plugin repository ([GitHub](https://github.com/jacksteamdev/obsidian-mcp-tools))
* **youtube-transcript-api:** Python package ([PyPI](https://pypi.org/project/youtube-transcript-api/))
* **uv:** Python package manager ([Astral Docs](https://docs.astral.sh/uv/))

## 🔗 Related Concepts & Further Learning

* Building MCP-powered assistants for Obsidian (install/usage walk-throughs)
* Additional "Obsidian + Claude" workflows (morning routine, inbox zero, 10x notes)
* Best practices for Claude Code agentic workflows

## 📝 Personal Notes

This workflow represents a significant shift from manual note organization to AI-driven, property-based systems. The emphasis on reliability over cleverness in the initial `/idea` command is particularly valuable - starting simple and building complexity incrementally is key to sustainable AI workflows.

## ⭐ Value Assessment

* **Practical Value:** High — the commands are immediately usable and extensible.
* **Technical Depth:** Medium — focuses on reproducible agent prompts, APIs, and plugin wiring rather than internals of embeddings.
* **Relevance:** Strong if you maintain an Obsidian PKM and want **agentic, property-driven organization**.