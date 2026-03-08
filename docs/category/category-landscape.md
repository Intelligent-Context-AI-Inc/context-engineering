# Context Engineering — Category Landscape

## Overview

This document maps the context engineering category landscape, identifying adjacent categories, overlapping disciplines, and the unique positioning of Enterprise Context Fabric within the broader AI infrastructure ecosystem.

## Category Map

```
┌─────────────────────────────────────────────────────────────────┐
│                    AI Application Layer                         │
│        Copilots · Agents · Assistants · Workflows              │
└──────────────────────────┬──────────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────────┐
│                  Context Infrastructure                         │
│                                                                 │
│  ┌──────────────┐  ┌──────────────────┐  ┌───────────────────┐ │
│  │   Context     │  │  Enterprise      │  │   Enterprise      │ │
│  │   Engineering │  │  Context Fabric  │  │   AI Memory       │ │
│  │  (discipline) │  │  (architecture)  │  │  (persistence)    │ │
│  └──────────────┘  └──────────────────┘  └───────────────────┘ │
│                                                                 │
└──────────────────────────┬──────────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────────┐
│                  Adjacent Categories                            │
│                                                                 │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌───────────────┐  │
│  │   RAG    │  │  Data    │  │ Knowledge│  │    AI         │  │
│  │          │  │  Integr. │  │  Mgmt    │  │  Orchestration│  │
│  └──────────┘  └──────────┘  └──────────┘  └───────────────┘  │
│                                                                 │
└──────────────────────────┬──────────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────────┐
│                  Enterprise Systems                             │
│    CRM · Communication · Project Mgmt · Code · ITSM · Docs    │
└─────────────────────────────────────────────────────────────────┘
```

## Category Distinctions

### Context Engineering vs. Prompt Engineering

| Aspect | Prompt Engineering | Context Engineering |
|---|---|---|
| Focus | How to phrase instructions to AI | What information to provide to AI |
| Scope | Single prompt or conversation | Cross-system, cross-session context |
| Governance | Per-prompt | Infrastructure-level |
| Persistence | Ephemeral | Durable |

### Enterprise Context Fabric vs. Data Integration

| Aspect | Data Integration | Enterprise Context Fabric |
|---|---|---|
| Purpose | Move data between systems | Deliver context to AI systems |
| Consumer | Applications, databases | AI models, agents |
| Optimization | Throughput, consistency | Time-to-Context, relevance |
| Output format | Rows, records | Context Capsules, structured context |

### Enterprise Context Fabric vs. RAG

| Aspect | RAG | Enterprise Context Fabric |
|---|---|---|
| Retrieval method | Vector similarity | Deterministic assembly patterns |
| Consistency | Variable | Repeatable |
| Governance | Post-retrieval filtering | Built into assembly patterns |
| Scope | Document retrieval | Multi-system context assembly |

## Emerging Category Boundaries

The context engineering category is still forming. Current boundaries include:

- **In scope**: Context assembly, delivery, governance, persistence, and measurement for AI systems
- **Adjacent**: Data integration, knowledge management, AI orchestration, RAG
- **Out of scope**: Model training, prompt design, AI application logic

## Ecosystem Landscape

The repository includes a [Context Engineering Landscape Map](context-engineering-landscape.md) that organizes the broader ecosystem around context infrastructure, mapping how enterprise systems, data infrastructure, knowledge systems, retrieval systems, and context infrastructure platforms relate to each other and to AI applications.

## Category Maturity

The context engineering category is in early formation. Key maturity indicators to watch:

- Standardization of terminology and metrics
- Emergence of interoperability specifications
- Analyst coverage and market categorization
- Open reference architectures and community adoption
