# Session Operating Standard v1

Proyecto: Codigo Cosmico - Evolucion Profunda
Version: 1.0
Estado: Vigente

## 1. Objetivo

Consolidar por escrito las reglas de trabajo usadas en sesiones de desarrollo para mantener continuidad entre colaboraciones futuras (humanas y agenticas).

## 2. Estructura oficial de carpetas

- Raiz: `README.md`, `app/`, `docs/`.
- Documentacion activa solo en `docs/`.
- Material historico o importado en `docs/90_archive/`.
- No mantener doble fuente en `_docs/` una vez procesada la importacion.

## 3. Source of Truth y versionado

- Source of Truth unico por tema.
- Si hay conflicto entre versiones, prevalece la mas reciente.
- Prioridad de version: `v1.6 > v1.5 > v1.4 > v1.3 > v1.2 > v1.1 > v1.0`.
- Todo cambio estructural debe reflejarse en:
  - `docs/00_governance/decisions/decision_log.md`
  - `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`

## 4. Reglas de referencias entre documentos

- No duplicar contenido ya definido en otro `.md`.
- Si se menciona un tema existente, enlazar al documento fuente.
- Mantener enlaces relativos o rutas `docs/...` validas.
- Validar enlaces despues de mover/renombrar archivos.

## 5. Modelo operativo de ejecucion

- Ejecucion por fases con gates PASS/FAIL (sin calendario fijo obligatorio).
- Prioridad por clases:
  - `P0` bloqueante,
  - `P1` critico,
  - `P2` incremental.
- Dudas por severidad:
  - `A0` bloquea avance,
  - `A1` bloquea QA/release,
  - `A2` deuda no bloqueante.
- No avanzar de fase con `A0` abiertas.

## 6. Convenciones de estado documental

Estados permitidos para documentos activos:

- `Vigente`: aplicable y util para ejecucion actual.
- `Borrador`: en construccion, no usar como contrato final.
- `Archivado`: historico, no fuente activa.

Nota de normalizacion:

- `Activo` se normaliza a `Vigente`.

## 7. Criterios de estructuracion de contenido

- `10_product`: vision y reglas de producto.
- `20_systems`: balance y datos.
- `30_experience`: UX, contenido, narrativa y localizacion.
- `40_technical`: arquitectura y specs tecnicas de sistemas.
- `50_delivery`: roadmap, gates, backlog y estado de ejecucion.
- `00_governance`: reglas, QA, decisiones e indices.

## 8. Flujo agentico (IDE + LLM)

Cada tarea debe incluir:

1. objetivo,
2. alcance in/out,
3. SoT implicados,
4. criterios de aceptacion verificables,
5. verificacion y evidencia de cierre.

Referencia: `docs/00_governance/agentic-workflow-v1.md`.

## 9. Protocolo de intake para nuevos archivos

Cuando aparezcan archivos nuevos fuera de `docs/`:

1. clasificar (activo vs archivo),
2. mover a carpeta dominio correcta,
3. actualizar referencias internas,
4. actualizar `README` de carpeta,
5. actualizar `Document Index`, `project-status` y `release notes`,
6. registrar dudas nuevas en `open-questions-log` si falta contexto.

## 10. Checklist de cierre de sesion

- [ ] Enlaces internos sin roturas.
- [ ] SoT y referencias actualizadas.
- [ ] Estado documental coherente.
- [ ] Cambios reflejados en release notes.
- [ ] Riesgos/dudas nuevos registrados.

## 11. Documentos relacionados

- [reference-rules-v1.md](./reference-rules-v1.md)
- [agentic-workflow-v1.md](./agentic-workflow-v1.md)
- [CÓDIGO CÓSMICO_ Document Index.md](./CÓDIGO CÓSMICO_ Document Index.md)
- [../50_delivery/phase-roadmap-v2.md](../50_delivery/phase-roadmap-v2.md)
- [../60_open-questions/open-questions-log.md](../60_open-questions/open-questions-log.md)
