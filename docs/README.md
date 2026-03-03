# Documentacion del Proyecto

Este es el punto de entrada oficial de documentacion para **Codigo Cosmico - Evolucion Profunda**.

## Reglas de consolidacion

- Fuente unica por tema (Source of Truth).
- No duplicar contenido: resumir y referenciar.
- Prioridad de version: `v1.3` > `v1.2` > `v1.1` > `v1.0`.
- Todo cambio significativo debe reflejarse en release notes y decision log.

## Estructura

- `00_governance/`: metodologia, QA, decisiones y releases documentales.
- `10_product/`: vision de producto y diseno base.
- `20_systems/`: balance y modelos de datos.
- `30_experience/`: UX, contenido y localizacion.
- `40_technical/`: arquitectura y especificaciones tecnicas de sistemas.
- `50_delivery/`: readiness, hitos y riesgos de implementacion.
- `60_open-questions/`: ambiguedades y dudas pendientes de resolver.
- `90_archive/`: fuentes historicas y referencias legado.

## Onboarding rapido (30 segundos)

| Carpeta | Objetivo | Documento de entrada |
|---|---|---|
| `docs/00_governance/` | Reglas de operacion, decisiones y QA | `docs/00_governance/README.md` |
| `docs/10_product/` | Vision de producto y bucles de juego | `docs/10_product/README.md` |
| `docs/20_systems/` | Balance y modelo de datos | `docs/20_systems/README.md` |
| `docs/30_experience/` | UX, contenido y localizacion | `docs/30_experience/README.md` |
| `docs/40_technical/` | Arquitectura y specs tecnicas | `docs/40_technical/README.md` |
| `docs/50_delivery/` | Estado real, roadmap, gates y backlog | `docs/50_delivery/README.md` |
| `docs/60_open-questions/` | Dudas y ambiguedades pendientes | `docs/60_open-questions/README.md` |
| `docs/90_archive/` | Referencias historicas (no SoT actual) | `docs/90_archive/README.md` |

## Si eres... empieza aqui

- Product Owner: `docs/50_delivery/project-status-v2.md` -> `docs/50_delivery/phase-roadmap-v2.md` -> `docs/10_product/README.md`.
- Tech Lead: `docs/50_delivery/priority-backlog-v2.md` -> `docs/40_technical/README.md` -> `docs/20_systems/README.md`.
- UX/Art: `docs/30_experience/README.md` -> `docs/50_delivery/phase-roadmap-v2.md` -> `docs/60_open-questions/open-questions-log.md`.
- QA/Editorial: `docs/00_governance/README.md` -> `docs/00_governance/qa/CÓDIGO CÓSMICO_ QA Editorial v1.1.md` -> `docs/50_delivery/phase-gates-v2.md`.

## Regla de referencias

Cuando un documento haga referencia a otro tema ya documentado, debe enlazar al `.md` fuente en lugar de duplicar contenido.
Fuente global: `docs/00_governance/reference-rules-v1.md`.

## Control operativo (nuevo)

- `docs/50_delivery/project-status-v2.md`: estado actual real por fase.
- `docs/50_delivery/phase-roadmap-v2.md`: roadmap faseado, priorizado y con gates.
- `docs/50_delivery/phase-gates-v2.md`: checklist PASS/FAIL por fase.
- `docs/50_delivery/priority-backlog-v2.md`: backlog ejecutable P0/P1/P2.
- `docs/00_governance/agentic-workflow-v1.md`: protocolo para flujo agentico en IDE + LLM.
- `docs/00_governance/reference-rules-v1.md`: reglas y criterios globales de documentacion.

## Ruta recomendada de lectura

1. `docs/10_product/CÓDIGO CÓSMICO_ PRD.md`
2. `docs/10_product/CÓDIGO CÓSMICO_ GDD-lite.md`
3. `docs/10_product/CÓDIGO CÓSMICO_ Core Loops.md`
4. `docs/20_systems/CÓDIGO CÓSMICO_ System Balance Sheet.md`
5. `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary.md`
6. `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary Complete.md`
7. `docs/40_technical/CÓDIGO CÓSMICO_ ADD.md`
8. `docs/30_experience/CÓDIGO CÓSMICO_ UI_UX.md`
9. `docs/30_experience/CÓDIGO CÓSMICO_ Event & Content Bible.md`
10. `docs/40_technical/CÓDIGO CÓSMICO_ Tournament System.md`
11. `docs/40_technical/CÓDIGO CÓSMICO_ Multiplayer Spec.md`
12. `docs/40_technical/CÓDIGO CÓSMICO_ Monetization Spec.md`
13. `docs/30_experience/CÓDIGO CÓSMICO_ Localization Spec.md`
14. `docs/00_governance/qa/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`
15. `docs/50_delivery/CÓDIGO CÓSMICO_ Implementation Readiness Pack v1.3.md`
16. `docs/50_delivery/CÓDIGO CÓSMICO_ Technical Milestones Plan v1.3.md`
17. `docs/50_delivery/CÓDIGO CÓSMICO_ Implementation Risk Matrix v1.3.md`
18. `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`

## Consolidacion aplicada

- Se migro contenido activo desde `_docs/docs` a carpetas por dominio.
- Se migro CANON y decision log a `docs/00_governance/`.
- Se archivaron insumos historicos en `docs/90_archive/`.
- Se incorporo sistema de dudas en `docs/60_open-questions/`.
- Se agrego un sistema de ejecucion por fases sin calendario fijo.
