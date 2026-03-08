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

## How to Navigate This Repository

- **New to context engineering?** Start with the [category overview](category/context-engineering.md) and the [glossary](glossary/context-engineering-glossary.md)
- **Evaluating architecture?** See the [reference architecture](architecture/reference-architecture.md) and [open architecture spec](specs/enterprise-context-fabric-open-architecture-spec-v0.1.md)
- **Looking for definitions?** Browse the [definitions](definitions/) directory
- **Building context systems?** Review the [architecture](architecture/) documents and [context capsule schema](specs/conceptual-context-capsule-schema-v0.1.md)
