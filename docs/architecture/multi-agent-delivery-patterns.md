# Multi-Agent Context Delivery Patterns

*How context delivery adapts for different AI consumer types*

Enterprise Context Fabric systems deliver context to a variety of AI consumers — from interactive copilots embedded in enterprise tools to autonomous agents performing multi-step tasks to batch workflows processing large volumes of requests. Each consumer type has distinct context requirements.

This document describes conceptual delivery patterns for different AI consumer types. It defines how context assembly, structuring, and delivery may adapt based on the nature of the consuming system.

This is a conceptual reference. Implementations may support different consumer types and delivery patterns based on their specific requirements.

---

## Consumer Types

Enterprise AI systems fall into several broad categories, each with distinct context delivery requirements.

### Interactive Copilots

Copilots are AI assistants embedded in enterprise tools that provide suggestions, answers, or drafts in response to user actions. They operate in real-time within a user's workflow.

**Context delivery characteristics**:
- **Latency sensitivity**: High — users expect responses within seconds
- **Context scope**: Narrow — focused on the immediate task and surrounding context
- **Session continuity**: Important — the copilot should maintain awareness of the current session
- **Freshness requirements**: High — context should reflect the latest state of relevant systems
- **Delivery mode**: Synchronous request-response

**Delivery pattern**: Context is assembled on-demand when the user triggers an action, using a task-specific assembly pattern with tight temporal focus. Pre-assembled capsules within freshness windows may be served from cache to reduce latency.

---

### Autonomous Agents

Autonomous agents are AI systems that perform multi-step tasks with minimal human intervention. They plan, execute, and adapt across multiple actions to achieve a goal.

**Context delivery characteristics**:
- **Latency sensitivity**: Moderate — agents can tolerate slightly higher latency per step since they operate across many steps
- **Context scope**: Broad and evolving — agents may need context from many systems, and their context needs change as they progress through task steps
- **Session continuity**: Critical — agents must maintain context across the entire task execution, which may span minutes or hours
- **Freshness requirements**: Variable — initial context should be fresh, but intermediate steps may reuse previously assembled context
- **Delivery mode**: Mixed — initial context via synchronous delivery, with incremental updates via streaming or subscription

**Delivery pattern**: Initial context is assembled comprehensively at task start. As the agent progresses, it may request incremental context updates for specific entities or time ranges. Enterprise Context Memory provides continuity across steps. The delivery layer may support context subscriptions that push updates when relevant signals change during agent execution.

---

### Decision-Support Systems

Decision-support systems present context-enriched analysis to human decision makers. They assemble context to support review, comparison, and judgment rather than automated action.

**Context delivery characteristics**:
- **Latency sensitivity**: Low to moderate — decision makers can tolerate seconds of assembly time
- **Context scope**: Comprehensive — decision support requires broad context across multiple dimensions
- **Session continuity**: Moderate — context should persist within a review session but does not need to span across sessions
- **Freshness requirements**: Moderate — context should be current but does not need to be real-time
- **Delivery mode**: Synchronous, with optional progressive loading for large context sets

**Delivery pattern**: Context is assembled using broad patterns that cover multiple entity types and time ranges. Structuring emphasizes comparison and summary views rather than raw signal presentation. Delivery may include multiple capsules organized by topic or dimension to support structured review.

---

### Automation Workflows

Automation workflows are event-driven processes that use context to make routing, escalation, notification, or action decisions. They operate without human interaction during execution.

**Context delivery characteristics**:
- **Latency sensitivity**: Variable — some automations are time-sensitive (incident routing), others are batch-oriented
- **Context scope**: Targeted — automations typically need specific context for specific decision points
- **Session continuity**: Not required — each automation execution is typically independent
- **Freshness requirements**: Depends on use case — incident routing needs real-time, periodic reports can use cached context
- **Delivery mode**: Event-driven push or polling

**Delivery pattern**: Context is pre-assembled based on trigger events. When an event occurs (ticket created, alert fired, threshold crossed), the delivery layer pushes a pre-defined capsule to the automation. Assembly patterns are optimized for the specific decision the automation needs to make.

---

### Batch Processing Systems

Batch systems process large volumes of context requests in bulk — generating summaries, performing analysis, or updating derived data across many entities.

**Context delivery characteristics**:
- **Latency sensitivity**: Low — batch processing prioritizes throughput over individual request latency
- **Context scope**: Repetitive — the same assembly pattern is executed across many entities
- **Session continuity**: Not required — each entity is processed independently
- **Freshness requirements**: Moderate — a consistent snapshot across all entities is more important than real-time freshness for any individual entity
- **Delivery mode**: Bulk/batch delivery

**Delivery pattern**: The delivery layer supports batch context requests that assemble context for multiple entities using the same pattern. Implementations may optimize batch delivery through parallel assembly, shared signal caching, and batched source system queries.

---

## Delivery Mode Summary

| Consumer Type | Primary Delivery Mode | Latency Target | Context Scope | Session Continuity |
|---|---|---|---|---|
| **Interactive Copilot** | Synchronous | Sub-second to seconds | Narrow, task-focused | Session-aware |
| **Autonomous Agent** | Mixed (sync + streaming) | Seconds per step | Broad, evolving | Critical |
| **Decision Support** | Synchronous | Seconds | Comprehensive | Within session |
| **Automation Workflow** | Event-driven push | Varies | Targeted | Not required |
| **Batch Processing** | Bulk/batch | Minutes (total) | Repetitive | Not required |

---

## Context Adaptation Patterns

### Scope Adaptation

Different consumers need different context scope for the same entity. An interactive copilot helping with a quick customer question needs recent interaction history. An autonomous agent investigating a complex issue needs the full customer timeline across all systems.

Implementations may support scope parameters on assembly patterns:

- **Minimal** — Core entity attributes and most recent events only
- **Standard** — Entity attributes, recent events, key relationships
- **Comprehensive** — Full entity history, all relationships, all contributing system data
- **Custom** — Consumer specifies required signal types and time ranges

### Format Adaptation

Different AI consumers may require context in different formats:

- **Structured JSON** — For programmatic consumers that parse context fields directly
- **Formatted text** — For AI models that consume context as natural language input
- **Hybrid** — Structured metadata with natural language summaries
- **Streaming tokens** — For real-time consumers that process context incrementally

The delivery layer adapts capsule format based on the consumer's declared preferences.

### Temporal Adaptation

Different consumer types have different temporal focus:

- **Snapshot** — Context assembled as of a specific point in time (decision support, compliance)
- **Window** — Context covering a defined time range (incident investigation, trend analysis)
- **Real-time** — Context reflecting the latest available state (copilots, incident response)
- **Progressive** — Context that starts with recent data and progressively includes historical context on demand (agents)

---

## Agent-Specific Considerations

Autonomous agents present unique challenges for context delivery:

### Context Accumulation

As agents execute multi-step tasks, they accumulate context from each step. The delivery layer may need to manage context size by summarizing or compressing earlier context to stay within model context windows.

### Dynamic Context Requests

Agents may not know all the context they need at task start. As they discover new entities or relationships during execution, they request additional context. The delivery layer should support incremental context requests without requiring full re-assembly.

### Tool-Mediated Context

Agents often use tools to interact with external systems. Context delivery may integrate with agent tool frameworks, providing context as tool outputs that the agent can consume within its reasoning loop.

### Handoff Context

When an agent hands a task to a human or another agent, the assembled context should transfer with the handoff. Enterprise Context Memory supports this by persisting the agent's assembled context for retrieval by the next participant.

---

## Related Documents

- [Context Delivery Layer](context-delivery-layer.md) — Detailed delivery layer architecture
- [Context Capsule Lifecycle](context-capsule-lifecycle.md) — Lifecycle stages including delivery
- [Canonical Architecture](context-engineering-canonical-architecture.md) — Six-layer canonical architecture
- [Context Engineering Principles](../principles/context-engineering-principles.md) — Design principles including "Context Must Be Task-Aware"
- [Enterprise Use Cases](../examples/enterprise-use-cases.md) — Common enterprise scenarios
