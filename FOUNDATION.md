# Gr4Ig — Project Foundation

*Created: 2026-03-08*
*Status: Seed — Pre-research phase*

---

## Mission

To build a free, open source, AI-driven personal operating environment that eliminates the cognitive cost of context switching — giving people back the mental energy they spend managing tools instead of doing work.

---

## Vision

A world where the interface adapts to the human, not the other way around. Where your workspace understands the shape of your day, the weight of your obligations, and the context of your work — and surfaces exactly what you need, when you need it, without you having to ask.

---

## Problem Statement

Modern knowledge work is fragmented by design. Email lives in one application. Tasks in another. Notes in another. Calendar in another. Each tool is optimized for itself, not for the human moving between them.

The result is a hidden tax on every worker — constant context switching, manual data transfer between applications, and the continuous cognitive overhead of maintaining a mental map across disconnected systems. The busier and more complex the work, the worse the problem becomes.

Integration platforms move data but not context. All-in-one tools solve fragmentation by replacing specialized tools with mediocre generalists. AI assistants are reactive, not proactive. 

Nobody has attacked the problem at the correct layer of abstraction. The application model itself is the problem. You cannot solve context fragmentation with another application.

---

## Core Insight

Every major leap in human-computer interaction required rethinking the operating system paradigm — not building a better app on top of an existing one. The desktop metaphor was a rethinking. The smartphone was a rethinking. A truly adaptive, context-aware personal computing environment requires the same level of foundational change.

The correct approach is to start at the Linux kernel and build upward — embedding the intelligence and integration infrastructure at the core rather than bolting it on at the application layer. The AI does not assist the UI. The AI *drives* the UI in real time, reshaping the workspace continuously based on context.

---

## Key Concepts

**Context-Aware Workspace**
A single, screen-filling environment that adapts dynamically throughout the day based on calendar state, task load, incoming communications, time, and inferred cognitive context. Not a dashboard. A living surface.

**AI-Driven UI**
The interface is not configured by the user and left static. It is generated and reshaped in real time by an AI layer reading continuous context signals. Static interfaces are designed for average moments. This is not designed for average moments.

**Composable Infrastructure**
Built on the Unix philosophy — small, sharp components that do one thing well and communicate through standard interfaces. Services, data, workflows, and intelligence combined in dynamic combinations as needed.

**Semantic Memory Layer**
A shared, searchable knowledge store that persists context across tools, sessions, and time. The connective tissue that makes composability meaningful rather than just mechanical.

**The End of Applications**
Applications, as we have known them, no longer have relevance. Functionality is delivered dynamically, with the exact services and data being exposed when they are needed. No more windows isolating work components from each other.  Seamless, frictionless experiences become normal.

**Full Stack Ownership**
Open at every layer. No corporate incentive corrupting the foundation. No data harvesting. No subscription gates. The user owns their environment completely.

**Free and Open Source**
Gr4Ig will never be a product in the commercial sense. It is infrastructure for people, built in the tradition of free open source software. The goal is longevity and community, not revenue.



---

## What This Is Not

- Not another productivity app
- Not an AI assistant bolted onto an existing desktop
- Not a dashboard or widget system
- Not a commercial product
- Not finished — and does not need to be to matter

---

## Current State

Pre-research. The infrastructure primitives are being assembled through the Open Brain project and home lab build-out. The problem is understood. The solution space is not yet mapped. The knowledge required to proceed is significant and will be acquired methodically.

The research phase is the work. Experiments, findings, and architectural decisions will be captured here and in Open Brain as they develop.

The first validation artifact exists: [Pythia](https://github.com/gr4ig/pythia) (2026-07) — a fully offline knowledge system consolidating local inference, semantic search across ~0.5 TB of reference material, live geographic computation, and voice interaction on a single laptop, with measured results published in the *AI Data Center in a Backpack* series. It is small-scale evidence that the single-host constraint holds.

---

## Infrastructure

### Deployment Target
The production target is a single host. All compute, inference, memory, and orchestration should eventually run on one machine. This is a significant engineering challenge today but is expected to become increasingly tractable as hardware density continues to improve. The multi-server prototype makes no assumptions that would prevent future single-host consolidation — that constraint should be treated as a first-class architectural requirement from the beginning.

**Near-term hardware candidate:** Apple Silicon Mac Studio (M5 Max or Ultra, 192GB+ unified memory) represents a plausible single-host validation target. The unified memory architecture — CPU, GPU, and Neural Engine sharing a single high-bandwidth memory pool — eliminates the resource contention that makes single-host consolidation difficult on conventional hardware. Inference, orchestration, and UI rendering could potentially coexist without competing across a bus. Asahi Linux is the likely OS path on Apple Silicon and should be tracked as it matures. This is not a commitment — it is an acknowledgment that the hardware curve may deliver a viable single-host platform sooner than expected.

**Second candidate (added 2026-07-08):** NVIDIA's RTX Spark platform — announced at Computex 2026, shipping in laptops and compact desktops from major OEMs beginning fall 2026 — pairs a GB10-recipe Arm CPU with a Blackwell GPU and up to 128GB of unified LPDDR5X at roughly 300 GB/s, comparable in bandwidth to current Apple Pro-tier silicon. It launches positioned as a Windows-on-Arm platform, but NVIDIA's silicon has first-party Linux in its institutional DNA: DGX OS runs on the same GB10 architecture and NVIDIA's kernel modules are open source. Linux enablement on this hardware is a driver-engineering problem, not the reverse-engineering effort the Apple path requires. The decisive difference is CUDA. It unlocks vLLM-class serving — continuous batching, concurrent low-latency inference, the exact operating point named in the open questions below — and local fine-tuning of small purpose-built models. Single-stream generation should be comparable to Apple silicon, not faster; the win is concurrency, which is the workload an adaptive UI actually generates.

### Prototype Stack
The following tools are used to develop and validate the architecture across multiple servers. They are reference implementations, not requirements. The architecture is the transferable asset — not the specific tools.

- PostgreSQL + pgvector — semantic memory store (Open Brain)
- n8n — event ingestion and automation pipeline
- MCP server — AI interface layer
- llama.cpp — local inference engine (migrating from Ollama)
- Open WebUI — local model interface
- Obsidian — primary knowledge capture

### Production Equivalents
To be determined through research. Each prototype component should be replaceable with best-of-class open source alternatives as the architecture matures.

---

## Open Questions

- What does the compositor and display server architecture look like for a fully AI-driven UI?
- How does context get defined, measured, and fed to the rendering layer in real time?
- What existing projects (Wayland, wlroots, etc.) provide the right foundation vs. what needs to be built fresh?
- What does a minimal, correct first scaffold look like — enough to attract the right contributors?
- How do existing attempts at adaptive UI (at any layer) inform or constrain the approach?
- What inference architecture can support real-time, concurrent, low-latency UI decisions at scale? Single-threaded engines (Ollama, bare llama.cpp) are a known bottleneck. Candidates include vLLM, distributed llama.cpp instances, and purpose-built inference fabrics. This is a core unsolved requirement — the adaptive UI model only works if inference keeps pace with continuous context changes.

---

## On Timeline

The time available is the time available. The goal is not to finish Gr4Ig. The goal is to start it correctly — with sound architecture, honest documentation, and enough working scaffold that it can grow beyond any single contributor. A well-planted seed outlasts its planter.

---

*This document is a living record. Update as understanding develops.*
