+++
title = "Building a Decentralized Knowledge Graph for AI // Tomaž Levak // MLOps Podcast #285"
date = 2026-04-11
draft = false

[taxonomies]
author = ["MLOps.community"]
categories = ["Artificial intelligence","Knowledge representation","Distributed data management","Software engineering--Distributed systems","Semantic web"]
tags = ["Decentralized knowledge graph","OriginTrail","Paranet","Edge node","Graph RAG","SPARQL","EVM","NFT","Merkle tree","TRAC","Agentic AI","Ontology","Verifiability proofs","Federated query","Local LLM","Aura Ring","Whoop","Llama","Blockchain interoperability","Access control"]

[extra]
excerpt = "The video argues that decentralized knowledge graphs can become the shared substrate for trustworthy AI systems: a place where organizations, agents, and applications can exchange knowledge without surrendering full data ownership. The distinctive claim is that verifiability, access control, and interoperability matter more than simply storing more data, especially as AI agents start acting like economic entities."
video_url = "https://www.youtube.com/watch?v=PxUH668mP5E"
video_id = "PxUH668mP5E"
cover = "https://img.youtube.com/vi/PxUH668mP5E/maxresdefault.jpg"
+++

## Overview

The video argues that decentralized knowledge graphs can become the shared substrate for trustworthy AI systems: a place where organizations, agents, and applications can exchange knowledge without surrendering full data ownership. The distinctive claim is that verifiability, access control, and interoperability matter more than simply storing more data, especially as AI agents start acting like economic entities.

## 🔍 Key Insights & Learnings

### Creator's Unique Angle
The angle is not "knowledge graphs for AI" in the abstract, but a decentralized, multi-chain, graph-native protocol where each participant keeps its own data while publishing verifiable claims into a shared network. The methodology combines private edge nodes, public discoverability, granular permissions, and on-chain proofs so that collaboration happens without a central aggregator in the middle.

### The Core Problem
Modern AI systems need trustworthy, up-to-date, and context-rich knowledge, but centralized data platforms force a tradeoff between transparency and ownership. Enterprises, agents, and partners often need to collaborate on sensitive data, yet they cannot safely expose everything, and conventional databases or plain retrieval systems do not provide native verifiability or fine-grained interoperability.

### The Solution Approach
The solution is a decentralized knowledge graph built as middleware between systems. Each participant can run an edge node that hosts its own knowledge graph, publish knowledge assets into a shared global graph, and attach proofs on-chain for verifiability. The network supports "paranets" (parallel networks) as domain-specific neighborhoods with their own ontologies, rules, and access policies. For speed and scale, the system uses random sampling for validation, sharding-like splitting of large graphs, and local reads from an edge node after global verification.

### Key Insights
- Transparency is valuable only when it does not require surrendering all data; the real win is selective disclosure with proofs.
- Knowledge graphs become much more powerful when they are paired with ontologies and access rules that match a specific domain instead of forcing one universal schema.
- Agents are a natural fit because they can use the graph as collective memory, evaluate data faster than humans, and transact with less emotional baggage.
- A decentralized graph can function like a "git for the whole system," not just code: it can capture conversations, PR context, incident history, and external signals that explain why decisions were made.
- Old information is a real problem in knowledge systems, so expiry dates and update semantics are essential rather than optional.
- The network becomes more useful as more specialized neighborhoods emerge, because narrow, well-governed graphs are easier to trust and query than one giant undifferentiated graph.

### Concepts & Definitions
- A decentralized knowledge graph is framed as a shared middleware layer where participants connect their own systems and data into a common graph while retaining ownership and control.
- Paranets are parallel networks or neighborhoods inside the larger graph, each with its own rules, ontologies, and contribution expectations.
- Knowledge assets are atomic units in the graph, roughly analogous to entities, that can be published, updated, discovered, and verified.
- An edge node is described as a lightweight gateway or modem into the network: a local wrapper around a participant's knowledge graph that can run on a laptop or phone.
- Graph RAG is retrieval augmented generation over graph-structured context rather than plain text chunks, giving the model more precise and connected evidence.
- A federated query is a distributed lookup that can traverse multiple graphs or agents and return a normalized answer with provenance.
- On-chain proofs are small cryptographic fingerprints, such as Merkle root hashes, that confirm the published data has not been tampered with.

### Technical Details & Implementation
- Publishing a knowledge asset creates an NFT that serves as ownership proof; only the NFT owner can update that asset.
- When a knowledge asset is created or modified, the system generates proofs and publishes a compact hash on-chain rather than storing the full data on-chain.
- The protocol is multi-chain and can integrate with any EVM chain depending on where activity or use-case fit makes the most sense.
- Edge nodes can use different databases and different LLMs; the protocol is intentionally not prescriptive about the underlying storage or model choice.
- A global query can search across the decentralized graph, but the fastest path is to query a local edge node after it has already synchronized and verified relevant data.
- Random sampling was introduced in version 8 to improve scale, allowing the network to validate subsets rather than every single knowledge asset.
- Large graphs can be split into smaller networks when they grow too big, creating an ever-expanding sharding-like structure.
- LLMs can be used to generate SPARQL queries from templates, making graph querying much easier for non-experts or agent workflows.
- Knowledge assets can also be pointers to external APIs or live data sources, enabling dynamic values like IoT readings or prices to stay current.
- Expiry dates can be attached to knowledge assets so the network stops incentivizing storage of stale information.

### Tools & Technologies
- OriginTrail decentralized knowledge graph
- Edge nodes
- Paranets
- EVM chains
- NFTs for ownership proofs
- Merkle tree root hashes
- SPARQL
- LLMs for query generation
- Graph RAG
- Local LLM instances
- Aura Ring
- Whoop
- Llama
- GitHub
- Discord
- TRAC token

### Contrarian Takes & Different Approaches
- Blockchains are described as "shitty databases" for this use case: useful for identities, transactions, and smart contracts, but not sufficient for knowledge graph capabilities.
- The video pushes back on the idea that transparency requires full data exposure; selective disclosure with proofs is presented as the superior model.
- Commercial agreements are expected to shift because agents may understand data value more rationally and transact faster than humans.
- The speaker suggests that the future of automation is not just automation itself, but automation of automation through agentic systems.
- A single global graph is not the end goal; many smaller, governed neighborhoods may be more practical and more powerful.

## 💡 Key Takeaways & Actionable Insights

### What You Should Do
- Start by identifying a narrow domain where shared trust and selective disclosure matter more than raw openness, then define a paranet with explicit ontologies and access rules.
- Run an edge node locally if you want to keep data in your own environment while still participating in the network.
- Use the graph as a source of provenance: publish claims with timestamps and proofs so downstream systems can verify them later.
- For agent workflows, keep a local knowledge graph as the fast read layer and sync it with the broader network for discovery and interoperability.
- Attach expiry dates to data that becomes stale, and design update flows so the latest state is always the one being incentivized.
- If building with agents, let them query the graph repeatedly in loops and use provenance-aware outputs rather than relying on a single retrieval pass.
- Use graph structure instead of flat text whenever relationships, lineage, or decision history matter.

### What to Avoid
- Do not treat a knowledge graph as a generic database replacement; the protocol is about coordination, verifiability, and interoperability, not just storage.
- Avoid centralizing the system through a single aggregator, because that reintroduces the trust and ownership problems the architecture is trying to solve.
- Stale data is dangerous in graph-based systems; if updates are not managed carefully, old claims can linger and pollute retrieval.
- A universal schema can be too blunt for many use cases; forcing everything into one ontology reduces usefulness.
- Public and private access need to be managed very granularly; coarse permissions will break the value proposition for enterprise use cases.
- Do not assume on-chain storage is the goal; the chain is used for proofs and ownership, not for holding the full graph.

### Best Practices
- Keep the heavy data off-chain and put only compact proofs on-chain for cheap, verifiable integrity.
- Use domain-specific ontologies and narrow neighborhoods when the use case is specialized, such as trade compliance or audit data.
- Let each participant choose their own database, blockchain, and model stack so the protocol remains flexible and composable.
- Prefer local reads from an edge node for production speed, then use the global graph for discovery and synchronization.
- Design for provenance from the start so every answer can be traced back to published knowledge assets.
- For AI agents, combine a local memory layer with federated access to shared knowledge so they can act quickly without losing context.

### Personal Stories & Experiences
- The founder described building OriginTrail over roughly a decade, with the architecture evolving from a single big graph into a network of paranets.
- A prototype with the Aura Ring and a local Llama instance was used to analyze sleep patterns against a small set of neuroscience papers, showing how personal health data can be paired with public research.
- He mentioned a real-time X conversation with an agent where a deal was struck in a few tweets to fund a DKG edge node with TRAC, illustrating how agent-native commerce can already happen.
- The team learned early that some data has short-lived value, which led to the expiry-date mechanism for knowledge assets.
- The system evolved from a centralized-company mindset to a protocol designed to remove the company from the middle entirely.

### Metrics & Examples
- Version 8 reportedly increased scale by more than 10x through random sampling and architectural redesign.
- The network is described as reaching internet-scale size after the redesign.
- A sleep-analysis prototype used about 10 papers as a proof of concept before scaling the idea to much larger corpora.
- The speaker referenced a three-tweet deal with an agent to fund an edge node with TRAC.
- The system can support queries across tens of thousands of agents operating 24/7/365 in the envisioned future.

## Resources & Links

- [Video URL](https://www.youtube.com/watch?v=PxUH668mP5E)

## Value Assessment

- **Practical Value:** requires setup
- **Uniqueness Factor:** fresh perspective
