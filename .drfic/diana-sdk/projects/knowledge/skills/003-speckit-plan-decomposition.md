# 003-speckit-plan-decomposition — Speckit Plan Decomposition

## Objetivo

Traducir una especificacion canonica en fases tecnicas ordenadas, sin adelantar implementacion ni romper la trazabilidad con el canon.

## Knowledge docs

- .github/prompts/diana.plan.prompt.md
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/shared-skills-manifest.yaml
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/master-index.md

## Criterios de exito

- El plan refleja la spec sin desviaciones de alcance.
- Las fases tecnicas quedan ordenadas por dependencia.
- Las decisiones de arquitectura permanecen subordinadas al canon.

## Fallback

Si falta esta skill, crear un plan basico y reportar gap 003-speckit-plan-decomposition.