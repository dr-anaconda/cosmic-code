# UI/UX Spec — Especificación de Interfaces

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md`
- `_docs/docs/CÓDIGO CÓSMICO_ GDD-lite.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Core Loops.md`

---

## 1. Propósito

Este documento establece la **dirección visual, arquitectura de navegación y especificaciones de componentes** para la interfaz de usuario del juego.

**Principios:**
1. Mobile-first: diseñar para móvil primero, escalar a desktop
2. Claridad: comunicar sistemas complejos con transparencia
3. Feedback: toda acción tiene respuesta visible
4. Contextual: mostrar solo lo relevante en cada momento

---

## 2. Dirección Visual

### 2.1 Estética: "Cósmica Orgánica"

La interfaz combina la vastedad del espacio con la vida orgánica:

| Elemento | Descripción |
|---------|-------------|
| **Fondo** | Gradientes oscuros (azul profundo → negro), nebulosas sutiles |
| **Superficies** | Transparencias suaves, bordes sutiles, glassmorphism ligero |
| **Formas** | Orgánicas (células, moléculas) combinadas con geométricas (órbitas, sistemas) |
| **Espaciado** | Generoso, respirable, no recargado |

### 2.2 Paleta de Colores

| Rol | Color | Uso |
|-----|-------|-----|
| **Fondo base** | #0A0E17 | Fondo principal |
| **Fondo secundario** | #151B2B | Cards, paneles |
| **Fondo terciario** | #1E2740 | Elementos elevados |
| **Texto primario** | #E8ECF4 | Títulos, datos importantes |
| **Texto secundario** | #8B95A8 | Descripciones |
| **Acento principal** | #00D4AA | Vida, evolución (teal cósmico) |
| **Acento secundario** | #7B61FF | Cósmico, poder (violeta) |
| **Warning** | #FFB84D | Alertas medias |
| **Danger** | #FF5757 | Peligro, crítico |
| **Éxito** | #4ADE80 | Progreso, éxito |

### 2.3 Tipografía

| Nivel | Fuente | Tamaño | Peso |
|-------|--------|--------|------|
| H1 | Inter / System | 24px | 700 |
| H2 | Inter / System | 20px | 600 |
| H3 | Inter / System | 16px | 600 |
| Body | Inter / System | 14px | 400 |
| Caption | Inter / System | 12px | 400 |
| Stats | JetBrains Mono / Monospace | 14px | 500 |

### 2.4 Espaciado (8px grid)

| Token | Valor |
|-------|-------|
| xs | 4px |
| sm | 8px |
| md | 16px |
| lg | 24px |
| xl | 32px |
| 2xl | 48px |

---

## 3. Arquitectura de Navegación

### 3.1 Estructura Principal

```
┌─────────────────────────────────────────┐
│              HEADER                      │
│  [Logo] [Breadcrumb]    [Stats] [User]  │
├─────────────────────────────────────────┤
│                                         │
│              MAIN CONTENT               │
│         (Variable por pantalla)         │
│                                         │
├─────────────────────────────────────────┤
│              BOTTOM NAV                 │
│  [Dashboard] [Planets] [Genetics] [More]│
└─────────────────────────────────────────┘
```

### 3.2 Bottom Navigation (Mobile)

| Icono | Etiqueta | Pantalla |
|-------|----------|----------|
| 🏠 | Inicio | Dashboard |
| 🌍 | Planetas | Selector de planetas |
| 🧬 | Genética | Editor / Banco |
| ⚔️ | Guerra | Torneos / Combates |
| ⚙️ | Más | Ajustes / Perfil |

### 3.3 Sidebar (Desktop)

Mismos items, adaptados a sidebar izquierda colapsable.

---

## 4. Pantallas Principales

### 4.1 Dashboard (Inicio)

**Propósito:** Vista general del estado del universo

**Elementos:**
- Header con día actual y bonificador de velocidad
- Stats globales (energía, material genético, tokens)
- Lista de planetas activos con mini-vista
- Eventos pendientes (1-3 más recientes)
- Acciones rápidas

**Layout Mobile:**
```
┌─────────────────────────────┐
│ Día 42  [+5%]    ⚡120 🧬25│
├─────────────────────────────┤
│ ┌─────────────────────────┐│
│ │  TUS PLANETAS           ││
│ │  [Planeta 1] [Planeta2]││
│ │  [Planeta 3] [+]        ││
│ └─────────────────────────┘│
├─────────────────────────────┤
│ ┌─────────────────────────┐│
│ │  EVENTOS                ││
│ │  ⚠️ Mutación detectada  ││
│ │  📅 Hito en 2h          ││
│ └─────────────────────────┘│
├─────────────────────────────┤
│ [Dashboard] [Planets] [Genetics] [+] │
└─────────────────────────────┘
```

### 4.2 Vista Planeta

**Propósito:** Ver y gestionar un planeta específico

**Elementos:**
- Vista visual del planeta (zoom configurable)
- Stats del planeta (temperatura, atmósfera, etc.)
- Lista de especies actuales
- Acciones: terraformar, editar, mover
- Progreso hacia siguiente nivel

**Niveles de Zoom:**
| Nivel | Vista |
|-------|-------|
| Planeta | Superficie con nubes, océanos, vida |
| Sistema | Órbitas, estrella, planeta |
| Galaxia | Mapa estelar completo |

### 4.3 Editor Genético

**Propósito:** Crear y editar especies

**Elementos:**
- Grid de genes disponibles
- Slots de genes de la especie
- Previsualización de stats
- Botón de crear/guardar
- Editor avanzado (red neuronal) - opcional

**Flujo:**
1. Seleccionar planeta destino
2. Elegir genes (drag & drop o tap)
3. Ver preview de stats
4. Confirmar (ver animación de creación)
5. La especie aparece en el planeta

### 4.4 Torneos / Guerra

**Propósito:** Competir con ecosistemas

**Elementos:**
- Lista de torneos activos
- Mi ecosistema (seleccionar especies)
- Rankings actuales
- Resultados de batallas
- Recompensas

### 4.5 Tienda

**Propósito:** Adquirir items con tokens

**Categorías:**
- Aceleradores
- Ranuras
- Genes raros
- Cosméticos

---

## 5. Componentes

### 5.1 StatChip

Muestra un valor con icono y tendencia.

```
┌──────────────────┐
│ ⚡ 120  (+15)   │
└──────────────────┘
```

**Estados:**
- Normal (gris)
- Subiendo (+verde)
- Bajando (-rojo)
- Crítico (rojo brillante)

### 5.2 PlanetCard

Mini-vista de planeta en dashboard.

```
┌──────────────────┐
│ 🌍    Nombre    │
│     [thumbnail] │
│    Nivel 4 • 34 │
│    ████░░ 65%   │
└──────────────────┘
```

### 5.3 SpeciesCard

Info de especie.

```
┌──────────────────────────────┐
│ 🧬 Nombre de Especie        │
│ Población: 1,250            │
│ Generación: 12               │
│ Stats: [▓▓▓░░] [▓▓▓▓░]    │
│ [Editar] [Ver] [Mover]      │
└──────────────────────────────┘
```

### 5.4 ProgressBar

Barra de progreso multi-nivel.

```
████████████░░░░░░░░░░  Level 3
░░░░░░░░░░░░░░░░░░░░░  45%
```

### 5.5 EventCard

Evento con decisiones.

```
┌──────────────────────────────┐
│ ⚠️  Mutación Detectada      │
│ Una nueva mutación ha        │
│ ocurrido en [Especie]        │
│                              │
│ [Aceptar] [Investigar]      │
└──────────────────────────────┘
```

### 5.6 Modal/Drawer

**Mobile:** Bottom drawer (slide up)  
**Desktop:** Center modal

Usos:
- Editor Genético completo
- Detalle de especie
- Confirmaciones críticas

---

## 6. Animaciones

### 6.1 Principios

- Duración: 150-250ms para interacciones
- Transiciones: 200-350ms para cambios de pantalla
- Respetar `prefers-reduced-motion`

### 6.2 Animaciones Permitidas

| Tipo | Uso |
|------|-----|
| Fade + Translate | Transiciones |
| Scale (subtle) | Reveals |
| Contadores | Stats que cambian |
| Pulsos | Alertas |
| Shimmer | Loading states |

### 6.3 Animaciones Prohibidas

- Partículas pesadas
- 3D complejo
- Animaciones infinitas (loops)
- Sombras animadas continuas

---

## 7. Responsive

### 7.1 Breakpoints

| Breakpoint | Ancho | Dispositivo |
|------------|-------|-------------|
| sm | <640px | Móvil pequeño |
| md | 640-1024px | Móvil grande / Tablet |
| lg | 1024-1440px | Desktop |
| xl | >1440px | Desktop grande |

### 7.2 Adaptaciones

| Elemento | Mobile | Desktop |
|----------|--------|---------|
| Navegación | Bottom bar | Sidebar |
| Dashboard | 1 columna | 2-3 columnas |
| Stats | Horizontal scroll | Grid |
| Modals | Full-screen | Centered |
| Tooltips | Long-press | Hover |

---

## 8. Accesibilidad

### 8.1 Requisitos

- Contraste mínimo 4.5:1
- Labels en todos los inputs
- Estados focus visibles
- Texto alternativo en iconos
- Soporte screen reader (ARIA)

### 8.2 Estados

Todo componente debe soportar:
- Normal
- Hover
- Focus
- Active
- Disabled
- Loading
- Error

---

## 9. Estados Vacíos

Cada pantalla debe manejar:

| Estado | Mensaje | Acción |
|--------|---------|--------|
| Empty | "Aún no tienes planetas" | Botón "Crear planeta" |
| Loading | Shimmer skeleton | - |
| Error | "Error al cargar" | Botón "Reintentar" |
| No events | "Todo tranquilo" | - |

---

## 10. Onboarding (Tutorial)

### 10.1 Estructura

| Paso | Duración | Contenido |
|------|----------|-----------|
| 1 | 30s | Bienvenida, crear primer planeta |
| 2 | 1min | Crear primera bacteria |
| 3 | 1min | Ver primera mutación |
| 4 | 1min | Siguiente paso (según progreso) |

### 10.2 UI del Tutorial

- Tooltips step-by-step
- No bloquea toda la UI
- Puede saltar
- Se puede replayear

---

## 11. Notificaciones

### 11.1 Tipos

| Tipo | Prioridad | Sound |
|------|-----------|-------|
| Hito alcanzado | Alta | Sí |
| Evento nuevo | Media | Opcional |
| Recordatorio | Baja | No |
| Social | Variable | Opcional |

### 11.2 Badges

- Rojos con número para no leídos
- Solo mostrar si >0

---

## 12. Checklist de Validación

- [ ] Mobile-first confirmado
- [ ] Estética coherente
- [ ] Navegación clara
- [ ] Pantallas principales diseñadas
- [ ] Componentes especificados
- [ ] Animaciones definidas
- [ ] Responsive rules
- [ ] Accesibilidad considerada
- [ ] Estados vacíos definidos
- [ ] Tutorial perfilado
- [ ] Sin contradicciones con GDD

---

## 13. Declaración Final

**Esta especificación es la referencia para todo diseño UI/UX. Cualquier desviación debe ser justificada y aprobada por el lead de diseño.**

---

**Documento creado bajo sistema CANON**  
**Siguiente: ADD (Architecture Design Document)**
