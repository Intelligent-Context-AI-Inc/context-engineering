# Conceptual Context Capsule Schema v0.1

**Status**: Draft — Illustrative Schema
**Version**: 0.1
**Date**: 2026-03-08
**Maintainer**: Intelligent Context AI, Inc.

---

## Purpose

This document describes a conceptual schema for Context Capsules — structured packages of contextual information designed for delivery to AI systems.

This schema is illustrative. It defines the logical elements a Context Capsule may contain, not a production data model. Implementations may adapt this schema based on their specific requirements.

## Overview

A Context Capsule is the primary delivery unit within Enterprise Context Fabric architecture. It encapsulates assembled, structured context along with metadata, governance information, and freshness indicators.

## Conceptual Schema

A Context Capsule may contain the following logical elements:

### Capsule Metadata

| Element | Description |
|---|---|
| `capsule_id` | Unique identifier for this capsule instance |
| `capsule_type` | The type or category of context this capsule contains (e.g., customer_support, developer_productivity) |
| `created_at` | Timestamp of capsule creation |
| `expires_at` | Timestamp after which the capsule should be considered stale |
| `assembly_pattern` | Identifier of the assembly pattern used to create this capsule |
| `version` | Schema version of this capsule |

### Entities

A capsule may contain one or more entities relevant to the context:

| Element | Description |
|---|---|
| `entity_id` | Unique identifier for the entity |
| `entity_type` | Type of entity (e.g., customer, account, project, incident, developer) |
| `entity_name` | Human-readable name or label |
| `attributes` | Key-value attributes describing the entity |
| `source_system` | The system from which this entity was ingested |

### Relationships

A capsule may describe relationships between entities:

| Element | Description |
|---|---|
| `relationship_type` | Type of relationship (e.g., owns, assigned_to, related_to, member_of) |
| `source_entity` | The originating entity in the relationship |
| `target_entity` | The target entity in the relationship |
| `relationship_metadata` | Additional context about the relationship |

### Events

A capsule may include time-stamped events relevant to the context:

| Element | Description |
|---|---|
| `event_id` | Unique identifier for the event |
| `event_type` | Type of event (e.g., message_sent, ticket_created, commit_pushed, status_changed) |
| `timestamp` | When the event occurred |
| `source_system` | The system where the event originated |
| `actor` | The person or system that triggered the event |
| `summary` | Brief description of the event |
| `details` | Structured or semi-structured event details |

### Temporal Metadata

| Element | Description |
|---|---|
| `time_range_start` | Earliest timestamp of included signals |
| `time_range_end` | Latest timestamp of included signals |
| `temporal_resolution` | Granularity of temporal information (e.g., minute, hour, day) |
| `recency_indicator` | Indicator of how recent the most critical signals are |

### Provenance

| Element | Description |
|---|---|
| `source_systems` | List of systems from which signals were ingested |
| `signal_count` | Number of signals included in this capsule |
| `assembly_timestamp` | When the assembly process completed |
| `assembly_duration_ms` | Time taken to assemble this capsule (contributes to Time-to-Context) |

### Policy Context

| Element | Description |
|---|---|
| `access_level` | The access level required to consume this capsule |
| `data_classification` | Classification of the data within the capsule (e.g., internal, confidential, restricted) |
| `masked_fields` | List of fields that have been masked or redacted |
| `compliance_tags` | Compliance frameworks applicable to this capsule's content |
| `retention_policy` | How long this capsule should be retained |

### Task Context

| Element | Description |
|---|---|
| `task_type` | The type of task this capsule supports (e.g., customer_inquiry, code_review, incident_triage) |
| `task_description` | Description of the task or query that triggered capsule assembly |
| `recommended_usage` | Guidance for the AI consumer on how to use this context |

## Example Capsule (Illustrative)

```json
{
  "capsule_id": "cap-example-001",
  "capsule_type": "customer_support",
  "created_at": "2026-03-08T10:30:00Z",
  "expires_at": "2026-03-08T11:30:00Z",
  "assembly_pattern": "customer-support-standard",
  "version": "0.1",
  "entities": [
    {
      "entity_id": "cust-12345",
      "entity_type": "customer",
      "entity_name": "Acme Corporation",
      "attributes": {
        "tier": "enterprise",
        "region": "north_america"
      },
      "source_system": "crm"
    }
  ],
  "events": [
    {
      "event_id": "evt-001",
      "event_type": "ticket_created",
      "timestamp": "2026-03-08T09:15:00Z",
      "source_system": "ticketing",
      "actor": "jane.doe@acme.com",
      "summary": "Customer reported integration issue"
    }
  ],
  "provenance": {
    "source_systems": ["crm", "ticketing", "communication"],
    "signal_count": 12,
    "assembly_timestamp": "2026-03-08T10:30:00Z",
    "assembly_duration_ms": 340
  },
  "policy_context": {
    "access_level": "support_agent",
    "data_classification": "internal",
    "masked_fields": [],
    "compliance_tags": ["soc2"]
  },
  "task_context": {
    "task_type": "customer_inquiry",
    "task_description": "Assist with reported integration issue",
    "recommended_usage": "Use customer history and ticket details to provide contextualized support"
  }
}
```

**Note**: This example is illustrative. Production implementations would define schemas based on their specific requirements and compliance needs.

## Schema Evolution

As the context engineering discipline matures, this schema may evolve to include:

- Standardized entity type taxonomies
- Cross-capsule reference mechanisms
- Capsule composition (capsules containing references to sub-capsules)
- Standardized event type vocabularies
- Machine-readable governance policy formats
