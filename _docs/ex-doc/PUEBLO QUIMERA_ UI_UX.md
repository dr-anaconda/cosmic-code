# **UI/UX SPEC — *Pueblo Quimera***

**Versión:** 0.1  
 **Rol:** coherencia visual, interacción y experiencia  
 **Ámbito:** todas las pantallas del juego

---

## **1\. Objetivos de la UI**

La interfaz debe:

1. Comunicar **sistemas complejos con claridad**

2. Ser **ligera y rápida** (sensación \< 100 ms)

3. Funcionar igual de bien en **móvil y desktop**

4. Traducir números en **significado narrativo**

5. Permitir crecer el juego sin rehacer layouts

---

## **2\. Principios UX (no negociables)**

### **2.1 Claridad antes que estética**

* El jugador debe entender:

  * qué está pasando

  * qué puede hacer ahora

  * qué pasará después (aprox.)

### **2.2 Todo cambio tiene feedback**

* Ninguna acción es silenciosa

* Todo cambio relevante produce:

  * animación breve

  * texto explicativo

  * delta visible

### **2.3 El riesgo se comunica explícitamente**

* Riesgo nunca es “sorpresa pura”

* Usa:

  * texto (“Riesgo alto”)

  * iconos

  * color

  * contexto narrativo

---

## **3\. Lenguaje visual (2026-ready)**

### **3.1 Estética general**

**Tema:** *Administración científica improvisada*

* Superficies limpias

* Bordes suaves

* Sombras mínimas

* Nada de efectos pesados (glassmorphism fuerte, partículas)

### **3.2 Colores (semánticos)**

No se define paleta exacta aquí, sino **roles**:

| Rol | Uso |
| ----- | ----- |
| Base | fondos, texto |
| Institucional | acciones “responsables” |
| Mutante | quimeras, viralidad |
| Advertencia | riesgo medio |
| Peligro | crisis |
| Éxito | mitigación / control |

Regla: **nunca comunicar estado solo con color**.

---

## **4\. Tipografía**

### **Jerarquía**

* **H1**: nombre del pueblo, eventos principales

* **H2**: secciones

* **Body**: lectura cómoda (boletín)

* **UI Text**: compacto (stats, botones)

### **Reglas**

* Máx. 2 familias tipográficas

* Interlineado generoso en texto narrativo

* Números alineados (tabulares si es posible)

---

## **5\. Arquitectura de navegación**

### **Áreas principales (persistentes)**

1. Dashboard (Hoy)

2. Criadero

3. Ecosistema

4. Feed / Boletín

### **Navegación**

* **Mobile:** bottom bar con icono \+ label

* **Desktop:** sidebar colapsable

### **Acción primaria global**

* **Pasar Día**

  * Siempre visible

  * Claramente destacada

  * Estado deshabilitado si hay decisiones pendientes

---

## **6\. Componentes base (design system mínimo)**

### **6.1 Card**

Contenedor universal.

Estados:

* normal

* warning

* danger

* disabled

Uso:

* eventos

* especies

* paneles

---

### **6.2 StatChip**

Muestra valor \+ tendencia.

Incluye:

* valor actual

* delta (+/−)

* icono semántico

Ej:

Felicidad 55 (−4)

---

### **6.3 Meter (0–100)**

Variables del ecosistema.

Requisitos:

* barra \+ etiqueta textual

* estado: OK / Tenso / Crítico

* tooltip explicativo

---

### **6.4 EventCard**

Elemento central del gameplay.

Debe incluir:

* título claro

* severidad visible (1–5)

* cuerpo narrativo

* 2–4 opciones

Las opciones:

* tienen intención clara

* muestran consecuencias aproximadas

---

### **6.5 ChoiceButton**

Tipos:

* Primario (responsable)

* Neutral

* Riesgo alto / sensacionalista

Siempre muestran:

* efecto principal

* coste implícito o explícito

---

### **6.6 Modal / Drawer**

Usos:

* Criadero (wizard)

* Detalle de especie

* Confirmaciones críticas

Regla:

* Desktop → modal

* Mobile → drawer inferior

---

### **6.7 Toast / Feedback**

Para:

* cambios de estado

* alertas rápidas

* consecuencias inmediatas

Duración:

* 2–3 segundos

* apilables

* accesibles

---

## **7\. Flujos UX clave**

### **7.1 Flujo “Crear Quimera”**

1. Abrir criadero

2. Seleccionar rasgos (chips)

3. Previsualización borrosa

4. Confirmar

5. Reveal del resultado

6. Decisión: implementar / contener / vender / postear

**Regla:**  
 Nunca más de **3 pasos visibles** a la vez.

---

### **7.2 Flujo “Evento diario”**

1. Evento aparece destacado

2. El jugador lee

3. Elige una opción

4. Feedback inmediato (toasts \+ animación)

5. Evento se archiva

6. Stats se actualizan

---

### **7.3 Flujo “Pasar Día”**

1. Botón activo

2. Confirmación ligera (si hay riesgos altos)

3. Animación de transición

4. Nuevo día cargado

5. Boletín visible automáticamente

---

## **8\. Animaciones permitidas (microinteracciones)**

### **Permitidas**

* fade \+ translate

* scale sutil

* contadores animados

* pulsos únicos (alertas)

### **Prohibidas**

* partículas

* animaciones infinitas

* efectos 3D complejos

* sombras animadas constantes

Duraciones:

* Interacciones: 120–180 ms

* Transiciones: 180–240 ms

Respetar:

* `prefers-reduced-motion`

---

## **9\. Responsive rules**

### **Mobile-first**

* stats en scroll horizontal

* eventos siempre arriba

* criadero en drawer

* ecosistema en accordions

### **Desktop**

* dashboard en 3 columnas

* sidebar persistente

* más contexto visible

---

## **10\. Estados del sistema (UI)**

Todo componente debe contemplar:

* loading

* empty

* error

* warning

* disabled

Ejemplo:

* Criadero bloqueado → texto narrativo explicando por qué

---

## **11\. Tono del texto en UI**

* Institucional

* Científico

* Irónicamente serio

Nunca:

* burlón

* moralizante

* excesivamente técnico

---

## **12\. Escalabilidad futura (desde UI)**

La UI debe permitir:

* nuevas pestañas

* nuevas métricas

* más tipos de eventos

* temporadas

Regla:

Si un componente no admite “más contenido”, rediseñarlo antes de usarlo.

---

## **13\. Checklist de validación UI**

Antes de cerrar una pantalla:

* ¿Se entiende sin tutorial?

* ¿El riesgo está claro?

* ¿Hay feedback?

* ¿Funciona en móvil?

* ¿Respeta el tono?

---

### **✅ UI/UX Spec completado**

Con esto ya tienes 4/7 documentos base:

1. PRD

2. GDD-lite

3. ADD

4. UI/UX Spec

