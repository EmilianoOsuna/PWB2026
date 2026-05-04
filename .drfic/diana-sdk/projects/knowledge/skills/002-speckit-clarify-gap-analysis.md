# 002-speckit-clarify-gap-analysis — Speckit Clarify Gap Analysis

## Objetivo

Identificar ambiguedades, gaps y supuestos faltantes en una especificacion canonica sin alterar el alcance definido por la fuente.

## Knowledge docs

- .github/prompts/speckit.clarify.prompt.md
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/shared-skills-manifest.yaml
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/master-index.md

## Criterios de exito

- Los gaps quedan enumerados de forma accionable.
- Las preguntas de aclaracion no inventan requisitos.
- La salida conserva trazabilidad hacia la constitucion y el UCC.

## Fallback

Si falta esta skill, continuar con la mejor interpretacion disponible y reportar gap 002-speckit-clarify-gap-analysis.