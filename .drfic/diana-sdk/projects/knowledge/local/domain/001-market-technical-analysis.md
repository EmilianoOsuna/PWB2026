# Technical Analysis Core — Diana Projects Knowledge

> **ID**: 001-market-technical-analysis
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: general
> **Status**: 🟢 Complete
> **Source**: Deep reasoning + Diana project context

## TL;DR

Technical analysis helps identify structure, trend, support, resistance, and momentum conditions in a market instrument. In Diana projects, it is used as one independent core that contributes to confluence-based signals and should never act as an opaque black box.

## Conceptos Clave

- Trend: the directional bias of price over time.
- Support: a price zone where demand has historically increased.
- Resistance: a price zone where supply has historically increased.
- Momentum: the speed and persistence of price movement.
- Indicator: a derived measure used to interpret structure or momentum.

## Core Concepts

### Market Structure
Technical analysis starts with structure: higher highs, higher lows, lower highs, lower lows, ranges, and breakouts. The key question is not just where price is, but how price got there and whether the current movement is likely continuation or exhaustion.

### Trend and Confirmation
A trend is more reliable when it is confirmed across multiple timeframes or by multiple indicators. Diana should treat trend as one input among several, not as a stand-alone decision mechanism.

### Support and Resistance
Support and resistance are zones, not exact lines. They should be modeled as ranges with tolerance rather than a single price point. That matters for signal generation because exact-price thinking creates false precision.

## Indicators and Usage

Common indicators in an investment workflow include RSI, MACD, moving averages, and volatility bands. They are best used as confirmation or warning signals, not as sole decision drivers.

Diana should prefer indicator combinations that are:
- Explainable
- Stable across sampling windows
- Traceable to the signal rationale

## Integration with the Project

For diana-inversions, technical analysis is one of the active cores in the confluence model. It contributes to buy/sell signal formation, opportunity screening, and alert conditions. It must remain decoupled from fundamental, institutional flow, options, and AI cores so each core can be evaluated independently.

## Decisions de Diseño

- Use zones instead of exact price levels to reduce false precision.
- Prefer confirmatory roles for indicators over predictive claims.
- Keep the core independent so it can be enabled or disabled per user.
- Treat technical analysis as actionable context, not as final authority.

## Referencias y Fuentes

- Diana constitution and project spec.
- General market structure and indicator practices.
- Typical discretionary and systematic technical analysis workflows.

## Siguiente Paso

Generate or refine the project-specific technical analysis core if more domain constraints are needed.