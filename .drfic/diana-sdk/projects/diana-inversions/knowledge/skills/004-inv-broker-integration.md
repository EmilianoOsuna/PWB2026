# 004-inv-broker-integration — Broker Integration

## Objetivo

Mantener la integracion desacoplada con Interactive Brokers y Alpaca, incluyendo conectividad, market data, sincronizacion y preparacion asistida de ordenes.

## Knowledge docs

- .drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/001-inv-spec.md
- .drfic/diana-sdk/projects/diana-inversions/inv-constitution.md
- .drfic/diana-sdk/projects/diana-inversions/governance/change-requests/001-inv-ucc.md

## Criterios de exito

- La logica de trading no queda acoplada a un broker especifico.
- La sincronizacion de portafolio preserva consistencia.
- La preparacion de ordenes conserva aprobacion humana.

## Fallback

Si falta esta skill, operar con contratos genericos y reportar gap 004-inv-broker-integration.