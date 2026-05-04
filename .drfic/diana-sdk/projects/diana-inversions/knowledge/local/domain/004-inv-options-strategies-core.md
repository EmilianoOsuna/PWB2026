# Options Strategies Core — diana-inversions Knowledge

> **ID**: 004-inv-options-strategies-core
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: project
> **Status**: 🟢 Complete
> **Source**: Project constitution + spec + UCC

## TL;DR

This core evaluates options strategies such as Wheel, Straddle, and Iron Condor in the context of U.S. market opportunities. It must make risk/reward assumptions explicit and keep strategy selection auditable.

## Conceptos Clave

- Wheel: strategy often used to generate income with assignment risk.
- Straddle: position that benefits from significant movement in either direction.
- Iron Condor: defined-risk, range-bound strategy.
- Greeks: sensitivity measures for options behavior.
- Volatilidad implicita: expectativa de movimiento futura incorporada al precio.

## Core Concepts

### Strategy Context
Options strategies are not universal. The platform should frame each strategy as a fit for specific market assumptions, volatility conditions, and user risk tolerance.

### Risk and Reward Shape
Because options change the payoff curve, the analysis should explain the shape of risk and reward in plain language. The user needs to know what kind of movement helps or hurts the position.

### Broker and Data Dependencies
The project spec requires broker integration and market-data awareness. This core should therefore be explicit about data freshness and broker support before presenting conclusions.

## Integration with the Project

For diana-inversions, options analysis is a first-class core used in opportunity screening and signal confluence. It is especially relevant when the user is comparing stock-only ideas against premium-generating or volatility-driven setups.

## Decisions de Diseño

- Present strategy assumptions clearly.
- Make risk limits visible before recommendation.
- Keep strategy analysis separate from execution.
- Preserve human approval before any order preparation.

## Referencias y Fuentes

- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`

## Siguiente Paso

Extend with broker-specific contract support or strategy templates if needed.