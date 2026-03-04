# Open Questions

Esta carpeta centraliza dudas, ambiguedades y decisiones pendientes.

## Objetivo

Evitar que la ejecucion avance con supuestos no alineados.

## Severidad

- `A0`: bloquea implementacion.
- `A1`: bloquea QA/release documental.
- `A2`: no bloquea, pero genera deuda.

## Flujo

1. Registrar duda en `open-questions-log.md`.
2. Asignar owner y fecha objetivo.
3. Resolver con decision trazable.
4. Actualizar estado y referencia al documento impactado.

## Plantilla

Usar `templates/question-template.md` para nuevas entradas.

## Documentos en este directorio

- [open-questions-log.md](./open-questions-log.md)
- [lore-gaps-log.md](./lore-gaps-log.md)
- [templates/question-template.md](./templates/question-template.md)

## Reglas y criterios aplicables

- Regla global (SoT): [../00_governance/reference-rules-v1.md](../00_governance/reference-rules-v1.md).
- `A0` se resuelve antes de avanzar de fase.
- Toda duda resuelta debe enlazar decision y documentos impactados.
- No cerrar una duda sin evidencia de actualizacion documental.
- Si una duda afecta alcance MVP, debe alinearse con `../50_delivery/phase-roadmap-v2.md`.
