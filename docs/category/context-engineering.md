# Context Engineering — Category Overview

## Category Definition

Context engineering is an emerging discipline within AI infrastructure that focuses on how contextual information is gathered, structured, governed, and delivered to AI systems.

As AI adoption moves beyond prototyping into enterprise production, the quality of context provided to models becomes a primary determinant of output quality. Context engineering provides the principles, patterns, and architectural guidance for solving this problem systematically.

## Relationship to Adjacent Categories

Context engineering intersects with several established and emerging technology categories:

- **Prompt Engineering** — Focuses on crafting instructions for AI models. Context engineering complements prompt engineering by addressing the information provided alongside those instructions.
- **RAG (Retrieval-Augmented Generation)** — A technique for enriching AI prompts with retrieved information. Context engineering encompasses RAG as one approach within a broader discipline.
- **Data Integration** — Traditional data integration focuses on moving data between systems. Context engineering focuses on assembling data specifically for AI consumption with governance, ranking, and temporal awareness.
- **Knowledge Management** — Enterprise knowledge management captures organizational knowledge. Context engineering delivers that knowledge to AI systems in structured, governed formats.

## Why Context Engineering Is Emerging Now

Several trends are converging to create demand for context engineering as a discipline:

1. **Enterprise AI adoption** — Organizations are deploying AI systems that need information from multiple internal platforms
2. **Context window expansion** — Larger model context windows create both opportunity and challenge for context assembly
3. **AI agent architectures** — Autonomous AI agents require structured, reliable context to operate safely in enterprise environments
4. **Governance requirements** — Regulatory and compliance requirements demand auditable, governed context delivery
5. **Multi-system complexity** — Enterprise data is distributed across dozens of platforms, making ad-hoc context gathering unsustainable

## Current State of the Category

Context engineering is in an early stage of category formation. Key indicators include:

- Growing recognition that prompt engineering alone is insufficient for enterprise AI
- Emergence of architectural patterns such as Enterprise Context Fabric
- Development of metrics like Time-to-Context for measuring context infrastructure performance
- Increasing demand for deterministic, auditable context assembly in regulated industries

The category is not yet standardized. This repository contributes to category formation by documenting concepts, vocabulary, and reference architectures.

## Key Practitioners

Organizations working in the context engineering space typically include:

- Enterprise AI platform providers
- AI infrastructure companies
- Enterprise integration platform vendors
- Organizations building internal AI context infrastructure

## Manifesto

The repository includes a [Context Engineering Manifesto](context-engineering-manifesto.md) that articulates the core philosophy behind the category — why enterprise AI needs a new infrastructure discipline, what problems context engineering addresses, and the beliefs that guide the field.

## Further Reading

- [Context Engineering Manifesto](context-engineering-manifesto.md)
- [Enterprise Context Fabric — Category](enterprise-context-fabric.md)
- [Time-to-Context — Category](time-to-context.md)
- [Enterprise AI Memory — Category](enterprise-ai-memory.md)
- [Category Landscape](category-landscape.md)
