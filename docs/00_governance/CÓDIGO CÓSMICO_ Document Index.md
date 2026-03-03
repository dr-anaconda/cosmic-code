# Document Index — Mapa Maestro de Documentación

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.2  
**Estado:** Vigente

---

## 1. Propósito

Centralizar navegación, propósito y dependencia de todos los documentos activos del proyecto para evitar duplicación, pérdida de contexto y deriva editorial.

---

## 2. Ruta de Lectura Recomendada

1. `docs/50_delivery/project-status-v2.md`
2. `docs/50_delivery/phase-roadmap-v2.md`
3. `docs/50_delivery/phase-gates-v2.md`
4. `docs/50_delivery/priority-backlog-v2.md`
5. `docs/00_governance/agentic-workflow-v1.md`
6. `docs/10_product/CÓDIGO CÓSMICO_ PRD.md`
7. `docs/10_product/CÓDIGO CÓSMICO_ GDD-lite.md`
8. `docs/10_product/CÓDIGO CÓSMICO_ Core Loops.md`
9. `docs/20_systems/CÓDIGO CÓSMICO_ System Balance Sheet.md`
10. `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary.md`
11. `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary Complete.md`
12. `docs/40_technical/CÓDIGO CÓSMICO_ ADD.md`
13. `docs/30_experience/CÓDIGO CÓSMICO_ UI_UX.md`
14. `docs/30_experience/CÓDIGO CÓSMICO_ Event & Content Bible.md`
15. `docs/30_experience/CÓDIGO CÓSMICO_ Localization Spec.md`
16. `docs/00_governance/qa/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`
17. `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`

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
