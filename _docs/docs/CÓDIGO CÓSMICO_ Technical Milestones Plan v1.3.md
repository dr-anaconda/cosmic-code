# Technical Milestones Plan v1.3 — Ruta Ejecutable

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.3  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/docs/CÓDIGO CÓSMICO_ Implementation Readiness Pack v1.3.md`
- `_docs/docs/CÓDIGO CÓSMICO_ ADD.md`
- `_docs/docs/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`

---

## 1. Propósito

Definir hitos técnicos secuenciados, con objetivos, entregables, dependencias y criterio de salida para habilitar ejecución incremental.

---

## 2. Estructura de hitos

### M0 — Foundation Ready

**Objetivo:** preparar base de trabajo técnica y operativa.

Entregables:

- repositorio y estructura de módulos definida,
- entorno local reproducible,
- pipeline básico CI con lint y test smoke,
- contrato de ramas y release activo.

Salida:

- [ ] build base ejecuta en CI,
- [ ] rama `develop` protegida,
- [ ] checklist DoR operativa.

### M1 — Core Data + Contracts

**Objetivo:** persistencia estable y contratos API mínimos.

Entregables:

- esquema base en DB,
- migraciones iniciales,
- endpoints para universes/planets/species,
- validación de payloads.

Salida:

- [ ] integridad referencial validada,
- [ ] cobertura de tests de contrato mínima,
- [ ] sin errores críticos de migración.

### M2 — Simulation Alpha

**Objetivo:** loop de simulación básico funcional.

Entregables:

- tick engine alfa,
- update de ecosistema por ciclo,
- generación de eventos base,
- logging de trazabilidad.

Salida:

- [ ] simulación 100 ticks sin crash,
- [ ] métricas 0..100 clamp correctas,
- [ ] causalidad de eventos auditable.

### M3 — Gameplay API Beta

**Objetivo:** habilitar experiencia jugable de backend.

Entregables:

- endpoints de acciones del jugador,
- control de cooldown/costes,
- serialización de estado de universo,
- hooks de notificación.

Salida:

- [ ] tiempos p95 en objetivo interno,
- [ ] errores funcionales críticos = 0,
- [ ] documentación de endpoints actualizada.

### M4 — UX Integration

**Objetivo:** conectar UI con runtime técnico.

Entregables:

- dashboard funcional,
- vista planeta y species,
- feed de eventos integrado,
- i18n base es/en.

Salida:

- [ ] flujos críticos navegables,
- [ ] textos críticos localizados,
- [ ] QA visual mobile-first aprobado.

### M5 — Competitive + Economy Alpha

**Objetivo:** activar sistemas de torneos, multiplayer y economía en modo controlado.

Entregables:

- entrada a torneo y ranking básico,
- banco genético mínimo,
- catálogo tienda alfa,
- reglas anti pay-to-win aplicadas.

Salida:

- [ ] torneos simulables end-to-end,
- [ ] sin fuga de ventaja competitiva por compra,
- [ ] anti-exploit básico activo.

### M6 — Stabilization & Pre-Release

**Objetivo:** estabilizar y preparar release de implementación inicial.

Entregables:

- hardening de rendimiento,
- observabilidad mínima,
- fixing de defectos de severidad alta,
- QA funcional y editorial final.

Salida:

- [ ] bugs críticos abiertos = 0,
- [ ] SLO mínimo cumplido,
- [ ] gate de release aprobado.

---

## 3. Dependencias entre hitos

`M0 -> M1 -> M2 -> M3 -> M4 -> M5 -> M6`

Regla:

- no saltar hito sin salida aprobada,
- excepciones solo con waiver documentado.

---

## 4. Cronograma sugerido

| Hito | Duración estimada |
|---|---|
| M0 | 1 semana |
| M1 | 2 semanas |
| M2 | 2 semanas |
| M3 | 2 semanas |
| M4 | 2 semanas |
| M5 | 2 semanas |
| M6 | 1-2 semanas |

Total estimado inicial: 12-13 semanas.

---

## 5. Métricas por hito

| Hito | Métrica principal | Objetivo |
|---|---|---|
| M1 | tests de contrato | >= 80% cobertura endpoints críticos |
| M2 | estabilidad de simulación | 0 crashes en corrida controlada |
| M3 | latencia API p95 | bajo objetivo interno |
| M4 | flujos UI críticos aprobados | 100% |
| M5 | fairness competitivo | sin ventaja de compra |
| M6 | defectos críticos | 0 |

---

## 6. Criterios de replanificación

Replanificar cuando:

- un hito se desvía >20% en tiempo,
- aparece riesgo crítico no mitigable en iteración,
- se rompe una dependencia estructural.

---

## 7. Criterios de aceptación

- [ ] hitos con objetivo y salida definidos
- [ ] dependencias explícitas
- [ ] cronograma base definido
- [ ] métricas por hito definidas
- [ ] reglas de replanificación documentadas

---

## 8. Declaración Final

Este plan transforma la visión técnica en una secuencia ejecutable. El éxito depende de mantener disciplina de salida por hito y ajuste temprano de desviaciones.
