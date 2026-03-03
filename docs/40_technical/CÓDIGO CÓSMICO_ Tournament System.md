# Tournament System — Ligas, Simulación y Recompensas

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/10_product/CÓDIGO CÓSMICO_ Core Loops.md`
- `docs/40_technical/CÓDIGO CÓSMICO_ Multiplayer Spec.md`
- `docs/20_systems/CÓDIGO CÓSMICO_ System Balance Sheet.md`

---

## 1. Propósito

Definir el sistema competitivo asíncrono semanal del juego: formato de ligas, reglas de inscripción, simulación de enfrentamientos, cálculo de puntuación, recompensas y controles de integridad.

Este documento cubre el sistema de torneos. El detalle general del multijugador vive en `docs/40_technical/CÓDIGO CÓSMICO_ Multiplayer Spec.md`.

---

## 2. Objetivos del Sistema

1. Dar un objetivo semanal claro para jugadores casuales y hardcore.
2. Premiar optimización sistémica, no gasto monetario.
3. Mantener una curva de dificultad progresiva por ligas.
4. Convertir el resultado competitivo en progreso útil para el loop meta.

---

## 3. Modelo de Competición

### 3.1 Cadencia

| Item | Valor |
|---|---|
| Frecuencia | Semanal |
| Inicio | Lunes 00:00 UTC |
| Cierre de inscripción | Martes 12:00 UTC |
| Simulaciones | Martes a Domingo |
| Cierre y rewards | Domingo 23:59 UTC |

### 3.2 Formatos de torneo

| Formato | Descripción | Duración |
|---|---|---|
| `ecosystem_clash` | Enfrenta dos ecosistemas completos | 1 semana |
| `species_trial` | Rendimiento de especies específicas por entorno | 1 semana |
| `survival_arc` | Resistencia a condiciones extremas por rondas | 1 semana |

El formato activo se anuncia al abrir temporada y rota cada semana.

### 3.3 División por ligas

| Liga | MMR objetivo | Perfil |
|---|---:|---|
| Bronce | 0-999 | Entrada |
| Plata | 1000-1499 | Intermedio |
| Oro | 1500-1999 | Avanzado |
| Platino | 2000-2399 | Competitivo |
| Élite | 2400+ | Alto rendimiento |

---

## 4. Requisitos de Inscripción

### 4.1 Requisitos globales

- Cuenta activa con al menos 1 universo no implosionado en la semana.
- Nivel evolutivo mínimo de entrada definido por temporada.
- No tener sanción competitiva activa.

### 4.2 Requisitos por formato

| Formato | Requisito mínimo |
|---|---|
| `ecosystem_clash` | 1 ecosistema con 5-10 especies activas |
| `species_trial` | 3 especies inscritas |
| `survival_arc` | 1 especie + setup ambiental válido |

### 4.3 Coste de inscripción

- Coste base en tokens de entrada competitiva (no premium).
- Reembolso parcial en caso de abandono por problema del sistema.

---

## 5. Paquete Competitivo (Loadout)

Cada inscripción congela un paquete competitivo:

```json
{
  "season_id": "S-2026-W11",
  "format": "ecosystem_clash",
  "league": "plata",
  "ecosystem_snapshot": "hash",
  "species_ids": ["sp1", "sp2", "sp3", "sp4", "sp5"],
  "constraints": {
    "max_rare_genes": 2,
    "max_population_delta": 0.15
  }
}
```

Regla clave: una vez cerrado el periodo de inscripción, no se puede modificar el loadout de esa semana.

---

## 6. Motor de Simulación

### 6.1 Principios

1. Determinismo con semilla controlada por servidor.
2. Repetición por lotes para reducir ruido de RNG.
3. Trazabilidad de resultado por reporte de combate.

### 6.2 Pipeline

1. Validar paquete competitivo.
2. Emparejar por liga y MMR.
3. Ejecutar `N` simulaciones por enfrentamiento.
4. Agregar resultado ponderado.
5. Actualizar ranking y MMR.

### 6.3 Parámetros base

| Parámetro | Valor base | Nota |
|---|---:|---|
| Simulaciones por match | 100 | Ajustable por formato |
| Tiempo máximo por match | 5 min | En cola asíncrona |
| Timeout duro | 8 min | Reintento automático |
| Reintentos por fallo técnico | 2 | Luego invalidación controlada |

---

## 7. Emparejamiento

### 7.1 Reglas de pairing

- Prioridad 1: misma liga.
- Prioridad 2: diferencia de MMR menor a umbral dinámico.
- Prioridad 3: evitar repetición de rival inmediata.

### 7.2 Ventana de MMR

| Minuto en cola | Ventana MMR |
|---:|---:|
| 0-2 | +-75 |
| 3-5 | +-125 |
| 6-10 | +-200 |
| >10 | +-300 |

### 7.3 Protección inicial

- Primeras 10 partidas semanales: protección de descenso brusco.
- Jugadores nuevos: cola de calibración de 5 partidas.

---

## 8. Puntuación y MMR

### 8.1 Puntos de temporada

`season_points = match_result + objective_bonus + consistency_bonus - penalties`

Componentes:

- `match_result`: victoria, derrota o empate.
- `objective_bonus`: metas del formato semanal.
- `consistency_bonus`: racha positiva controlada.
- `penalties`: abandono, desconexión recurrente, comportamiento anómalo.

### 8.2 MMR

Modelo Elo adaptado:

`new_mmr = old_mmr + K * (actual - expected)`

| Liga | K factor |
|---|---:|
| Bronce | 40 |
| Plata | 32 |
| Oro | 24 |
| Platino | 20 |
| Élite | 16 |

### 8.3 Desempates

1. Mayor `season_points`
2. Mayor win rate
3. Mejor rendimiento contra top 25%
4. Menor ratio de penalizaciones

---

## 9. Recompensas

### 9.1 Tipos

- Tokens cósmicos
- Cosméticos de temporada
- Insignias competitivas
- Componentes de laboratorio (no pay-to-win)

### 9.2 Distribución por percentil

| Percentil final | Recompensa |
|---|---|
| Top 1% | Alto + insignia exclusiva |
| Top 10% | Alta |
| Top 30% | Media |
| Participación activa | Base |

Regla: nunca otorgar ventajas competitivas no alcanzables por juego normal.

---

## 10. Fair Play e Integridad

### 10.1 Controles automáticos

- Detección de patrones de boosting.
- Detección de cuentas espejo (smurfing).
- Validación de loadout y snapshots.
- Rate limit de inscripciones y acciones por ventana temporal.

### 10.2 Sanciones

| Nivel | Motivo | Acción |
|---|---|---|
| S1 | Incidencia leve | Advertencia |
| S2 | Reincidencia | Penalización de puntos |
| S3 | Explotación confirmada | Suspensión de temporada |
| S4 | Fraude sistemático | Bloqueo competitivo temporal |

### 10.3 Auditoría

Cada match conserva:
- semilla,
- versión de reglas,
- hash de loadout,
- log resumido de resultado.

---

## 11. UX Competitiva

Pantallas mínimas:

1. Lobby de temporada.
2. Estado de inscripción y loadout.
3. Ranking por liga.
4. Historial de matches.
5. Pantalla de recompensas.

Reglas UX:

- Mostrar siempre motivo de victoria/derrota.
- Mostrar delta de MMR por partido.
- No ocultar penalizaciones: deben ser explicables.

---

## 12. Métricas Operativas

| Métrica | Objetivo |
|---|---|
| Participación semanal | > 20% de DAU |
| Tiempo medio en cola | < 120s |
| Matches inválidos | < 1% |
| Reclamaciones por injusticia | < 3% de participantes |
| Repetición de rivales | < 15% |

---

## 13. Riesgos y Mitigaciones

| Riesgo | Mitigación |
|---|---|
| Metajuego dominante único | Rotación de formatos y objetivos |
| Colas largas en ligas altas | Ventana MMR dinámica y cross-pool controlado |
| Percepción de RNG injusto | Simulación por lotes y reporte de causalidad |
| Incentivo a smurfing | Calibración y detección de cuentas espejo |

---

## 14. Criterios de Aceptación

- [ ] Ligas y MMR definidos
- [ ] Pipeline de simulación definido
- [ ] Recompensas sin pay-to-win
- [ ] Reglas anti-exploit y sanciones definidas
- [ ] Métricas operativas incluidas
- [ ] Sin contradicciones con Multiplayer y Balance

---

## 15. Declaración Final

El sistema de torneos es el motor competitivo semanal del juego. Debe sentirse justo, comprensible y exigente, manteniendo siempre la identidad sistémica de Código Cósmico.
