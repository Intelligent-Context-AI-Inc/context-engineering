# Context Quality Dimensions

*A framework for evaluating the quality of assembled context*

Delivering context to AI systems is necessary but not sufficient. The context must also be of high quality — complete enough for the task, relevant to the question, fresh enough to be accurate, and structured enough for effective reasoning.

This document defines a conceptual framework for evaluating context quality. It describes the dimensions along which context quality can be assessed without prescribing specific measurement algorithms or scoring methods.

This is a conceptual reference. Implementations may define their own quality measurement approaches based on these dimensions.

---

## Why Context Quality Matters

AI systems produce better outputs when they receive better context. Poor-quality context leads to:

- **Hallucinations** — When context is incomplete, AI systems may fabricate information to fill gaps
- **Stale decisions** — When context is outdated, AI systems may reason about situations that have already changed
- **Irrelevant responses** — When context is not filtered for task relevance, AI systems may be distracted by unrelated information
- **Governance violations** — When context is not properly governed, AI systems may expose or act on information they should not have access to

Context quality is a prerequisite for AI reliability in enterprise environments.

---

## Quality Dimensions

### Completeness

**Definition**: The degree to which assembled context includes all signals required for the specified task.

A context object is complete when it contains sufficient information for the AI system to reason about the task without requiring additional retrieval. Completeness is relative to the task — a customer support context capsule has different completeness requirements than a code review capsule.

**Indicators of completeness**:
- All source systems specified in the assembly pattern were successfully queried
- All required entity types are present in the assembled context
- Relationship data connects entities as expected by the pattern
- Temporal coverage spans the time range relevant to the task

**Completeness gaps may arise from**:
- Source system unavailability during ingestion
- Permission restrictions preventing access to certain signals
- Assembly pattern specifications that do not cover all relevant sources

---

### Relevance

**Definition**: The degree to which assembled context is pertinent to the specific task being performed.

Relevance measures whether the context is useful for the task at hand, not merely available. A large volume of context is not inherently valuable — context that is closely aligned with the task enables more effective AI reasoning.

**Indicators of relevance**:
- Context entities are directly related to the primary entity of the task
- Events fall within the time range relevant to the task
- Signals come from source systems pertinent to the task type
- Context structure is adapted for the specific task category

**Relevance challenges may include**:
- Assembly patterns that are too broad, including signals from unrelated workflows
- Temporal ranges that extend too far into the past, including outdated context
- Cross-system linking that surfaces tangentially related entities

---

### Freshness

**Definition**: The degree to which assembled context reflects the current state of enterprise systems.

Context freshness measures how recently the contributing signals were ingested or updated. In enterprise environments, situations change rapidly — a customer ticket may be resolved, a deployment may complete, a team assignment may change. Context that was accurate an hour ago may no longer reflect reality.

**Indicators of freshness**:
- Time elapsed since the most recent signal in the context was ingested
- Whether the context falls within its defined freshness window
- Whether real-time signals were available during assembly or only cached/historical data was used

**Freshness considerations**:
- Different task types have different freshness requirements (incident response demands near-real-time; quarterly business review tolerates hours-old data)
- Freshness windows should be defined per assembly pattern based on task requirements
- Stale context should be flagged or trigger re-assembly rather than being silently delivered

---

### Accuracy

**Definition**: The degree to which assembled context correctly represents the state of enterprise systems.

Accuracy measures whether the context faithfully reflects the source data. Context can be inaccurate due to ingestion errors, normalization failures, stale caches, or incorrect cross-system entity linking.

**Indicators of accuracy**:
- Ingested signals match their source system values
- Entity linking correctly identifies the same entity across systems (not false matches)
- Temporal ordering reflects the actual sequence of events
- Structured context preserves the meaning of the original signals

**Accuracy risks may include**:
- Entity resolution errors that conflate different entities
- Normalization that loses important distinctions from source data
- Caching that serves outdated values when source data has changed

---

### Consistency

**Definition**: The degree to which the same assembly pattern produces equivalent context given equivalent inputs.

Consistency is a hallmark of deterministic context assembly. When the same task type and entity are queried at different times (with no underlying changes), the resulting context should be structurally equivalent. This enables predictable AI behavior and simplifies debugging.

**Indicators of consistency**:
- Repeated executions of the same assembly pattern with the same inputs produce structurally equivalent context
- Context structure follows defined schemas without variation
- Governance rules are applied uniformly across all context deliveries

**Consistency considerations**:
- Non-deterministic elements (such as probabilistic retrieval) reduce consistency
- Time-dependent queries naturally produce different results as source data changes — this is expected, not an inconsistency
- Schema versioning helps maintain consistency as context structures evolve

---

### Provenance

**Definition**: The degree to which the origin and assembly history of context is traceable and documented.

Provenance enables auditability. Every element in a delivered context object should be traceable to its source signal, the assembly pattern that included it, and the governance rules that were applied. Provenance is essential for compliance, debugging, and trust in context delivery.

**Indicators of provenance**:
- Every signal in the context includes source system identification
- Assembly pattern identifiers are recorded with the context
- Governance decisions (masking, filtering, classification) are documented
- Delivery metadata records when, to whom, and under what authorization context was delivered

---

### Timeliness

**Definition**: The elapsed time required to assemble and deliver context — measured as Time-to-Context.

Timeliness is distinct from freshness. Freshness measures how current the source data is; timeliness measures how quickly the system assembles and delivers context once a request is made. Both matter for AI system performance.

**Indicators of timeliness**:
- Time-to-Context metric for each delivery
- Breakdown of latency by lifecycle stage (ingestion, assembly, structuring, governance, delivery)
- Comparison to target Time-to-Context thresholds for the task type

See the [Time-to-Context Metric Framework](../specs/time-to-context-metric-framework-v0.1.md) for detailed measurement approaches.

---

## Quality Dimensions Summary

| Dimension | Question It Answers | Key Indicator |
|---|---|---|
| **Completeness** | Does the context include everything needed? | Signal coverage relative to pattern |
| **Relevance** | Is the context useful for this task? | Task alignment of included signals |
| **Freshness** | Does the context reflect current state? | Age of most recent signal |
| **Accuracy** | Does the context correctly represent source data? | Fidelity of normalization and linking |
| **Consistency** | Is the context predictable and repeatable? | Equivalence across repeated assemblies |
| **Provenance** | Can we trace where the context came from? | Source and audit metadata completeness |
| **Timeliness** | Was the context delivered quickly enough? | Time-to-Context measurement |

---

## Applying Quality Dimensions

Context quality is not a single score. Different tasks may prioritize different dimensions:

- **Incident response** prioritizes **freshness** and **timeliness** — the context must reflect the current situation and arrive quickly
- **Compliance review** prioritizes **completeness** and **provenance** — the context must be comprehensive and fully traceable
- **Customer support** prioritizes **relevance** and **accuracy** — the context must be pertinent to the specific customer issue and correctly represent account data
- **Strategic analysis** prioritizes **completeness** and **consistency** — the context must cover all relevant systems and be reproducible

Implementations may define quality profiles for different task types, specifying target thresholds for each dimension.

---

## Related Documents

- [Time-to-Context Metric Framework](../specs/time-to-context-metric-framework-v0.1.md) — Measurement framework for the timeliness dimension
- [Context Capsule Lifecycle](context-capsule-lifecycle.md) — Lifecycle stages that affect context quality
- [Context Governance Model](context-governance-model.md) — Governance checkpoints that support accuracy and provenance
- [Context Engineering Principles](../principles/context-engineering-principles.md) — Principles that inform quality expectations
- [Context Engineering Glossary](../glossary/context-engineering-glossary.md) — Terminology reference
