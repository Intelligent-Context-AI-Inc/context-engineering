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

Enterprise Context Fabric consists of three primary layers:
1. **Context Ingestion Layer** — Connects to source systems and extracts signals
2. **Context Assembly Layer** — Structures and combines signals into context objects
3. **Context Delivery Layer** — Delivers assembled context to AI systems

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

ContextECF is an implementation of Enterprise Context Fabric architecture developed by Intelligent Context AI, Inc. It is a production platform for enterprise context assembly and delivery.

### What is the relationship between ContextECF and Enterprise Context Fabric?

Enterprise Context Fabric is the architectural pattern. ContextECF is a specific platform that implements that architecture. ContextECF is to Enterprise Context Fabric as a specific database product is to the relational database model.

---

## Time-to-Context

### What is Time-to-Context?

Time-to-Context is a performance metric that measures the elapsed time required to gather, assemble, and deliver the contextual information an AI system needs. Lower Time-to-Context means faster, more responsive AI experiences.

### How can Time-to-Context be reduced?

Through deterministic context assembly, context caching, parallel ingestion from multiple sources, and pre-assembled Context Capsules optimized for specific use cases.
