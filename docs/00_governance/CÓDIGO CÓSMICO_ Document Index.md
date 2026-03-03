# Document Index — Mapa Maestro de Documentacion

**Proyecto:** Codigo Cosmico - Evolucion Profunda  
**Version:** 1.6  
**Estado:** Vigente

---

## 1. Proposito

Centralizar navegacion, ownership y dependencias de la documentacion activa, evitando duplicacion y deriva editorial.

---

## 2. Ruta de lectura recomendada

1. `docs/50_delivery/project-status-v2.md`
2. `docs/50_delivery/phase-roadmap-v2.md`
3. `docs/50_delivery/phase-gates-v2.md`
4. `docs/50_delivery/priority-backlog-v2.md`
5. `docs/10_product/CÓDIGO CÓSMICO_ PRD.md`
6. `docs/10_product/CÓDIGO CÓSMICO_ GDD-lite.md`
7. `docs/10_product/CÓDIGO CÓSMICO_ Core Loops.md`
8. `docs/20_systems/CÓDIGO CÓSMICO_ System Balance Sheet.md`
9. `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary.md`
10. `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary Complete.md`
11. `docs/40_technical/CÓDIGO CÓSMICO_ ADD.md`
12. `docs/30_experience/CÓDIGO CÓSMICO_ UI_UX.md`
13. `docs/30_experience/CÓDIGO CÓSMICO_ Event & Content Bible.md`
14. `docs/30_experience/CÓDIGO CÓSMICO_ Localization Spec.md`
15. `docs/30_experience/narrative/README.md`
16. `docs/00_governance/qa/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`
17. `docs/00_governance/reference-rules-v1.md`
18. `docs/00_governance/session-operating-standard-v1.md`
19. `docs/00_governance/agentic-workflow-v1.md`
20. `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`
21. `docs/50_delivery/CÓDIGO CÓSMICO_ Execution Backlog v1.4.md`
22. `docs/50_delivery/CÓDIGO CÓSMICO_ Sprint 0 Kickoff Checklist v1.4.md`
23. `docs/50_delivery/CÓDIGO CÓSMICO_ Sprint 0 Active Pack v1.5.md`
24. `docs/50_delivery/CÓDIGO CÓSMICO_ Sprint 0 Board v1.5.md`
25. `docs/50_delivery/CÓDIGO CÓSMICO_ Execution Ownership Matrix v1.5.md`
26. `docs/50_delivery/CÓDIGO CÓSMICO_ Start Build Now Pack v1.6.md`
27. `docs/50_delivery/CÓDIGO CÓSMICO_ Week 1 Execution Order v1.6.md`
28. `docs/50_delivery/CÓDIGO CÓSMICO_ Issue Templates v1.6.md`

---

## 3. Catalogo activo

| Documento | Rol principal | No duplicar con |
|---|---|---|
| PRD | vision de producto, KPIs, alcance | GDD-lite, Balance |
| GDD-lite | principios de diseno y limites | PRD, Core Loops |
| Core Loops | dinamica de juego por escalas | GDD-lite |
| System Balance Sheet | formulas, umbrales y targets | Data Dictionary |
| Data Dictionary | entidades y campos clave | Data Dictionary Complete |
| Data Dictionary Complete | tipos, indices y restricciones | ADD |
| ADD | arquitectura tecnica y despliegue | Data Dictionary Complete |
| UI/UX | experiencia, componentes y responsive | Event Bible |
| Event & Content Bible | taxonomia y operacion de contenido | Localization |
| Localization Spec | i18n, glosario, pipeline linguistico | QA Editorial |
| Narrative Docs | onboarding humano, comunidad y pitch | PRD, UI/UX |
| QA Editorial v1.1 | scorecard y gate documental | reference-rules |
| phase-roadmap-v2 | ejecucion por fases y prioridades | milestones por tiempo |
| phase-gates-v2 | gate PASS/FAIL por fase | QA editorial |
| priority-backlog-v2 | cola ejecutable P0/P1/P2 | roadmap narrativo |
| project-status-v2 | estado actual por fase y bloqueos | roadmap/backlog |
| session-operating-standard-v1 | reglas de trabajo inter-sesion y estructura | reference-rules + workflow |
| Execution Backlog v1.4 | epics e historias ejecutables | phase-roadmap-v2 |
| Sprint 0 Kickoff Checklist v1.4 | control de inicio de ejecucion | Execution Backlog v1.4 |
| Sprint 0 Active Pack v1.5 | contrato operativo de sprint activo | Kickoff + Backlog |
| Sprint 0 Board v1.5 | tablero semanal de tareas y estado | Sprint 0 Active Pack v1.5 |
| Execution Ownership Matrix v1.5 | ownership operativo por flujo | Sprint 0 Active Pack v1.5 |
| Start Build Now Pack v1.6 | activacion inmediata de ejecucion | Sprint 0 Active Pack v1.5 |
| Week 1 Execution Order v1.6 | secuencia diaria de ejecucion | Start Build Now Pack v1.6 |
| Issue Templates v1.6 | plantillas operativas para issues | Execution Backlog v1.4 |
| agentic-workflow-v1 | protocolo operativo IDE + LLM | canon general |
| reference-rules-v1 | reglas globales de referencia y trazabilidad | docs README |
| Release Notes | historial de cambios documentales | Document Index |

---

## 4. Dependencias criticas

### 4.1 Nucleo de producto

`PRD -> GDD-lite -> Core Loops`

### 4.2 Nucleo tecnico

`Core Loops -> Balance -> Data Dictionary -> Data Dictionary Complete -> ADD`

### 4.3 Nucleo de experiencia

`UI/UX + Event Bible + Localization + Narrative Docs`

### 4.4 Nucleo de ejecucion

`project-status -> phase-roadmap -> phase-gates -> priority-backlog`

---

## 5. Politica de actualizacion

- Cada documento nuevo debe declararse aqui.
- Todo cambio mayor debe reflejarse en `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`.
- Si se migra contenido desde `_docs/`, registrar decision y destino final.
- Si un archivo legado contradice contenido activo, prevalece el documento activo mas reciente.

---

## 6. Nota sobre legado importado

Se importaron archivos desde `_docs/`.

- Narrativa activa migrada a `docs/30_experience/narrative/`.
- Releases legacy v1.4-v1.6 integrados en `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`.

Las referencias del legado no reemplazan la documentacion activa vigente.

---

## 7. Checklist del indice

- [ ] Todos los docs activos listados
- [ ] Ruta de lectura actualizada
- [ ] Dependencias coherentes
- [ ] Sin enlaces rotos

---

## 8. Declaracion final

Este indice es el punto de entrada documental oficial del proyecto. Antes de crear o modificar contenido, validar primero este mapa.
