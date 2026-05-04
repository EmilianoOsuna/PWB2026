# Fundamental Analysis Core — diana-inversions Knowledge

> **ID**: 002-inv-fundamental-analysis-core
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: project
> **Status**: 🟢 Complete
> **Source**: Project constitution + spec + UCC

## TL;DR

This core evaluates company quality, valuation, and long-term business strength for the platform's target instruments. In diana-inversions it is a conviction layer, not a final verdict layer.

## Conceptos Clave

- Calidad: resiliencia y salud del negocio.
- Valoracion: precio relativo frente a fundamentos.
- Crecimiento: expansion del negocio o de las ganancias.
- Rentabilidad: capacidad de convertir ingresos en beneficio.
- Solidez: estabilidad del balance y del modelo de negocio.

## Core Concepts

### Business Fundamentals
The project spec frames the platform as a decision-support tool for U.S. stocks and options. Fundamental analysis should therefore emphasize business quality, financial health, and relative valuation within the broader market context.

### Screening and Ranking
This core should help the user filter weak candidates and rank stronger ones. It should not attempt to replace market structure, flow, or options context; instead, it should strengthen or weaken the overall confluence.

### Explainable Outputs
Every output should explain the reasoning in user-friendly terms, not just emit raw ratios. That helps preserve the project constitution's emphasis on clarity and traceability.

## Integration with the Project

For diana-inversions, fundamental analysis supports portfolio decision-making, signal confidence, and opportunity exploration. It should be particularly useful when the user is comparing multiple candidates or assessing whether a signal aligns with business quality.

## Decisions de Diseño

- Use fundamentals as a ranking input, not a standalone answer.
- Present ratios with context and limitations.
- Keep the core independent and switchable by the user.
- Avoid overfitting to one metric or one sector benchmark.

## Referencias y Fuentes

- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`

## Siguiente Paso

Add sector-specific metrics or watchlist rules if the project later requires custom filters.