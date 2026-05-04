# Real-Time News Core — diana-inversions Knowledge

> **ID**: 006-inv-realtime-news-core
> **Generated**: 2026-05-03
> **Scope**: project
> **Layer**: project
> **Status**: 🟢 Complete
> **Source**: Project constitution + spec + UCC

## TL;DR

This core filters and explains real-time market news for relevance to the user's portfolio and watchlist. In diana-inversions it is an event-catalyst layer, not a headline firehose.

## Conceptos Clave

- Catalizador: evento con potencial de mover precio o sentimiento.
- Relevancia: importancia para el portafolio o la watchlist.
- Frescura: cercania temporal del evento al momento actual.
- Ruido: informacion disponible pero poco accionable.
- Sentimiento: tono agregado de la informacion disponible.

## Core Concepts

### Relevance Filtering
Not every headline should become a signal or alert. The platform should prioritize news that affects tracked instruments, sectors, or the broader market context.

### Recency and Decay
The value of news decays over time. The core should therefore score both freshness and likely market impact so older commentary does not masquerade as a live catalyst.

### Noise Management
Because the platform aims to reduce manual work and improve clarity, this core should summarize and prioritize instead of dumping raw headlines on the user.

## Integration with the Project

For diana-inversions, real-time news supports exploration, alerting, and signal confirmation. It helps explain sudden movement and may strengthen or weaken a candidate recommendation when it aligns with other cores.

## Decisions de Diseño

- Score relevance before surfacing information.
- Separate market-moving events from generic commentary.
- Keep the output concise and explainable.
- Use news to add context, not to override the multi-core model.

## Referencias y Fuentes

- `.drfic/diana-sdk/projects/diana-inversions/inv-constitution.md`
- `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md`
- `.drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md`

## Siguiente Paso

Add provider-specific news sources or alert triggers if the project later needs them.