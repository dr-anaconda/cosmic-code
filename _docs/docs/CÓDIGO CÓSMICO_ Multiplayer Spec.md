# Multiplayer Spec — Arquitectura de Interacción Asíncrona

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/docs/CÓDIGO CÓSMICO_ Core Loops.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Tournament System.md`
- `_docs/docs/CÓDIGO CÓSMICO_ ADD.md`

---

## 1. Propósito

Definir el sistema multijugador asíncrono del juego: contratos de interacción, reglas de integridad, resolución de acciones diferidas y mecánicas sociales conectadas al progreso.

El detalle competitivo semanal vive en `_docs/docs/CÓDIGO CÓSMICO_ Tournament System.md`.

---

## 2. Principios del Multijugador

1. **Asíncrono por diseño:** no exige coincidencia horaria.
2. **Legible para el jugador:** cada resultado explica causalidad.
3. **Justicia competitiva:** sin ventaja de pago en resultados.
4. **Baja fricción social:** interacción opt-in y controlable.
5. **Escalable:** preparado para miles de resoluciones por hora.

---

## 3. Dominios Funcionales

| Dominio | Objetivo |
|---|---|
| Banco Genético | Compartir y reutilizar especies |
| Torneos | Competición semanal por ligas |
| Intercambio Civilizatorio | Comercio y pactos asíncronos |
| Sondas y Encuentros | Eventos entre universos |
| Perfil y Reputación | Identidad y confianza social |

---

## 4. Banco Genético Global

### 4.1 Flujo básico

1. Jugador publica especie elegible.
2. Sistema genera snapshot firmada.
3. Otros jugadores pueden importar (con límites).
4. Se registran descargas, uso y valoración.

### 4.2 Reglas de elegibilidad

- Especie viva o históricamente válida.
- Sin flags de exploit en genoma.
- Metadata completa (tags, rol, entorno recomendado).

### 4.3 Límites operativos

| Parámetro | Límite base |
|---|---:|
| Publicaciones por día | 5 |
| Descargas por día | 20 |
| Revisiones por especie | 1 por usuario |

---

## 5. Intercambio Civilizatorio

### 5.1 Modelo

Interacciones tipo contrato diferido entre civilizaciones de jugadores:

- intercambio de recursos,
- transferencia de conocimiento,
- acuerdos de no agresión,
- pactos temporales.

### 5.2 Contrato asíncrono

```json
{
  "contract_id": "C-1092",
  "issuer": "u1",
  "receiver": "u2",
  "type": "resource_trade",
  "offer": {"lab_credits": 120},
  "request": {"knowledge_points": 40},
  "ttl_hours": 48,
  "status": "pending"
}
```

### 5.3 Reglas

- Tiempo de vida máximo por contrato: 72h.
- Contratos expirados no penalizan MMR.
- Trazabilidad completa de emisión y aceptación.

---

## 6. Sondas y Encuentros entre Universos

### 6.1 Objetivo

Crear eventos de interacción emergente fuera del torneo semanal:

- detección de señales,
- intercambio cultural,
- conflictos menores,
- oportunidades de cooperación.

### 6.2 Resolución

Las sondas se resuelven en lotes por ventana temporal (ej. cada 2h), con resultado narrativo + efecto sistémico.

### 6.3 Tipos de resultado

| Tipo | Efecto principal |
|---|---|
| Cooperativo | bonus de conocimiento |
| Neutro | información de entorno |
| Hostil | tensión y coste de recursos |
| Anómalo | evento raro desbloqueable |

---

## 7. Matchmaking Asíncrono General

Aunque torneos tienen reglas propias, el sistema multijugador general usa:

- cola por dominio,
- prioridad por afinidad de nivel,
- protección anti repetición,
- ventana de espera adaptativa.

Regla de experiencia:
- si una acción asíncrona tarda más del objetivo, mostrar estado intermedio y ETA.

---

## 8. Perfil, Reputación y Señales Sociales

### 8.1 Perfil público

Incluye:

- insignias,
- histórico de temporadas,
- especies destacadas,
- reputación comunitaria.

### 8.2 Reputación

`reputation_score` se ajusta por:

- cumplimiento de contratos,
- reportes válidos,
- comportamiento tóxico,
- calidad de contribución al banco genético.

No afecta MMR de torneo; sí afecta prioridad social y visibilidad.

---

## 9. Integridad y Anti-exploit

### 9.1 Controles

- Firmado de snapshots competitivos.
- Detección de multi-cuenta vinculada.
- Detección de ciclos de intercambio anómalos.
- Rate limits por acción sensible.

### 9.2 Sanciones

| Nivel | Acción |
|---|---|
| L1 | Advertencia |
| L2 | Restricción temporal social |
| L3 | Bloqueo competitivo temporal |
| L4 | Suspensión prolongada |

### 9.3 Auditoría

Cada interacción sensible guarda:

- actor,
- timestamp,
- payload hash,
- resultado,
- versión de reglas.

---

## 10. API y Contratos de Datos (alto nivel)

| Endpoint | Método | Uso |
|---|---|---|
| `/multiplayer/bank/publish` | POST | Publicar especie |
| `/multiplayer/bank/import` | POST | Importar especie |
| `/multiplayer/contracts/create` | POST | Crear contrato |
| `/multiplayer/contracts/respond` | POST | Aceptar/rechazar |
| `/multiplayer/probe/launch` | POST | Enviar sonda |
| `/multiplayer/profile/{id}` | GET | Ver perfil público |

Eventos asíncronos:

- `contract_resolved`
- `probe_result_ready`
- `bank_species_flagged`

---

## 11. UX de Interacción Social

Pantallas mínimas:

1. Hub multijugador
2. Banco genético
3. Contratos activos
4. Centro de sondas
5. Perfil y reputación

Reglas UX:

- Explicar siempre por qué una interacción falló.
- Mostrar estado de cola en acciones diferidas.
- Permitir optar por menor exposición social (modo privado parcial).

---

## 12. Métricas Clave

| Métrica | Objetivo |
|---|---|
| Uso semanal de banco genético | > 15% de DAU |
| Tasa de contratos aceptados | > 35% |
| Tiempo medio de resolución asíncrona | < 10 min (p95) |
| Reportes válidos de abuso | < 1.5% |
| Repetición de interacción con mismo actor | < 20% |

---

## 13. Riesgos y Mitigaciones

| Riesgo | Mitigación |
|---|---|
| Fricción social alta | UX simplificada y defaults seguros |
| Abuso de intercambio | límites y scoring de confianza |
| Saturación de eventos asíncronos | colas priorizadas y notificación resumida |
| Percepción de injusticia | trazabilidad visible y soporte de apelación |

---

## 14. Criterios de Aceptación

- [ ] Banco genético definido con límites
- [ ] Contratos asíncronos definidos
- [ ] Sondas y encuentros modelados
- [ ] Integridad anti-exploit documentada
- [ ] Métricas y riesgos definidos
- [ ] Coherencia con Tournament, Balance y ADD

---

## 15. Declaración Final

El multijugador de Código Cósmico debe potenciar la narrativa sistémica y la competencia justa sin exigir sincronía. La experiencia social debe ser opcional, clara y segura.
