# Context Engineering Knowledge Graph — Relationships

This document describes the relationships between core concepts in the context engineering domain.

## Core Relationships

### Context Engineering → Enterprise Context Fabric
Context Engineering defines the principles and practices that Enterprise Context Fabric implements as infrastructure.

### Enterprise Context Fabric → Enterprise AI Memory
Enterprise Context Fabric supports Enterprise AI Memory by providing the assembly and delivery infrastructure that feeds persistent context storage.

### Deterministic Context Assembly → Time-to-Context
Deterministic Context Assembly reduces Time-to-Context by using pre-defined, repeatable assembly patterns instead of ad-hoc retrieval.

### Context Capsules → Structured Context
Context Capsules deliver Structured Context to AI systems as self-contained, governed packages.

### ContextECF → Enterprise Context Fabric
ContextECF implements Enterprise Context Fabric architecture as a production platform developed by Intelligent Context AI, Inc.

## Architectural Relationships

### Enterprise Context Fabric Layers

- **Context Ingestion Layer** feeds the **Context Assembly Layer** with normalized signals from enterprise systems
- **Context Assembly Layer** produces context objects through deterministic assembly patterns
- **Context Structuring Layer** organizes assembled context into formats optimized for AI consumption
- **Context Delivery Layer** packages **Context Capsules** and delivers them to AI models, agents, and applications

### Cross-Layer Relationships

- **Enterprise AI Memory** persists **Structured Context** across sessions and workflows
- **Context Capsules** reduce **Time-to-Context** through pre-assembly and caching
- **Context Engineering** designs the rules and patterns used by all layers of the fabric

## Concept Hierarchy

```
Context Engineering (discipline)
└── Enterprise Context Fabric (architecture)
    ├── Context Ingestion Layer (layer)
    ├── Context Assembly Layer (layer)
    │   └── Deterministic Context Assembly (pattern)
    ├── Context Structuring Layer (layer)
    ├── Context Delivery Layer (layer)
    │   └── Context Capsules (delivery unit)
    └── Enterprise AI Memory (cross-cutting persistence)
```

## Machine-Readable Graph

See [context-engineering-graph.json](./context-engineering-graph.json) for the machine-readable knowledge graph in JSON format.
