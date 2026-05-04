# Quickstart

**Project**: diana-inversions  
**Initiative**: 001-inversions  
**Date**: 2026-05-03

## Goal

Boot a minimal implementation path for the investment platform without violating the constitution.

## Minimal Working Path

1. Create the frontend and backend roots described in the plan.
2. Implement portfolio, signal and alert read models first.
3. Add broker adapters behind interfaces before wiring execution flows.
4. Preserve human approval for all order preparation and execution boundaries.
5. Add logging and traceability before expanding feature breadth.

## Validation Checklist

- The portfolio view renders central holdings and evolution.
- Signals remain invalid unless confluence and traceability are present.
- Prepared operations cannot execute without explicit approval.
- Broker access remains behind adapters.
- Critical code paths include the required bilingual `💬Osuna:` documentation.

## First Implementation Slice

- Frontend: portfolio dashboard shell.
- Backend: portfolio and signal API contracts.
- Shared: entity and contract types.
- Tests: basic unit and contract coverage for the approval gate and signal validity.
