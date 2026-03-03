# Execution Ownership Matrix v1.5 — Responsables por Flujo

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.5  
**Estado:** Activo

---

## 1. Propósito

Definir ownership operativo por flujo de trabajo para reducir zonas grises durante Sprint 0 y transición a M1.

---

## 2. Matriz de ownership

| Flujo | Responsible | Accountable | Consulted | Informed |
|---|---|---|---|---|
| Arquitectura y módulos base | Backend Lead | Tech Lead | Product | QA |
| CI/CD y calidad automatizada | DevOps | Tech Lead | Backend Lead | Product |
| Backlog y priorización | Product Owner | Product Owner | Tech Lead | Equipo |
| Riesgo y mitigaciones | QA Lead | Tech Lead | Product | Equipo |
| Consistencia documental | Editor técnico | Product Owner | Tech Lead | Equipo |

---

## 3. Reglas de responsabilidad

1. Cada tarea P0 debe tener Responsible y ETA.
2. Si Responsible cambia, actualizar tablero y log en el mismo día.
3. Accountable aprueba cierre de tarea P0 y P1.

---

## 4. Criterios de escalado

- Bloqueo técnico > 24h: Responsible -> Accountable.
- Bloqueo de alcance > 48h: Accountable -> Product + Tech sync.
- Bloqueo crítico de release: escalado inmediato a comité técnico.

---

## 5. Declaración Final

Sin ownership explícito no hay ejecución confiable. Esta matriz es obligatoria para operar Sprint 0 con trazabilidad y velocidad.