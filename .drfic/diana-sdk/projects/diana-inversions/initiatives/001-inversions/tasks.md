# Tasks: Plataforma de Gestión de Inversiones con Inteligencia Artificial

**Input**: Design documents from `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: Included because the spec requires test-first validation for critical behavior and traceability.

**Organization**: Tasks are grouped by user story so each story can be implemented and validated independently.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and base workspace structure for the web app and backend API.

- [ ] T001 Create the workspace scaffold for frontend, backend, shared, and tests directories in `frontend/`, `backend/`, `shared/`, and `tests/`
- [ ] T002 Initialize the TypeScript monorepo baseline with package manifests, PostgreSQL client dependencies, and compiler settings in `package.json`, `frontend/package.json`, `backend/package.json`, `shared/package.json`, and `tsconfig.base.json`
- [ ] T003 [P] Configure linting, formatting, and editor defaults in `.eslintrc.cjs`, `.prettierrc`, and `.vscode/settings.json`

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core abstractions and app shells that every story depends on.

**⚠️ CRITICAL**: No user story work should begin until this phase is complete.

- [ ] T004 Define shared portfolio, signal, operation, alert, core, broker, and traceability types in `shared/src/types/` and `shared/src/contracts/`
- [ ] T005 [P] Create the backend application shell, health route, and middleware pipeline in `backend/src/api/app.ts`, `backend/src/api/routes/index.ts`, and `backend/src/api/routes/healthRoute.ts`
- [ ] T006 [P] Create the frontend application shell and base navigation in `frontend/src/main.tsx`, `frontend/src/App.tsx`, and `frontend/src/components/AppShell.tsx`
- [ ] T007 Establish PostgreSQL repository, schema, and migration interfaces for portfolio, operation, signal, and alert data in `backend/src/persistence/`
- [ ] T008 Establish broker adapter contracts and capability metadata in `backend/src/adapters/`
- [ ] T009 Establish core registry and confluence scoring interfaces in `backend/src/domain/cores/` and `backend/src/domain/signals/`
- [ ] T010 Configure structured logging and audit trail primitives in `backend/src/observability/logger.ts` and `backend/src/services/auditTrailService.ts`

**Checkpoint**: Foundation ready - user story implementation can now begin in parallel.

---

## Phase 3: User Story 1 - Gestionar Portafolio Centralizado (Priority: P1) 🎯 MVP

**Goal**: Deliver a centralized portfolio view with positions, value, and evolution that can be updated and reviewed traceably.

**Independent Test**: Create, query, and update a portfolio with visible positions and verify the displayed state matches the recorded state.

### Tests for User Story 1

- [ ] T011 [P] [US1] Add contract tests for portfolio endpoints in `tests/contract/portfolio.contract.test.ts`
- [ ] T012 [P] [US1] Add integration tests for the portfolio create/read/update flow in `tests/integration/portfolio.integration.test.ts`

### Implementation for User Story 1

- [ ] T013 [P] [US1] Add portfolio and position domain models in `shared/src/types/portfolio.ts` and `shared/src/types/position.ts`
- [ ] T014 [P] [US1] Implement the portfolio repository and projection layer in `backend/src/persistence/portfolioRepository.ts` and `backend/src/domain/portfolio/portfolioProjection.ts`
- [ ] T015 [US1] Implement the portfolio service and validation rules in `backend/src/services/portfolioService.ts`
- [ ] T016 [US1] Implement portfolio API routes and response shaping in `backend/src/api/routes/portfolioRoutes.ts`
- [ ] T017 [P] [US1] Implement the portfolio dashboard, summary, and evolution chart in `frontend/src/pages/PortfolioDashboard.tsx`, `frontend/src/components/PortfolioSummary.tsx`, and `frontend/src/components/PortfolioEvolutionChart.tsx`

**Checkpoint**: User Story 1 should now be fully functional and independently testable.

---

## Phase 4: User Story 2 - Evaluar Señales Confluentes con IA (Priority: P1)

**Goal**: Generate explainable buy/sell signals from decoupled cores and validate them only when confluence and confidence are sufficient.

**Independent Test**: Activate selected cores, generate a signal, and verify it is valid only when confluence, confidence, and traceability are present.

### Tests for User Story 2

- [ ] T018 [P] [US2] Add contract tests for signal generation and validation in `tests/contract/signals.contract.test.ts`
- [ ] T019 [P] [US2] Add integration tests for confluence-based signal flow in `tests/integration/signals.integration.test.ts`

### Implementation for User Story 2

- [ ] T020 [P] [US2] Add signal, core, and confluence models in `shared/src/types/signal.ts` and `shared/src/types/core.ts`
- [ ] T021 [P] [US2] Implement the core registry and confluence scoring engine in `backend/src/domain/cores/coreRegistry.ts` and `backend/src/domain/signals/confluenceEngine.ts`
- [ ] T022 [US2] Implement the AI confluence orchestrator service in `backend/src/services/aiConfluenceService.ts`
- [ ] T023 [US2] Implement signal API routes and validation responses in `backend/src/api/routes/signalRoutes.ts`
- [ ] T024 [P] [US2] Implement signal and core selection views in `frontend/src/pages/SignalsPage.tsx` and `frontend/src/components/CoreSelector.tsx`

**Checkpoint**: User Stories 1 and 2 should both work independently.

---

## Phase 5: User Story 3 - Registrar y Revisar Operaciones con Control Humano (Priority: P2)

**Goal**: Prepare, review, and record operations with explicit human approval and a non-executable default state.

**Independent Test**: Prepare an order, review its context, and confirm it cannot execute without explicit approval.

### Tests for User Story 3

- [ ] T025 [P] [US3] Add contract tests for the operation approval gate in `tests/contract/operations.contract.test.ts`
- [ ] T026 [P] [US3] Add integration tests for the human approval workflow in `tests/integration/operations.integration.test.ts`

### Implementation for User Story 3

- [ ] T027 [P] [US3] Add operation and approval status models in `shared/src/types/operation.ts`
- [ ] T028 [US3] Implement the approval gate and operation preparation service in `backend/src/domain/operations/approvalGate.ts` and `backend/src/services/operationService.ts`
- [ ] T029 [US3] Implement operation persistence and audit linkage in `backend/src/persistence/operationRepository.ts` and `backend/src/services/auditTrailService.ts`
- [ ] T030 [US3] Implement the operation review and approval routes in `backend/src/api/routes/operationRoutes.ts`
- [ ] T031 [P] [US3] Implement the operation review and approval UI in `frontend/src/pages/OperationsPage.tsx` and `frontend/src/components/OperationReviewPanel.tsx`

**Checkpoint**: User Story 3 should now be independently usable without enabling execution.

---

## Phase 6: User Story 4 - Explorar Mercado y Configurar Alertas (Priority: P2)

**Goal**: Search instruments, inspect market context, and configure relevant alerts without unnecessary noise.

**Independent Test**: Search an instrument, review market context, configure an explicit alert, and verify the notification occurs only when the condition is met.

### Tests for User Story 4

- [ ] T032 [P] [US4] Add contract tests for market exploration and alert configuration in `tests/contract/market-alerts.contract.test.ts`
- [ ] T033 [P] [US4] Add integration tests for instrument search and alert triggering in `tests/integration/market-alerts.integration.test.ts`

### Implementation for User Story 4

- [ ] T034 [P] [US4] Add instrument and alert models in `shared/src/types/instrument.ts` and `shared/src/types/alert.ts`
- [ ] T035 [US4] Implement market exploration search, filtering, and comparison logic in `backend/src/services/marketExplorationService.ts`
- [ ] T036 [US4] Implement alert rules, trigger evaluation, and alert routes in `backend/src/domain/alerts/alertEngine.ts` and `backend/src/api/routes/alertRoutes.ts`
- [ ] T037 [P] [US4] Implement the market explorer and alert configuration UI in `frontend/src/pages/MarketExplorerPage.tsx` and `frontend/src/components/AlertConfigForm.tsx`

**Checkpoint**: User Story 4 should now be independently testable and usable.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Improve reliability, auditability, and documentation across all stories.

- [ ] T038 [P] Harden structured logging and metrics in `backend/src/observability/logger.ts` and `backend/src/observability/metrics.ts`
- [ ] T039 [P] Add cross-cutting audit export and traceability helpers in `backend/src/services/auditTrailService.ts` and `backend/src/api/routes/auditRoutes.ts`
- [ ] T040 [P] Refresh bilingual `💬Osuna:` documentation in touched files under `backend/src/`, `frontend/src/`, and `shared/src/`
- [ ] T041 Run the quickstart validation path and update `.drfic/diana-sdk/projects/diana-inversions/initiatives/001-inversions/quickstart.md` if any step diverges
- [ ] T042 Run the final validation suite across `tests/unit/`, `tests/integration/`, and `tests/contract/` and fix regressions in touched source files

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately.
- **Foundational (Phase 2)**: Depends on Setup completion - blocks all user stories.
- **User Stories (Phase 3+)**: Depend on Foundational phase completion.
- **Polish (Final Phase)**: Depends on the desired user stories being complete.

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Foundational; no dependencies on other stories.
- **User Story 2 (P1)**: Can start after Foundational; may reuse shared portfolio context but remains independently testable.
- **User Story 3 (P2)**: Can start after Foundational; may consume signals or portfolio context but remains independently testable.
- **User Story 4 (P2)**: Can start after Foundational; may read portfolio or signal context but remains independently testable.

### Within Each User Story

- Tests are written before implementation and must fail first.
- Shared models come before services and routes.
- Services come before UI wiring where applicable.
- Core implementation comes before integration code.
- Each story must reach a checkpoint before the next story begins if a sequential workflow is chosen.

### Parallel Opportunities

- All Setup tasks marked [P] can run in parallel.
- All Foundational tasks marked [P] can run in parallel where they touch different files.
- Once Foundational work is complete, User Stories 1 through 4 can begin in parallel if staffing allows.
- All tests marked [P] within a user story can run in parallel.
- Different user stories can be implemented in parallel by different developers once the foundation is done.

---

## Parallel Example: User Story 1

```bash
Task: "Add contract tests for portfolio endpoints in tests/contract/portfolio.contract.test.ts"
Task: "Add integration tests for the portfolio create/read/update flow in tests/integration/portfolio.integration.test.ts"
Task: "Implement the portfolio dashboard, summary, and evolution chart in frontend/src/pages/PortfolioDashboard.tsx, frontend/src/components/PortfolioSummary.tsx, and frontend/src/components/PortfolioEvolutionChart.tsx"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup.
2. Complete Phase 2: Foundational.
3. Complete Phase 3: User Story 1.
4. Stop and validate User Story 1 independently.
5. Demo or inspect the portfolio slice before expanding scope.

### Incremental Delivery

1. Finish Setup + Foundational to unblock implementation.
2. Deliver User Story 1 as the MVP portfolio foundation.
3. Add User Story 2 for confluence-based signals.
4. Add User Story 3 for approved operations and auditability.
5. Add User Story 4 for exploration and alerting.
6. Finish with polish, observability, and validation.

### Parallel Team Strategy

1. One developer can own the frontend shell and portfolio UI.
2. One developer can own backend portfolio and signal services.
3. One developer can own broker and audit abstractions.
4. One developer can own alerting and market exploration.

---

## Notes

- [P] tasks = different files, no dependencies.
- [Story] labels map each task to a specific user story for traceability.
- The spec requires auditability, human approval, and non-black-box signals, so those gates are represented as blocking tasks.
- Verify tests fail before implementing each story.

---

## Phase 8: Broker Integration Follow-up

**Purpose**: Close the remaining broker-execution gap with concrete connectivity and synchronization work.

- [ ] T043 [P] Establish Interactive Brokers connectivity, market data ingestion, and sync plumbing in `backend/src/adapters/interactiveBrokersAdapter.ts` and `backend/src/services/brokerSyncService.ts`
- [ ] T044 [P] Establish Alpaca connectivity, paper-trading sync, and order-preparation plumbing in `backend/src/adapters/alpacaAdapter.ts` and `backend/src/services/brokerSyncService.ts`
- [ ] T045 Define broker reconciliation, retry, and failover behavior in `backend/src/services/brokerSyncService.ts` and `backend/src/domain/brokers/brokerReconciliation.ts`