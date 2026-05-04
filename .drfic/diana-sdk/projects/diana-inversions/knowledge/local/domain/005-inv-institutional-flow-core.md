# Institutional Flow Core — diana-inversions Knowledge

> **ID**: 005-inv-institutional-flow-core
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: project
> **Status**: 🟢 Complete
> **Source**: Project constitution + spec + UCC

## TL;DR

This core interprets market flow, unusual activity, and options-related participation to infer whether larger participants may be influencing price behavior. In diana-inversions it should be cautious, observable, and never presented as hidden certainty.

## Conceptos Clave

- Flujo: evidencia observable de presión compradora o vendedora.
- Participación: indicios de actividad relevante en el mercado.
- Strike: precio de ejercicio relevante en opciones.
- Expiración: vencimiento que condiciona la estructura de la operación.
- Imbalance: desbalance entre presión de compra y venta.

## Core Concepts

### Observable Evidence
The platform should only report what can be observed: volume concentration, unusual movement, strike clustering, expiration context, and related price structure. It should not claim privileged knowledge of intent.

### Options Context
The spec explicitly mentions options and market exploration. For diana-inversions, strike and expiration context help explain where flow may be concentrated and why a candidate deserves attention.

### Confluence Role
Flow should strengthen or weaken the broader signal, especially when technical and fundamental context agree. It should not be the only reason to surface a recommendation.

## Integration with the Project

For diana-inversions, institutional flow is a specialized core that supports signal confidence and options decision-making. It must remain transparent enough for the user to review and challenge.

## Decisions de Diseño

- Keep flow language evidence-based and non-assertive.
- Tie strike/expiration observations to visible structure.
- Treat flow as supporting context, not as hidden proof.
- Make the output compatible with alerting and review.

## Referencias y Fuentes

- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`

## Siguiente Paso

Refine with broker-specific flow data if later supported by the platform.