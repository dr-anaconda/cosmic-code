# Event & Content Bible — Taxonomía y Pipeline de Contenido

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.1  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/docs/CÓDIGO CÓSMICO_ GDD-lite.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Core Loops.md`
- `_docs/docs/CÓDIGO CÓSMICO_ UI_UX.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Localization Spec.md`
- `_docs/docs/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`

---

## 1. Propósito

Este documento define cómo se diseña, clasifica, produce y valida el contenido dinámico del juego:

- Eventos sistémicos
- Eventos narrativos
- Alertas del jugador
- Notificaciones sociales

No define reglas numéricas de balance ni fórmulas de simulación. Esas viven en `_docs/docs/CÓDIGO CÓSMICO_ System Balance Sheet.md`.

---

## 2. Principios de Contenido

1. **Explicar causalidad:** cada evento debe ayudar a responder "qué pasó" y "por qué pasó".
2. **Evitar ruido:** no saturar al jugador con mensajes redundantes.
3. **Priorizar decisiones:** los eventos relevantes deben proponer acción concreta.
4. **Escalar con progreso:** early-game claro y guiado; late-game más complejo y emergente.
5. **Consistencia tonal:** voz cósmica, observacional y elegante; sin humor fuera de lugar.

---

## 3. Taxonomía de Eventos

| Familia | Código | Propósito | Frecuencia |
|---|---|---|---|
| Evolutivo | EVO | Señalar hitos biológicos | Media |
| Ecológico | ECO | Mostrar tensión/colapso ambiental | Media-Alta |
| Civilizatorio | CIV | Informar progreso social/tecnológico | Media |
| Cósmico | COS | Eventos del mapa estelar o singularidades | Baja |
| Jugador | PLY | Resultado directo de acciones del jugador | Alta |
| Competitivo | PVP | Torneos, rankings, banco genético | Baja-Media |
| Sistema | SYS | Mensajes técnicos/operativos de sesión | Baja |

---

## 4. Severidad y Respuesta Esperada

| Severidad | Etiqueta UI | Impacto | Acción sugerida |
|---|---|---|---|
| S1 | Informativo | Bajo | Ninguna o revisión rápida |
| S2 | Relevante | Medio-bajo | Ajuste opcional |
| S3 | Tensión | Medio | Decisión recomendada |
| S4 | Crítico | Alto | Intervención casi obligatoria |
| S5 | Catastrófico | Muy alto | Plan de contención inmediato |

Regla operativa:
- Nunca mostrar más de 1 evento S5 por sesión.
- Si hay S4/S5, deben ir arriba del feed.

---

## 5. Estructura Canónica de un Evento

```json
{
  "event_id": "ECO-0421",
  "family": "ECO",
  "severity": 4,
  "title": "Colapso de cadena trófica",
  "summary": "La especie depredadora dominante perdió su presa base.",
  "cause": "Biodiversidad < 20 durante 3 ticks",
  "effects_preview": ["-estabilidad", "+riesgo ecológico"],
  "choices": [
    {"key": "introducir_presa", "coste": "medio", "riesgo": "medio"},
    {"key": "regular_dep", "coste": "alto", "riesgo": "bajo"},
    {"key": "observar", "coste": "bajo", "riesgo": "alto"}
  ],
  "cooldown_ticks": 5,
  "tags": ["ecosistema", "depredador", "equilibrio"]
}
```

Campos mínimos obligatorios:
- `event_id`, `family`, `severity`, `title`, `summary`, `cause`, `choices`.

---

## 6. Plantillas Narrativas

Cada evento se redacta con 3 capas:

1. **Titular** (1 línea): impacto inmediato.
2. **Explicación causal** (1-2 líneas): contexto del sistema.
3. **Opciones** (2-4): decisiones con trade-off visible.

Ejemplo corto:

- **Titular:** "Mutación de plasticidad neuronal detectada"
- **Causa:** "Radiación alta y presión depredadora sostenida"
- **Opciones:**
  - Estabilizar (coste alto, reduce riesgo)
  - Explotar (coste bajo, sube riesgo)
  - Observar (sin coste, resultado incierto)

---

## 7. Catálogo Inicial de Contenido (MVP+)

### 7.1 Distribución por Familia

| Familia | Cantidad mínima |
|---|---:|
| EVO | 40 |
| ECO | 45 |
| CIV | 30 |
| COS | 20 |
| PLY | 35 |
| PVP | 20 |
| SYS | 10 |
| **Total** | **200** |

### 7.2 Reglas de Cobertura

- Cada nivel evolutivo (1-9) debe tener al menos 8 eventos propios.
- Cada dimensión del juego debe tener al menos 20 eventos asociados.
- Debe existir una cadena mínima de 3 eventos por "colapso" relevante.

---

## 8. Orquestación y Prioridad

Orden de render en sesión:

1. Eventos S5/S4 activos
2. Eventos con decisión pendiente
3. Hitos evolutivos recientes
4. Mensajes informativos

Reglas anti-spam:

- Límite de 6 eventos visibles por entrada de sesión.
- Agrupar eventos repetitivos en 1 card resumida.
- Aplicar cooldown por familia (por planeta y por usuario).

---

## 9. Relación con Loops de Juego

| Loop | Tipo de contenido dominante |
|---|---|
| L1 Inmediato | PLY + EVO |
| L2 Sesión | ECO + CIV + PLY |
| L3 Progresión | EVO + ECO + CIV |
| L4 Meta | COS + SYS + resumen de universo |
| L5 Social | PVP + CIV |

Esto evita duplicar la definición de loops, ya detallada en `_docs/docs/CÓDIGO CÓSMICO_ Core Loops.md`.

---

## 10. Pipeline Editorial y Operativo (v1.1)

1. **Diseño sistémico:** definir trigger, efectos y ámbito.
2. **Redacción narrativa:** titular, resumen, causa, opciones.
3. **Validación UX:** claridad, longitud, prioridad.
4. **Validación de balance:** impacto, frecuencia, cooldown.
5. **Etiquetado técnico:** familia, severidad, tags, versión.
6. **Localización:** claves i18n y traducción validada.
7. **QA editorial:** checklist y score de calidad.
8. **Publicación:** lote semanal o release de temporada.

### 10.1 Estados de contenido

| Estado | Descripción |
|---|---|
| Draft | Redacción inicial |
| Ready for QA | Listo para revisión editorial |
| Ready for Build | Validado para integración |
| Live | Publicado en producción |
| Deprecated | Retirado del pool activo |

### 10.2 Convención de versión

`major.minor.patch`

- `major`: cambio estructural en familia o formato.
- `minor`: nuevos eventos o cadenas.
- `patch`: corrección textual o ajuste de prioridad.

---

## 11. Operación de Temporadas

### 11.1 Calendario

| Día | Acción |
|---|---|
| Lunes | Activación de lote semanal |
| Martes | Monitoreo de métricas y ruido |
| Miércoles | Ajustes menores de priorización |
| Jueves | Backlog de nuevos eventos |
| Viernes | Freeze de textos para siguiente release |

### 11.2 Runbook de incidentes

Si un evento rompe UX o balance:

1. Cambiar estado a `deprecated`.
2. Activar fallback de familia equivalente.
3. Registrar incidente en bitácora editorial.
4. Publicar patch de texto o trigger.

---

## 12. Calidad de Escritura

Checklist por evento:

- [ ] El título comunica impacto
- [ ] La causa es entendible
- [ ] Hay 2-4 opciones con trade-off
- [ ] No hay opción claramente "correcta" siempre
- [ ] El tono es consistente con el universo
- [ ] La longitud es mobile-friendly
- [ ] Clave de localización definida
- [ ] Placeholders validados

Reglas de estilo:

- Frases cortas y directas
- Evitar tecnicismo innecesario
- Evitar tono moralizante
- No usar humor que rompa el tono cósmico
- Mantener consistencia terminológica con glosario

---

## 13. Integración con Localización

Toda pieza de contenido debe declarar:

- `key_title`
- `key_summary`
- `key_cause`
- `key_choices[]`

Reglas:

- No se publica contenido sin `es-ES` y `en-US` completos.
- No se permite hardcode de textos en runtime.
- Cambios terminológicos deben actualizar glosario maestro.

Referencia: `_docs/docs/CÓDIGO CÓSMICO_ Localization Spec.md`.

---

## 14. Métricas de Contenido

| Métrica | Objetivo |
|---|---|
| Ratio de resolución de eventos | > 85% |
| Tiempo de lectura por evento | < 12s |
| Eventos ignorados por sesión | < 20% |
| Repetición percibida (encuesta) | < 15% |
| Eventos con error de clave i18n | 0 |
| Incidentes editoriales por release | < 3 |

Si una familia supera 25% de repetición percibida, se prioriza expansión de su pool en el siguiente sprint.

---

## 15. Riesgos y Mitigación

| Riesgo | Mitigación |
|---|---|
| Repetición temprana | Pool inicial amplio y rotación por tags |
| Sobrecarga cognitiva | Priorización por severidad y agrupación |
| Eventos "sin sentido" | Validación de causalidad obligatoria |
| Tono inconsistente | Revisión editorial centralizada |
| Deriva terminológica entre idiomas | Glosario y QA de localización |

---

## 16. Checklist de Validación

- [ ] Taxonomía de eventos definida
- [ ] Severidades y prioridades definidas
- [ ] Estructura canónica de evento establecida
- [ ] Catálogo mínimo inicial definido
- [ ] Pipeline editorial y operativo documentado
- [ ] Integración de localización definida
- [ ] Métricas de contenido definidas
- [ ] Sin redundancia con loops, balance y multiplayer

---

## 17. Declaración Final

El contenido de eventos es la interfaz narrativa del sistema. En v1.1, además de diseñar eventos, el equipo opera un ciclo editorial continuo con QA y localización como parte obligatoria del release.
