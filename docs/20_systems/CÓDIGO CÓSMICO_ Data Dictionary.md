# Data Dictionary — Entidades y Campos

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/90_archive/init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md`
- `docs/10_product/CÓDIGO CÓSMICO_ GDD-lite.md`
- `docs/10_product/CÓDIGO CÓSMICO_ Core Loops.md`

---

## 1. Propósito

Este documento define las **entidades principales** del juego y sus **campos clave**. Es la "verdad única" sobre los datos: toda decisión de diseño relacionada con datos debe ser coherente con este documento.

**Principios:**
1. Cada campo tiene significado jugable, no solo técnico
2. Los rangos son explícitos
3. Se distingue entre datos persistentes y derivados
4. Si algo afecta decisiones futuras, se guarda

> **Nota:** Este es un documento resumido. Para un esquema completo, ver `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary Complete.md` (futuro).

---

## 2. Entidades Principales

```
┌─────────────────────────────────────────────────────────────┐
│                    MODELO DE DATOS                          │
├─────────────────────────────────────────────────────────────┤
│ users                                                      │
│   └─ universes (1:N)                                       │
│         ├─ planets (1:N)                                   │
│         │   ├─ species (1:N)                              │
│         │   │   ├─ genome                                 │
│         │   │   └─ neural_network                         │
│         │   ├─ ecosystem_state                            │
│         │   └─ events_log (1:N)                          │
│         ├─ player_progress                                │
│         └─ achievements (1:N)                              │
│                                                          │
│ global:                                                   │
│   ├─ genes_catalog                                        │
│   ├─ milestones_catalog                                   │
│   ├─ skills_tree                                         │
│   ├─ species_bank (multijugador)                          │
│   └─ tournaments (config)                                 │
└─────────────────────────────────────────────────────────────┘
```

---

## 3. Entidad: `users`

Jugador autenticado.

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador único | ✅ |
| username | string | 3-20 chars | Nombre de usuario | ✅ |
| email | string | email valido | Correo (único) | ✅ |
| created_at | datetime | - | Fecha de registro | ✅ |
| last_login | datetime | - | Última sesión | ✅ |
| settings | JSON | - | Preferencias | ✅ |

---

## 4. Entidad: `universes`

Un universo es una partida completa. Cada jugador puede tener varios.

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador | ✅ |
| user_id | FK | - | Dueño | ✅ |
| name | string | 1-30 chars | Nombre del universo | ✅ |
| day | int | ≥1 | Día actual del universo | ✅ |
| is_active | bool | - | Universo activo | ✅ |
| implosion_level | int | ≥0 | Nivel de implosión | ✅ |
| speed_bonus | float | ≥0 | Bonificador velocidad | ✅ |
| knowledge_points | int | ≥0 | Puntos de conocimiento | ✅ |
| discovered_genes | JSON | - | Genes raros conseguidos | ✅ |
| created_at | datetime | - | Inicio del universo | ✅ |
| imploded_at | datetime | nullable | Fecha de implosión | ✅ |

---

## 5. Entidad: `planets`

Planetas dentro de un universo. Un universo puede tener múltiples planetas.

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador | ✅ |
| universe_id | FK | - | Universo padre | ✅ |
| name | string | 1-25 chars | Nombre del planeta | ✅ |
| position_x | float | - | Posición en sistema | ✅ |
| position_y | float | - | Posición en sistema | ✅ |
| star_type | enum | O,B,A,F,G,K,M | Tipo de estrella | ✅ |
| orbit_distance | float | - | Distancia a estrella | ✅ |
| mass | float | - | Masa planetaria | ✅ |
| radius | float | - | Radio | ✅ |
| gravity | float | - | Gravedad superficie | ✅ |
| temperature | int | -200 a +500 | Temperatura media | ✅ |
| atmosphere | JSON | - | Composición atmosférica | ✅ |
| water_level | float | 0-1 | Nivel de agua | ✅ |
| radiation | int | 0-100 | Radiación superficie | ✅ |
| life_stage | enum | none, bacterial, eukaryotic, multicellular, nervous, intelligent, civilization, space | Etapa de vida actual | ✅ |
| life_level | int | 0-9 | Nivel de evolución (1-9) | ✅ |
| terraform_progress | JSON | - | Progreso terraformación | ✅ |
| is_terraformed | bool | - | Si está terraformado | ✅ |
| colonization_date | datetime | nullable | Fecha primera vida | ✅ |

### 5.1 Entidad: `ecosystem_state` (por planeta)

Estado ambiental de cada planeta.

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador | ✅ |
| planet_id | FK | - | Planeta | ✅ |
| biodiversity | int | 0-100 | Biodiversidad | ✅ |
| stability | int | 0-100 | Estabilidad | ✅ |
| pollution | int | 0-100 | Contaminación | ✅ |
| predators | int | 0-100 | Presión depredadores | ✅ |
| resource_abundance | int | 0-100 | Abundancia recursos | ✅ |
| last_tick_at | datetime | - | Último tick | ✅ |

---

## 6. Entidad: `species`

Especies en un planeta. Cada planeta puede tener múltiples especies.

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador | ✅ |
| planet_id | FK | - | Planeta | ✅ |
| name | string | 1-30 chars | Nombre de especie | ✅ |
| parent_species_id | FK | nullable | Especie progenitora | ✅ |
| generation | int | ≥1 | Generación actual | ✅ |
| population | int | ≥0 | Población actual | ✅ |
| genome | JSON | - | Genoma completo | ✅ |
| neural_network | JSON | - | Red neuronal (nivel 5+) | ✅ |
| traits | JSON | - | Rasgos activos | ✅ |
| mutation_rate | float | 0-1 | Tasa de mutación | ✅ |
| metabolic_type | enum | autotroph, heterotroph, mixotroph | Tipo metabólico | ✅ |
| reproduction_type | enum | asexual, sexual, both | Reproducción | ✅ |
| mobility | float | 0-1 | Capacidad movimiento | ✅ |
| aggression | float | 0-1 | Agresividad | ✅ |
| intelligence | float | 0-1 | Inteligencia (nivel 5+) | ✅ |
| social_structure | enum | solitary, pack, colony, civilization | Estructura social | ✅ |
| created_at | datetime | - | Fecha creación | ✅ |
| extinct_at | datetime | nullable | Fecha extinción | ✅ |
| status | enum | alive, extinct, dominant, recessive | Estado | ✅ |

### 6.1 Sub-entidad: `genome`

Genoma de una especie (estructura simplificada).

| Campo | Tipo | Descripción |
|-------|------|-------------|
| metabolism_genes | JSON | Genes de metabolismo |
| resistance_genes | JSON | Genes de resistencia |
| reproduction_genes | JSON | Genes de reproducción |
| morphology_genes | JSON | Genes de morfología |
| behavior_genes | JSON | Genes de comportamiento |
| rare_genes | JSON | Genes raros posesionados |

### 6.2 Sub-entidad: `neural_network` (nivel 5+)

Red neuronal que controla comportamiento.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| inputs | JSON | Neuronas de entrada |
| hidden | JSON | Neuronas ocultas |
| outputs | JSON | Neuronas de salida |
| weights | JSON | Pesos de conexiones |

---

## 7. Entidad: `player_progress`

Progresión del jugador (se conserva entre implosiones).

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador | ✅ |
| user_id | FK | - | Usuario | ✅ |
| total_knowledge | int | ≥0 | Conocimiento total | ✅ |
| total_implosions | int | ≥0 | Total implosiones | ✅ |
| global_speed_bonus | float | ≥0 | Bonificador global | ✅ |
| rare_genes_discovered | JSON | - | Genes raros | ✅ |
| achievements | JSON | - | Logros obtenidos | ✅ |
| tokens_cosmicos | int | ≥0 | Tokens del juego | ✅ |

### 7.1 Sub-entidad: `skills_tree`

Árbol de habilidades del jugador.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| travel_skill | int | 0-3 |
| genetics_skill | int | 0-3 |
| war_skill | int | 0-3 |
| management_skill | int | 0-3 |
| cosmic_skill | int | 0-3 |

---

## 8. Entidad: `events_log`

Registro de eventos en un planeta/universo.

| Campo | Tipo | Rango | Descripción | Persistente |
|-------|------|-------|-------------|-------------|
| id | PK | - | Identificador | ✅ |
| universe_id | FK | - | Universo | ✅ |
| planet_id | FK | nullable | Planeta | ✅ |
| day | int | - | Día del evento | ✅ |
| type | enum | milestone, mutation, disaster, player_action, system | Tipo | ✅ |
| severity | int | 1-5 | Severidad | ✅ |
| title | string | - | Título | ✅ |
| description | text | - | Descripción | ✅ |
| data | JSON | - | Datos adicionales | ✅ |
| choices | JSON | - | Opciones (si aplica) | ✅ |
| chosen_choice | string | nullable | Elección del jugador | ✅ |
| effects | JSON | - | Efectos aplicados | ✅ |
| created_at | datetime | - | Creación | ✅ |

---

## 9. Entidad: `genes_catalog` (Global)

Catálogo de genes disponibles en el juego.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | PK | - |
| key | string | Identificador único |
| name | string | Nombre visible |
| description | text | Descripción |
| category | enum | metabolism, resistance, reproduction, morphology, behavior, rare |
| rarity | int | 1-5 |
| effects | JSON | Efectos en stats |
| unlock_condition | JSON | Condición de desbloqueo |
| tags | JSON | Tags para sinergias |

---

## 10. Entidad: `milestones_catalog` (Global)

Catálogo de hitos alcanzables.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | PK | - |
| key | string | Identificador único |
| name | string | Nombre |
| description | text | Descripción |
| required_level | int | Nivel requerido |
| required_species_count | int | Especies necesarias |
| knowledge_reward | int | Puntos de conocimiento |
| unlock_condition | JSON | Condición completa |

---

## 11. Entidad: `species_bank` (Multijugador)

Banco global de especies compartidas.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | PK | - |
| species_data | JSON | Datos de la especie |
| author_id | FK | Creador |
| downloads | int | Veces descargada |
| rating | float | Valoración |
| created_at | datetime | Fecha |

---

## 12. Entidad: `tournaments` (Global)

Configuración de torneos.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | PK | - |
| theme | string | Tema del torneo |
| start_date | datetime | Inicio |
| end_date | datetime | Fin |
| format | enum | ecosystem, species, survival |
| min_level | int | Nivel mínimo |
| rewards | JSON | Recompensas |

---

## 13. Campos Derivados (NO Persistir)

Los siguientes se calculan en tiempo real:

| Campo | Cómo se calcula |
|--------|-----------------|
| Tendencias (↑↓) | Comparación con tick anterior |
| Predicciones | Basado en stats actuales |
| Resúmenes UI | Agregación de datos |
| Complejidad cerebral | Evaluación de red neuronal |

**Regla:** Si afecta decisión futura → persistir. Si solo es display → calcular.

---

## 14. Rangos Comunes

| Variable | Rango | Notas |
|----------|-------|-------|
| Porcentajes | 0-100 | Nunca <0 o >100 |
| Poblaciones | ≥0 | Enteras |
| Días | ≥1 | Enteras |
| Versiones | X.Y | Semántica |
| Timestamps | ISO 8601 | UTC |

---

## 15. Validaciones Críticas

- Ningún stat global < 0 o > 100 (usar clamp)
- Población nunca negativa
- No tick doble mismo día
- species_id en genome debe existir
- FK siempre referenciar registro existente

---

## 16. Checklist de Validación

- [ ] Entidades principales definidas
- [ ] Campos tienen rangos explícitos
- [ ] Distinción persistido/derivado clara
- [ ] FK relaciones definidas
- [ ] Validaciones críticas documentadas
- [ ] Sin contradicciones con GDD
- [ ] Dependencias referenciadas

---

## 17. Declaración Final

**Este documento es la referencia para todos los datos del juego. Cualquier nuevo campo o entidad debe ser coherente con estas definiciones.**

---

**Documento creado bajo sistema CANON**  
**Siguiente: System Balance Sheet**
