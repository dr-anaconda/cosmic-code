# Release Notes — Documentación

**Proyecto:** Código Cósmico – Evolución Profunda  
**Tipo:** Histórico de releases documentales

---

## v2.1 — Reference Rules Consolidation (2026-03-03)

### Added

- `docs/00_governance/reference-rules-v1.md`

### Changed

- `docs/README.md` (fuente global de reglas enlazada)
- `docs/00_governance/README.md` y READMEs de carpetas de dominio (seccion "Reglas y criterios aplicables")
- `docs/00_governance/agentic-workflow-v1.md` (alineado a regla global)
- `docs/50_delivery/phase-roadmap-v2.md`, `phase-gates-v2.md`, `priority-backlog-v2.md`, `project-status-v2.md` (referencias cruzadas de control)

### Impact

- Se establece una fuente unica de reglas para reducir deriva editorial y ambiguedad operativa.

---

## v2.0 — Phase Control + Agentic Workflow (2026-03-03)

### Added

- `docs/50_delivery/phase-roadmap-v2.md`
- `docs/50_delivery/project-status-v2.md`
- `docs/50_delivery/phase-gates-v2.md`
- `docs/50_delivery/priority-backlog-v2.md`
- `docs/00_governance/agentic-workflow-v1.md`

### Changed

- `docs/README.md` (seccion de control operativo)
- `docs/00_governance/CÓDIGO CÓSMICO_ Document Index.md` (v1.2 con nueva ruta de lectura operativa)
- `docs/60_open-questions/open-questions-log.md` (resoluciones de alcance, stack y modelo de ejecucion)

### Impact

- El proyecto pasa a ejecucion por fases y gates, sin calendario fijo.
- El flujo en IDE con LLM queda estandarizado para reducir ambiguedad y retrabajo.

---

## v1.3 — Implementation Readiness Pack (2026-03-03)

### Added

- `docs/50_delivery/CÓDIGO CÓSMICO_ Implementation Readiness Pack v1.3.md`
- `docs/50_delivery/CÓDIGO CÓSMICO_ Technical Milestones Plan v1.3.md`
- `docs/50_delivery/CÓDIGO CÓSMICO_ Implementation Risk Matrix v1.3.md`

### Changed

- `docs/00_governance/CÓDIGO CÓSMICO_ Document Index.md` (v1.1 con ruta y dependencias de ejecución)
- `docs/00_governance/decisions/decision_log.md` con DEC-0029, DEC-0030, DEC-0031

### Impact

- Se habilita transición de documentación a ejecución técnica por hitos.
- Se formaliza gestión de riesgo de implementación como parte del ciclo documental.

---

## v1.2 — Data/Navigation/Release Governance (2026-03-03)

### Added

- `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary Complete.md` (paso de esqueleto a especificación completa)
- `docs/00_governance/CÓDIGO CÓSMICO_ Document Index.md` (mapa maestro de navegación documental)
- `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md` (este historial)

### Changed

- `docs/00_governance/decisions/decision_log.md` con DEC-0026, DEC-0027, DEC-0028

### Impact

- Se cierra el gap entre modelo conceptual y especificación persistente.
- Se formaliza navegación y gobernanza de versiones de documentación.

---

## v1.1 — Localization/Event Ops/QA Editorial (2026-03-03)

### Added

- `docs/30_experience/CÓDIGO CÓSMICO_ Localization Spec.md`
- `docs/00_governance/qa/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`

### Changed

- `docs/30_experience/CÓDIGO CÓSMICO_ Event & Content Bible.md` (v1.1 operativo)
- `docs/10_product/CÓDIGO CÓSMICO_ GDD-lite.md` (alineación de referencias)
- `docs/30_experience/CÓDIGO CÓSMICO_ UI_UX.md` (alineación de referencias)
- `docs/00_governance/decisions/decision_log.md` (DEC-0023..DEC-0025)

---

## v1.0 — Foundation + Tanda 2 (2026-03-03)

### Foundation

- CANON completo
- PRD, GDD-lite, Core Loops
- Data Dictionary, System Balance, UI/UX, ADD
- Event & Content Bible inicial

### Tanda 2

- Tournament System completo
- Monetization Spec completo
- Multiplayer Spec completo

---

## Plantilla para próximas versiones

```markdown
## vX.Y — Nombre del release (YYYY-MM-DD)

### Added
- archivo

### Changed
- archivo

### Deprecated
- archivo

### Impact
- efecto esperado en el proyecto
```
