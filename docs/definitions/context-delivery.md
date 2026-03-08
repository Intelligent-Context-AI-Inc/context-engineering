# Context Delivery

Context Delivery is the process of transmitting assembled, structured context from the Enterprise Context Fabric to AI models, agents, and applications that require it for reasoning and decision making.

## Overview

Context Delivery is the final stage of the Enterprise Context Fabric pipeline. After context has been ingested, assembled, and structured, the delivery layer ensures it reaches the consuming AI system in the right format, at the right time, with the right governance controls applied.

## Delivery Mechanisms

- **Synchronous Delivery** — Context is assembled and delivered in real time in response to a request from an AI system
- **Asynchronous Delivery** — Context is pre-assembled and pushed to AI systems or queued for consumption
- **Streaming Delivery** — Context signals are delivered as a continuous stream, enabling AI systems to process information as it arrives
- **Cached Delivery** — Previously assembled context is served from cache when freshness requirements permit

## Delivery Formats

Context can be delivered in multiple formats depending on the consuming system's requirements:

- **Context Capsules** — Structured, self-contained context packages with metadata and governance tags
- **Structured JSON** — Machine-readable JSON documents containing assembled context
- **Natural Language Summaries** — Human-readable summaries generated from structured context
- **Embedding-Ready Formats** — Context pre-processed for vector storage and similarity retrieval

## Delivery Governance

The delivery layer enforces governance at the point of consumption:

- **Access Control** — Verifying that the requesting system or user is authorized to receive the context
- **Data Masking** — Redacting sensitive fields based on the consumer's authorization level
- **Audit Logging** — Recording what context was delivered, to whom, and when
- **Freshness Enforcement** — Ensuring delivered context meets the consumer's recency requirements

## Relationship to Time-to-Context

The delivery layer is the final contributor to Time-to-Context. Optimizations at this layer, such as caching, pre-assembly, and format standardization, directly reduce the total time between a context request and AI system readiness.
