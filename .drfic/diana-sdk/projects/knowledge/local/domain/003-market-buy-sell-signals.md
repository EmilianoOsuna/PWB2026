# Buy/Sell Signals Core — Diana Projects Knowledge

> **ID**: 003-market-buy-sell-signals
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: general
> **Status**: 🟢 Complete
> **Source**: Deep reasoning + Diana project context

## TL;DR

Buy and sell signals are not predictions; they are structured recommendations produced from evidence. In Diana, a signal should only become valid when multiple cores converge and the reasoning remains explainable and auditable.

## Conceptos Clave

- Signal: a structured recommendation to consider buying or selling.
- Confluence: agreement between multiple analysis cores.
- Confidence: the system's measured belief in the signal.
- Threshold: the minimum score required to surface a signal as valid.
- Explainability: the ability to trace why the signal exists.

## Core Concepts

### Signal as Recommendation
A signal should be treated as decision support, not as a command. That distinction matters for user autonomy, compliance, and risk management.

### Validity Rules
A signal is only valid when the configured cores contribute, the confidence threshold is met, and the reasoning can be explained back to the user. If one of those conditions is missing, the system should not present the output as a valid signal.

### False Precision Avoidance
Signal language should avoid implying certainty. Phrases that suggest inevitability or guaranteed return should be avoided because they misrepresent the underlying uncertainty.

## Integration with the Project

For diana-inversions, signal generation is one of the central outputs of the platform. It combines fundamental, technical, institutional flow, options, and AI analysis into a user-visible recommendation that must remain traceable to each contributing core.

## Decisions de Diseño

- Require confluence before surfacing a signal.
- Keep confidence and threshold settings explicit.
- Avoid black-box signal generation.
- Preserve per-core traceability inside the signal rationale.

## Referencias y Fuentes

- Diana constitution and project spec.
- General decision-support and signal aggregation practices.

## Siguiente Paso

Define core-specific scoring rules if the project needs more granular thresholds per signal type.