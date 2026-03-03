# 00_governance

Esta carpeta concentra las reglas de gobierno documental del proyecto: indice maestro, proceso de trabajo con agentes, decisiones, QA y trazabilidad de releases.

## Resumen rapido

- Punto de control del sistema documental y su operacion diaria.
- Define como se decide, como se valida y como se versiona.

## Documentos en este directorio

- [agentic-workflow-v1.md](agentic-workflow-v1.md)
- [CÓDIGO CÓSMICO_ Document Index.md](./CÓDIGO CÓSMICO_ Document Index.md)

## Subdirectorios relacionados

- `canon/`
- `decisions/`
- `qa/`
- `release-notes/`

## Reglas y criterios aplicables

- Regla global (SoT): [reference-rules-v1.md](./reference-rules-v1.md).
- Fuente unica por tema: si un contenido ya existe, se referencia y no se duplica.
- Toda referencia entre documentos debe enlazar al `.md` origen.
- Prioridad de version: `v1.3` > `v1.2` > `v1.1` > `v1.0`.
- No avanzar de fase con dudas `A0` abiertas (ver `../60_open-questions/README.md`).
- Todo cambio estructural debe dejar traza en `decisions/decision_log.md` y en `release-notes/`.
