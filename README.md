# alerting

**Reusable alert lifecycle and notification capabilities for FlossWare.**

This repository is intended to define how alerts are created, deduplicated, tracked, acknowledged, resolved, and delivered to notification targets.

## Scope

- Alert and severity contracts
- Lifecycle and deduplication semantics
- Routing to notification channels
- Acknowledgement, resolution, and escalation
- Alert history interfaces and provenance
- Pluggable notification adapters

## Architectural boundaries

- `observability` records metrics, traces, and execution telemetry; `alerting` turns configured conditions or explicit events into actionable alerts.
- `messaging` may transport notifications but does not own alert lifecycle semantics.
- `resilience` provides retry and failure-handling primitives.
- `loom` and `loom-ai` define execution contracts, not the alerting domain model.

Alerts should identify their source, condition, timestamps, lifecycle state, and relevant evidence without leaking credentials or sensitive payloads.

## Status

Repository scaffold. Define lifecycle and deduplication contracts before implementing channel-specific integrations.
