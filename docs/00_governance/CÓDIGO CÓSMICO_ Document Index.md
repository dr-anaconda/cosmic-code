# Document Index — Mapa Maestro de Documentación

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.4  
**Estado:** Vigente

---

## 1. Propósito

Centralizar navegación, propósito y dependencia de todos los documentos activos del proyecto para evitar duplicación, pérdida de contexto y deriva editorial.

---

## 2. Ruta de Lectura Recomendada

2. `_docs/docs/CÓDIGO CÓSMICO_ PRD.md`
3. `_docs/docs/CÓDIGO CÓSMICO_ GDD-lite.md`
4. `_docs/docs/CÓDIGO CÓSMICO_ Core Loops.md`
5. `_docs/docs/CÓDIGO CÓSMICO_ System Balance Sheet.md`
6. `_docs/docs/CÓDIGO CÓSMICO_ Data Dictionary.md`
7. `_docs/docs/CÓDIGO CÓSMICO_ Data Dictionary Complete.md`
8. `_docs/docs/CÓDIGO CÓSMICO_ ADD.md`
9. `_docs/docs/CÓDIGO CÓSMICO_ UI_UX.md`
10. `_docs/docs/CÓDIGO CÓSMICO_ Event & Content Bible.md`
11. `_docs/docs/CÓDIGO CÓSMICO_ Tournament System.md`
12. `_docs/docs/CÓDIGO CÓSMICO_ Multiplayer Spec.md`
13. `_docs/docs/CÓDIGO CÓSMICO_ Monetization Spec.md`
14. `_docs/docs/CÓDIGO CÓSMICO_ Localization Spec.md`
15. `_docs/docs/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`
16. `_docs/docs/CÓDIGO CÓSMICO_ Implementation Readiness Pack v1.3.md`
17. `_docs/docs/CÓDIGO CÓSMICO_ Technical Milestones Plan v1.3.md`
18. `_docs/docs/CÓDIGO CÓSMICO_ Implementation Risk Matrix v1.3.md`
19. `_docs/docs/CÓDIGO CÓSMICO_ Execution Backlog v1.4.md`
20. `_docs/docs/CÓDIGO CÓSMICO_ Sprint 0 Kickoff Checklist v1.4.md`
21. `_docs/docs/CÓDIGO CÓSMICO_ Sprint 0 Active Pack v1.5.md`
22. `_docs/docs/CÓDIGO CÓSMICO_ Sprint 0 Board v1.5.md`
23. `_docs/docs/CÓDIGO CÓSMICO_ Execution Ownership Matrix v1.5.md`
24. `_docs/docs/CÓDIGO CÓSMICO_ Start Build Now Pack v1.6.md`
25. `_docs/docs/CÓDIGO CÓSMICO_ Week 1 Execution Order v1.6.md`
26. `_docs/docs/CÓDIGO CÓSMICO_ Issue Templates v1.6.md`
27. `_docs/docs/CÓDIGO CÓSMICO_ Release Notes.md`
1. `_docs/init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md`

---

## 3. Catálogo Activo

| Documento | Rol principal | No duplicar con |
|---|---|---|
| PRD | visión de producto, KPIs, alcance | GDD-lite, Balance |
| GDD-lite | principios de diseño y límites | PRD, Core Loops |
| Core Loops | dinámica de juego por escalas | GDD-lite |
| System Balance Sheet | fórmulas, umbrales y targets | Data Dictionary |
| Data Dictionary | entidades y campos clave | Data Dictionary Complete |
| Data Dictionary Complete | tipos, índices, restricciones | ADD |
| ADD | arquitectura técnica y despliegue | Data Dictionary Complete |
| UI/UX | experiencia, componentes y responsive | Event Bible |
| Event & Content Bible | taxonomía y operación de contenido | Localization |
| Tournament System | ligas, MMR, rewards competitivos | Multiplayer Spec |
| Multiplayer Spec | contratos sociales y asíncronos | Tournament System |
| Monetization Spec | economía ética y guardrails | Balance |
| Localization Spec | i18n, glosario, pipeline lingüístico | QA Editorial |
| QA Editorial v1.1 | scorecard y gate documental | CANON base |
| Implementation Readiness Pack v1.3 | criterios de entrada y ejecución | Milestones, Risk Matrix |
| Technical Milestones Plan v1.3 | secuencia de hitos técnicos | Readiness Pack |
| Implementation Risk Matrix v1.3 | priorización y mitigación de riesgos | Milestones, Readiness Pack |
| Execution Backlog v1.4 | epics e historias ejecutables | Milestones Plan |
| Sprint 0 Kickoff Checklist v1.4 | control de inicio de ejecución | Execution Backlog |
| Sprint 0 Active Pack v1.5 | contrato operativo de sprint activo | Backlog + Kickoff |
| Sprint 0 Board v1.5 | tablero semanal de tareas y estado | Active Pack |
| Execution Ownership Matrix v1.5 | ownership operativo por flujo | Active Pack + Board |
| Start Build Now Pack v1.6 | activación inmediata de ejecución | Sprint 0 Active Pack |
| Week 1 Execution Order v1.6 | secuencia diaria de trabajo | Start Build Now Pack |
| Issue Templates v1.6 | plantillas de issues listas para usar | Execution Backlog |
| Release Notes | historial de cambios documentales | Document Index |
| project-status-v2 | estado actual por fase y bloqueos | roadmap/backlog |
| phase-roadmap-v2 | ejecucion por fases y prioridades | milestones con tiempo |
| phase-gates-v2 | gate PASS/FAIL por fase | QA editorial |
| priority-backlog-v2 | cola ejecutable P0/P1/P2 | roadmap narrativo |
| agentic-workflow-v1 | protocolo operativo IDE + LLM | canon general |

---

## 4. Dependencias Críticas

### 4.1 Núcleo de producto

`PRD -> GDD-lite -> Core Loops`

### 4.2 Núcleo técnico

`Core Loops -> Balance -> Data Dictionary -> Data Dictionary Complete -> ADD`

### 4.3 Núcleo de operación

`UI/UX + Event Bible + Localization + QA Editorial`

### 4.4 Núcleo competitivo-económico

`Tournament System + Multiplayer Spec + Monetization Spec`

### 4.5 Núcleo de ejecución

`Readiness Pack -> Milestones Plan -> Risk Matrix -> Release Notes`

### 4.6 Núcleo de arranque de ejecución

`Readiness Pack -> Execution Backlog -> Sprint 0 Checklist -> M0`

### 4.7 Núcleo operativo de Sprint 0

`Sprint 0 Active Pack -> Sprint 0 Board -> Ownership Matrix -> Daily Execution`

### 4.8 Núcleo de activación inmediata

`Start Build Now Pack -> Week 1 Order -> Issue Templates -> Sprint 0 Board`

---

## 5. Responsables sugeridos

| Área | Owner sugerido |
|---|---|
| Producto | Product Owner |
| Diseño sistémico | Game Design Lead |
| Datos/arquitectura | Tech Lead |
| UX y contenido | UX Lead + Narrative Lead |
| QA documental | Editor técnico |

---

## 6. Política de Actualización

- Cada nuevo documento debe añadirse aquí.
- Cada cambio mayor de versión debe reflejarse en `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`.
- Si un documento se depreca, marcarlo explícitamente y proponer reemplazo.

---

## 7. Checklist del índice

- [ ] Todos los docs activos listados
- [ ] Ruta de lectura actualizada
- [ ] Dependencias coherentes
- [ ] Sin enlaces rotos

---

## 8. Declaración Final

Este índice es el punto de entrada documental oficial del proyecto. Antes de crear o modificar documentos, revisar este mapa para preservar coherencia global.