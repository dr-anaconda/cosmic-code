# Sprint 0 Board v1.5 — Tablero de Trabajo Activo

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.5  
**Estado:** Activo

---

## 1. Estructura del tablero

Estados:

- `ready`
- `in_progress`
- `blocked`
- `in_review`
- `done`

Regla WIP:

- máximo 2 tareas `in_progress` por responsable.

---

## 2. Tablero inicial (Semana 1)

| ID | Tarea | Prioridad | Estado inicial | Responsable de rol |
|---|---|---|---|---|
| S0-001 | Estructura de módulos base | P0 | ready | Backend Lead |
| S0-002 | Configurar lint y formateo | P0 | ready | DX Owner |
| S0-003 | Pipeline CI smoke | P0 | ready | DevOps |
| S0-004 | Plantillas PR/Issue | P1 | ready | Project Ops |
| S0-005 | Setup local reproducible (guía + validación) | P0 | ready | Tech Lead |
| S0-006 | Mapa de dependencias M1 | P1 | ready | Product + Tech |

---

## 3. Tablero objetivo (Semana 2)

| ID | Tarea | Prioridad | Estado objetivo | Responsable de rol |
|---|---|---|---|---|
| S0-101 | Historias M1 P0 en `ready` | P0 | done | Product Owner |
| S0-102 | Definir schemas iniciales API | P0 | in_review | Backend Lead |
| S0-103 | Checklist de riesgos top actualizada | P0 | done | QA Lead |
| S0-104 | Informe de cierre Sprint 0 | P1 | done | Tech Lead |

---

## 4. Regla de bloqueos

Si una tarea queda en `blocked` > 24h:

1. Escalar en daily.
2. Asignar acción de desbloqueo con ETA.
3. Si ETA > 48h, activar contingencia de Sprint 0 Active Pack.

---

## 5. Métricas de tablero

| Métrica | Objetivo |
|---|---|
| Throughput semanal | >= 8 tareas |
| Blocked ratio | < 15% |
| Tiempo en review | < 24h |
| Reapertura de tareas | < 10% |

---

## 6. Declaración Final

Este tablero es operativo y debe reflejar la realidad diaria. Si el estado no está actualizado, la planificación pierde validez.
