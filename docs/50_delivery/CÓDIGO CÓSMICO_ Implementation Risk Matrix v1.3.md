# Implementation Risk Matrix v1.3 — Riesgos de Ejecución

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.3  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/50_delivery/CÓDIGO CÓSMICO_ Implementation Readiness Pack v1.3.md`
- `docs/50_delivery/CÓDIGO CÓSMICO_ Technical Milestones Plan v1.3.md`

---

## 1. Propósito

Priorizar riesgos de implementación con enfoque operativo: probabilidad, impacto, score, señales tempranas, mitigación y plan de contingencia.

---

## 2. Escala de evaluación

| Valor | Probabilidad | Impacto |
|---|---|---|
| 1 | Baja | Menor |
| 2 | Media-baja | Moderado |
| 3 | Media | Significativo |
| 4 | Alta | Alto |
| 5 | Muy alta | Crítico |

`risk_score = probabilidad * impacto`

---

## 3. Matriz priorizada

| ID | Riesgo | P | I | Score | Owner |
|---|---|---:|---:|---:|---|
| R-01 | Complejidad del motor de simulación supera capacidad inicial | 4 | 5 | 20 | Tech Lead |
| R-02 | Inconsistencia entre balance y comportamiento real | 4 | 4 | 16 | Game Design Lead |
| R-03 | Deriva de contratos API durante iteraciones | 3 | 4 | 12 | Backend Lead |
| R-04 | Deuda técnica por entregar hitos sin DoD | 3 | 5 | 15 | Tech Lead |
| R-05 | Sobrecarga de contenido sin pipeline operativo | 3 | 4 | 12 | Content Lead |
| R-06 | Riesgos de fairness en competitivo/economía | 3 | 5 | 15 | Product + Data |
| R-07 | Latencia alta en torneos simulados | 3 | 4 | 12 | Backend Lead |
| R-08 | Falta de capacidad QA para ritmo de cambios | 4 | 3 | 12 | QA Lead |
| R-09 | Localización tardía rompe UI mobile | 3 | 3 | 9 | UX Lead |
| R-10 | Dependencia de servicios externos inestable | 2 | 4 | 8 | DevOps |

---

## 4. Riesgos críticos (score >= 15)

### R-01 Simulación compleja

- **Señal temprana:** spike técnico > 2 semanas sin estabilizar tick alfa.
- **Mitigación:** definir versión simplificada del motor para M2.
- **Contingencia:** recortar dimensiones simultáneas de simulación en primera release.

### R-04 Deuda por salida prematura

- **Señal temprana:** aumento sostenido de hotfixes por hito.
- **Mitigación:** gate DoD obligatorio por milestone.
- **Contingencia:** sprint de estabilización obligatorio antes de M5.

### R-06 Fairness competitivo/economía

- **Señal temprana:** reportes de pay-to-win o sesgo en ranking.
- **Mitigación:** auditoría cruzada Tournament/Monetization por release.
- **Contingencia:** congelar cambios económicos hasta cerrar hallazgos.

---

## 5. Registro de monitoreo semanal

Formato mínimo por riesgo activo:

- estado (`green`, `amber`, `red`),
- tendencia (sube/baja/estable),
- acción en curso,
- fecha de próxima revisión.

---

## 6. Umbrales de escalado

- Score 1-8: seguimiento normal.
- Score 9-14: seguimiento reforzado.
- Score 15-25: escalado obligatorio en comité técnico semanal.

---

## 7. Riesgo residual aceptable

Solo se acepta riesgo residual alto cuando:

1. existe plan de contingencia probado,
2. impacto de no avanzar es mayor,
3. Product y Tech aprueban explícitamente.

---

## 8. Checklist de aceptación

- [ ] Top riesgos priorizados
- [ ] Owner definido por riesgo
- [ ] Mitigación y contingencia por riesgo crítico
- [ ] Umbrales de escalado definidos
- [ ] Mecanismo de monitoreo semanal definido

---

## 9. Declaración Final

Esta matriz convierte incertidumbre en trabajo gestionable. La disciplina de revisión semanal es tan importante como la mitigación técnica inicial.
