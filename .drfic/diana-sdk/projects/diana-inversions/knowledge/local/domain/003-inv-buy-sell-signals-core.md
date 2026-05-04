# Buy/Sell Signals Core — diana-inversions Knowledge

> **ID**: 003-inv-buy-sell-signals-core
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: project
> **Status**: 🟢 Complete
> **Source**: Project constitution + spec + UCC

## TL;DR

This core produces the user-facing buy and sell recommendation layer for the platform. It only becomes valid when the configured cores converge, confidence is sufficient, and the rationale can be traced.

## Conceptos Clave

- Señal: recomendacion estructurada de compra o venta.
- Confluencia: acuerdo entre varios cores independientes.
- Confianza: nivel de credibilidad calculado para la señal.
- Umbral: minimo requerido para presentar la señal como valida.
- Trazabilidad: capacidad de reconstruir por que surgio la señal.

## Core Concepts

### Signal Validity
The constitution explicitly forbids black-box signals. For diana-inversions, a signal must be explainable, user-visible, and backed by the active cores selected by the user.

### Confidence and Thresholds
Thresholds should be configurable, because the platform is intended to support different risk preferences and workflows. The confidence layer should not overstate certainty when data is incomplete.

### Explainability
Every signal should state which cores contributed and what the main reasons were. That keeps the output reviewable and auditable.

## Integration with the Project

For diana-inversions, this core is central to the investment workflow. It powers signal generation, opportunity ranking, and alerting while remaining subordinate to the user's final decision and to the constitutional rule against autonomous execution.

## Decisions de Diseño

- Require multi-core confluence before validation.
- Avoid hidden weighting that cannot be explained.
- Preserve per-core traceability inside the signal summary.
- Let the user choose which cores participate.

## Referencias y Fuentes

- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`

## Siguiente Paso

Define project-specific scoring rules if the platform later needs different thresholds by asset class or strategy.