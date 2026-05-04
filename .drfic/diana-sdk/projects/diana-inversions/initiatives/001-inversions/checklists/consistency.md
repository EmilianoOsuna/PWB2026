# Checklist de Validación: Plataforma de Gestión de Inversiones con Inteligencia Artificial

**Propósito**: Validar consistencia entre spec, plan y tasks; calidad de la nueva estructura; trazabilidad de requerimientos; riesgos técnicos; y calidad de criterios de aceptación.
**Creado**: 2026-05-03
**Feature**: [spec.md](../spec.md)

## Consistencia Spec-Plan

| Criterio | Estado | Evidencia | Acción sugerida |
|---|---|---|---|
| El plan apunta a la spec correcta y no a sí mismo como entrada primaria. | OK | [plan.md](../plan.md#L1-L4) ahora muestra `Input: Feature specification from .drfic/.../spec.md`, alineado con la spec canónica. | Mantener esta referencia estable para evitar confusiones en futuras ejecuciones de Speckit. |
| La estrategia técnica del plan está alineada con la restricción constitucional de no usar inferencias no sustentadas. | OK | [constitution.md](../../../../../../../.specify/memory/constitution.md#L20-L28) y [plan.md](../plan.md#L10-L21) mantienen la subordinación a constitución/spec. | Mantener esta alineación durante la fase de implementación y evitar decisiones fuera de la spec. |
| La arquitectura del plan refleja el alcance funcional de la spec. | OK | [spec.md](../spec.md#L83-L93) y [plan.md](../plan.md#L58-L87) cubren portafolio, señales, broker, alertas y auditoría. | Conservar la misma cobertura en cualquier refinamiento posterior. |

## Calidad de Estructura de Proyecto

| Criterio | Estado | Evidencia | Acción sugerida |
|---|---|---|---|
| La estructura modular propuesta separa frontend, backend, shared y tests de forma clara. | OK | [plan.md](../plan.md#L58-L87) define una estructura web modular con carpetas diferenciadas. | Mantener esa separación y evitar mezclar contratos, UI y persistencia en una sola capa. |
| La estructura incluye una base razonable para persistencia y migraciones PostgreSQL. | OK | [plan.md](../plan.md#L24-L35) y [tasks.md](../tasks.md#L34-L41) fijan PostgreSQL y repositorios/migraciones. | Definir el framework de migraciones en la siguiente iteración técnica. |
| La estructura propuesta es suficientemente específica para implementar sin ambigüedad de capas. | OK | [plan.md](../plan.md#L89-L110) añade convenciones explícitas para frontend, backend, shared y contracts. | Mantener estas convenciones como base del primer corte de implementación. |

## Trazabilidad de Requerimientos

| Criterio | Estado | Evidencia | Acción sugerida |
|---|---|---|---|
| Cada requisito funcional principal tiene un bloque de tareas asociado. | OK | [spec.md](../spec.md#L29-L100) y [tasks.md](../tasks.md#L51-L174) cubren FR-001 a FR-012 con tareas dedicadas. | Mantener el mapeo FR↔Tarea visible al agregar nuevos requisitos. |
| Los criterios de éxito cuentan con cobertura operativa en el plan y tasks. | OK | [spec.md](../spec.md#L104-L113) y [tasks.md](../tasks.md#L51-L174) reflejan SC-001 a SC-006. | Añadir trazabilidad explícita por criterio si se amplía el alcance. |
| La trazabilidad de decisiones críticas está documentada en la spec. | OK | [spec.md](../spec.md#L115-L123) y la sección de clarificaciones registran el almacenamiento PostgreSQL. | Mantener un registro similar para futuras decisiones de arquitectura. |
| La cobertura de trazabilidad entre constitution, spec y tasks es completa para el alcance actual. | OK | [spec.md](../spec.md#L115-L123), [plan.md](../plan.md#L10-L21) y [tasks.md](../tasks.md#L34-L174). | No avanzar a implementación sin conservar esta cadena de trazabilidad. |

## Riesgos Técnicos

| Criterio | Estado | Evidencia | Acción sugerida |
|---|---|---|---|
| El riesgo de integración con brokers está reconocido y separado de la lógica de señal. | OK | [plan.md](../plan.md#L123-L151) y [tasks.md](../tasks.md#L37-L41) separan adaptadores y confluencia. | Detallar contratos de broker antes de consumir APIs reales. |
| El plan no oculta el riesgo de decisiones de persistencia no cerradas. | OK | [plan.md](../plan.md#L34-L36) antes de la aclaración marcaba el gap; la decisión fue fijada después. | Registrar el motivo de la elección de PostgreSQL en research o data-model. |
| Existe riesgo de subespecificación en las tareas de integración con brokers. | OK | [tasks.md](../tasks.md#L224-L231) añade tareas concretas para conectividad, market data, sincronización y reconciliación por broker. | Mantener este nivel de detalle si aparecen nuevos brokers o flujos de ejecución. |
| El plan contempla observabilidad y auditoría desde la base. | OK | [plan.md](../plan.md#L28-L35) y [tasks.md](../tasks.md#L42-L50) incluyen logging y audit trail. | Mantener estas tareas como bloqueantes antes de la entrega. |

## Calidad de Criterios de Aceptación

| Criterio | Estado | Evidencia | Acción sugerida |
|---|---|---|---|
| Los criterios de aceptación de la spec son verificables y medibles. | OK | [spec.md](../spec.md#L104-L113) usa resultados observables en SC-001 a SC-006. | Mantener el formato medible en cualquier expansión futura. |
| Los user stories incluyen pruebas independientes claras. | OK | [spec.md](../spec.md#L11-L82) define Independent Test por historia de usuario. | Reusar este patrón para nuevas historias. |
| Las edge cases cubren fallo de datos, confluencia insuficiente, aprobación humana y riesgo regulatorio. | OK | [spec.md](../spec.md#L43-L50) enumera los escenarios críticos. | Añadir edge cases para degradación de brokers y pérdida parcial de sincronización si aparecen. |
| Los criterios de aceptación del plan siguen la misma semántica que la spec. | OK | [plan.md](../plan.md#L92-L117) y [spec.md](../spec.md#L104-L113) coinciden en trazabilidad, aprobación humana y confluencia. | No introducir atajos de implementación que debiliten esta semántica. |

## Resumen de Estado

| Estado | Conteo |
|---|---:|
| OK | 14 |
| Pendiente | 0 |

## Acciones Prioritarias

1. No hay acciones pendientes de consistencia crítica para el alcance actual.
