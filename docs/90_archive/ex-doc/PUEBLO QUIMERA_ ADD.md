# **ADD — Architecture Design Document**

**Proyecto:** *Pueblo Quimera*  
 **Versión:** 0.1  
 **Objetivo:** arquitectura clara, escalable y mantenible

---

## **1\. Objetivos de la arquitectura**

La arquitectura debe:

1. Soportar **lógica sistémica compleja** sin acoplarla a la UI

2. Permitir **ticks diarios deterministas**

3. Ser **debuggeable** (entender por qué pasó algo)

4. Escalar en contenido sin refactor masivo

5. Funcionar bien en **hosting tradicional (Apache \+ PHP)**

---

## **2\. Restricciones y decisiones base**

### **Stack decidido**

* Backend: **PHP 8.x**

* Framework: **CodeIgniter 3**

* DB: **MySQL o SQLite**

* Frontend: **Tailwind \+ JS ligero (Alpine o vanilla)**

* Arquitectura: **server-driven \+ interacciones parciales**

### **Decisiones explícitas**

* ❌ No SPA

* ❌ No lógica crítica en frontend

* ❌ No simulación en tiempo real

* ✅ Tick discreto por día

* ✅ Estado 100% persistente

---

## **3\. Visión general del sistema**

### **Capas principales**

`┌──────────────────────────┐`  
`│        UI / Views        │`  
`│  (Dashboard, Criadero)   │`  
`└─────────────▲────────────┘`  
              `│`  
`┌─────────────┴────────────┐`  
`│      Application Layer   │`  
`│  Controllers / Actions   │`  
`└─────────────▲────────────┘`  
              `│`  
`┌─────────────┴────────────┐`  
`│      Domain Layer        │`  
`│  Game Logic / Services   │`  
`└─────────────▲────────────┘`  
              `│`  
`┌─────────────┴────────────┐`  
`│     Persistence Layer    │`  
`│  Models / Repositories   │`  
`└──────────────────────────┘`

**Regla clave:**  
 Controllers coordinan.  
 Services piensan.  
 Models guardan.

---

## **4\. Modelo de dominio (conceptual)**

### **Entidades principales**

* **Save (Ciudad)**

* **EcosystemState**

* **ChimeraSpecies**

* **ChimeraPopulation**

* **Event**

* **Trait**

* **Policy / Infrastructure**

* **Bulletin**

Estas entidades:

* no conocen la UI

* no dependen de HTTP

* se comunican por datos simples (arrays / DTOs)

---

## **5\. Application Layer (Controllers)**

### **Responsabilidad**

* Validar input

* Llamar servicios de dominio

* Preparar respuesta (HTML o JSON)

### **Controllers clave**

* `GameController`

  * `dashboard()`

  * `advance_day()`

* `ChimeraController`

  * `create()`

  * `contain()`

* `EventController`

  * `choose()`

* `ApiController` (opcional)

  * endpoints JSON

### **Regla**

❌ lógica de negocio  
 ❌ cálculos  
 ✅ orquestación

---

## **6\. Domain Layer (Services) — el corazón**

Aquí vive el juego.

### **Servicios principales**

#### **`GameTickService`**

Responsable de:

* ejecutar el tick diario

* coordinar sub-sistemas

* garantizar orden de ejecución

Sub-servicios:

* `EconomyService`

* `PopulationService`

* `EcosystemService`

* `EventGenerationService`

* `BulletinService`

Este servicio **no sabe nada de HTTP ni vistas**.

---

#### **`ChimeraFactoryService`**

Responsable de:

* crear especies

* aplicar rasgos

* calcular sinergias

* asignar side-effects

Input:

* trait IDs

* estado actual del mundo

Output:

* objeto especie completo (stats derivados)

---

#### **`EventResolutionService`**

Responsable de:

* aplicar efectos de decisiones

* programar efectos diferidos

* actualizar estado global

---

#### **`ReputationService`**

Responsable de:

* viralidad

* reputación

* confianza científica

* presión mediática

---

## **7\. Persistence Layer (Models / Repositories)**

### **Principios**

* 1 Model \= 1 tabla (aprox)

* Queries simples y explícitas

* Nada de lógica compleja aquí

### **Ejemplo de responsabilidades**

* `Save_model`: CRUD de ciudad

* `Ecosystem_model`: estado ambiental

* `Chimera_model`: especies \+ poblaciones

* `Event_model`: eventos \+ elecciones

* `Trait_model`: catálogo

* `Bulletin_model`: textos generados

Si una función tiene más de 10–15 líneas → probablemente no es Model.

---

## **8\. Flujo crítico: Tick diario**

### **Secuencia (resumen)**

`Jugador pulsa "Pasar Día"`  
        `↓`  
`GameController::advance_day`  
        `↓`  
`GameTickService::run(save_id)`  
        `↓`  
`1. Aplicar efectos pendientes`  
`2. Economía humana`  
`3. Poblaciones`  
`4. Ecosistema`  
`5. Riesgo y felicidad`  
`6. Generación de eventos`  
`7. Generación de boletín`  
        `↓`  
`Persistencia`  
        `↓`  
`Respuesta UI`

### **Garantías**

* Transacción DB

* Tick idempotente (no doble ejecución)

* Log de eventos para debugging

---

## **9\. Gestión del estado (clave para escalar)**

### **Qué se guarda**

* Todo lo necesario para reproducir el mundo

* Nada “derivable” en tiempo real

### **Qué se calcula**

* Tendencias

* Predicciones

* Resúmenes UI

### **Regla**

Si afecta a una decisión futura → se persiste.

---

## **10\. Interacciones UI ↔ Backend**

### **Patrón recomendado**

* Acción → POST

* Backend procesa

* Devuelve:

  * cambios de stats

  * eventos nuevos

  * mensajes (toasts)

  * HTML parcial o JSON

### **Ejemplo**

`{`  
  `"stats": { "budget": 1200, "risk": 65 },`  
  `"toasts": ["Los depredadores aumentan"],`  
  `"events": [...],`  
  `"html": { "dashboard": "<div>...</div>" }`  
`}`

---

## **11\. Escalabilidad futura (sin romper nada)**

Esta arquitectura permite:

* múltiples ciudades por usuario

* cron ticks (idle)

* temporadas

* reglas alternativas (NG+)

* A/B testing de balance

Porque:

* la lógica está desacoplada

* el tick es determinista

* los sistemas son modulares

---

## **12\. Logging y debug (MUY importante)**

### **Qué loguear**

* Cada tick

* Cambios grandes de estado

* Entradas en plaga/colapso

* Decisiones del jugador

### **Para qué**

* reproducir bugs

* entender “por qué explotó todo”

* balancear sin adivinar

---

## **13\. Anti-patrones prohibidos**

❌ lógica en vistas  
 ❌ cálculos en JS  
 ❌ acceso directo a DB desde JS  
 ❌ estados “mágicos” no persistidos  
 ❌ eventos sin explicación narrativa

---

## **14\. Mantra de arquitectura**

**El juego es una simulación discreta,**  
 **no una app interactiva con adornos.**

Si respetas eso, crecerá sin romperse.

---

### **✅ ADD completado**

Con esto ya tienes:

* **qué es el juego** (PRD)

* **cómo se juega** (GDD-lite)

* **cómo se construye** (ADD)
