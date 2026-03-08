# Gr4Ig — Functional Architecture

*Version 0.2 — 2026-03-08*
*Status: Draft*

> An interactive version of this document is available at `functional-architecture.html`.
> The narrative content below is identical — the HTML version adds a visual layer diagram.

---

## A Paradigm Shift

*This must be understood before the first line of code is written.*

Every computing paradigm before Gr4Ig has been built on the same implicit contract: the user manages the machine. More capable machines required more capable management. More tools required more context switching. More complexity required more cognitive overhead. The user's attention became the scarcest resource in knowledge work — and the computer consumed it.

**Gr4Ig rejects that contract entirely.**

The window-and-application model is not a neutral design choice — it is the physical expression of a task-centric theory of work that no longer reflects how people actually think, create, or operate. It fragments flow. It isolates context. It taxes the user continuously for the privilege of using the tool.

Gr4Ig is organized around a flow-based theory of work. Work is not a collection of discrete tasks executed in separate applications. It is a continuous, branching river of thought and action — context-rich, nonlinear, and deeply personal. The system's job is to understand that flow, enable it, and stay out of its way.

The shift this requires from the user is real: relinquishing the control that previous systems demanded. In exchange, the user recovers something more valuable — the freedom to think, create, and innovate without the machine demanding management. The computer stops being an obstacle and becomes, for the first time, a genuine partner.

---

## The User Compact

*What the system commits to the user. What the relationship requires in return.*

### What the system commits

- The system will carry the cognitive overhead you have always carried alone.
- It will remember what you cannot hold in mind simultaneously.
- It will anticipate what you need before you know you need it.
- It will grow more capable the longer you work together.
- It will never harvest your data, gate your environment, or serve any interest but yours.
- Your work, your context, and your relationship with the system belong entirely to you.

### What the relationship requires

- You will need to release some control — not your judgment or your agency, but the exhausting habit of managing the machine.
- Early in the relationship, the system will know little. Trust the arc, not just the moment.
- The partnership deepens through use. The system cannot know you without working with you.
- Your role is to think, create, decide, and direct. The system's role is everything else.

---

## The Architecture

Gr4Ig is organized as six concentric layers. The user sits at the outside — the system exists entirely in their service. Each layer inward is less visible to the user and more foundational to the system. The Orchestration Fabric at the hub is what makes the layers behave as a single coherent thing rather than independent components.

---

### Experience Layer
*The surface the user touches*

The Experience Layer is the only part of the system the user directly perceives. It is generated and reshaped in real time by the layers beneath it — never configured once and left static. Its sole obligation is to surface exactly what is needed, at the moment it is needed, with zero unnecessary friction. The experience is not designed for average moments. It is designed for this moment.

**Visual Surface** — The adaptive, context-driven workspace. Not a window manager — a living canvas that reshapes continuously based on the user's current flow state. No windows. No application boundaries. A unified surface that serves the work.

**Voice Interface** — First-class ambient speech I/O. Interruptible, parallel to other activity, and deeply integrated — not a microphone button bolted onto a keyboard-centric system. Voice is a native mode of interaction, not an alternative one.

**Flow Navigator** — The visible representation of the user's current flow — where they are, where they've been, where the system predicts they're going. Forks and returns are native, not workarounds. The user is never lost in their own work.

---

### Cognitive & Flow Layer
*Reasoning, prediction, intent, partnership*

The Cognitive & Flow Layer is where Gr4Ig diverges most sharply from every previous computing system. It does not only respond to commands — it reasons ahead of the user's current position, anticipates needs before they are expressed, and continuously deepens its understanding of who the user is and how they work. This layer is the seat of the collaborative partnership between user and system. The user brings intent, judgment, and creativity. The system brings memory, anticipation, and context. Over time, as the relationship deepens, the system requires fewer commands because it already knows — and the user is freed to think, create, and move without the machine demanding management.

**Cognitive Engine** — Reasons over context signals to derive intent at three horizons: immediate (what am I doing now), session (what am I accomplishing today), and project (what am I working toward). Responds to commands — and reasons far beyond them. The brain of the system.

**Flow Engine** — Maintains a continuously updated model of the user's work flow. Predicts next states, prepares resources before they are needed, and manages forks and returns without losing context. The user's flow is never interrupted by the system — only enabled by it. The most novel component in the architecture.

**User Relationship Model** — The system's growing knowledge of the user — their patterns, working style, priorities, and obligations. Never declared, never frozen. Continuously observed, inferred, and revised. The longer the relationship, the more capable the system becomes. This is what transforms a tool into a partner.

---

### Orchestration Fabric
*The hub — connective tissue*

The Orchestration Fabric is the hub that everything speaks through — the most structurally critical layer in the system and the least visible to the user. It moves signals with precision and speed, maintains state coherence across all components, and ensures the system behaves as a single integrated thing rather than a collection of parts negotiating with each other. This is where many OS-level projects fail: individual components work, but the fabric between them is an afterthought that becomes a bottleneck. In Gr4Ig the fabric is a first-class architectural concern from the beginning. Everything above it depends on it being fast, coherent, and invisible.

**Event Bus** — The nervous system of signal transmission. All context signals, state changes, and inter-component messages move through here. High-throughput, low-latency, no bottlenecks. The speed of the fabric is the speed of the system.

**Service Mesh** — Manages the lifecycle, discovery, and communication of all system services. Ensures composable components behave as one coherent system rather than a collection of parts. Composability is only meaningful if the mesh is invisible.

**State Coordinator** — Maintains coherence across the system at all times. When context changes, the State Coordinator ensures every dependent component is updated consistently and in the right order. Coherence is not a feature — it is the baseline.

---

### Data & Memory Layer
*The persistent foundation*

The Data & Memory Layer is the foundation everything builds on. All user data lives here — never siloed by the service that created it, always owned entirely by the user. The semantic store supports both known retrieval and unknown discovery. The relationship memory is what accumulates over time and makes the system genuinely more capable the longer it is used. This layer is not infrastructure in the background sense — it is the substance of the user relationship, persisted. Its integrity is as important as any other system property.

**Semantic Store** — A unified, searchable knowledge base for all user data. Supports both explicit retrieval (find what I know I need) and inference-driven surfacing (find what I don't know I need). No data silo may exist above this layer. All data belongs to the user.

**Context Stream** — A continuous, time-ordered record of context signals — calendar state, task load, communications, activity patterns. The raw material the Cognitive Engine reasons over. The richer the stream, the more accurate the partnership.

**Relationship Memory** — The persistent substrate of the system's growing knowledge of the user. Long-lived, carefully maintained, and treated as a first-class asset. Loss or corruption here does not break a feature — it damages the relationship. Continuity here is non-negotiable.

---

### Hardware Abstraction Layer
*Boundary with physical reality*

The Hardware Abstraction Layer is the boundary between Gr4Ig and physical reality. Most of this is inherited from Linux — kernel, drivers, and resource management are well-solved problems that the project leverages rather than rebuilds. The novel concern here is the inference runtime: local AI inference is a hard real-time requirement for this system, not a background task. Its resource demands must be managed at this layer so the layers above can treat intelligence as a reliable, low-latency service. The single-host deployment target is a first-class constraint that this layer must satisfy.

**Kernel & Drivers** — Linux kernel and hardware drivers. Largely inherited, not built. Presents a clean, stable surface to everything above. The goal is maximum leverage of existing open source infrastructure — Gr4Ig builds on this layer, not against it.

**Resource Manager** — CPU, memory, storage, and network allocation. Ensures inference, orchestration, and experience rendering coexist without resource contention — especially critical on single-host deployments where all layers share the same hardware.

**Inference Runtime** — The local AI inference engine. A dedicated concern at this layer because inference throughput is a first-class architectural constraint — the entire adaptive system depends on it keeping pace with continuous context changes. Latency here propagates upward through every layer.

---

*This document is a living record. Update as understanding develops.*
