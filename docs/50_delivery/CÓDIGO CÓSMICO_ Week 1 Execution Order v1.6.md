# Week 1 Execution Order v1.6 — Orden de Trabajo Operativo

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.6  
**Estado:** Vigente

---

## 1. Objetivo de semana 1

Cerrar base técnica de M0 y dejar M1 desbloqueado para ejecución continua.

---

## 2. Secuencia recomendada por día

### Día 1

- Inicializar tablero y abrir issues P0.
- Configurar estructura de módulos.
- Configurar lint/formato y hooks.

### Día 2

- Pipeline CI smoke.
- Verificación de setup local en 2+ entornos.
- Ajustes de scripts de arranque.

### Día 3

- Definir contratos API mínimos v1.
- Validación inicial de schemas de request/response.

### Día 4

- Preparar migraciones base de `users`, `universes`, `planets`.
- Tests de integridad de migración.

### Día 5

- Hardening de bloqueos detectados.
- Revisión semanal de riesgos.
- Cierre de sprint-week review con estado de P0.

---

## 3. Orden de prioridad (si hay conflicto)

1. desbloqueo de dependencia crítica,
2. estabilización de pipeline,
3. contratos de datos/API,
4. mejoras no bloqueantes.

---

## 4. Criterios diarios de cierre

- [ ] Estado de issues actualizado.
- [ ] PRs críticas revisadas o con owner de revisión.
- [ ] Bloqueos con ETA explícita.
- [ ] Nota de handoff publicada.

---

## 5. Señales de alerta temprana

| Señal | Acción inmediata |
|---|---|
| CI fallando > 4h | congelar merges no críticos |
| >2 P0 bloqueadas | triage técnico extraordinario |
| Reaperturas en cadena | revisar criterios de aceptación |

---

## 6. Declaración Final

El valor de la primera semana está en construir una base estable, no en maximizar volumen de tareas. Secuencia y disciplina importan más que velocidad aparente.
