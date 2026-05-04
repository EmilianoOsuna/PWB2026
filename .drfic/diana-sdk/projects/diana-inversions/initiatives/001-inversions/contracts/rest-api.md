# REST API Contract

**Project**: diana-inversions  
**Initiative**: 001-inversions  
**Date**: 2026-05-03

## Purpose

Define the stable contract boundary between the PWA frontend and the backend REST API.

## Resource Groups

### Portfolio

- Purpose: read and update portfolio state.
- Data contract: portfolio id, metadata, positions, valuation summary, evolution data.

### Signal

- Purpose: expose generated buy/sell recommendations.
- Data contract: signal id, target instrument, direction, confidence score, rationale, contributing cores, status.

### Operation

- Purpose: expose prepared and recorded investment actions.
- Data contract: operation id, side, quantity, approval status, context, outcome, broker metadata.

### Alert

- Purpose: manage explicit market and portfolio notifications.
- Data contract: alert id, condition type, threshold, enabled state, trigger metadata.

### Broker

- Purpose: synchronize broker capability and portfolio connection state.
- Data contract: broker id, provider, status, sync timestamp, supported capabilities.

## Contract Rules

- The frontend must not hold broker credentials.
- Signal validity must be explicit in the payload.
- Operation execution must be blocked unless human approval is recorded.
- The API must preserve traceability metadata for audit and review.
