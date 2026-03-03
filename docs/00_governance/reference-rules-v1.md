# Reference Rules v1

Proyecto: Codigo Cosmico - Evolucion Profunda
Version: 1.0
Estado: Vigente

## 1. Objetivo

Centralizar reglas editoriales y criterios operativos comunes para todo `docs/`, con una sola fuente de verdad.

## 2. Reglas globales de referencia

- Fuente unica por tema: no duplicar contenido que ya existe en otro `.md`.
- Si se cita un tema ya definido, enlazar al documento fuente.
- Si hay versiones, prevalece la mas reciente: `v1.3` > `v1.2` > `v1.1` > `v1.0`.
- Cambios estructurales deben reflejarse en decision log y release notes.

## 3. Reglas de ejecucion por fases

- El avance es por fases con gate PASS/FAIL.
- No avanzar con dudas `A0` abiertas.
- `P0` bloquea avance, `P1` y `P2` no deben comprometer cierre de `P0`.
- No saltar fase sin waiver documentado.

## 4. Criterios de calidad documental

- Coherencia cross-doc sin contradicciones.
- Enlaces funcionales a fuentes referenciadas.
- Alcance y limites del documento explicitos.
- Trazabilidad de decisiones para cambios relevantes.

## 5. Criterios de trazabilidad minima

Antes de cerrar una actualizacion documental:

- [ ] Se actualizaron los documentos afectados.
- [ ] Se mantuvo la fuente unica por tema.
- [ ] Se registraron decisiones de cambio estructural.
- [ ] Se actualizo release notes si aplica.

## 6. Documentos de apoyo

- [agentic-workflow-v1.md](./agentic-workflow-v1.md)
- [CÓDIGO CÓSMICO_ Document Index.md](./CÓDIGO CÓSMICO_ Document Index.md)
- [release-notes/CÓDIGO CÓSMICO_ Release Notes.md](./release-notes/CÓDIGO CÓSMICO_ Release Notes.md)
- [../50_delivery/phase-roadmap-v2.md](../50_delivery/phase-roadmap-v2.md)
- [../60_open-questions/open-questions-log.md](../60_open-questions/open-questions-log.md)
