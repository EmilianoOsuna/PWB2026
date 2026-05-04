# Technical Analysis Core — diana-inversions Knowledge

> **ID**: 001-inv-technical-analysis-core
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: project
> **Status**: 🟢 Complete
> **Source**: Project constitution + spec + UCC

## TL;DR

This core interprets price structure, trend, support, resistance, and momentum for U.S. stocks and options. It contributes one independent input to Diana's confluence model and must remain explainable, user-controllable, and non-authoritative.

## Conceptos Clave

- Tendencia: dirección predominante del precio.
- Soporte: zona donde la demanda ha reaccionado históricamente.
- Resistencia: zona donde la oferta ha reaccionado históricamente.
- Momentum: persistencia y fuerza del movimiento.
- Confirmación: evidencia adicional que valida o debilita la lectura técnica.

## Core Concepts

### Market Structure for diana-inversions
The project constitution requires a professional investment platform that can analyze U.S. market opportunities with traceability. Technical analysis in this project should emphasize structure, trend, and zone-based interpretation suitable for actionable review.

### Indicators and Context
The spec allows technical indicators such as RSI, MACD, and Bollinger Bands, but the core should not reduce the analysis to a single indicator. It should combine structure and indicator context into one explainable summary.

### User-Selectable Core
The user must be able to enable or disable this core as part of the platform's multi-core confluence model. If disabled, the orchestrator should continue with the remaining active cores.

## Integration with the Project

For diana-inversions, technical analysis is one of the primary cores used to generate buy and sell signals, screen opportunities, and power alert conditions. It should feed the confluence layer with both trend direction and structural context.

## Decisions de Diseño

- Use zones instead of exact levels to avoid false precision.
- Keep the core separate from the signal decision layer.
- Make all outputs auditable and user-visible.
- Support both stock and options chart context where relevant.

## Referencias y Fuentes

- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`

## Siguiente Paso

Refine with any broker-specific chart data or timeframe preferences if the project later requires them.