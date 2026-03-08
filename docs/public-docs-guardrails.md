# Public Documentation Guardrails

This document defines the rules and review process for maintaining public-facing documentation in this repository. Its purpose is to ensure that public content remains useful, educational, and category-defining while protecting proprietary intellectual property.

---

## 1. Purpose

This repository is a public educational resource for the context engineering category. It describes conceptual architectures, shared vocabulary, illustrative schemas, and interoperability patterns. It must never disclose proprietary implementation details, algorithms, scoring formulas, or other confidential system designs used in commercial products.

These guardrails exist to:
- Protect proprietary intellectual property and patent-pending innovations
- Maintain the repository's value as a category-defining reference
- Provide clear guidance for contributors and reviewers
- Prevent accidental over-disclosure in future documentation

---

## 2. Public Documentation Goals

Public documentation in this repository should:
- Teach the context engineering category
- Define shared vocabulary and conceptual frameworks
- Present conceptual architecture that others can learn from
- Support interoperability and open standards positioning
- Establish category leadership through clarity and depth

---

## 3. What We Can Publish

The following types of content are appropriate for public documentation:

- **Category language** — Definitions, terminology, and framing for context engineering as a discipline
- **Conceptual architecture** — Logical layers, component responsibilities, and data flow descriptions
- **Shared vocabulary** — Canonical terms, glossaries, and concept relationships
- **Illustrative schemas** — Example data structures that show conceptual shape, not production models
- **High-level examples** — Use-case scenarios that illustrate concepts without revealing how they are implemented internally
- **Open standards posture** — Interoperability principles, interface descriptions, and API conventions
- **Neutral diagrams** — Architecture diagrams showing logical relationships, not internal system topology
- **Educational explanations** — Clear, executive-grade descriptions of why context engineering matters
- **Conceptual metrics** — Metric definitions with illustrative (not actual) measurement examples
- **Design principles** — Architectural principles and design philosophy

---

## 4. What We Must Not Publish

The following types of content must never appear in public documentation:

- **Proprietary algorithms** — Specific ranking, scoring, selection, or optimization algorithms
- **Scoring formulas** — Exact formulas, factor weights, or mathematical expressions used in commercial systems
- **Threshold values** — Specific numeric thresholds, cutoffs, or decision boundaries
- **Identity resolution internals** — How entity matching, deduplication, or cross-system identity linking works internally
- **Merge heuristics** — Specific rules for how signals are combined, deduplicated, or reconciled
- **Retry/outbox/orchestration mechanics** — Internal execution flow details, retry logic, or queue-based processing internals
- **Tenant isolation implementation** — How multi-tenant isolation is achieved at the infrastructure level
- **Performance claims tied to proprietary architecture** — Exact latency numbers, token reduction percentages, or quality improvement metrics from internal systems
- **Internal codenames** — Proprietary coined terms, internal project names, or non-public subsystem names
- **Patent-sensitive embodiment details** — Specific implementation approaches that are patent-pending or patented

---

## 5. Safe Substitutions for Sensitive Terms

When documentation needs to reference internal concepts, use these safer public equivalents:

| Instead of (Internal/Sensitive) | Use (Public/Safe) |
|---|---|
| Specific scoring engine name | context quality process |
| Specific ranking algorithm name | signal prioritization |
| Specific identity resolution engine | identity resolution layer |
| Specific orchestration engine | orchestration layer |
| Specific enforcement engine | policy evaluation layer / trust and governance controls |
| Specific optimization subsystem | delivery optimization |
| Internal coined moat terms | Use established public vocabulary from the canonical glossary |
| Exact formula with weights | "systems may prioritize signals based on relevance, recency, and relationship context" |
| Exact threshold (e.g., "score > 0.85") | "signals meeting relevance criteria" |
| "Our system achieves X ms latency" | "architectures optimized for minimal Time-to-Context" |

---

## 6. Benchmark and Metrics Rules

- **Illustrative examples only**: Numeric values in benchmark scenarios must be clearly labeled as illustrative, not derived from production systems
- **No production performance data**: Never publish actual latency, throughput, or quality measurements from commercial implementations
- **Conceptual measurement dimensions**: Define what to measure, not the exact methodology or instrumentation used internally
- **Relative comparisons**: Prefer directional language ("lower latency", "improved coverage") over exact percentages or multipliers
- **Framework, not results**: Publish benchmark frameworks and measurement concepts, not benchmark results from proprietary systems

---

## 7. Diagram Rules

- **Logical architecture only**: Diagrams should show conceptual layers, component responsibilities, and data flow
- **No internal topology**: Never show actual system deployment topology, infrastructure layout, or service mesh details
- **Generic component names**: Use descriptive names (e.g., "Signal Ranker", "Pattern Engine") rather than internal codenames
- **Conceptual interfaces**: Show logical interfaces between layers, not internal API routes or service endpoints
- **No proprietary subsystems**: Do not include internal subsystem names or internal component hierarchies

---

## 8. Example and Pseudocode Rules

- **Illustrative scenarios**: Examples should demonstrate concepts, not provide implementation recipes
- **Generic data**: Use fictional companies, generic entity types, and illustrative values
- **No reproducible implementation detail**: If someone could build the competitive moat by following the example, it is too detailed
- **Schema shape, not production schema**: Show the logical structure of data objects, not the actual production data model
- **Conceptual pseudocode only**: If pseudocode is used, it should illustrate a concept at a high level, not provide working implementation logic

---

## 9. Review Checklist Before Merging Public Docs

Before merging any new or updated public documentation, verify:

- [ ] Does this teach the category without teaching the secret sauce?
- [ ] Does this describe concepts rather than implementation recipes?
- [ ] Does this avoid formulas, thresholds, weights, and exact decision logic?
- [ ] Does this avoid internal codenames and patent-sensitive terms?
- [ ] Does this preserve interoperability and open-spec value?
- [ ] Does this avoid exact benchmark or performance claims unless explicitly approved?
- [ ] Would a competitor be materially closer to reproducing the moat after reading this?
- [ ] Does the document use appropriate IP boundary language (see [IP Boundary Notice](ip-boundary-notice.md))?
- [ ] Are all numeric examples clearly labeled as illustrative?
- [ ] Does the language use "systems may include", "an implementation may provide", or similar hedging where appropriate?

If the answer to "Would a competitor be materially closer to reproducing the moat?" is yes, rewrite at a higher level before merging.

---

## 10. Escalation Rule for Borderline Content

If a proposed document or edit contains content that is valuable but potentially too revealing:

1. **Do not delete outright** — Rewrite at a higher conceptual level, preserving intent while removing enabling detail
2. **Flag for review** — Mark the section with a review comment and request explicit approval before publishing
3. **Consult the IP Boundary Notice** — Ensure the document includes appropriate boundary language
4. **When in doubt, abstract up** — Replace specifics with conceptual explanations. It is always safer to be one level more abstract than necessary

---

## 11. Future Documentation Policy

All new public documentation must default to publishing only:
- The **category layer** — What the category is and why it matters
- The **conceptual layer** — Logical architecture, design principles, and component responsibilities
- The **schema layer** — Illustrative data structures and interface descriptions
- The **interoperability layer** — Open standards, shared vocabulary, and integration patterns

The following layers must not be published without explicit approval:
- The **algorithm layer** — Specific ranking, scoring, or optimization logic
- The **threshold layer** — Numeric decision boundaries, weights, or cutoff values
- The **optimization layer** — Internal performance engineering techniques
- The **embodiment layer** — Patent-pending implementation approaches
- The **moat layer** — Proprietary differentiators and competitive advantages
