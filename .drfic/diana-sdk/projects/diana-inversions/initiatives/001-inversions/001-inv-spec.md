# Especificación Funcional Canónica
## Plataforma de Gestión de Inversiones con Inteligencia Artificial

**Iniciativa**: 001-inversions  
**Proyecto**: diana-inversions → diana-inversions_app  
**Alias**: inv | inversions  
**Versión**: 1.0.0  
**Estado**: Draft (Specification Driven Development)  
**Fecha de Creación**: 2026-05-03  
**Fuentes Primarias**: 
- Constitución: inv-constitution.md (v2.1.0)
- UCC: 001-inv-ucc.md (Plataforma de Gestion de Inversiones con Inteligencia Artificial)

---

## 1. Objetivo Estratégico

Diseñar, construir y evolucionar una **plataforma profesional de inversiones asistida por inteligencia artificial**, orientada al mercado estadounidense de acciones y opciones, que ayude a personas y equipos a **tomar decisiones de inversión con mayor precisión, trazabilidad y control**.

El sistema centraliza portafolios, explora mercado, genera señales, registra operaciones, muestra rendimiento y aporta análisis asistido por IA **sin sustituir el criterio humano**.

---

## 2. Alcance Funcional (RF - Requisitos Funcionales)

### RF-001: Gestión Centralizada del Portafolio
- El sistema permite crear, visualizar y actualizar portafolios de inversiones.
- Soporta múltiples portafolios por usuario.
- Cada portafolio incluye instrumentos (acciones, opciones) con cantidad, precio de compra, contexto de operación.
- La información se sincroniza con brokers profesionales (Interactive Brokers, Alpaca).

### RF-002: Visualización de Estado del Portafolio
- Dashboard profesional que muestra:
  - Posición actual del portafolio (composición por instrumento)
  - Ganancia/pérdida realizada y no realizada
  - Exposición por sector, clase de activo, estrategia
  - Evolución temporal del valor total
- Información actualizable sin automátismos.
- Acceso desde dispositivos múltiples (PWA).

### RF-003: Generación de Señales de Compra y Venta
- Sistema de cores desacoplados (análisis fundamental, técnico, flujo institucional, opciones, IA).
- Cada core es independiente y puede activarse/desactivarse por el usuario.
- Una señal es válida SOLO cuando:
  1. Participan cores activos/seleccionados.
  2. Hay confluencia de resultados entre cores.
  3. Se alcanza nivel de confianza y score configurables.
  4. El razonamiento es explicable y trazable.
- **Prohibición constitucional**: No se permiten señales black-box.

### RF-004: Cores de Análisis Permitidos
- **Análisis Fundamental**: Evaluación de métricas de empresa (P/E, PEG, dividendos, balance).
- **Análisis Técnico**: Estructura, tendencia, soportes, resistencias, indicadores (RSI, MACD, Bollinger Bands).
- **Flujo Institucional**: Eventos de mercado, movimientos de grandes posiciones, noticias correladas.
- **Evaluación de Opciones**: Cadena de opciones, volatilidad implícita, Greeks, probabilidad de rentabilidad.
- **IA como Core**: Correlación de múltiples señales, resumen de análisis, evaluación de riesgo (NO decisiones autónomas).

### RF-005: Confirmación Asistida por IA
- La IA puede:
  - Resumir análisis de multiple cores.
  - Correlacionar resultados.
  - Clasificar oportunidades por riesgo/rentabilidad.
  - Explicar lógica de cada core.
- La IA NO puede:
  - Ejecutar operaciones automáticamente.
  - Presentarse como única fuente de decisión.
  - Generar señales opacas o no explicables.
- Todo contexto y límites de incertidumbre deben conservarse.

### RF-006: Historial Completo de Operaciones
- Registro permanente de:
  - Fecha, hora, instrumento, precio, cantidad, contexto de decisión.
  - Core(s) que influyeron en la decisión.
  - Resultado de la operación (ganancia/pérdida, rendimiento %).
  - Evidencia auditable de la trazabilidad.
- Permite entender "qué se decidió, cuándo y por qué".

### RF-007: Alertas Configurables y Relevantes
- Usuario puede configurar alertas por:
  - Cambios de precio en instrumentos específicos.
  - Disparadores técnicos (ruptura de soportes/resistencias, cambios de indicadores).
  - Eventos de mercado relevantes.
  - Nuevas señales confluentes que alcanzan threshold de confianza.
- Las alertas responden a **condiciones explícitas, NO inferencias opacas**.
- Relevancia: el usuario evita ruido innecesario.

### RF-008: Exploración del Mercado
- Búsqueda y filtrado de instrumentos (acciones, opciones) por criterios múltiples.
- Visualización de cadena de opciones.
- Comparación de instrumentos.
- Análisis técnico rápido de candidatos.
- Integración con datos de mercado en tiempo real (brokers).

### RF-009: Integración con Brokers Profesionales
- **Brokers Requeridos**:
  - Interactive Brokers (primario, profesional)
  - Alpaca (secundario, paper trading)
- **Funcionalidades**:
  - Conectividad segura (credenciales cifradas).
  - Sincronización de portafolio.
  - Market data en tiempo real.
  - Preparación asistida de órdenes (NO ejecución automática).
- La arquitectura debe ser **extensible y desacoplada** (nuevos brokers sin reescritura de lógica de señales).

### RF-010: Preparación de Órdenes Asistida (NO Ejecución)
- El sistema prepara órdenes con contexto:
  - Instrumento, cantidad, tipo (compra/venta).
  - Condiciones técnicas: límite de precio, tiempo, estrategia.
  - Justificación: análisis que recomienda la operación.
- Usuario **SIEMPRE** revisa y aprueba ANTES de ejecución.
- No hay automátismos de ejecución sin intervención humana explícita.

---

## 3. Alcance No Funcional (RNF - Requisitos No Funcionales)

### RNF-001: Experiencia de Usuario
- Clara, rápida, confiable.
- Lenguaje del inversionista (NO jerga de desarrollo).
- Accesible desde múltiples dispositivos (PWA base).
- Intuitividad sin sacrificar profundidad de análisis.

### RNF-002: Auditabilidad
- Toda decisión, señal y resultado debe ser auditable.
- Trazabilidad completa: contexto → análisis → decisión → resultado.
- Logs persistentes de eventos críticos.
- Exportabilidad de evidencia para auditoría humana.

### RNF-003: Seguridad de Credenciales
- Credenciales de brokers **NUNCA** se almacenan en cliente.
- Cifrado de extremo a extremo para comunicación broker.
- Backend (Node.js/Express) responsable de seguridad.
- Cumplimiento de estándares de protección de datos.

### RNF-004: Consistencia de Datos
- Información de portafolio consistente entre cliente y broker.
- Sincronización periodizable sin acoplamiento temporal.
- Resolución de conflictos (ej: operación ejecutada en broker no reflejada en UI).

### RNF-005: Performance
- Dashboard carga en < 2 segundos.
- Búsqueda/filtrado de instrumentos en < 1 segundo.
- Análisis de cores completables en < 30 segundos.
- Real-time para market data (según disponibilidad de broker).

### RNF-006: Escalabilidad
- Arquitectura modular que permite:
  - Nuevos cores sin ruptura de contratos.
  - Nuevos brokers sin reescritura de lógica.
  - Evolución incremental (portafolio, señales, alertas).

### RNF-007: Observabilidad
- Structured logging en JSON.
- Métricas de uso y performance.
- Trazabilidad de errores y situaciones anómalas.
- Acceso a logs para debugging y análisis post-operación.

### RNF-008: Testing y Confiabilidad
- Test-First Development (TDD obligatorio).
- Cobertura mínima: 80% para lógica crítica de señales.
- Especificación de comportamiento esperado ANTES de implementación.
- Evidencia funcional obligatoria.

### RNF-009: Documentación
- Código generado incluye comentarios con prefijo `💬Osuna:`.
- Emojis al inicio de comentarios:
  - 💬 explicación
  - ⚠️ advertencia
  - 🐞 bug
  - 💡 idea
- Bilingüe: EN/ES.
- Aplicado obligatoriamente en módulos, servicios, hooks públicos, lógica crítica.
- **Bloqueador**: Ausencia bloquea cierre de tickets.

---

## 4. Restricciones Constitucionales (NO Negociables)

### C-001: Modelo Semi-Automático Obligatorio
- La automatización se limita a **análisis, correlación, recomendación y observación**.
- **Decisión final siempre con el usuario**.
- Ninguna orden se ejecuta sin aprobación humana explícita.

### C-002: Sin IA Soberana
- La IA actúa como **asistente, confirmador, correlador**—NO autoridad.
- No puede ejecutar decisiones por sí sola en esta versión constitucional.
- No puede reemplazar lógica determinística base.

### C-003: Sin Señales Black-Box
- Toda señal debe ser explicable y trazable.
- Los prompts, criterios de señal y límites de recomendación forman parte del diseño (documentables).

### C-004: Prohibición de Asesoría Financiera Certificada
- El sistema NUNCA debe presentarse como asesoría financiera certificada.
- Información es análisis y recomendación, no consejo legal/financiero.

### C-005: Gobernanza de Agentes Obligatoria
- Orden operativo constitucional: **Morpheus → (Neo ∥ Architect) → (Trinity ∥ Oracle) → Osuna**
- Todo agente debe declarar skill activo, cabecera de actividad, evidencia verificable de salida.
- Violaciones bloquean flujo inmediatamente.

### C-006: Stack Tecnológico Mínimo Constitucional
- **PWA Base**: Vite, React, TypeScript (JavaScript solo en interoperabilidad).
- **Backend**: REST API, Node.js, Express.
- **Persistencia**: Estándares de Express + base de datos establecida por arquitectura.

---

## 5. Supuestos Clave

### S-001: Disponibilidad de Market Data
- Se asume disponibilidad de market data en tiempo real desde brokers.
- Si no está disponible, sistema degrada pero continúa operativo con datos históricos.

### S-002: Usuario Responsable
- Se asume que el usuario entiende conceptos básicos de inversión.
- No reemplaza educación financiera del usuario.

### S-003: Infraestructura Estable
- Se asume disponibilidad de conectividad a internet.
- Se asume acceso confiable a APIs de brokers.

### S-004: Regulación Constante
- Se asume cumplimiento actual de leyes del mercado estadounidense.
- Cambios regulatorios requieren evolución de la spec.

### S-005: Agentes Disponibles
- Se asume disponibilidad de agentes Diana para ejecución (Morpheus, Neo, Trinity, Oracle).
- SpecKit se subordina a gobernanza Diana.

---

## 6. Criterios de Éxito

### E-001: Funcionalidad
- Sistema permite gestionar portafolio centralizado sin errores de cálculo.
- Generación de señales con al menos 2 cores activos (confluencia validable).
- Historial completo y auditable de operaciones.

### E-002: Usabilidad
- Usuarios sin experiencia técnica pueden operar dashboards base.
- Terminología clara y orientada a inversionista.
- < 5 clics para acciones frecuentes (compra preparada, alerta configurada).

### E-003: Confiabilidad
- Zero ejecuciones no autorizadas.
- 99.5% uptime de servicios críticos.
- Recuperación de fallos < 5 minutos.

### E-004: Seguridad
- Credenciales de brokers nunca expuestas en cliente.
- Cumplimiento de estándares de encriptación.
- Auditoría de acceso a portafolios/operaciones.

### E-005: Trazabilidad
- 100% de operaciones con contexto auditable.
- Trazabilidad clara: UCC → Constitución → Spec → Implementación.

---

## 7. Componentes Arquitectónicos Esperados

(Nota: Detalle arquitectónico elaborado en Plan Técnico fase posterior)

### Dominio del Cliente (PWA)
- **UI Components**: Dashboard, Portafolio, Señales, Alertas, Exploración
- **State Management**: Context API o Redux
- **Integration Layer**: REST client para APIs de backend

### Dominio del Backend (Node.js/Express)
- **API REST**: Contratos de portafolio, operaciones, señales, brokers
- **Broker Adapter**: Interfaz desacoplada a Interactive Brokers, Alpaca
- **Signal Engine**: Coordinador de cores, confluencia, scoring
- **Persistence**: Base de datos para portafolios, historial, configuración

### Dominio de Cores (Análisis)
- **Fundamental Core**: Cálculos de métricas de empresa
- **Technical Core**: Indicadores, soportes, resistencias
- **Institutional Flow Core**: Integración con datos de flujo
- **Options Core**: Análisis especializado de opciones
- **AI Core**: Correlación, resumen, evaluación de riesgo

---

## 8. Restricciones de Alcance (Fuera de Alcance)

### X-001: Auto-Trading sin Intervención Humana
- NO permitido en esta versión constitucional.
- Requeriría enmienda constitucional explícita.

### X-002: IA Autónoma para Decisiones
- NO permitido.
- IA acompaña, no reemplaza.

### X-003: Operación sin Trazabilidad
- NO permitido.
- Auditoría es obligatoria.

### X-004: Señales No Explicables
- NO permitido.
- Transparencia es constitucional.

### X-005: Mercados No Estadounidenses
- Especificación inicial cubre USA (acciones, opciones).
- Expansión a cripto/mercados globales en futuras iniciativas.

---

## 9. Trazabilidad Constitución → Especificación

| Principio Constitucional | Requisito(s) Especificación | Mapeo |
|--------------------------|-------------------------|--------|
| **Especificación gobierna código** | RF-001 a RF-010, RNF-001 a RNF-009 | Spec es fuente de verdad para implementación |
| **Semi-automatismo obligatorio** | C-001, RF-010 | Preparación asistida, NO ejecución automática |
| **IA como asistente** | RF-005, C-002 | IA resume, correlaciona, recomienda, NO decide |
| **Confluencia de señales** | RF-003, RF-004 | Múltiples cores + coincidencia + score configurable |
| **Auditabilidad** | RF-006, RNF-002, RNF-007 | Historial completo, logs, trazabilidad |
| **Cores desacoplados** | RF-004, RF-009 | Independencia, activación/desactivación |
| **Stack tech mínimo** | RNF-001, C-006 | Vite, React, TypeScript, Node.js, Express |
| **Documentación 💬Osuna** | RNF-009 | Obligatorio, bilingüe, emoji prefix |
| **Gobernanza de agentes** | C-005 | Morpheus→Neo→Trinity→Oracle→Osuna |
| **Seguridad de credenciales** | RNF-003, RF-009 | Backend responsable, cliente nunca almacena |

---

## 10. Trazabilidad UCC → Especificación

| Elemento del UCC | Traducción a Requisito | Requisito(s) |
|-----------------|----------------------|--------------|
| **Contexto**: Portafolio disperso | Gestión centralizada | RF-001 |
| **Contexto**: Múltiples fuentes | Single source of truth | RF-002, RNF-004 |
| **Necesidad**: Consolidar información | Sincronización con brokers | RF-009 |
| **Necesidad**: Identificar señales | Sistema de cores + confluencia | RF-003, RF-004 |
| **Necesidad**: Apoyo analítico con IA | IA como core de correlación | RF-005 |
| **Necesidad**: Registrar operaciones | Historial completo | RF-006 |
| **Necesidad**: Alertas claras | Alertas configurables | RF-007 |
| **Impacto**: Menos trabajo manual | Automatización limitada a análisis | C-001 |
| **Impacto**: Mayor confianza | Confluencia, explicabilidad, trazabilidad | RF-003, RF-005 |
| **Riesgo**: Sobrecarga de info | Alertas por relevancia, no ruido | RF-007 |
| **Riesgo**: IA como consejo | Prohibición constitucional | C-004 |
| **Observación**: Sin auto-trading | Aprobación humana obligatoria | RF-010, C-001 |
| **Observación**: IA acompaña | IA como asistente/confirmador | RF-005, C-002 |

---

## 11. Gaps Detectados y Status

### Gap-001: Especificación de Brokers
- **Tipo**: Pendiente de detalle técnico
- **Resolución**: Se detallan en fase `/diana.plan`
- **Status**: Aceptado (roadmap)

### Gap-002: Reglas de Scoring de Confluencia
- **Tipo**: No especificadas en este documento
- **Resolución**: Detalle en `/diana.skills` (signal engine skill)
- **Status**: Aceptado (skills generation next)

### Gap-003: Estándares Exactos de IA/Prompts
- **Tipo**: Pendiente de definición
- **Resolución**: Detalle en `/diana.skills` y `/diana.knowledge`
- **Status**: Aceptado (design phases)

### Gap-004: Seguridad y Cumplimiento Regulatorio
- **Tipo**: Criterios de alto nivel, no implementación
- **Resolución**: Especificación de seguridad en `/diana.plan` + validación legal
- **Status**: Aceptado (risk register)

---

## 12. Versionado y Enmiendas

**Versión**: 1.0.0  
**Fecha de Ratificación**: 2026-05-03  
**Última Enmienda**: Ninguna (inicial)

### Política de Enmiendas
- MAJOR: Cambios de objetivo estratégico, alcance funcional fundamental, restricciones constitucionales.
- MINOR: Nuevos requisitos no negociables, clarificaciones.
- PATCH: Correcciones de redacción, ejemplos, formato.

Toda enmienda debe:
- Originarse en UCC o documento formal equivalente.
- Preservar trazabilidad.
- Documentarse con referencia a cambio formal.

---

## 13. Autorización y Estado Final

**Esta Especificación**:
- Es la fuente canónica para la iniciativa 001-inversions.
- Prevalece sobre suposiciones, inferencias o conversaciones verbales.
- Debe ser respetada por todos los artefactos posteriores (plan, skills, knowledge, implementación).
- Está sujeta a enmiendas formales SOLO mediante UCC o documento equivalente.

**Estado**: 🟡 **Draft** (Specification Driven Development)
- Próxima fase: `/diana.skills` para generación de skills y knowledge.
- Luego: `/diana.plan` para plan técnico operativo.
- Finalmente: `/speckit.plan` para ejecución.

**Declaración Final**:

> Esta Especificación define QUÉ debe construir la iniciativa 001-inversions,  
> derivada de constitución canónica y cambios formales del negocio.  
> CÓMO se construye y CON QUÉ herramientas se define en artefactos posteriores.  
> La Especificación permanece como fuente de verdad funcional durante toda la vida del proyecto.

---

**FIN DE ESPECIFICACIÓN**
