# Gr4Ig — MVP and Phased Roadmap

*Version 0.2 — 2026-03-08*
*Status: Draft — Pre-research phase*

---

## Purpose

This document defines a minimum viable product for Gr4Ig and the phases that follow it toward full vision realization.

The full vision — an AI-driven personal operating environment that replaces the window paradigm, eliminates context switching, and operates as a genuine collaborative partner — contains several hard unsolved problems. Building toward that vision does not require solving all of them before putting something real into people's hands.

The MVP is not a compromise. It is a deliberate first step that delivers meaningful value, validates core architectural decisions, and creates the foundation on which harder problems can be solved with real-world feedback rather than speculation.

---

## The Line Between MVP and Vision

The full vision requires solving three genuinely hard problems: real-time local inference at low latency, an AI-driven compositor that replaces the window paradigm, and a Flow Engine with no direct prior art. None of these are solved today.

The MVP defers all three. It operates within existing desktop environments, does not attempt to replace the compositor, and makes no claims about real-time flow prediction. What it does — done well — still represents a fundamentally different relationship between the user and their computer.

The test for the MVP is not "does it realize the full vision." It is "does it feel like a different paradigm, even in its limited form." A user who experiences the MVP should feel that something has genuinely changed — not that they have installed another productivity tool.

---

## Phase 1 — MVP: The Memory and Voice Foundation

*Deliverable: A working system that knows the user's work, surfaces what is relevant without being asked, and accepts voice as a first-class interaction.*

### What it is

A local, open source, AI-powered layer that sits alongside the user's existing desktop environment and does three things:

**1. Unified Semantic Memory**
All of the user's work — documents, notes, emails, calendar, tasks, communications — flows into a single, locally hosted semantic store. Nothing is siloed. Everything is searchable. The system surfaces relevant context automatically, including content the user did not know they needed, based on what they are currently working on.

This is the Data & Memory Layer made real. It is the connective tissue that existing tools have never provided. It eliminates the manual data transfer between applications that is one of the primary drivers of context switching.

**2. Context-Aware Retrieval**
The system maintains awareness of the user's current activity and uses it to proactively surface relevant information. Not search — anticipation. When the user is in a meeting, relevant notes and prior context appear. When they open a document, related work surfaces. The system is always reading the situation and preparing for what comes next.

This is a first, limited implementation of the Cognitive Engine — intent inference at the immediate horizon only, without session or project-level reasoning.

**3. Voice as a First-Class Interaction**
The user can speak to the system naturally — asking questions, capturing thoughts, issuing instructions — and receive spoken responses. Voice is not a wrapper around a text interface. It is a genuine interaction mode, ambient and always available, that does not require the user to stop what they are doing to engage with their computer.

This is the Voice Interface made real, independent of the compositor work it will eventually be integrated with.

### What it is not

- It does not replace the window manager or desktop environment
- It does not attempt real-time flow prediction
- It does not reshape the visual surface dynamically
- It is not yet the full collaborative partner described in the vision

### Why this is still a paradigm shift

A user whose computer knows everything they have worked on, surfaces what is relevant without being asked, and listens and responds naturally — without switching applications, without searching, without manually transferring context — is experiencing something qualitatively different from any existing tool. The cognitive overhead reduction is real and immediate even without the full vision realized.

This is the proof that the paradigm is right. Everything else builds on this foundation.

### Capability composition model

Phase 1 does not deliver the full capability composition model — the framework through which microservices, information, and flow replace monolithic applications. That model is a longer-term architectural effort. However, Phase 1 must be designed in a way that does not inadvertently foreclose it. The microservice and data architecture established in the MVP must be compatible with the composition model that will be built above it.

Defining the capability composition model conceptually is a research task that runs in parallel with Phase 1 development, not after it.

### Target platform

Existing Linux desktop environment. The MVP does not require custom kernel work, a custom compositor, or purpose-built inference infrastructure. It runs on the prototype stack already in development.

### Success criteria

- The system knows the user's work across all connected sources without manual input
- Relevant context surfaces automatically and accurately during active work
- Voice interaction is natural, responsive, and genuinely useful as a primary mode
- A user with no prior knowledge of the system can experience the difference within their first session
- All data remains local and user-owned

---

## Phase 2 — The Cognitive Layer

*Deliverable: A system that reasons about the user's work at multiple time horizons and begins to demonstrate genuine anticipation.*

### What changes

Phase 2 deepens the intelligence layer established in Phase 1. The Cognitive Engine expands from immediate intent inference to session and project-level reasoning. The User Relationship Model begins accumulating meaningful knowledge of the user — their patterns, priorities, and working style — and demonstrably applying it.

The system starts to feel like it knows the user, not just their documents.

**Session-level reasoning** — The system understands what the user is trying to accomplish today, not just what they are doing right now. It prepares for the arc of the day rather than reacting to each moment.

**Project-level reasoning** — The system maintains awareness of longer-running work — ongoing projects, open obligations, recurring patterns — and factors them into what it surfaces and when.

**Early flow modeling** — A first, limited implementation of the Flow Engine. Not real-time prediction — a simpler model that identifies patterns in the user's work behavior over time and uses them to improve anticipation. The foundation on which the full Flow Engine will be built.

**Deepening user relationship** — The User Relationship Model accumulates enough longitudinal knowledge to make the system demonstrably more capable than it was in Phase 1. Users who have been on the system for months should experience something meaningfully richer than users in their first week.

### Success criteria

- The system demonstrably anticipates needs at session and project level
- Users report that the system feels like it knows them
- The User Relationship Model produces measurable improvements in relevance over time
- Early flow modeling produces at least one class of accurate next-state prediction

---

## Phase 3 — The Experience Layer: Voice and Flow

*Deliverable: Voice interaction that is genuinely ambient and a visible flow representation that makes the user's work navigable.*

### What changes

Phase 3 begins the work of the Experience Layer — not the full visual surface replacement, but the two components that do not require compositor work.

**Ambient voice** — Voice interaction becomes truly ambient. The system listens continuously, responds contextually, and integrates with the cognitive layer deeply enough that voice feels like thinking out loud rather than issuing commands. The keyboard recedes as the primary interaction mode for a meaningful class of tasks.

**Flow Navigator** — A visible representation of the user's current flow — where they are, where they have been, where the system predicts they are going — appears as an overlay or companion surface within the existing desktop environment. Forks and returns are visible and navigable. The user can see the shape of their work and move through it intentionally.

This is the first visible evidence of the flow-based working model. Users encounter it here for the first time.

### Success criteria

- Voice interaction is the preferred mode for a meaningful class of tasks
- The Flow Navigator accurately represents the user's work flow
- Users can navigate forks and returns without losing context
- The flow model shows measurable improvement in prediction accuracy over Phase 2

---

## Phase 4 — The Compositor: Replacing the Window Paradigm

*Deliverable: A custom Wayland compositor driven by the AI layer, replacing the window model with a context-aware visual surface.*

### What changes

This is the hardest phase and the one that most directly realizes the full vision. The window-and-application paradigm is replaced.

**AI-driven compositor** — A custom Wayland compositor accepts real-time layout and content instructions from the cognitive layer. The visual surface reshapes continuously based on context. Windows, as the user has known them, no longer exist as the organizing principle of the experience.

**Legacy application integration** — Existing applications are abstracted within the new surface. The user does not lose access to their tools. The compositor presents legacy application content as elements within a larger context-aware workspace rather than as isolated windows.

**Full Experience Layer** — The Visual Surface, Voice Interface, and Flow Navigator operate as an integrated whole for the first time. The experience is no longer a layer on top of an existing desktop — it is the desktop.

### Dependency

Phase 4 cannot begin until the inference runtime problem is solved. The AI-driven compositor requires low-latency, continuous inference decisions. That operating point must be achieved and validated before the compositor is built to depend on it. Research on the inference architecture runs in parallel with Phases 1–3 and must reach a viable solution before Phase 4 begins.

### A note on legacy applications

Phase 4 does not permanently accommodate legacy applications. Applications as currently understood — monolithic, window-based, data-siloed — are not the target model for this environment. They are the problem the architecture is designed to solve.

During Phase 4, legacy applications will be accommodated as a transitional bridge. Users arriving on the platform before the capability composition model is fully mature need access to their existing tools. That accommodation exists for practical reasons, not architectural ones. It will be retired when the new model is ready to replace it. The compositor's architectural design is not driven by this transitional requirement.

### Success criteria

- The compositor operates stably and performantly on the target hardware
- The visual surface reshapes accurately in response to context changes
- The window paradigm is no longer the organizing principle of the experience
- Legacy applications are accommodated transitionally without driving architectural decisions
- Inference latency is below the threshold of perceptible delay
- The capability composition model is sufficiently mature for early developers to build against

---

## Phase 5 — Single Host and Full Vision

*Deliverable: The complete Gr4Ig vision running on a single host.*

### What changes

All compute, inference, memory, and orchestration consolidated onto one machine. The multi-server prototype architecture is retired. The system achieves the deployment target described in the Foundation document.

**Single-host consolidation** — All layers run on one machine without resource contention. The unified memory architecture of the target hardware (Apple Silicon or equivalent) makes this tractable in ways that conventional hardware does not.

**Full Flow Engine** — The complete Flow Engine — real-time, continuously updated causal model of the user's work flow — replaces the early flow modeling of Phase 2. Next-state prediction is accurate, continuous, and fast enough to drive the Experience Layer in real time.

**Mature user relationship** — The User Relationship Model has accumulated enough longitudinal depth to make the system a genuine collaborative partner in the full sense described in the vision. The system knows the user well enough that explicit instruction is the exception rather than the rule.

### Success criteria

- All components run on a single host without performance degradation
- The full Flow Engine operates at real-time latency
- The user relationship model produces genuine anticipatory behavior across all three time horizons
- The system is demonstrably more capable for a user of two years than a user of two weeks
- The experience matches the vision described in the Foundation document

---

## Roadmap Summary

| Phase | Focus | Hard Problems Addressed | Depends On |
|---|---|---|---|
| 1 — MVP | Memory and voice foundation | None — high feasibility components only | Prototype stack |
| 2 — Cognitive Layer | Multi-horizon reasoning, user relationship | Flow Engine research begins | Phase 1 |
| 3 — Experience Layer | Ambient voice, Flow Navigator | Flow modeling validation | Phase 2 |
| 4 — Compositor | Window paradigm replacement, transitional legacy accommodation | Inference runtime, AI compositor | Phase 3 + inference research |
| 5 — Full Vision | Single host, full Flow Engine, legacy accommodation retired | All hard problems | Phase 4 + capability composition model |
| Future — Generative Capabilities | System generates new capabilities for unmet user needs | Composition model generativity | Phase 5 + mature user relationship |

---

## A Note on Parallelism

The phases above describe the sequence of user-facing capability delivery. Research does not follow this sequence. The hard problems — real-time inference architecture, compositor design, Flow Engine foundations — must be researched in parallel with early phase development, not deferred until they are needed. Phase 4 cannot begin without solutions to problems that must be explored starting now.

Contributors with deep expertise in inference architecture, Wayland compositor development, flow modeling, or capability composition model design are needed from the beginning of the project, not from the phase in which their work becomes visible. The research track and the development track run together.

The capability composition model — the framework that replaces the application paradigm with composable microservices, information, and flow — is a research and design effort that must begin in parallel with Phase 1. It is the most significant architectural concept not yet defined in the current document set. It will have its own dedicated document when the design work matures.

---

*This document is a living record. Update as understanding develops.*
