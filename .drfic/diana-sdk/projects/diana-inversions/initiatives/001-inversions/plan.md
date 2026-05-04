# Implementation Plan: Plataforma de Gestión de Inversiones con Inteligencia Artificial

**Branch**: `main` | **Date**: 2026-05-03 | **Spec**: `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/spec.md`
**Input**: Feature specification from `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/spec.md`

## Summary

Construir una plataforma web profesional para inversiones asistida por inteligencia artificial, con portafolio centralizado, exploración de mercado, señales confluentes, historial auditable, alertas relevantes e integración desacoplada con brokers. La arquitectura debe mantener el control humano, la trazabilidad y la separación de cores de análisis para que la IA opere como asistente de correlación y explicación, no como ejecutor autónomo.

## Technical Context

**Language/Version**: TypeScript para frontend y backend  
**Primary Dependencies**: Vite, React, Node.js, Express  
**Storage**: PostgreSQL with explicit migrations and audit-oriented tables for portafolio, operaciones, señales, alertas y auditoría  
**Testing**: Unit, integration y contract testing con trazabilidad funcional  
**Target Platform**: Web application / PWA con backend REST  
**Project Type**: Web application  
**Performance Goals**: Dashboard usable en menos de 2 s; búsqueda/filtrado en menos de 1 s; análisis de cores acotado por disponibilidad de datos  
**Constraints**: Sin auto-trading; sin black-box signals; credenciales fuera del cliente; documentación `💬Osuna:` obligatoria; trazabilidad completa  
**Scale/Scope**: Portafolios, instrumentos, señales, alertas, historial, múltiples cores y múltiples brokers con crecimiento incremental

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

- La especificación y la constitución gobiernan al código: OK.
- La IA actúa como asistente, no como autoridad soberana: OK.
- No se permiten señales black-box: OK.
- La decisión final pertenece siempre al usuario: OK.
- No se permite ejecución automática de órdenes: OK.
- La arquitectura de brokers debe permanecer desacoplada: OK.
- Observabilidad, auditoría y trazabilidad son obligatorias: OK.
- Documentación crítica bilingüe con prefijo `💬Osuna:`: OK.

Gap no bloqueante:
- Contratos detallados de broker quedan para diseño de fase 1.
- La convención final de módulos por dominio debe cerrarse antes de escribir la primera historia.

## Project Structure

### Documentation (this feature)

```text
.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/
├── 001-inv-plan.md
├── 001-inv-spec.md
├── data-model.md
├── meta.md
├── plan.md
├── quickstart.md
├── research.md
└── contracts/
    └── rest-api.md
```

### Source Code (repository root)

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

**Structure Decision**: Arquitectura web modular con separación explícita entre frontend PWA, backend REST, contratos compartidos y pruebas. Esta estructura respeta la constitución porque desacopla UI, lógica de dominio, persistencia, integración con brokers y observabilidad.

### Module Conventions

- Frontend: organizar por `features/` y `pages/` por dominio funcional, evitando componentes genéricos sin contexto.
- Backend: organizar por `domain/`, `services/`, `api/routes/`, `adapters/`, `persistence/` y `observability/`.
- Shared: centralizar tipos, contratos y utilidades comunes para evitar duplicación entre frontend y backend.
- Contracts: documentar los límites entre UI y backend, y entre backend y brokers, antes de implementar la integración real.

### Broker Integration Scope

- Interactive Brokers y Alpaca deben implementarse como adaptadores independientes.
- Cada adaptador debe cubrir conectividad, sincronización de portafolio, market data y preparación asistida de órdenes.
- El motor de señales no puede depender de detalles internos del broker.
- Los contratos de broker deben quedar explícitos antes de consumir APIs reales.

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

Ninguna violación constitucional requiere justificación en este punto.

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
| N/A | N/A | N/A |

