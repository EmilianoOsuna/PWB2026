# 004-speckit-tasks-atomicity — Speckit Tasks Atomicity

## Objetivo

Convertir un plan tecnico en tareas atomicas, ordenadas y verificables, manteniendo independencia entre unidades de trabajo.

## Knowledge docs

- .drfic/diana-sdk/sdk/diana/knowledge/indexes/master-index.md
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/shared-skills-manifest.yaml
- .github/prompts/diana.plan.prompt.md

## Criterios de exito

- Cada tarea tiene una responsabilidad unica.
- El orden de dependencias es explicito.
- Las tareas no adelantan supuestos de implementacion.

## Fallback

Si falta esta skill, descomponer tareas manualmente y reportar gap 004-speckit-tasks-atomicity.