# Execution Backlog v1.4 — Epics e Historias Ejecutables

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.4  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/docs/CÓDIGO CÓSMICO_ Implementation Readiness Pack v1.3.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Technical Milestones Plan v1.3.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Implementation Risk Matrix v1.3.md`

---

## 1. Propósito

Traducir el plan de hitos en backlog técnico accionable: epics, historias, criterios de aceptación y prioridad de ejecución.

Este documento es la base para planificación semanal de desarrollo.

---

## 2. Convenciones de backlog

### 2.1 Prioridad

| Nivel | Significado |
|---|---|
| P0 | Crítico para desbloquear siguiente hito |
| P1 | Alto impacto, debe entrar en el hito |
| P2 | Importante, puede moverse una iteración |
| P3 | Deseable, no bloqueante |

### 2.2 Estimación

| Talla | Rango referencial |
|---|---|
| XS | 0.5-1 día |
| S | 1-2 días |
| M | 2-4 días |
| L | 4-7 días |
| XL | > 7 días (dividir) |

### 2.3 Estado

`todo`, `ready`, `in_progress`, `in_review`, `done`, `blocked`

---

## 3. Epic map por hito (M0..M6)

| Hito | Epic ID | Nombre |
|---|---|---|
| M0 | E-00 | Foundation Engineering |
| M1 | E-10 | Core Data and API Contracts |
| M2 | E-20 | Simulation Engine Alpha |
| M3 | E-30 | Gameplay Services Beta |
| M4 | E-40 | UI Runtime Integration |
| M5 | E-50 | Competitive and Economy Alpha |
| M6 | E-60 | Stabilization and Release Readiness |

---

## 4. Backlog detallado por hito

## M0 — Foundation Engineering

### E-00.1 Repositorio y calidad base

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-001 Configurar estructura de módulos backend/frontend | P0 | S | - |
| B-002 Configurar lint + formato + hooks | P0 | S | B-001 |
| B-003 Pipeline CI mínimo (lint + test smoke) | P0 | M | B-002 |
| B-004 Definir plantillas de PR y issue | P1 | XS | - |

Criterios de aceptación:

- [ ] CI corre en cada PR
- [ ] estándar de calidad de código aplicado
- [ ] documentación de contribución actualizada

## M1 — Core Data and API Contracts

### E-10.1 Persistencia y migraciones

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-101 Implementar tablas núcleo (`users`, `universes`, `planets`) | P0 | M | M0 |
| B-102 Implementar tablas especies/genoma/red | P0 | L | B-101 |
| B-103 Implementar tablas eventos y decisiones | P1 | M | B-102 |
| B-104 Implementar tablas competitivo/economía | P1 | L | B-103 |

### E-10.2 Contratos API base

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-111 Definir schemas request/response para universos | P0 | S | B-101 |
| B-112 Definir schemas para especies y eventos | P0 | M | B-102 |
| B-113 Versionar contratos v1 | P1 | S | B-111, B-112 |

Criterios de aceptación:

- [ ] migraciones ejecutan sin error en entorno limpio
- [ ] contratos API validados por tests
- [ ] documentación de endpoints publicada

## M2 — Simulation Engine Alpha

### E-20.1 Tick engine

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-201 Implementar scheduler de tick | P0 | M | M1 |
| B-202 Implementar update ecosistema (clamp 0..100) | P0 | M | B-201 |
| B-203 Implementar mutaciones y reproducción base | P0 | L | B-202 |
| B-204 Registrar causalidad de eventos por tick | P1 | M | B-203 |

### E-20.2 Validación de simulación

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-211 Escenario controlado de 100 ticks | P0 | S | B-203 |
| B-212 Escenario de estrés con 1000 ticks | P1 | M | B-211 |
| B-213 Informe de estabilidad y métricas | P1 | S | B-212 |

Criterios de aceptación:

- [ ] corrida estable sin crash
- [ ] valores fuera de rango = 0
- [ ] trazabilidad causal disponible por evento

## M3 — Gameplay Services Beta

### E-30.1 Servicios de acciones jugador

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-301 Endpoint crear especie con validación completa | P0 | M | M2 |
| B-302 Endpoint editar genoma con reglas de coste | P0 | M | B-301 |
| B-303 Endpoint pasar día / ejecutar tick seguro | P0 | M | B-301 |
| B-304 Endpoint decisiones de evento | P1 | S | B-303 |

### E-30.2 Observabilidad operativa

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-311 Logging estructurado por request | P1 | S | M1 |
| B-312 Trazas por flujo crítico | P1 | M | B-311 |

## M4 — UI Runtime Integration

### E-40.1 Flujos críticos UI

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-401 Dashboard conectado a estado real | P0 | M | M3 |
| B-402 Flujo crear especie end-to-end | P0 | M | B-401 |
| B-403 Feed de eventos con decisiones | P0 | M | B-401 |
| B-404 Localización base es/en en flujos críticos | P1 | M | B-401 |

## M5 — Competitive and Economy Alpha

### E-50.1 Torneos y multiplayer

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-501 Inscripción y loadout de torneo | P0 | M | M3 |
| B-502 Simulación de match asíncrono por lotes | P0 | L | B-501 |
| B-503 Ranking con MMR y desempates | P1 | M | B-502 |

### E-50.2 Economía

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-511 Catálogo de tienda seguro | P1 | M | M3 |
| B-512 Compra de ítems cosméticos/comodidad | P1 | M | B-511 |
| B-513 Validación anti pay-to-win automática | P0 | S | B-511 |

## M6 — Stabilization and Release Readiness

### E-60.1 Hardening

| Story | Prioridad | Talla | Dependencias |
|---|---|---|---|
| B-601 Fix de defectos severidad alta | P0 | L | M5 |
| B-602 Pruebas de carga objetivo | P1 | M | M5 |
| B-603 Documentación final de operación | P1 | S | B-602 |

---

## 5. Historias transversales obligatorias

| Story | Objetivo |
|---|---|
| X-001 Seguridad de secretos y configuración | prevenir incidentes operativos |
| X-002 QA de localización por release | evitar regresiones de texto |
| X-003 Actualización de Release Notes | mantener trazabilidad |
| X-004 Revisión de risk matrix semanal | reducir sorpresa de ejecución |

---

## 6. Criterios de priorización semanal

Orden:

1. desbloqueo de dependencia crítica,
2. reducción de riesgo alto,
3. impacto en flujo jugable principal,
4. deuda técnica acumulada.

---

## 7. Criterios de aceptación del backlog

- [ ] Todas las historias P0 tienen dependencia explícita
- [ ] Ninguna historia XL sin división
- [ ] Cada hito tiene criterio de salida asociado
- [ ] Historias transversales activas en cada iteración

---

## 8. Declaración Final

Execution Backlog v1.4 convierte el roadmap técnico en un tablero ejecutable. La calidad de entrega dependerá de mantener prioridad disciplinada y cierre estricto de dependencias.