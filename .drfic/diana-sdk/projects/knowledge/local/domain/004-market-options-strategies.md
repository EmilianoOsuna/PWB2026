# Options Strategies Core — Diana Projects Knowledge

> **ID**: 004-market-options-strategies
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: general
> **Status**: 🟢 Complete
> **Source**: Deep reasoning + Diana project context

## TL;DR

Options strategies translate market views into structured risk/reward profiles. In Diana, they should be evaluated as specialized opportunities with explicit constraints, Greeks awareness, and clear user-facing reasoning.

## Conceptos Clave

- Call: option contract that benefits from upside movement.
- Put: option contract that benefits from downside movement.
- Greeks: sensitivity measures such as delta, gamma, theta, and vega.
- Implied volatility: the market's expected future volatility.
- Spread: a multi-leg position that shapes risk and reward.

## Core Concepts

### Strategy Selection
Strategies such as Wheel, Straddle, and Iron Condor should be viewed as distinct decision templates. Each one implies different assumptions about direction, volatility, and time decay.

### Risk/Reward Shape
Options are not just directional bets. They create payoff curves that need to be understood before use. A Diana knowledge layer should describe the risk profile in a form the user can validate.

### Greeks and Volatility
Greeks and implied volatility are critical for understanding how a strategy may behave under changing market conditions. The analysis should make those sensitivities visible instead of hiding them inside a recommendation score.

## Integration with the Project

For diana-inversions, options analysis is a dedicated core used when the user evaluates options-driven opportunities. It contributes to confluence and should align with broker support, market data availability, and the user's risk tolerance.

## Decisions de Diseño

- Describe each strategy in terms of assumptions and risk profile.
- Keep Greeks visible in user-facing reasoning.
- Avoid presenting options analysis as universally suitable.
- Make broker support and data freshness explicit dependencies.

## Referencias y Fuentes

- Diana constitution and project spec.
- Standard options trading education and brokerage documentation.

## Siguiente Paso

Add project-specific strategy filters or broker constraints if the trading workflow needs them.