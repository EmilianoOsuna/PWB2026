# Data Model

**Project**: diana-inversions  
**Initiative**: 001-inversions  
**Date**: 2026-05-03

## Entities

### Portfolio

- Fields: id, userId, name, baseCurrency, createdAt, updatedAt
- Relationships: contains many Instruments through Positions; relates to many Operations and Alerts
- Rules: must represent a centralized investment view; supports multiple portfolios per user

### Instrument

- Fields: id, symbol, name, assetClass, exchange, currentPrice, metadata
- Relationships: belongs to many Portfolios through Positions; referenced by Signals, Operations and Alerts
- Rules: supports stocks and options as initial scope

### Position

- Fields: id, portfolioId, instrumentId, quantity, averageCost, marketValue, unrealizedPnL, realizedPnL
- Relationships: belongs to one Portfolio and one Instrument
- Rules: stores the current state of a holding inside the portfolio

### Core

- Fields: id, name, type, enabled, confidenceWeight, lastRunAt
- Relationships: participates in Signal evaluation and AI confluence summaries
- Rules: independently activatable or deactivatable by the user

### Signal

- Fields: id, portfolioId, instrumentId, direction, confidenceScore, rationale, status, generatedAt
- Relationships: references multiple contributing Cores; may be linked to Alerts and Operations
- Rules: only valid when confluence and traceable reasoning are present

### Operation

- Fields: id, portfolioId, instrumentId, side, quantity, proposedPrice, approvalStatus, outcome, createdAt
- Relationships: may originate from a Signal and may reference broker-specific metadata
- Rules: no execution without explicit human approval

### Alert

- Fields: id, portfolioId, instrumentId, conditionType, threshold, enabled, triggeredAt, message
- Relationships: belongs to one Portfolio and optionally one Instrument
- Rules: conditions must be explicit and relevance-filtered

### Broker

- Fields: id, name, type, connectionStatus, capabilities, lastSyncAt
- Relationships: syncs Portfolios and supports prepared Operations
- Rules: broker logic must be isolated behind adapters

## State and Validation Rules

- Signal.status values should include draft, valid, rejected and expired.
- Operation.approvalStatus should include pending, approved and blocked.
- Alert.enabled controls whether the alert participates in evaluation.
- Core.enabled controls whether a core participates in confluence.
- Any entity carrying market decision data must preserve traceability metadata.

## Key Relationships

- Portfolio 1..* Position
- Portfolio 1..* Signal
- Portfolio 1..* Operation
- Portfolio 1..* Alert
- Instrument 1..* Position
- Instrument 1..* Signal
- Instrument 1..* Operation
- Instrument 1..* Alert
- Signal *..* Core
- Broker 1..* Portfolio sync metadata
