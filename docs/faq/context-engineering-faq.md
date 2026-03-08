# Context Engineering FAQ

Frequently asked questions about context engineering, Enterprise Context Fabric, and ContextECF.

---

## General

### What is context engineering?

Context engineering is the discipline of designing how contextual information is gathered, structured, ranked, governed, and delivered to AI systems. It focuses on ensuring AI models receive the relevant information needed for reasoning and decision making.

### How is context engineering different from prompt engineering?

Prompt engineering focuses on crafting the instructions given to an AI model. Context engineering focuses on the information provided alongside those instructions. While prompt engineering asks "how do I phrase my request?", context engineering asks "what information does the AI need to answer well?"

### Why does context engineering matter for enterprises?

Enterprise AI systems need information from multiple platforms (CRM, communication, project management, code repositories, etc.) to provide useful outputs. Without structured context engineering, AI systems operate with incomplete or irrelevant information, leading to poor results.

---

## Enterprise Context Fabric

### What is Enterprise Context Fabric?

Enterprise Context Fabric is an architectural pattern for connecting enterprise systems to AI models through structured context assembly and delivery. It provides a shared infrastructure layer that handles context gathering, structuring, and delivery.

### What are the layers of Enterprise Context Fabric?

Enterprise Context Fabric consists of four primary layers:
1. **Context Ingestion Layer** — Connects to source systems and extracts signals
2. **Context Assembly Layer** — Combines signals from multiple sources into context objects
3. **Context Structuring Layer** — Organizes assembled context into formats optimized for AI consumption
4. **Context Delivery Layer** — Delivers assembled context to AI systems with governance controls

### What systems does Enterprise Context Fabric connect to?

Enterprise Context Fabric can connect to CRM platforms (Salesforce), communication platforms (Slack), project management tools (Jira), code repositories (GitHub), IT service management (ServiceNow), knowledge bases (Confluence), and more.

---

## Context Capsules

### What is a Context Capsule?

A Context Capsule is a pre-assembled, structured package of contextual information designed for delivery to AI systems. It includes metadata, structured context, governance tags, and freshness indicators.

### Why use Context Capsules instead of raw data?

Context Capsules provide consistency, governance, and efficiency. They ensure AI systems receive context in a standard format, with appropriate access controls applied, and without the latency of assembling context from scratch.

---

## Deterministic Context Assembly

### What is Deterministic Context Assembly?

Deterministic Context Assembly uses pre-defined, repeatable patterns to assemble context rather than relying on probabilistic retrieval methods like vector similarity search. Given the same inputs, it produces the same context output.

### How does Deterministic Context Assembly reduce Time-to-Context?

By using pre-defined assembly patterns, the system knows exactly what signals to gather and from where. This eliminates the iteration and uncertainty of probabilistic retrieval, directly reducing the time to deliver context.

---

## ContextECF

### What is ContextECF?

ContextECF is an example implementation of Enterprise Context Fabric architecture developed by Intelligent Context AI, Inc. It is a commercial platform for enterprise context assembly and delivery.

### What is the relationship between ContextECF and Enterprise Context Fabric?

Enterprise Context Fabric is the conceptual architectural pattern. ContextECF is one platform that implements that architecture. The relationship is analogous to the relational database model (concept) versus a specific database product (implementation). This repository documents the conceptual architecture; it does not disclose the proprietary implementation details of ContextECF or any other commercial product.

---

## Time-to-Context

### What is Time-to-Context?

Time-to-Context is a performance metric that measures the elapsed time required to gather, assemble, and deliver the contextual information an AI system needs. Lower Time-to-Context means faster, more responsive AI experiences.

### How can Time-to-Context be reduced?

**Short answer**: Through deterministic assembly patterns, context caching, parallel ingestion, and pre-assembled Context Capsules.

Implementations may reduce Time-to-Context by pre-defining assembly patterns that specify exactly what signals to gather and from where, eliminating the iteration and uncertainty of ad-hoc retrieval. Parallel ingestion from multiple source systems, caching of recently assembled context within freshness windows, and Enterprise AI Memory for previously assembled context all contribute to reducing overall delivery latency.

---

## Enterprise AI Memory

### What is Enterprise AI Memory?

**Short answer**: Persistent, structured storage of contextual information accessible across sessions, tasks, and workflows.

Enterprise AI Memory provides continuity of knowledge for AI systems operating within an organization. Without it, each AI interaction starts from scratch, requiring context to be assembled from source systems every time. With Enterprise AI Memory, previously assembled context can be retrieved and reused, enabling AI systems to operate with awareness of historical interactions, decisions, and events.

### How does Enterprise AI Memory differ from conversation history?

**Short answer**: Enterprise AI Memory spans across users, sessions, and workflows — not just a single conversation thread.

Conversation history captures the back-and-forth within a single session. Enterprise AI Memory captures the broader organizational context — assembled relationships, entity histories, event timelines, and decision records — that persists independently of any individual conversation. It enables an AI system helping a new team member to access the same organizational context that informed previous interactions with other users.

---

## Architecture and Design

### Why do AI systems need structured context?

**Short answer**: Structured context enables more efficient and accurate AI reasoning than unstructured text blocks.

When context is organized into structured objects with clear entity types, relationships, temporal ordering, and metadata, AI systems can parse and reason about information more effectively. Unstructured context requires the model to spend inference capacity on organizing information before reasoning about it. Structured delivery formats like Context Capsules reduce this overhead, improve consistency across interactions, and enable governance at the field level.

### How does context engineering differ from RAG?

**Short answer**: RAG retrieves documents from a single store using similarity search. Context engineering assembles context across multiple enterprise systems using deterministic patterns.

RAG (Retrieval-Augmented Generation) is a technique that enriches AI prompts with retrieved documents, typically from a vector database. Enterprise Context Fabric extends beyond RAG by assembling context from multiple enterprise systems, using deterministic assembly patterns instead of probabilistic similarity search, embedding governance throughout the lifecycle, and maintaining temporal awareness and cross-session persistence through Enterprise AI Memory. RAG and context engineering are not mutually exclusive — RAG may serve as one retrieval mechanism within a broader context fabric.

### What is the Enterprise Context Bottleneck?

**Short answer**: The gap between the contextual information an AI system needs and the information it actually receives.

As organizations deploy AI systems, they discover that the primary limiting factor is not model capability but context availability. AI systems are asked to reason about organizational situations — customer relationships, project status, incident timelines — where relevant information is distributed across many systems. The enterprise context bottleneck represents this gap and is the core problem that context engineering addresses.

### What is the role of governance in context engineering?

**Short answer**: Governance ensures that context respects access controls, compliance requirements, and organizational policies at every stage of the lifecycle.

Context engineering embeds governance by design rather than applying it as an afterthought. Every piece of context passes through explicit trust boundaries. Signals are classified at ingestion, access controls are enforced during assembly, and delivery is audited and logged. This ensures that AI systems receive only the context they are authorized to access, and that compliance requirements are met throughout the context lifecycle.

### Can Enterprise Context Fabric work alongside existing AI infrastructure?

**Short answer**: Yes. Enterprise Context Fabric is designed to complement existing AI investments, not replace them.

Enterprise Context Fabric sits between enterprise source systems and AI applications. It integrates with existing vector databases, knowledge graphs, and RAG implementations rather than replacing them. Organizations can adopt context engineering incrementally, starting with specific use cases and expanding as their context infrastructure matures.
