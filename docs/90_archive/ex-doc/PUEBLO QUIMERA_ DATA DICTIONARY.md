# **DATA DICTIONARY / SCHEMA DOC — *Pueblo Quimera***

**Versión:** 0.1  
 **Rol:** verdad única sobre los datos  
 **Ámbito:** backend, balance, debug, futuras features

---

## **1\. Principios del modelo de datos**

1. **Cada campo tiene significado jugable**, no solo técnico.

2. **Los rangos son explícitos** (0–100, positivos, negativos).

3. Se distingue claramente entre:

   * datos **persistentes**

   * datos **derivados**

4. Nada “mágico”: si algo afecta decisiones futuras, **se guarda**.

---

## **2\. Entidad: `users`**

| Campo | Tipo | Descripción | Notas |
| ----- | ----- | ----- | ----- |
| id | PK | Identificador del jugador |  |
| username/email | string | Identidad de login | Único |
| password\_hash | string | Seguridad | Nunca se usa en lógica |
| created\_at | datetime | Alta del usuario |  |

**Uso jugable:** ninguno directo  
 **Uso técnico:** autenticación

---

## **3\. Entidad: `saves` (Ciudad / Partida)**

Representa **el estado político-social** del pueblo.

| Campo | Rango | Significado jugable |
| ----- | ----- | ----- |
| id | PK | Identificador de la ciudad |
| user\_id | FK | Dueño |
| name | string | Nombre narrativo |
| day | int ≥ 1 | Día actual |
| budget | int ≥ 0 | Recursos económicos |
| population | int ≥ 0 | Habitantes humanos |
| happiness | 0–100 | Humor ciudadano |
| online\_rep | int ≥ 0 | Atención pública |
| trust\_science | 0–100 | Confianza institucional |
| risk\_ecology | 0–100 | Tensión acumulada |
| created\_at | — | Inicio de partida |
| updated\_at | — | Última modificación |

### **Reglas importantes**

* `risk_ecology` **nunca baja a 0 automáticamente**

* `happiness < 30` desbloquea eventos sociales

* `budget < 0` **no permitido** (se bloquean acciones antes)

---

## **4\. Entidad: `ecosystem_state`**

Estado ambiental **global**, no localizado.

| Campo | Rango | Significado |
| ----- | ----- | ----- |
| pollution | 0–100 | Nivel de contaminación |
| biodiversity | 0–100 | Salud del ecosistema |
| predators | 0–100 | Presión de depredadores |
| stability | 0–100 | Amortiguador sistémico |
| invasion\_pressure | 0–100 | Riesgo de expansión |
| water\_quality | 0–100 | (Opcional) Calidad del agua |
| waste\_daily | int ≥ 0 | Basura humana |
| last\_tick\_at | datetime | Último tick ejecutado |

### **Interpretación**

* `stability` **reduce impactos**, nunca crea beneficios.

* `invasion_pressure > 50` habilita plagas.

* `pollution > 70` genera mutaciones y crisis.

---

## **5\. Entidad: `traits` (Catálogo)**

Describe **piezas de diseño**, no instancias.

| Campo | Tipo | Significado |
| ----- | ----- | ----- |
| id | PK | ID del rasgo |
| key | string | Identificador estable |
| name | string | Nombre visible |
| description | text | Explicación |
| rarity | 1–5 | Frecuencia |
| tags | string | Temas (csv o json) |
| effects\_json | JSON | Beneficios |
| risk\_json | JSON | Riesgos |
| unlock\_condition\_json | JSON | Condición de acceso |

### **Reglas**

* Un rasgo **siempre tiene risk\_json**

* Los efectos **no son absolutos**, se combinan

* Tags gobiernan sinergias y side-effects

---

## **6\. Entidad: `chimera_species`**

Define una **especie creada por el jugador**.

| Campo | Tipo | Significado |
| ----- | ----- | ----- |
| id | PK | ID de especie |
| save\_id | FK | Ciudad |
| name | string | Nombre |
| trait\_ids\_json | JSON | Rasgos aplicados |
| created\_day | int | Día de creación |
| repro\_rate | float | Tasa reproductiva |
| mobility | float | Capacidad de expansión |
| aggression | float | Conflicto |
| pollution\_delta | int | Impacto ambiental |
| biodiversity\_delta | int | Impacto ecológico |
| tourism\_delta | int | Impacto económico |
| predator\_attract | int | Atrae depredadores |
| stability\_impact | int | Desestabilización |
| public\_acceptance | 0–100 | Opinión ciudadana |
| viral\_score | int | Potencial mediático |
| is\_invasive | bool | Riesgo sistémico |
| notes | text | Side-effect narrativo |

### **Importante**

* Estos campos son **derivados al crear la especie**

* No se recalculan cada día

* Permiten ticks rápidos

---

## **7\. Entidad: `chimera_populations`**

Histórico de población por día.

| Campo | Tipo | Significado |
| ----- | ----- | ----- |
| species\_id | FK | Especie |
| day | int | Día |
| count | int ≥ 0 | Población |
| status | enum | contained / wild / plague / extinct |
| zone | enum | urban / rural / water |
| notes | text | Incidentes |

### **Reglas**

* Una fila por especie y día

* `plague` desbloquea eventos especiales

* `extinct` no elimina la especie (historia persiste)

---

## **8\. Entidad: `events_log`**

Registro **narrativo y decisional**.

| Campo | Tipo | Significado |
| ----- | ----- | ----- |
| id | PK | Evento |
| save\_id | FK | Ciudad |
| day | int | Día |
| type | string | Tipo de evento |
| severity | 1–5 | Impacto |
| title | string | Título |
| body | text | Texto |
| choices\_json | JSON | Opciones |
| chosen\_choice\_key | string | Elección |
| effects\_json | JSON | Consecuencias |
| created\_at | datetime | Creación |

### **Reglas**

* Un evento puede quedar sin resolver

* Los efectos pueden ser inmediatos o diferidos

* Nunca borrar eventos (debug \+ narrativa)

---

## **9\. Entidad: `bulletins`**

Narrativa diaria.

| Campo | Tipo | Significado |
| ----- | ----- | ----- |
| save\_id | FK | Ciudad |
| day | int | Día |
| headline | string | Titular |
| body | text | Cuerpo |
| tone | enum | neutral / alarmist / celebratory |
| created\_at | datetime |  |

### **Uso**

* Traduce números a historia

* Da contexto emocional

---

## **10\. Campos derivados vs persistidos**

### **Persistidos (SIEMPRE)**

* estados globales

* contadores

* decisiones

* poblaciones

### **Derivados (NO persistir)**

* tendencias (↑ ↓)

* predicciones

* resúmenes UI

* tooltips explicativos

---

## **11\. Convenciones de nombres**

* snake\_case en DB

* nombres narrativos en UI

* claves estables (`key`) nunca cambian

---

## **12\. Validaciones críticas**

* Ningún stat global \< 0 o \> 100

* Población nunca negativa

* No tick doble mismo día

* `trait_ids_json` no vacío

---

## **13\. Uso del documento**

Este documento debe:

* actualizarse cuando se añade un campo

* revisarse antes de balancear

* consultarse al debuggear

Si un campo no puede explicarse aquí, **no debería existir**.
