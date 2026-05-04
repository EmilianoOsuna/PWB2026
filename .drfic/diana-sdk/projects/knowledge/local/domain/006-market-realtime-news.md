# Real-Time News Core — Diana Projects Knowledge

> **ID**: 006-market-realtime-news
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: general
> **Status**: 🟢 Complete
> **Source**: Deep reasoning + Diana project context

## TL;DR

Real-time news analysis helps identify market-moving events, sentiment shifts, and catalysts that may affect portfolio decisions. In Diana, it should be filtered, contextualized, and tied to actionable user-facing relevance.

## Conceptos Clave

- Catalyst: an event that may change market perception or pricing.
- Sentiment: the tone of information around an asset or sector.
- Relevance: how much the event matters to the user's portfolio or watchlist.
- Recency: how fresh the news is relative to current market conditions.
- Noise: information that is available but not decision-relevant.

## Core Concepts

### Event Relevance
Not all news should trigger an alert or signal. The system should filter by relevance to the portfolio, watchlist, instrument, or broader market context.

### Timing and Freshness
The usefulness of news decays quickly. A good knowledge layer should distinguish between immediate catalysts and stale commentary.

### Noise Reduction
News data is high-volume and noisy. Diana should avoid flooding the user with every headline and instead focus on event classification and relevance scoring.

## Integration with the Project

For diana-inversions, real-time news supports market exploration, alerting, and signal confirmation. It can explain sudden movement, reinforce or weaken a candidate signal, and help the user understand why an asset is moving.

## Decisions de Diseño

- Filter headlines by user relevance and portfolio context.
- Score freshness and event strength separately.
- Keep the news core distinct from signal generation.
- Prefer curated explanations over raw headline dumps.

## Referencias y Fuentes

- Diana constitution and project spec.
- Standard financial-news filtering and event-summarization practices.

## Siguiente Paso

Add source-specific integrations if the project needs vendor-specific news feeds or alert logic.