# Data Dictionary Complete — Esquema Detallado v1.0

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary.md`
- `docs/40_technical/CÓDIGO CÓSMICO_ ADD.md`
- `docs/20_systems/CÓDIGO CÓSMICO_ System Balance Sheet.md`

---

## 1. Propósito

Extender el diccionario resumido con definición técnica detallada por entidad:

- tipos exactos,
- restricciones,
- índices,
- claves externas,
- reglas de integridad,
- convenciones de migración.

Este documento es la referencia para modelado de base de datos y contratos de persistencia.

---

## 2. Convenciones Globales

### 2.1 Naming

- Tablas en `snake_case` y plural (`users`, `universes`).
- PK estándar: `id` (`uuid`).
- FK: `<tabla_singular>_id`.
- Timestamps: `created_at`, `updated_at` en UTC.

### 2.2 Tipos base

| Tipo lógico | Tipo SQL sugerido |
|---|---|
| ID global | `uuid` |
| Texto corto | `varchar(n)` |
| Texto largo | `text` |
| Entero | `integer` |
| Decimal | `numeric(p,s)` |
| Booleano | `boolean` |
| Fecha/hora | `timestamptz` |
| Estructura flexible | `jsonb` |

### 2.3 Reglas comunes

- Todos los porcentajes se almacenan en rango `0..100`.
- Todos los contadores son `>= 0`.
- Campos de estado usan `check` o enum controlado.

---

## 3. Dominios

1. Identidad y cuenta.
2. Universo y progreso.
3. Planetas y estado ecosistémico.
4. Especies, genoma y red neuronal.
5. Eventos y bitácora.
6. Competitivo y social.
7. Monetización y catálogo.

---

## 4. Identidad y Cuenta

### 4.1 `users`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| email | varchar(255) | no | unique |
| username | varchar(32) | no | unique |
| password_hash | varchar(255) | sí | login externo permitido |
| locale | varchar(10) | no | default `es-ES` |
| settings_json | jsonb | no | default `{}` |
| created_at | timestamptz | no | default now() |
| updated_at | timestamptz | no | default now() |

Índices:

- `uq_users_email`
- `uq_users_username`

### 4.2 `user_profiles`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| user_id | uuid | no | PK/FK users(id) |
| display_name | varchar(40) | no | |
| avatar_url | text | sí | |
| reputation_score | integer | no | check >= 0 |
| country_code | varchar(2) | sí | ISO-3166 |
| bio | varchar(280) | sí | |
| updated_at | timestamptz | no | default now() |

---

## 5. Universo y Progreso

### 5.1 `universes`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| user_id | uuid | no | FK users(id) |
| name | varchar(40) | no | |
| day | integer | no | check >= 1 |
| implosion_level | integer | no | check >= 0 |
| speed_bonus_pct | numeric(5,2) | no | check >= 0 |
| knowledge_points | integer | no | check >= 0 |
| is_active | boolean | no | default true |
| created_at | timestamptz | no | default now() |
| updated_at | timestamptz | no | default now() |

Índices:

- `idx_universes_user_id`
- `idx_universes_active`

### 5.2 `player_progress`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| user_id | uuid | no | PK/FK users(id) |
| total_implosions | integer | no | check >= 0 |
| total_knowledge | integer | no | check >= 0 |
| global_speed_bonus_pct | numeric(5,2) | no | check >= 0 |
| tokens_cosmicos | integer | no | check >= 0 |
| rare_genes_json | jsonb | no | default `[]` |
| achievements_json | jsonb | no | default `[]` |
| updated_at | timestamptz | no | default now() |

---

## 6. Planetas y Ecosistema

### 6.1 `planets`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| universe_id | uuid | no | FK universes(id) |
| name | varchar(32) | no | |
| star_type | varchar(8) | no | check in O,B,A,F,G,K,M |
| orbit_distance_au | numeric(8,3) | no | check > 0 |
| mass_earth | numeric(8,3) | no | check > 0 |
| gravity_g | numeric(5,2) | no | check > 0 |
| temperature_c | integer | no | check between -200 and 500 |
| atmosphere_json | jsonb | no | default `{}` |
| water_pct | numeric(5,2) | no | check between 0 and 100 |
| radiation | integer | no | check between 0 and 100 |
| life_level | integer | no | check between 0 and 9 |
| life_stage | varchar(24) | no | stage controlado |
| created_at | timestamptz | no | default now() |

Índices:

- `idx_planets_universe_id`
- `idx_planets_life_level`

### 6.2 `ecosystem_states`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| planet_id | uuid | no | PK/FK planets(id) |
| biodiversity | integer | no | check between 0 and 100 |
| stability | integer | no | check between 0 and 100 |
| pollution | integer | no | check between 0 and 100 |
| predators | integer | no | check between 0 and 100 |
| resource_abundance | integer | no | check between 0 and 100 |
| last_tick_at | timestamptz | no | |
| updated_at | timestamptz | no | default now() |

---

## 7. Especies, Genoma y Red

### 7.1 `species`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| planet_id | uuid | no | FK planets(id) |
| parent_species_id | uuid | sí | FK species(id) |
| name | varchar(40) | no | |
| generation | integer | no | check >= 1 |
| population | integer | no | check >= 0 |
| status | varchar(16) | no | alive/extinct/dominant/recessive |
| mutation_rate | numeric(6,4) | no | check between 0 and 1 |
| mobility | numeric(5,2) | no | check between 0 and 1 |
| aggression | numeric(5,2) | no | check between 0 and 1 |
| intelligence | numeric(5,2) | no | check between 0 and 1 |
| social_structure | varchar(24) | no | enumerado |
| created_at | timestamptz | no | default now() |
| extinct_at | timestamptz | sí | |

Índices:

- `idx_species_planet_id`
- `idx_species_status`

### 7.2 `species_genomes`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| species_id | uuid | no | PK/FK species(id) |
| metabolism_json | jsonb | no | default `{}` |
| resistance_json | jsonb | no | default `{}` |
| reproduction_json | jsonb | no | default `{}` |
| morphology_json | jsonb | no | default `{}` |
| behavior_json | jsonb | no | default `{}` |
| rare_genes_json | jsonb | no | default `[]` |
| checksum | varchar(64) | no | hash de integridad |
| updated_at | timestamptz | no | default now() |

### 7.3 `species_neural_networks`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| species_id | uuid | no | PK/FK species(id) |
| version | varchar(12) | no | |
| inputs_json | jsonb | no | |
| hidden_json | jsonb | no | |
| outputs_json | jsonb | no | |
| weights_json | jsonb | no | |
| checksum | varchar(64) | no | hash de integridad |
| updated_at | timestamptz | no | default now() |

---

## 8. Eventos y Bitácora

### 8.1 `events_log`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| universe_id | uuid | no | FK universes(id) |
| planet_id | uuid | sí | FK planets(id) |
| event_code | varchar(16) | no | familia + id |
| event_type | varchar(24) | no | milestone/mutation/etc. |
| severity | integer | no | check between 1 and 5 |
| title_key | varchar(128) | no | clave i18n |
| summary_key | varchar(128) | no | clave i18n |
| cause_key | varchar(128) | sí | clave i18n |
| payload_json | jsonb | no | default `{}` |
| created_at | timestamptz | no | default now() |

Índices:

- `idx_events_universe_created`
- `idx_events_type_severity`

### 8.2 `event_decisions`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| event_id | uuid | no | FK events_log(id) |
| user_id | uuid | no | FK users(id) |
| choice_key | varchar(64) | no | |
| effects_json | jsonb | no | default `{}` |
| decided_at | timestamptz | no | default now() |

---

## 9. Competitivo y Social

### 9.1 `seasons`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| season_code | varchar(20) | no | unique |
| starts_at | timestamptz | no | |
| ends_at | timestamptz | no | |
| format | varchar(24) | no | ecosystem_clash/species_trial/survival_arc |
| status | varchar(16) | no | scheduled/active/closed |

### 9.2 `tournament_entries`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| season_id | uuid | no | FK seasons(id) |
| user_id | uuid | no | FK users(id) |
| league | varchar(16) | no | bronce/plata/oro/platino/elite |
| mmr_before | integer | no | check >= 0 |
| loadout_hash | varchar(64) | no | |
| snapshot_json | jsonb | no | |
| created_at | timestamptz | no | default now() |

Índices:

- `idx_entries_season_league`
- `idx_entries_user`

### 9.3 `tournament_matches`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| season_id | uuid | no | FK seasons(id) |
| entry_a_id | uuid | no | FK tournament_entries(id) |
| entry_b_id | uuid | no | FK tournament_entries(id) |
| simulations | integer | no | default 100 |
| winner_entry_id | uuid | sí | FK tournament_entries(id) |
| result_json | jsonb | no | |
| created_at | timestamptz | no | default now() |

### 9.4 `genetic_bank_species`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| author_user_id | uuid | no | FK users(id) |
| species_id | uuid | sí | FK species(id) |
| snapshot_json | jsonb | no | |
| tags_json | jsonb | no | default `[]` |
| downloads_count | integer | no | check >= 0 |
| rating_avg | numeric(3,2) | no | check between 0 and 5 |
| status | varchar(16) | no | active/flagged/archived |
| created_at | timestamptz | no | default now() |

---

## 10. Monetización y Catálogo

### 10.1 `store_items`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| item_code | varchar(32) | no | unique |
| category | varchar(24) | no | cosmetic/convenience/boost/season |
| name_key | varchar(128) | no | clave i18n |
| description_key | varchar(128) | no | clave i18n |
| price_usd | numeric(8,2) | sí | |
| price_tokens | integer | sí | check >= 0 |
| is_competitive_safe | boolean | no | default true |
| metadata_json | jsonb | no | default `{}` |
| is_active | boolean | no | default true |

### 10.2 `purchases`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| user_id | uuid | no | FK users(id) |
| store_item_id | uuid | no | FK store_items(id) |
| currency | varchar(12) | no | usd/tokens |
| amount | numeric(8,2) | no | check >= 0 |
| provider_txn_id | varchar(128) | sí | unique parcial |
| status | varchar(16) | no | pending/paid/refunded/failed |
| created_at | timestamptz | no | default now() |

### 10.3 `rewarded_ads_events`

| Campo | Tipo | Null | Restricciones |
|---|---|---|---|
| id | uuid | no | PK |
| user_id | uuid | no | FK users(id) |
| ad_network | varchar(24) | no | |
| reward_type | varchar(24) | no | tokens/boost/retry |
| reward_amount | integer | no | check >= 0 |
| granted_at | timestamptz | no | default now() |

---

## 11. Integridad Referencial

Reglas críticas:

1. Borrado de usuario no cascada en histórico competitivo; usar anonimización.
2. Borrado de especie no rompe eventos: conservar snapshot.
3. `tournament_matches` exige que entradas pertenezcan a la misma `season_id`.
4. `store_items.is_competitive_safe` debe ser true para cualquier item visible en contexto competitivo.

---

## 12. Índices recomendados por carga

- Eventos: `(universe_id, created_at desc)`.
- Torneos: `(season_id, league, created_at)`.
- Banco genético: `(status, downloads_count desc)`.
- Compras: `(user_id, created_at desc)`.

---

## 13. Migraciones y Versionado

### 13.1 Convención

`YYYYMMDD_HHMM__descripcion.sql`

Ejemplo:

`20260303_1800__create_tournament_matches.sql`

### 13.2 Reglas

- Una migración por cambio lógico atómico.
- Toda migración con rollback definido cuando aplique.
- Cambios destructivos requieren ventana controlada.

---

## 14. Validaciones de Runtime

- Clamp de métricas 0..100 al persistir.
- Rechazo de payloads sin checksum en snapshots críticos.
- Rechazo de inserción de evento sin claves i18n en campos críticos.
- Rate limit de escritura en acciones sociales.

---

## 15. Criterios de Aceptación

- [ ] Entidades críticas definidas con tipos y restricciones
- [ ] Índices mínimos definidos
- [ ] Integridad referencial descrita
- [ ] Migraciones/versionado establecidos
- [ ] Coherencia con ADD, Balance y Multiplayer

---

## 16. Declaración Final

Data Dictionary Complete v1.0 transforma el modelo conceptual en una especificación persistente operable. Cualquier implementación de backend debe adherirse a estas reglas o documentar la excepción.
