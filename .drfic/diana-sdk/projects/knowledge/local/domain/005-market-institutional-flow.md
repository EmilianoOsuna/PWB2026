# Institutional Flow Core — Diana Projects Knowledge

> **ID**: 005-market-institutional-flow
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: general
> **Status**: 🟢 Complete
> **Source**: Deep reasoning + Diana project context

## TL;DR

Institutional flow analysis looks for price, volume, and market-structure evidence that larger participants may be active. In Diana, it should inform signal confidence, not act as hidden proof of intent.

## Conceptos Clave

- Flow: evidence of buying or selling pressure.
- Volume: the amount of activity supporting a move.
- Imbalance: asymmetric pressure between buyers and sellers.
- Participation: signs that larger participants may be involved.
- Expiration/strike context: option-related structure that may influence flow interpretation.

## Core Concepts

### Interpreting Flow
Institutional flow is inferential and probabilistic. The system should describe what is observable, such as concentration, pressure, or unusual activity, rather than claiming certainty about the identity or intention of participants.

### Strike and Expiration Context
For option-related instruments, strike and expiration can be useful for grouping activity and assessing interest. That context should be part of the explanation, but not treated as definitive evidence of future direction.

### Flow as Confluence Input
Flow works best when combined with technical and fundamental context. It can strengthen or weaken a candidate signal, but it should not override all other evidence on its own.

## Integration with the Project

For diana-inversions, institutional flow is a separate analysis core used to strengthen confluence-based signals and to provide richer context around options and market events. It should remain transparent and user-reviewable.

## Decisions de Diseño

- Keep flow interpretation evidence-based and cautious.
- Tie flow explanations to observable structure, not hidden intent.
- Use strike and expiration context as supporting structure.
- Avoid overclaiming institutional certainty.

## Referencias y Fuentes

- Diana constitution and project spec.
- Common market microstructure and options-flow analysis practices.

## Siguiente Paso

Refine with broker-specific flow inputs or market-data constraints if needed.