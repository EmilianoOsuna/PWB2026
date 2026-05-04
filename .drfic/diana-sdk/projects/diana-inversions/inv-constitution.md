# Constitución del Proyecto
## diana-inversions_app

**Alias canónico:** inversions  
**Versión:** 2.1.0  
**Fuente primaria:** [001-inversions-ucc](governance/change-requests/001-inversions-ucc.md)  
**Fuente de enriquecimiento:** temporal/project_constitution.md
**Última actualización**: 02/05/2026

---

## 1. Propósito y Alcance

Este proyecto existe para diseñar, construir y evolucionar una plataforma profesional de inversiones asistida por inteligencia artificial, orientada al mercado estadounidense de acciones y opciones, que ayude a personas y equipos a tomar decisiones de inversión con mayor precisión, trazabilidad y control.

El sistema debe centralizar portafolios, explorar mercado, generar señales, registrar operaciones, mostrar rendimiento y aportar análisis asistido por IA sin sustituir el criterio humano.

Fuera de alcance:
- Ejecución automática de órdenes sin aprobación humana explícita
- IA como fuente única de decisión
- Operación sin trazabilidad, evidencia o auditoría
- Asesoría financiera certificada o sustitución del inversionista

---

## 2. Modelo Operativo Constitucional

La plataforma adopta un modelo semi-automático por definición constitucional:

- La automatización se limita a análisis, correlación, recomendación y observación.
- La decisión final pertenece siempre al usuario.
- Ninguna señal puede presentarse como válida si depende de lógica opaca o no explicable.
- El sistema debe favorecer control humano, auditabilidad y reversibilidad operativa.

---

## 3. Principios No Negociables

- La especificación y la constitución gobiernan al código.
- No se permiten inferencias funcionales no sustentadas por una fuente formal.
- La IA actúa como asistente, confirmador y correlador, no como autoridad soberana.
- Toda decisión relevante debe quedar documentada y trazable.
- La señal útil nace de confluencia, confianza configurable y razonamiento explicable.
- El lenguaje del producto debe ser el del inversionista y no el del desarrollo.
- El sistema debe priorizar claridad, rapidez, confiabilidad y auditabilidad.

---

## 4. Arquitectura Constitucional del Sistema

El sistema se organiza por cores desacoplados. Cada core representa una fuente de verdad especializada, activable o desactivable por el usuario.

Cores admitidos por esta constitución:
- Análisis fundamental
- Análisis técnico de estructura, tendencia, soportes, resistencias e indicadores
- Flujo institucional y eventos de mercado
- Cadena de opciones y evaluación especializada de opciones
- Inteligencia artificial como core de correlación y evaluación de riesgo

Cada core debe ser funcional y técnicamente desacoplado. La arquitectura debe permitir añadir nuevos cores sin reescribir la lógica de señal ni romper contratos estables.

---

## 5. Principio de Confluencia

Una señal solo puede considerarse constitucionalmente válida cuando:

1. Participan los cores activos o seleccionados por el usuario.
2. Existe coincidencia suficiente entre los resultados de esos cores.
3. Se alcanza el nivel de confianza y score definidos por la configuración del sistema.
4. El razonamiento de cada core es explicable y trazable.

No se permiten señales black-box.

---

## 6. Rol de la Inteligencia Artificial

- La IA es un core adicional del sistema.
- La IA puede confirmar, correlacionar, resumir y evaluar riesgo.
- La IA no reemplaza la lógica determinística base.
- La IA no ejecuta operaciones por sí misma en esta versión constitucional.
- Toda salida de IA debe conservar contexto, trazabilidad y límites de incertidumbre.

---

## 7. Alcance Funcional Constitucional

Incluye:
- Generación y visualización de señales de compra y venta
- Evaluación de oportunidades en acciones y opciones
- Integración con brokers profesionales reales
- Confirmación asistida por IA
- Dashboard profesional trazable
- Persistencia, logs y evidencia operativa
- Exploración del mercado y seguimiento del portafolio

Excluye:
- Auto-trading sin intervención humana
- IA como única fuente de decisión
- Operación sin trazabilidad
- Señales no explicables

---

## 8. Ingeniería y Calidad

El proyecto se rige por estos principios de ingeniería:

- Spec-Driven Development como metodología base
- Separación estricta entre UI, contratos, lógica cliente y servicios de persistencia o integración
- Arquitectura modular y escalable
- Seguridad estricta de credenciales
- Evidencia funcional obligatoria
- Testing, observabilidad y control de errores

La arquitectura debe permitir evolución incremental de portafolio, señales, alertas, brokers e historial sin acoplamiento indebido.

---

## 9. Stack Tecnológico Constitucional

La constitución fija estándares mínimos, no la implementación detallada.

PWA base:
- Vite como entorno de desarrollo y bundler
- React como framework de interfaz
- TypeScript como lenguaje principal
- JavaScript permitido solo como interoperabilidad o legado
- Arquitectura modular por features

Este stack define el estándar mínimo constitucional para todas las aplicaciones PWA del ecosistema.

Backend mínimo:
- REST API
- Node.js
- Express como framework base

El backend es responsable de persistencia real, seguridad de credenciales, integración con brokers y exposición de contratos estables.

---

## 10. Estándar Constitucional de Documentación

Todo código generado para el proyecto, ya sea por humanos o por agentes de IA, debe cumplir obligatoriamente con este estándar:

- Comentarios con el prefijo `💬Osuna:`
- Emojis al inicio de comentarios:
  - 💬 explicación
  - ⚠️ advertencia
  - 🐞 bug
  - 💡 idea
- Documentación en inglés y español (EN/ES)

Todo código generado debe incluir documentación suficiente para mantener auditabilidad del comportamiento crítico.

Mínimos esperados:
- Aplicado obligatoriamente en: módulos, servicios, hooks públicos, lógica crítica e integraciones con brokers y motores de señales o integraciones sensibles
- Explicación clara de propósito, decisión y efecto
- Trazabilidad suficiente para revisión humana y de agentes

La documentación de código no puede reemplazar pruebas ni evidencia funcional.

### Ejemplo Constitucional

```ts
//💬Osuna: Calculates RSI indicator for trading signals (EN)
//💬Osuna: Calcula el indicador RSI para señales de trading (ES)
export function calculateRSI(...) { ... }
```
La ausencia de este estándar bloquea el cierre de tickets.

---

## 11. Integración con Brokers

La plataforma debe operar al menos con:
- Interactive Brokers como broker primario profesional
- Alpaca como broker secundario o de paper trading

Ambos deberán soportar:

- Conectividad
- Market data
- Sincronización de portafolio
- Preparación de órdenes asistidas

La arquitectura de brokers debe ser extensible y desacoplada. El sistema debe permitir agregar nuevos brokers sin reescribir la lógica de señales o de decisión.

Ejemplos de brokers futuros soportables:

- Tradier
- TD Ameritrade / Schwab
- NinjaTrader
- Brokers crypto (en specs futuras)

La lógica de trading no puede acoplarse a un broker específico.

---

## 12. Gobierno Constitucional de Agentes
### 12.1 Naturaleza de los Agentes

Los agentes de IA son roles documentados y no entidades autónomas sin control.

Principios obligatorios:
- Ningún agente puede actuar fuera de su rol asignado
- Ningún agente puede ejecutar trabajo sin trazabilidad
- Ningún agente puede sustituir la aprobación humana
- Todo agente debe declarar su skill activo, su cabecera de actividad y evidencia verificable de salida cuando aplique

Los roles conceptuales del proyecto se entienden como herramientas de gobernanza y no como autoridad constitutiva superior al equipo humano.

### 12.2 Reglas Obligatorias para Todo Agente

Todo agente de IA que participe en el desarrollo:

- DEBE declarar explícitamente el skill activo
- DEBE mostrar cabecera de actividad
- DEBE dejar evidencia verificable de salida
- NO puede ejecutar trabajo fuera de su fase asignada

La ausencia de cualquiera de estos elementos bloquea el avance del trabajo.

---

### 12.3 Orden Operativo Constitucional Obligatorio

El flujo operativo de agentes es obligatorio e inmutable:

``Morpheus → (Neo ∥ Architect) → (Trinity ∥ Oracle) → Aprobación``

- Morpheus: análisis, investigación y diseño
- Neo: implementación
- Trinity: optimización y seguridad
- Architect: gestor de bases de datos y servicios REST API 
- Oracle: validación y testing
- Osuna: aprovación y validación humana explícita

Violaciones a este flujo bloquean el avance del trabajo.
Cualquier violación a:

- El orden de agentes
- Las reglas de visibilidad
- La falta de evidencia

resulta en:

- Bloqueo inmediato del flujo
- No cierre de tickets
- No avance de fase

---

### 12.4 Independencia de Frameworks

Los agentes definidos en esta Constitución:

- Son independientes de los agentes internos de SpecKit u otros frameworks
- Funcionan como modelo de gobierno y orquestación
- Pueden operar sobre SpecKit, OpenSpec, u otros frameworks

SpecKit no reemplaza este gobierno; se subordina a él.

---

## 13. Escalabilidad del Ecosistema

Los principios de esta Constitución aplican a todas las aplicaciones del ecosistema, garantizando reutilización de agentes, skills y gobierno, consistencia técnica, escalabilidad organizacional, incluyendo:
- Plataformas educativas (cursos, tutoriales, LMS Empresariales)
- Sistemas con agentes  IA Copilot integrada
- Aplicaciones PWA + REST API futuras con framework AI Skill Development

---

## 14. Evolución y Enmiendas

La plataforma está diseñada para evolucionar hacia:

- Backtesting avanzado
- Automatización progresiva (opt‑in)
- Nuevos brokers y mercados
- Nuevos cores especializados

Cualquier cambio que:

- Modifique la filosofía
- Altere el rol de la IA
- Habilite ejecución automática

requiere enmienda constitucional explícita y documentada.

---

## 15. Gobernanza de Cambios

1. Todo cambio relevante debe originarse en un UCC o en un artefacto formal equivalente.
2. Cualquier modificación del comportamiento del sistema debe preservar la trazabilidad entre necesidad de negocio, decisión de diseño e implementación.
3. Los cambios que afecten alcance, señales, alertas, brokers, historial o analítica deben registrarse antes de implementación.
4. Ninguna capacidad que contradiga la constitución puede introducirse por inferencia técnica.
5. Las nuevas necesidades del negocio se gestionan como cambios explícitos y versionados.

---

## 16. Criterios de Calidad y Cumplimiento

El sistema debe cumplir, como mínimo, con estos criterios:

- Ser consistente en cálculo y visualización de portafolio
- Mantener auditabilidad sobre decisiones, señales y resultados
- Presentar información relevante sin ruido innecesario
- Conservar una experiencia accesible desde distintos dispositivos
- Proteger la integridad de los datos operativos del usuario
- Evitar afirmaciones que puedan interpretarse como asesoría financiera certificada
- Mantener trazabilidad de contexto para señales y salidas de IA

La plataforma debe mantener separación clara entre observación, análisis y decisión humana.

---

## 17. Trazabilidad UCC -> Constitución

- Contexto y motivación del UCC: se traduce en el propósito de centralizar la gestión de inversiones y reducir dispersión de información.
- Necesidad general: se convierte en el alcance funcional base del sistema.
- Gestión del portafolio: se formaliza como capacidad central.
- Señales de mercado: se transforma en el principio de confluencia y trazabilidad de señales.
- Análisis con inteligencia artificial: se limita a rol asistencial y de correlación.
- Seguimiento de operaciones: se incorpora como obligación de auditabilidad e historial.
- Alertas y notificaciones: se integra como criterio de relevancia operativa.
- Visibilidad del rendimiento: se refleja en criterios de calidad y experiencia.
- Exploración del mercado: se incluye en el alcance funcional permitido.
- Restricciones del negocio: se consolidan como límites constitucionales no negociables.

---

## 18. Política de Versionado de la Constitución

- MAJOR: cambios de propósito, alcance, modelo operativo o principios no negociables.
- MINOR: ampliaciones normativas sin ruptura del propósito base.
- PATCH: ajustes de redacción, trazabilidad o claridad sin cambio de sentido.

Toda nueva versión debe estar vinculada a un UCC o cambio formal que justifique la actualización.

---

## 19. Estado

- Activa

Este documento constituye la constitución canónica del proyecto diana-inversions_app y reemplaza la versión 2.0.0 previa.

---

## 20. Gaps Detectados

- El UCC y el borrador constitucional no fijan criterios detallados de despliegue, observabilidad ni seguridad operacional.
- Los estándares exactos de prompts, agentes y evidencias deberán concretarse en los artefactos posteriores de skills, knowledge y plan.
- La integración con brokers reales debe validarse con especificación técnica y restricciones de mercado/regulación.

## 21. Declaración Final

Esta Constitución define qué es y qué no es la plataforma.

Toda SPEC, ticket, agente, skill o línea de código deberá:

- Respetar, reflejar y reforzar esta Constitución