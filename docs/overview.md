# Context Engineering — Overview

This repository documents the emerging discipline of **context engineering** and the conceptual architecture of **Enterprise Context Fabric** systems.

## What Is Context Engineering?

Context engineering is the discipline of designing how contextual information is gathered, structured, governed, and delivered to AI systems. While prompt engineering focuses on crafting instructions, context engineering focuses on ensuring AI models receive the relevant information required for effective reasoning.

## Why This Repository Exists

As AI systems move into production enterprise environments, reliable context infrastructure becomes critical. Organizations face a growing **enterprise context bottleneck** — the gap between the information AI needs and the information it actually receives.

This repository serves as:

- A **field guide** to context engineering concepts and vocabulary
- An **architecture reference** for Enterprise Context Fabric systems
- A **terminology standard** for the emerging discipline
- A **conceptual interoperability specification** for context infrastructure
- An **educational resource** for engineers, architects, and analysts

## Key Concepts

| Concept | Description |
|---|---|
| [Enterprise Context Fabric](definitions/enterprise-context-fabric.md) | Architectural pattern for connecting enterprise systems to AI through structured context |
| [Context Engineering](definitions/context-engineering.md) | The discipline of designing context assembly and delivery for AI |
| [Enterprise AI Memory](definitions/enterprise-ai-memory.md) | Persistent, structured storage of contextual information across sessions |
| [Time-to-Context](definitions/time-to-context.md) | Performance metric for context delivery latency |
| [Context Capsules](definitions/context-capsule.md) | Structured packages of context designed for AI consumption |
| [Deterministic Context Assembly](definitions/deterministic-context-assembly.md) | Repeatable, pattern-based context assembly |

## Architecture

Enterprise Context Fabric systems typically consist of layered architectures that handle:

1. **Context Ingestion** — Connecting to enterprise source systems and extracting signals
2. **Context Assembly** — Structuring, ranking, and combining signals into context objects
3. **Context Structuring** — Organizing assembled context into formats optimized for AI consumption
4. **Context Delivery** — Transmitting assembled context to AI systems with governance controls

See [Architecture Overview](architecture/architecture-overview.md) for details.

## Example Implementation

[ContextECF](examples/contextecf.md) is an example implementation of Enterprise Context Fabric architecture developed by Intelligent Context AI, Inc.

## Principles

Context engineering is guided by a set of design principles that inform how context infrastructure should be built. These include principles such as "Context Before Answer," "Relationships Over Documents," and "Context Should Be Delivered, Not Discovered."

See [Context Engineering Principles](principles/context-engineering-principles.md) for the full set.

## How to Navigate This Repository

- **New to context engineering?** Start with the [category overview](category/context-engineering.md) and the [glossary](glossary/context-engineering-glossary.md)
- **Understanding the principles?** Read the [context engineering principles](principles/context-engineering-principles.md)
- **Evaluating architecture?** See the [canonical architecture](architecture/context-engineering-canonical-architecture.md), [architecture diagram](architecture/context-engineering-architecture-diagram.md), and [open architecture spec](specs/enterprise-context-fabric-open-architecture-spec-v0.1.md)
- **Visualizing the stack?** See the [stack diagram](architecture/context-engineering-stack-diagram.md) for a visual representation of the conceptual architecture
- **Comparing to adjacent tech?** Review the [context engineering stack](architecture/context-engineering-stack.md) for comparisons with RAG, vector databases, and knowledge graphs
- **Looking for definitions?** Browse the [definitions](definitions/) directory
- **Building context systems?** Review the [architecture](architecture/) documents and [context capsule schema](specs/conceptual-context-capsule-schema-v0.1.md)
