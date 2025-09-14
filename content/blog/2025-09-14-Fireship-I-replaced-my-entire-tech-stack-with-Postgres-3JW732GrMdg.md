+++
title = "I replaced my entire tech stack with Postgres..."
date = 2025-09-14
draft = false

[taxonomies]
author = ["Fireship"]
categories = ["Database management systems"]
tags = ["Database management systems", "Web application development", "Software engineering--Open source software", "Software engineering--System architecture"]

[extra]
excerpt = "Fireship radically reimagines the modern web development stack by demonstrating how PostgreSQL alone can replace a sprawling array of SaaS tools and backend services. His perspective matters because he exposes the overlooked power and extensibility of PostgreSQL, challenging the prevailing trend of ever-increasing stack complexity and vendor lock-in."
video_url = "https://www.youtube.com/watch?v=3JW732GrMdg"
video_id = "3JW732GrMdg"
cover = "https://img.youtube.com/vi/3JW732GrMdg/maxresdefault.jpg"
+++

## Overview

Fireship radically reimagines the modern web development stack by demonstrating how PostgreSQL alone can replace a sprawling array of SaaS tools and backend services. His perspective matters because he exposes the overlooked power and extensibility of PostgreSQL, challenging the prevailing trend of ever-increasing stack complexity and vendor lock-in.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
Fireship's approach is iconoclastic and efficiency-driven: he advocates for using PostgreSQL as a 'one database to rule them all' platform, leveraging its extensibility and ecosystem of extensions to collapse the traditional multi-tool stack into a single, open-source solution. He frames PostgreSQL not just as a database, but as a fullstack application platform, pushing its boundaries with creative, sometimes 'weird', use cases.

### The Core Problem
The core problem addressed is the excessive complexity, cost, and fragmentation of modern web development, where developers are pressured to integrate and pay for dozens of specialized SaaS tools for caching, scheduling, authentication, analytics, and more. This complexity leads to higher costs, cognitive overload, and increased risk of vendor lock-in.

### The Solution Approach
Fireship's methodology is to systematically replace each common backend service (e.g., cron jobs, in-memory cache, REST APIs) with native PostgreSQL features or extensions. He reasons that most web apps' needs can be met by creatively exploiting PostgreSQL's advanced data types, extension ecosystem, and configuration options. His step-by-step approach involves: (1) provisioning a free PostgreSQL instance (e.g., via Neon), (2) connecting locally with SQL tools, (3) installing and configuring extensions like pg_cron and unlogged tables, and (4) building out fullstack features directly in the database.

### Key Insights
- PostgreSQL's extensibility and advanced data types allow it to serve as more than just a relational database—it's a full application platform.
- You can implement cron jobs, caching, and even REST APIs directly in PostgreSQL, eliminating the need for external services.
- Disabling write-ahead logging for unlogged tables creates a high-performance, in-memory cache within PostgreSQL—no need for Redis for most use cases.

### Concepts & Definitions
- Unlogged tables: Tables in PostgreSQL that skip write-ahead logging, trading durability for speed, ideal for cache-like use cases.
- pg_cron: A PostgreSQL extension that enables scheduled execution of SQL statements, effectively replicating cron job functionality inside the database.
- Extensibility: The ability to add new features to PostgreSQL via extensions, analogous to 'modding a game' to enhance its capabilities.

### Technical Details & Implementation
- Uses Neon to provision up to 10 free PostgreSQL databases for experimentation and deployment.
- Connects to PostgreSQL via VS Code using the SQL Tools extension for local development.
- Implements cron jobs using the pg_cron extension, allowing SQL statements to run on a schedule within the database.
- Creates unlogged tables for caching, disables write-ahead logging for performance, and configures shared buffers for in-RAM storage.
- Suggests using PostgreSQL's built-in JSON, array, and geometric types for complex data modeling.
- Mentions auto-vacuum daemon configuration to prevent table bloat in cache tables.

### Tools & Technologies
- Neon (for free PostgreSQL hosting)
- VS Code (as the code editor)
- SQL Tools extension (for database connectivity)
- pg_cron (for scheduled tasks)
- Auto-vacuum daemon (for table maintenance)

### Contrarian Takes & Different Approaches
- Argues that most web apps do not need separate services for caching, scheduling, or even REST APIs—PostgreSQL can do it all.
- Challenges the trend of ever-increasing stack complexity and SaaS dependency in web development.
- Mocks the idea that you need a specialized tool for every backend function, advocating for a 'PostgreSQL-first' approach.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Provision a free PostgreSQL instance on Neon and connect with SQL Tools in VS Code to start experimenting.
- Install pg_cron to run scheduled SQL tasks directly in your database, replacing external cron services.
- Use unlogged tables for high-speed, in-memory caching needs, and configure shared buffers for optimal RAM usage.
- Explore PostgreSQL's extension ecosystem to add features instead of reaching for new SaaS products.

### What to Avoid
- Warns against overcomplicating your stack with unnecessary SaaS tools when PostgreSQL can handle most needs.
- Highlights the trade-off of using unlogged tables: loss of durability in exchange for speed—do not use for critical data.
- Cautions that not all PostgreSQL extensions are officially supported or stable; vet before using in production.

### Best Practices
- Start with PostgreSQL's native capabilities and only add external tools when absolutely necessary.
- Leverage extensions to incrementally add features, keeping your stack simple and maintainable.
- Use configuration tuning (e.g., shared buffers, auto-vacuum) to optimize performance for your specific use case.

### Personal Stories & Experiences
- Shares the frustration of paying for and managing dozens of SaaS tools for simple projects.
- Describes the 'aha moment' of realizing PostgreSQL's extensibility could replace most of his backend stack.
- Mentions pushback from sponsors (Neon) about the 'crazy' ways he's using PostgreSQL, but stands by his experiments.

### Metrics & Examples
- Neon allows up to 10 free PostgreSQL databases per user.
- Demonstrates daily scheduled data aggregation and cache expiry tasks using pg_cron.

## Resources & Links

- [https://fyi.neon.tech/fireship](https://fyi.neon.tech/fireship)
- [https://discord.gg/fireship](https://discord.gg/fireship)
- [https://youtu.be/n2Fluyr3lbc](https://youtu.be/n2Fluyr3lbc)
- [https://youtu.be/Cz3WcZLRaWc](https://youtu.be/Cz3WcZLRaWc)
- [https://fireship.io/pro](https://fireship.io/pro)
- [Video URL](https://www.youtube.com/watch?v=3JW732GrMdg)

## Value Assessment
- **Practical Value:** Immediately Actionable
- **Uniqueness Factor:** Contrarian Wisdom

