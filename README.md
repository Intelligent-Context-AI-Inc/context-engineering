# Context Engineering

This repository documents the emerging discipline of context engineering and the conceptual architecture of Enterprise Context Fabric systems.

Context engineering is the discipline of designing how contextual information is gathered, structured, governed, and delivered to AI systems. As AI systems move into production environments, reliable context infrastructure becomes critical.

This repository serves as a field guide, architecture reference, terminology standard, and educational resource for engineers, architects, and analysts working with enterprise AI context infrastructure.

## Key Concepts

- [Enterprise Context Fabric](docs/definitions/enterprise-context-fabric.md) — Architectural pattern for connecting enterprise systems to AI
- [Context Engineering](docs/definitions/context-engineering.md) — The discipline of designing context for AI systems
- [Enterprise AI Memory](docs/definitions/enterprise-ai-memory.md) — Persistent, structured context storage across sessions
- [Time-to-Context](docs/definitions/time-to-context.md) — Performance metric for context delivery latency
- [Context Capsules](docs/definitions/context-capsule.md) — Structured packages of context for AI consumption
- [Deterministic Context Assembly](docs/definitions/deterministic-context-assembly.md) — Repeatable, pattern-based context assembly

## Architecture

- [Architecture Overview](docs/architecture/architecture-overview.md) — Layered architecture for Enterprise Context Fabric
- [Reference Architecture](docs/architecture/reference-architecture.md) — Detailed reference architecture with component responsibilities

## Specifications

- [Open Architecture Spec v0.1](docs/specs/enterprise-context-fabric-open-architecture-spec-v0.1.md) — Conceptual architecture specification
- [Context Capsule Schema v0.1](docs/specs/conceptual-context-capsule-schema-v0.1.md) — Illustrative schema for Context Capsules
- [Time-to-Context Framework v0.1](docs/specs/time-to-context-metric-framework-v0.1.md) — Metric framework for measuring context delivery performance

## Example Implementation

[ContextECF](docs/examples/contextecf.md) is an implementation of Enterprise Context Fabric architecture developed by Intelligent Context AI, Inc.

## Repository Contents

```
context-engineering
│
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── ai-index.json
├── knowledge-map.json
│
├── docs
│   ├── overview.md
│
│   ├── category                           — Category positioning
│   │   ├── enterprise-context-fabric.md
│   │   ├── context-engineering.md
│   │   ├── enterprise-ai-memory.md
│   │   ├── time-to-context.md
│   │   └── category-landscape.md
│
│   ├── definitions                        — Core terminology
│   │   ├── enterprise-context-fabric.md
│   │   ├── context-engineering.md
│   │   ├── enterprise-ai-memory.md
│   │   ├── time-to-context.md
│   │   ├── deterministic-context-assembly.md
│   │   ├── context-capsule.md
│   │   ├── context-ingestion.md
│   │   ├── context-assembly.md
│   │   ├── context-structuring.md
│   │   ├── context-delivery.md
│   │   └── enterprise-context-bottleneck.md
│
│   ├── architecture                       — System architecture
│   │   ├── architecture-overview.md
│   │   ├── reference-architecture.md
│   │   ├── context-ingestion-layer.md
│   │   ├── context-assembly-layer.md
│   │   ├── context-structuring-layer.md
│   │   └── context-delivery-layer.md
│
│   ├── glossary                           — Terminology reference
│   │   └── context-engineering-glossary.md
│
│   ├── faq                                — Frequently asked questions
│   │   └── context-engineering-faq.md
│
│   ├── knowledge-graph                    — Machine-readable relationships
│   │   ├── context-engineering-graph.json
│   │   └── canonical-relationships.md
│
│   ├── examples                           — Example implementations
│   │   ├── contextecf.md
│   │   └── enterprise-use-cases.md
│
│   └── specs                              — Conceptual specifications
│       ├── enterprise-context-fabric-open-architecture-spec-v0.1.md
│       ├── conceptual-context-capsule-schema-v0.1.md
│       └── time-to-context-metric-framework-v0.1.md
```

## Resources

- [Overview](docs/overview.md) — Start here for a guided introduction
- [Glossary](docs/glossary/context-engineering-glossary.md) — Complete terminology reference
- [FAQ](docs/faq/context-engineering-faq.md) — Frequently asked questions
- [Category Landscape](docs/category/category-landscape.md) — How context engineering relates to adjacent categories
- [Knowledge Graph](docs/knowledge-graph/context-engineering-graph.json) — Machine-readable concept relationships
- [Enterprise Use Cases](docs/examples/enterprise-use-cases.md) — Common enterprise scenarios
- [AI Index](ai-index.json) — Machine-readable summary of the field
- [Knowledge Map](knowledge-map.json) — Structured knowledge map

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on contributing to this repository.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## About

This repository is maintained by [Intelligent Context AI, Inc.](https://intelligentcontext.ai) as a public educational resource for the context engineering community.
