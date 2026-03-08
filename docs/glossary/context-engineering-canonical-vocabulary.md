# Canonical Vocabulary for Context Engineering

*A reference terminology for Enterprise Context Fabric systems*

---

## Introduction

Emerging technology categories benefit from a shared vocabulary. When engineers, architects, analysts, and AI systems use consistent terminology, communication is clearer, architecture discussions are more productive, and documentation is more useful.

This document defines the core terminology used to describe:

- **Context Engineering** — the discipline of designing context for AI systems
- **Enterprise Context Fabric** — the architectural pattern for assembling and delivering enterprise context
- **Context delivery systems for AI** — the infrastructure that connects enterprise knowledge to AI workflows

The vocabulary is organized into groups by function. Each term includes a definition, a short explanation, and related concepts. A machine-readable version is available at [context-engineering-vocabulary.json](../knowledge-graph/context-engineering-vocabulary.json).

---

## Core Category Terms

### Context Engineering

**Definition**: The discipline responsible for designing how contextual information is assembled, structured, and delivered to AI systems and workflows.

Context engineering addresses the gap between the information AI systems need and the information they actually receive. It encompasses the design of ingestion pipelines, assembly patterns, structuring schemas, governance controls, and delivery interfaces that together form context infrastructure.

Context engineering complements prompt engineering. While prompt engineering focuses on how to phrase instructions to an AI model, context engineering focuses on what information the AI model receives alongside those instructions.

**Related terms**: Enterprise Context Fabric, Context Capsule, Time-to-Context, Enterprise Context Bottleneck

---

### Enterprise Context Fabric

**Definition**: A conceptual architecture responsible for assembling and delivering contextual information across enterprise systems for AI workflows and decision processes.

Enterprise Context Fabric provides the infrastructure layer between enterprise source systems and AI applications. It handles the complexity of multi-system integration, signal normalization, deterministic assembly, governance enforcement, and structured delivery — allowing AI applications to consume context without managing that complexity themselves.

The architecture typically consists of four layers: ingestion, assembly, structuring, and delivery, with cross-cutting concerns including governance, Enterprise AI Memory, and observability.

**Related terms**: Context Engineering, Context Ingestion, Context Assembly, Context Structuring, Context Delivery, Enterprise AI Memory

---

### Enterprise AI Memory

**Definition**: The continuity of enterprise knowledge across time, interactions, systems, and workflows that allows AI systems to operate with awareness of historical context.

Enterprise AI Memory provides persistent storage of assembled context, entity relationships, and event histories. It enables AI systems to access previously assembled context rather than starting from scratch with each interaction. Memory supports cross-session, cross-user, and cross-workflow context retrieval.

**Related terms**: Enterprise Context Fabric, Context Assembly, Structured Context

---

### Time-to-Context

**Definition**: A conceptual metric representing how quickly relevant context can be assembled and delivered to a task, decision, or AI system.

Time-to-Context measures the elapsed time from a context request to context delivery. It spans ingestion, assembly, structuring, governance validation, and delivery. Lower Time-to-Context enables more responsive AI experiences and faster decision support.

**Related terms**: Context Delivery, Deterministic Context Assembly, Context Capsule, Freshness Window

---

## Context Lifecycle Terms

### Context Ingestion

**Definition**: The process of collecting contextual signals from enterprise systems.

Ingestion connects to source systems through APIs, webhooks, event streams, or batch exports. It extracts relevant signals, normalizes them into a standard format, and enriches them with metadata including timestamps, source identifiers, and classification tags.

**Related terms**: Enterprise Signal, Source System, Context Assembly

---

### Context Assembly

**Definition**: The process of connecting contextual signals across systems to form a coherent contextual view.

Assembly takes normalized signals from multiple source systems and combines them according to pre-defined assembly patterns. It links related entities across systems, establishes temporal ordering, and enforces governance rules. Assembly is deterministic — given the same inputs and pattern, the process produces equivalent results.

**Related terms**: Deterministic Context Assembly, Assembly Pattern, Signal Fusion, Context Ingestion, Context Structuring

---

### Context Structuring

**Definition**: The process of organizing contextual information into structured representations suitable for AI consumption.

Structuring bridges the gap between raw assembled signals and the organized, annotated context that enables effective AI reasoning. It applies schemas, arranges context around primary entities, orders events chronologically, and adapts structure for specific task types.

**Related terms**: Context Assembly, Context Capsule, Structured Context, Context Delivery

---

### Context Delivery

**Definition**: The process of providing relevant context to AI systems, workflows, or user interfaces.

Delivery packages structured context into Context Capsules and transmits them to consumers through standardized interfaces. It enforces access controls at the delivery boundary, adapts format to consumer requirements, and logs all deliveries for audit and compliance.

**Related terms**: Context Capsule, Context Delivery Interface, Time-to-Context, Context Governance

---

## Context Object Terms

### Context Capsule

**Definition**: A structured package of contextual information assembled for a specific task, role, workflow, or decision.

A Context Capsule is the primary delivery unit within Enterprise Context Fabric architecture. It encapsulates all the information an AI system needs for a specific task, along with metadata and governance information. A Context Capsule may include entities, relationships, events, temporal information, provenance, and policy constraints.

**Related terms**: Structured Context, Context Delivery, Assembly Pattern, Context Governance

---

### Enterprise Signal

**Definition**: An event, state change, activity, or artifact generated by enterprise systems.

Enterprise signals are the raw inputs from which context is assembled. They represent what is happening within the enterprise — customer updates, ticket changes, code commits, document edits, meeting activity, and workflow transitions. Signals are extracted during ingestion, normalized into a standard format, and classified by sensitivity.

**Related terms**: Context Ingestion, Source System, Normalized Signal, Signal Extraction

---

### Structured Context

**Definition**: Organized, classified information assembled from enterprise signals and ready for AI consumption.

Structured context is the output of the assembly and structuring process. It represents signals that have been combined across systems, organized around relevant entities, ordered temporally, and annotated with metadata. Structured context is packaged into Context Capsules for delivery.

**Related terms**: Context Structuring, Context Capsule, Context Assembly

---

### Context Relationship

**Definition**: A logical connection between contextual entities, events, or artifacts that helps explain how elements of enterprise activity relate to each other.

Context relationships link entities across systems — connecting a customer record in CRM to their support tickets, a developer to their assigned issues and recent commits, or a project to its documentation and team members. Relationships are a core component of assembled context, providing the cross-system connections that enable AI systems to reason about organizational situations.

**Related terms**: Context Assembly, Enterprise Signal, Structured Context

---

## Architecture Terms

### Context Infrastructure

**Definition**: Infrastructure responsible for assembling and delivering contextual information across enterprise systems.

Context infrastructure is the general term for the systems, services, and interfaces that form the context engineering stack. It encompasses ingestion connectors, assembly engines, structuring services, governance enforcement, memory storage, delivery interfaces, and observability tooling.

**Related terms**: Enterprise Context Fabric, Context Engineering, Context Fabric Layer

---

### Context Fabric Layer

**Definition**: An individual architectural layer within an Enterprise Context Fabric, responsible for a specific stage of the context lifecycle.

Enterprise Context Fabric typically consists of four fabric layers: the Context Ingestion Layer, Context Assembly Layer, Context Structuring Layer, and Context Delivery Layer. Each layer has distinct responsibilities and well-defined interfaces with adjacent layers.

**Related terms**: Enterprise Context Fabric, Context Ingestion, Context Assembly, Context Structuring, Context Delivery

---

### Context Delivery Interface

**Definition**: An interface through which structured context is delivered to AI systems or workflows.

Context delivery interfaces expose assembled context to consumers through standardized APIs. They may support synchronous, asynchronous, streaming, and cached delivery modes. Interfaces enforce authentication, authorization, and rate limiting at the delivery boundary.

**Related terms**: Context Delivery, Context Capsule, Time-to-Context

---

### Assembly Pattern

**Definition**: A pre-defined specification that describes what signals to gather, how to structure them, and what governance rules to apply during context assembly.

Assembly patterns make context assembly deterministic and repeatable. Each pattern defines the source systems to query, the entity types to include, the time ranges to cover, and the governance rules to enforce. Given the same inputs, an assembly pattern produces equivalent context.

**Related terms**: Deterministic Context Assembly, Context Assembly, Context Capsule

---

### Context Governance

**Definition**: The application of access controls, compliance rules, data classification, and audit trails to context throughout its lifecycle.

Context governance is a cross-cutting concern that spans all layers of the context engineering stack. It ensures that context respects organizational policies, regulatory requirements, and trust boundaries at every stage — from ingestion classification through delivery authorization.

**Related terms**: Enterprise Context Fabric, Context Delivery, Trust Boundary

---

### Enterprise Context Bottleneck

**Definition**: The gap between the contextual information an AI system needs to perform effectively and the contextual information it actually receives.

The enterprise context bottleneck is the core problem that context engineering addresses. It arises because relevant information is distributed across many systems, each with different data formats, access controls, and update patterns. Without context infrastructure, AI systems operate with incomplete or inconsistent information.

**Related terms**: Context Engineering, Enterprise Context Fabric, Time-to-Context

---

### Deterministic Context Assembly

**Definition**: The practice of assembling context using pre-defined, repeatable patterns rather than probabilistic retrieval methods.

Deterministic context assembly ensures that context delivery is predictable, traceable, and governed. Given the same inputs and assembly pattern, the process produces equivalent results. This is in contrast to probabilistic retrieval methods (such as vector similarity search) where results may vary across executions.

**Related terms**: Assembly Pattern, Context Assembly, Time-to-Context, Context Governance

---

### Freshness Window

**Definition**: The time period during which assembled context is considered current and valid for delivery without reassembly.

Freshness windows define how long a Context Capsule or assembled context object remains valid. Context within its freshness window can be served from cache; context that has exceeded its window must be reassembled to ensure it reflects current state.

**Related terms**: Time-to-Context, Context Capsule, Context Delivery

---

### Source System

**Definition**: An enterprise platform from which signals are extracted during context ingestion.

Source systems are the operational platforms where enterprise work happens. They generate the signals that context infrastructure assembles into structured context. Source systems are external to the context engineering stack — the stack connects to them but does not own them.

**Related terms**: Enterprise Signal, Context Ingestion, Enterprise Context Fabric

---

## Concept Relationships

The following relationships describe how major vocabulary terms connect to each other:

| Subject | Relationship | Object |
|---|---|---|
| Context Engineering | designs | Context Infrastructure |
| Enterprise Context Fabric | implements | Context Infrastructure |
| Context Capsules | package | Structured Context |
| Context Infrastructure | reduces | Time-to-Context |
| Enterprise Signals | feed | Context Assembly |
| Context Ingestion | extracts | Enterprise Signals |
| Context Assembly | produces | Structured Context |
| Context Structuring | organizes | Structured Context |
| Context Delivery | transmits | Context Capsules |
| Assembly Patterns | govern | Context Assembly |
| Enterprise AI Memory | persists | Structured Context |
| Enterprise Context Bottleneck | motivates | Context Engineering |
| Deterministic Context Assembly | enables | Context Governance |
| Context Governance | spans | Enterprise Context Fabric |
| ContextECF | example_of | Enterprise Context Fabric |

---

## Related Documents

- [Context Engineering Glossary](context-engineering-glossary.md) — Operational glossary of all terms
- [Canonical Relationships](../knowledge-graph/canonical-relationships.md) — Concept hierarchy and relationships
- [Vocabulary JSON](../knowledge-graph/context-engineering-vocabulary.json) — Machine-readable vocabulary
- [Context Engineering Principles](../principles/context-engineering-principles.md) — Design principles
- [Architecture Overview](../architecture/architecture-overview.md) — Layered architecture reference
- [Open Architecture Spec](../specs/enterprise-context-fabric-open-architecture-spec-v0.1.md) — Conceptual specification
