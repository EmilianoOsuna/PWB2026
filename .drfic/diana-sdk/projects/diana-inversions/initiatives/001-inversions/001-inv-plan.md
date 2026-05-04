# Plan Técnico Canónico
## Plataforma de Gestión de Inversiones con Inteligencia Artificial

**Proyecto**: diana-inversions → diana-inversions_app  
**Alias**: inv | inversions  
**Iniciativa**: 001-inversions  
**Versión**: 1.0.0  
**Estado**: Draft técnico alineado a constitución + spec  
**Fecha**: 2026-05-03  
**Fuentes oficiales**:
- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/tickets/001-inv-tkt.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/meta.md`
- `.drfic/diana-sdk/projects/knowledge/indexes/projects-knowledge-radar.yaml`

## Summary

El proyecto requiere una plataforma web profesional para inversiones asistida por inteligencia artificial, con portafolio centralizado, exploración de mercado, señales confluentes, historial auditable, alertas relevantes e integración desacoplada con brokers profesionales. El plan técnico propone una arquitectura web modular con frontend PWA en Vite/React/TypeScript y backend REST en Node.js/Express, organizada por dominios, cores de análisis, adaptadores de broker y capas de auditoría y observabilidad.

La prioridad arquitectónica es mantener el control humano, la trazabilidad y la separabilidad de los cores. La IA opera como asistente de correlación y resumen, nunca como autoridad soberana ni como ejecutor automático.

## Technical Context

**Language/Version**: TypeScript para cliente y backend; JavaScript solo interoperabilidad si aparece una dependencia legacy  
**Primary Dependencies**: Vite, React, Node.js, Express; broker adapters; signal engine; logging/metrics stack  
**Storage**: Persistencia relacional y/o documental por definir en fase de diseño; debe cubrir portafolio, operaciones, señales, alertas y auditoría  
**Testing**: Unit, integration, contract, and traceability-oriented validation  
**Target Platform**: Web application / PWA con backend API  
**Project Type**: Web application con backend REST  
**Performance Goals**: Dashboard usable en menos de 2 s; búsqueda/filtrado en menos de 1 s; análisis de cores en tiempos acotados por la disponibilidad de datos  
**Constraints**: Sin auto-trading; sin black-box signals; credenciales fuera del cliente; trazabilidad completa; documentación `💬Osuna:` obligatoria  
**Scale/Scope**: Portafolios, instrumentos, señales, alertas, historial, múltiples cores y múltiples brokers con crecimiento incremental

## Constitution Check

GATE: debe pasar antes de cualquier ejecución posterior.

- La especificación y la constitución gobiernan al código: OK.
- La IA actúa como asistente y correlador, no como autoridad soberana: OK.
- No se permiten señales black-box: OK.
- La decisión final pertenece siempre al usuario: OK.
- No se permite ejecución automática de órdenes: OK.
- La arquitectura de brokers debe ser extensible y desacoplada: OK.
- La documentación crítica debe respetar el estándar `💬Osuna:` bilingüe: OK.
- Observabilidad, auditoría y trazabilidad son obligatorias: OK.

Gap no bloqueante detectado:
- La persistencia concreta todavía no está fijada por la fuente canónica; el diseño la resolverá en fase de arquitectura sin romper la constitución.

## Project Structure

### Documentación de la iniciativa

```text
.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/
├── 001-inv-spec.md
├── 001-inv-plan.md
├── meta.md
└── spec.md
```

### Estructura de trabajo objetivo

```text
frontend/
├── src/
│   ├── components/
│   ├── pages/
│   ├── features/
│   ├── services/
│   └── styles/

backend/
├── src/
│   ├── api/
│   ├── domain/
│   ├── services/
│   ├── adapters/
│   ├── persistence/
│   └── observability/

shared/
└── src/
    ├── types/
    ├── contracts/
    └── utils/

tests/
├── unit/
├── integration/
└── contract/
```

**Structure Decision**: Arquitectura web modular con separación clara entre frontend, backend, contratos compartidos y pruebas. Esta estructura respeta la constitución porque desacopla UI, lógica de dominio, persistencia, integración con brokers y observabilidad.

## Architecture

### Layer 1: Frontend PWA

- Dashboard de portafolio, señales, alertas y exploración.
- Componentes de presentación con lenguaje orientado al inversionista.
- Consumo de API REST sin almacenar credenciales sensibles.
- Visualización de trazabilidad de señales, operaciones y resultados.

### Layer 2: Backend REST

- Exposición de contratos estables para portafolio, operaciones, señales, alertas y brokers.
- Autenticación/autorización y manejo de credenciales fuera del cliente.
- Orquestación entre persistencia, brokers y motores de análisis.

### Layer 3: Domain Cores

- Technical core.
- Fundamental core.
- Institutional flow core.
- Options core.
- AI confluence orchestrator.

Cada core debe ser evaluable por separado y combinable por confluencia.

### Layer 4: Broker Adapters

- Adaptador para Interactive Brokers.
- Adaptador para Alpaca.
- Contratos desacoplados para futuros brokers sin reescritura del motor de señal.

### Layer 5: Observability and Audit

- Structured logging.
- Event trail for portfolio and signal decisions.
- Validation-friendly metrics for performance, errors and data freshness.

## Delivery Phases

### Phase 0: Source-of-truth alignment

Objetivo: congelar requisitos, trazabilidad y estructura base.

- Verificar constitución, spec, UCC y ticket.
- Confirmar FR/SC y gaps de diseño.
- Resolver estructura de proyecto objetivo.

Salida: plan aprobado para descomposición posterior en `/speckit.plan`.

### Phase 1: Domain and contract design

Objetivo: definir dominios, entidades y contratos de integración.

- Modelar Portfolio, Instrument, Signal, Operation, Alert, Core y Broker.
- Definir contratos REST y contratos compartidos.
- Alinear validaciones de trazabilidad y auditabilidad.

FR/SC principal: FR-001, FR-002, FR-003, FR-004, FR-006, FR-011; SC-001, SC-002, SC-003, SC-006.

### Phase 2: Frontend shell and portfolio workflows

Objetivo: habilitar la experiencia principal del usuario.

- Dashboard de portafolio.
- Exploración y visualización de instrumentos.
- Estado de señales y alertas.
- Interfaces para revisión humana de operaciones.

FR/SC principal: FR-001, FR-002, FR-007, FR-008, FR-010; SC-001, SC-004, SC-005.

### Phase 3: Signal engine and confluence

Objetivo: implementar la lógica de evaluación por cores.

- Activación/desactivación de cores por usuario.
- Combinación por confluencia y score configurable.
- Explicación trazable por core.
- IA como capa de síntesis y no como autoridad.

FR/SC principal: FR-003, FR-004, FR-005, FR-011, FR-012; SC-002, SC-003.

### Phase 4: Broker integration and order preparation

Objetivo: conectar data y preparación de órdenes con aprobación humana.

- Integración desacoplada con Interactive Brokers y Alpaca.
- Sincronización de portafolio.
- Preparación asistida de órdenes.
- Bloqueo de ejecución sin aprobación explícita.

FR/SC principal: FR-009, FR-010, FR-012; SC-005, SC-006.

### Phase 5: Audit, observability and quality gate

Objetivo: cerrar brechas de confiabilidad y evidencia.

- Logging estructurado.
- Trazabilidad de eventos críticos.
- Pruebas unitarias, de integración y contractuales.
- Revisión de cumplimiento documental y técnico.

FR/SC principal: FR-006, FR-011, FR-012; SC-003, SC-005.

## Traceability Matrix

| Phase | Main Requirements | Main Success Criteria |
|------|--------------------|------------------------|
| Phase 0 | FR-003, FR-004, FR-011 | SC-002, SC-003 |
| Phase 1 | FR-001, FR-002, FR-006, FR-011 | SC-001, SC-003, SC-006 |
| Phase 2 | FR-001, FR-002, FR-007, FR-008, FR-010 | SC-001, SC-004, SC-005 |
| Phase 3 | FR-003, FR-004, FR-005, FR-011, FR-012 | SC-002, SC-003, SC-005 |
| Phase 4 | FR-009, FR-010, FR-012 | SC-005, SC-006 |
| Phase 5 | FR-006, FR-011, FR-012 | SC-003, SC-005 |

## Technical Risks

- Broker API volatility and rate limits may affect live data and synchronization.
- Signal opacity can reappear if confluence rules are not enforced at the boundary.
- Scope creep can blur the line between assistance and autonomous execution.
- Auditability can degrade if event logs are not designed from the start.
- Persistence choice can create rework if it is not fixed before implementation.

## Technical Validation Criteria

- A signal is never valid without confluence, confidence and traceable reasoning.
- No order can be executed without explicit human approval.
- Broker integrations remain isolated behind adapters.
- Portfolio state, operations and alerts remain auditable end to end.
- Logging and metrics are available for critical flows.
- Documentation standards for critical code are enforced.

## Readiness for /speckit.plan

This plan is aligned with the constitutional sources, the canonical spec, the UCC, the service ticket, and the project knowledge indexes. It is ready to feed `/speckit.plan` for detailed decomposition into research, design and implementation artifacts.

## Open Design Gaps

- Concrete persistence technology.
- Exact broker payload contracts.
- Final scoring model for confluence.
- Operational thresholds for real-time news relevance.

These gaps do not block plan generation, but they should be resolved before implementation tasks are frozen.
