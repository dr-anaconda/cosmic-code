# Project Status v2

Proyecto: Codigo Cosmico - Evolucion Profunda
Version: 2.0
Estado: Vigente
Ultima actualizacion: 2026-03-03

## Referencias de control

- Regla global: [../00_governance/reference-rules-v1.md](../00_governance/reference-rules-v1.md)
- Roadmap por fases: [phase-roadmap-v2.md](./phase-roadmap-v2.md)
- Gates: [phase-gates-v2.md](./phase-gates-v2.md)
- Backlog: [priority-backlog-v2.md](./priority-backlog-v2.md)

## 1. Resumen ejecutivo

El proyecto esta en transicion de documentacion extensa a ejecucion controlada de MVP.
La estructura documental ya fue consolidada en `docs/` y se definio un roadmap por fases.
Se integraron documentos narrativos importados desde `_docs/` a `docs/30_experience/narrative/`.

## 2. Estado por fase

| Fase | Estado | Evidencia | Bloqueos |
|---|---|---|---|
| F0 Gobernanza | In Progress | estructura docs consolidada, CANON migrado | cerrar SoT final por dominio |
| F1 Scope freeze MVP | In Progress | alcance MVP definido en decisiones recientes | formalizar fronteras cross-doc |
| F2 Visual direction | Ready | estilo artistico definido (luminoso/poetico) | volcar en art bible formal |
| F3 Arquitectura MVP | Ready | stack objetivo definido | cerrar contratos API minimos |
| F4 Vertical slice | Pending | alcance visual/hud definido | depende de F3 PASS |
| F5 MVP completo | Pending | KPIs de validacion definidos | depende F4 PASS |
| F6 Validacion externa | Pending | gate go/no-go definido | depende F5 PASS |

## 3. Decisiones ya cerradas (alta relevancia)

- MVP sin competitivo, implosion ni monetizacion.
- Competitivo pasa a Fase 2.
- Frontend con React + Vite + PixiJS para escena.
- Backend Flask + SQLAlchemy + SQLite inicial.
- Sesion objetivo 5-8 min, target 3 sesiones por dia.
- KPI para validar: D1 >= 35% y 3 sesiones/dia.

## 4. Riesgos activos

| ID | Riesgo | Severidad | Mitigacion actual |
|---|---|---|---|
| R-A0-01 | Solape entre docs tecnicos | Alta | cerrar contrato de frontera por documento |
| R-A0-02 | Scope creep visual en PixiJS | Alta | limitar a planeta + 3 biomas + VFX base |
| R-A1-01 | Estados documentales inconsistentes | Media | normalizar estado Draft/In Review/Vigente |
| R-A1-02 | Falta de SoT operativo por dominio | Media | publicar matriz SoT en governance |
| R-A1-03 | Referencias a artefactos v1.4-v1.6 no presentes | Baja | Resuelto: artefactos integrados en `docs/50_delivery` |

## 5. Proximo checkpoint de control

Objetivo: cerrar F0 y F1 con evidencia documental.

Checklist:

- [ ] Matriz SoT publicada.
- [ ] Contrato de frontera tournament/multiplayer/monetization publicado.
- [ ] Contrato de frontera data dictionary/complete/ADD publicado.
- [ ] Estado documental normalizado en docs P0.

## 6. Criterio para declarar "MVP en ejecucion"

Se declara cuando F3 este en PASS y exista:

- backlog tecnico P0,
- contratos API minimos,
- modelo de datos MVP,
- definicion de eventos de analitica core.
