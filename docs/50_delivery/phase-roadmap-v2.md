# Phase Roadmap v2

Proyecto: Codigo Cosmico - Evolucion Profunda
Version: 2.0
Estado: Vigente

## Referencias de control

- Regla global: [../00_governance/reference-rules-v1.md](../00_governance/reference-rules-v1.md)
- Gates: [phase-gates-v2.md](./phase-gates-v2.md)
- Estado actual: [project-status-v2.md](./project-status-v2.md)
- Backlog priorizado: [priority-backlog-v2.md](./priority-backlog-v2.md)

## 1. Objetivo

Definir una ruta de ejecucion por fases, priorizada y controlada por gates, sin dependencia de calendario fijo.

## 2. Regla de prioridad

- P0: bloquea avance de fase si no esta cerrado.
- P1: critico para calidad de MVP, pero no bloquea inicio de fase siguiente si hay mitigacion.
- P2: mejora incremental posterior.

## 3. Alcance MVP confirmado

- Plataforma: web responsive.
- Equipo: 2-3 personas.
- Backend: Flask + SQLAlchemy + SQLite (inicial).
- Frontend: React + Vite + PixiJS (escena) + UI HTML/CSS.
- Juego MVP: single-player core, 1 planeta, niveles 1-4.
- Excluido de MVP: competitivo, implosion, monetizacion.
- KPI de validacion MVP: D1 >= 35% y 3 sesiones por dia.

## 4. Fases y prioridades

### F0 - Gobernanza ejecutable (P0)

Salida esperada:

- Source of Truth por dominio publicado.
- Owners por documento definidos.
- Log de dudas activo con severidad A0/A1/A2.

Gate:

- A0 abiertas = 0.

### F1 - Scope freeze de MVP (P0)

Salida esperada:

- Incluye/no-incluye del MVP firmado.
- KPI norte y gate de validacion definidos.
- Fronteras entre docs tecnicos y de producto cerradas.

Gate:

- No hay contradicciones entre PRD, Core Loops, ADD y Milestones.

### F2 - Visual direction operativa (P1)

Salida esperada:

- Art bible MVP: luminoso/poetico, amanecer cosmico.
- Sistema visual: vector organico + grano.
- Produccion modular: comunes simples y raras destacadas.

Gate:

- Planeta + 3 biomas + VFX base definidos y documentados.

### F3 - Arquitectura MVP implementable (P0)

Salida esperada:

- Contratos API minimos.
- Data model MVP (users, universes, planets, species, milestones).
- Auth con magic link y analitica core minima.

Gate:

- Endpoints criticos especificados con criterios de aceptacion.

### F4 - Vertical slice jugable (P1)

Salida esperada:

- Bucle crear-observar-gestionar funcional.
- Sesion de 5-8 min jugable extremo a extremo.
- Persistencia base funcionando.

Gate:

- Demo interna jugable sin bloqueos criticos.

### F5 - MVP funcional completo (P0)

Salida esperada:

- Tutorial contextual 3 pasos.
- Balance inicial niveles 1-4.
- Instrumentacion de eventos para D1 y sesiones/dia.

Gate:

- QA funcional minima aprobada y A0 = 0.

### F6 - Readiness y validacion externa (P0)

Salida esperada:

- Build candidata de beta cerrada.
- KPIs y decision go/no-go para Fase 2.
- Plan de correcciones si no se alcanza target.

Gate:

- Decision formal registrada en decision log.

## 5. Secuencia de ejecucion

`F0 -> F1 -> F2 -> F3 -> F4 -> F5 -> F6`

No se permite salto de fase sin waiver documentado.

## 6. Entregables por prioridad

- P0 inmediato: F0, F1, F3.
- P1 siguiente: F2, F4.
- P0 cierre MVP: F5, F6.
- P2 post-MVP: competitivo, implosion, monetizacion.

## 7. Definicion de avance real

Una fase cuenta como completada solo si:

- Gate PASS,
- documentos actualizados,
- decisiones trazadas,
- riesgos A0 cerrados.
