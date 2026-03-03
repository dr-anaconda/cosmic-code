# Start Build Now Pack v1.6 — Activación de Construcción

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.6  
**Estado:** Activo  
**Documentos relacionados:**
- `_docs/docs/CÓDIGO CÓSMICO_ Execution Backlog v1.4.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Sprint 0 Active Pack v1.5.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Sprint 0 Board v1.5.md`

---

## 1. Propósito

Pasar de planificación documental a ejecución inmediata con un paquete operativo que incluye:

1. orden de trabajo para la primera semana,
2. estructura de issues listas para abrir,
3. definición de handoff diario,
4. reglas de cierre para tareas P0.

---

## 2. Activación (T-0)

Checklist de arranque en el día 0:

- [ ] Verificar que `develop` esté limpio y actualizado.
- [ ] Crear tablero Sprint 0 en herramienta de tracking.
- [ ] Crear issues P0 desde plantillas v1.6.
- [ ] Asignar Responsible + ETA para cada P0.
- [ ] Confirmar daily técnico y horario de triage de bloqueos.

---

## 3. Paquete mínimo de issues a abrir

| Grupo | Cantidad objetivo | Prioridad |
|---|---:|---|
| Foundation (M0) | 6-8 | P0 |
| Core Data (M1) | 6-10 | P0/P1 |
| Riesgo/QA transversal | 3-5 | P0/P1 |

Regla: ninguna tarea XL entra como issue única; debe dividirse.

---

## 4. Reglas de ejecución diaria

1. Daily de 15 minutos enfocada en bloqueos y ETA.
2. Actualización obligatoria de estado de issue al final del día.
3. Si una P0 queda `blocked` > 24h, escalado inmediato.
4. No abrir trabajo P2/P3 si hay P0 abiertas bloqueadas.

---

## 5. Flujo de handoff

Cada handoff técnico debe incluir:

- contexto,
- estado actual,
- siguiente paso concreto,
- riesgo detectado,
- definición de done parcial.

Formato mínimo:

```text
Contexto:
Estado:
Siguiente paso:
Riesgo:
DoD parcial:
```

---

## 6. Criterios de salida de Semana 1

- [ ] 80% de issues P0 en `done` o `in_review`.
- [ ] Pipeline CI estable sin fallos recurrentes.
- [ ] M1 P0 en estado `ready` al menos al 80%.
- [ ] Riesgos críticos con mitigación activa y dueños asignados.

---

## 7. Anti-patrones a evitar

- Paralelizar demasiadas P0 sin dependencias cerradas.
- Hacer merge de PRs sin actualización documental mínima.
- Reabrir tareas por criterios de aceptación ambiguos.
- Convertir blockers técnicos en "pendientes indefinidos".

---

## 8. Métricas de control de arranque

| Métrica | Objetivo |
|---|---|
| Issue readiness score | >= 4/5 |
| P0 blocked >24h | 0 |
| PR lead time (P0) | < 48h |
| Reapertura de issues P0 | < 10% |

---

## 9. Criterios de aceptación

- [ ] Activación T-0 documentada
- [ ] Paquete de issues definido
- [ ] Flujo de handoff definido
- [ ] Criterios de salida de semana 1 definidos
- [ ] Métricas de control de arranque definidas

---

## 10. Declaración Final

Start Build Now Pack v1.6 convierte el plan en operación inmediata. Si este paquete no se sigue, la ejecución de Sprint 0 pierde foco y previsibilidad.
