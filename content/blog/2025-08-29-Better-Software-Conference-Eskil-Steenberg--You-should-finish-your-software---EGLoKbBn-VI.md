+++
title = "Eskil Steenberg – You should finish your software – BSC 2025"
date = 2025-08-29
draft = false

[taxonomies]
author = ["Better Software Conference"]
categories = ["Software project completion"]
tags = ["Software project completion", "API stability and backward compatibility", "Software ecosystem trust and adoption", "3D graphics tools and protocols", "Open source and proprietary software distribution", "Verse (real-time 3D networking protocol)", "Laro (subdivision surface modeler)", "Love (procedural first-person action adventure game engine)"]

[extra]
excerpt = "This talk addresses the critical importance of actually finishing software projects and maintaining stable APIs, highlighting how incomplete or unstable software undermines both individual productivity and the broader software ecosystem."
video_url = "https://www.youtube.com/watch?v=EGLoKbBn-VI"
video_id = "EGLoKbBn-VI"
cover = "https://img.youtube.com/vi/EGLoKbBn-VI/maxresdefault.jpg"
+++

## Overview

This talk addresses the critical importance of actually finishing software projects and maintaining stable APIs, highlighting how incomplete or unstable software undermines both individual productivity and the broader software ecosystem.

![Video Thumbnail](https://img.youtube.com/vi/EGLoKbBn-VI/maxresdefault.jpg)

## 🔍 Key Insights & Learnings

### The Core Problem
The main problem discussed is the widespread tendency among developers and organizations to leave software unfinished or to break APIs, resulting in unreliable tools, wasted effort, and a lack of trust in software components. This issue is contextualized by contrasting the long-term stability and backward compatibility of platforms like Windows with the fragmentation and instability seen in Linux distributions, which hinders adoption and usability.

### The Solution Approach
The speaker advocates for a disciplined approach to software development: finish what you start, ensure your software is truly 'done' and reliable, and maintain stable APIs. When changes are necessary, introduce new API calls rather than breaking existing ones, allowing users to migrate at their own pace. This approach compartmentalizes problems, builds trust in software, and enables both creators and users to move on to new challenges without being burdened by unfinished or unstable work.

### Key Insights
- Stable APIs are a foundational reason why legacy software (e.g., from the 90s) still runs on modern Windows systems, fostering long-term trust and usability.
- Linux's lack of a stable userland API across distributions is a major barrier to its widespread adoption, as software built for one version often fails on another.
- Finishing software and making it reliable is as much for the developer's benefit (freeing mental space) as for users (enabling reuse and trust).
- Breaking APIs—even internally within small teams—creates unnecessary friction and technical debt.
- Compartmentalization of solved problems (finished software) allows for more effective focus on new challenges.

### Technical Details & Implementation
- When an API needs to change, do not break the old one; instead, add a new API call and deprecate the old one, allowing gradual migration.
- Example: In a custom game engine, if a function needs to be replaced, create a new function rather than modifying the existing one, and inform users to switch when convenient.
- The speaker references having written a real-time networking protocol for 3D graphics (Verse), a subdivision surface modeler (Laro), a procedural networked game (Love), a fully automatic UV unwrapper (Ministry of Flat), and a simple asset file format (hacka).

### Tools & Technologies
- Verse (real-time 3D networking protocol)
- Laro (subdivision surface modeler)
- Love (procedural first-person action adventure game engine)
- Ministry of Flat (automatic UV unwrapper, licensed in Cinema 4D)
- Cinema 4D (3D modeling software)
- hacka (simple asset file format for polygons and pixels)
- Kel Solar (pack of libraries)
- C language (with reference to C standard committee involvement)

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Finish your software projects to a point where they are reliable and can be trusted by others.
- Maintain stable APIs; never break existing interfaces for users or teammates.
- When changes are necessary, add new API calls and deprecate old ones, rather than replacing or modifying existing ones.
- Compartmentalize solved problems by considering finished software as 'done' and moving on, reducing mental overhead.
- If you want your software to be widely adopted, prioritize backward compatibility and stability.

### What to Avoid
- Avoid breaking APIs, as it erodes user trust and creates migration headaches.
- Do not leave software unfinished, as it leads to wasted effort and ongoing maintenance burdens.
- Beware of the anti-pattern of constantly refactoring or rewriting without ever reaching a stable, finished state.
- Fragmentation (as seen in Linux distributions) can kill adoption if users cannot rely on software to work across versions.

### Best Practices
- Always provide stable, backward-compatible APIs.
- Finish and polish software before moving on to new projects.
- Communicate API changes clearly and provide migration paths.
- Treat finished software as a solved problem to enable focus on new work.
- License and distribute tools in ways that maximize accessibility and reuse (e.g., Ministry of Flat available via Cinema 4D and standalone site).

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=EGLoKbBn-VI)

## Value Assessment
- **Practical Value:** High
- **Technical Depth:** Intermediate
- **Relevance:** [To be determined]

