# Research

**Project**: diana-inversions  
**Initiative**: 001-inversions  
**Date**: 2026-05-03

## Decision 1: Frontend and backend architecture

- Decision: Use a Vite + React + TypeScript PWA frontend and a Node.js + Express REST backend.
- Rationale: The constitution fixes this as the minimum stack and the feature requires a browser-facing dashboard plus broker-facing services.
- Alternatives considered: Single-page frontend only; server-rendered app; desktop client. These were rejected because broker integration, auditability and scalable separation of concerns are better served by a web frontend plus backend API.

## Decision 2: Domain separation by cores

- Decision: Model analysis as independent cores for technical, fundamental, institutional flow, options, and AI synthesis.
- Rationale: The constitution explicitly requires decoupled cores and confluence-based signal validity.
- Alternatives considered: One monolithic signal engine; indicator-only approach. These were rejected because they weaken explainability and make future evolution harder.

## Decision 3: Storage and audit trail

- Decision: Use PostgreSQL with explicit migrations and audit-oriented tables as the canonical persistence layer for portfolios, operations, signals, alerts and event history.
- Rationale: The spec clarification resolved the storage question, and PostgreSQL best satisfies traceability, relational integrity, auditability, and broker synchronization needs.
- Alternatives considered: Client-only storage; ad hoc file persistence; document-only storage. These were rejected because they do not satisfy auditability, relational constraints, or synchronization needs as well as PostgreSQL.

## Decision 4: Broker integration model

- Decision: Use broker adapters behind stable contracts for Interactive Brokers and Alpaca.
- Rationale: The constitution requires extensibility and decoupling so brokers can be added without rewriting signal logic.
- Alternatives considered: Direct broker calls from UI; hardcoded broker-specific flows. These were rejected because they would couple execution concerns to the presentation layer.

## Decision 5: Testing strategy

- Decision: Validate by unit, integration and contract tests with traceability to FR/SC items.
- Rationale: The spec requires auditable behavior, and the plan needs a narrow but complete validation path.
- Alternatives considered: Manual-only validation; pure snapshot testing. These were rejected because they do not prove confluence rules, approval gates or broker decoupling.

## Decision 6: AI role

- Decision: Treat AI as a synthesis and explanation layer only.
- Rationale: This is required by the constitution and the spec, which prohibit autonomous decision-making and black-box signals.
- Alternatives considered: AI-led execution; AI-generated final recommendations without rationale. These were rejected because they violate the governing sources.
