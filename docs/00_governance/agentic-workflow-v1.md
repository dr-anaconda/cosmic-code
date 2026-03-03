# Agentic Workflow v1 (IDE + LLM)

Proyecto: Codigo Cosmico - Evolucion Profunda
Version: 1.0
Estado: Vigente

Regla global aplicable: [reference-rules-v1.md](./reference-rules-v1.md)

## 1. Objetivo

Optimizar ejecucion documental y tecnica para flujo agentico asistido por LLM en IDE, con trazabilidad y control de calidad.

## 2. Principios

- Una tarea por objetivo verificable.
- Contexto minimo suficiente, no contexto infinito.
- Archivos de verdad explicitos por cada tarea.
- Aceptacion definida antes de escribir codigo.
- Todo cambio relevante deja evidencia en docs.

## 3. Paquete estandar de tarea (task packet)

Cada tarea para agente debe incluir:

1. Objetivo concreto.
2. Alcance (incluye/no incluye).
3. Archivos SoT que mandan.
4. Cambios esperados por archivo.
5. Criterio de aceptacion medible.
6. Comando(s) de verificacion.
7. Riesgo y rollback.

## 4. Plantilla breve de prompt para IDE con LLM

```text
Objetivo:
<resultado esperado>

Contexto minimo:
<3-6 bullets max>

Source of Truth:
- <ruta 1>
- <ruta 2>

Instrucciones de cambio:
- <archivo>: <cambio>

Criterios de aceptacion:
- [ ] <criterio 1>
- [ ] <criterio 2>

Verificacion:
- <comando 1>
- <comando 2>

No hacer:
- <restriccion 1>
- <restriccion 2>
```

## 5. Flujo de ejecucion recomendado

1. Abrir tarea desde backlog P0/P1/P2.
2. Resolver dudas A0/A1 antes de editar.
3. Ejecutar cambios en lote pequeno.
4. Verificar criterios de aceptacion.
5. Actualizar docs de estado y decision log.
6. Cerrar tarea con evidencia.

## 6. Definicion de done para tareas con agente

Una tarea se cierra si:

- cumple criterios de aceptacion,
- no rompe SoT,
- referencias y docs actualizadas,
- verificacion ejecutada,
- decision registrada si cambio estructural.

## 7. Anti-patrones a evitar

- Prompts vagos tipo "hazlo mejor".
- Cambios en muchos archivos sin criterio.
- Mezclar refactor + feature + docs en una sola tarea.
- Cerrar tarea sin verificacion.
- Avanzar con dudas A0 abiertas.

## 8. Metrica de salud del flujo agentico

- % tareas con criterios de aceptacion explicitos.
- % tareas cerradas sin retrabajo en 48h.
- % cambios con SoT referenciado.
- tiempo medio de cierre por prioridad.
