# 001-speckit-specify-validation — Speckit Specify Validation

## Objetivo

Validar que una especificacion canonica preserve el sentido de la fuente, alinee encabezados al formato SpecKit y evite inferencias funcionales no autorizadas.

## Knowledge docs

- .github/prompts/speckit.specify.prompt.md
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/shared-skills-manifest.yaml
- .drfic/diana-sdk/sdk/diana/knowledge/indexes/master-index.md

## Criterios de exito

- La spec final conserva el significado de la fuente canonica.
- Los encabezados y secciones quedan alineados a SpecKit.
- No se generan endpoints, tareas ni codigo durante la normalizacion.

## Fallback

Si falta esta skill, usar la plantilla minima de SpecKit y reportar gap 001-speckit-specify-validation.