# GDD-lite — Filosofía y Reglas Core

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:** 
- `_docs/init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md` (fuente primaria)
- `_docs/docs/CÓDIGO CÓSMICO_ PRD.md` (visión de producto)

---

## 1. Propósito

Este documento establece la **filosofía de diseño** y las **reglas operativas fundamentales** que rigen el juego. No es una especificación técnica ni un manual de funcionalidades.

El GDD-lite responde a las preguntas:
- ¿Cuál es la experiencia que queremos crear?
- ¿Qué principios son inquebrantables?
- ¿Qué reglas definen el comportamiento del sistema?
- ¿Qué NO es este juego?

Los detalles de implementación, números y fórmulas se encuentran en:
- `_docs/docs/CÓDIGO CÓSMICO_ System Balance Sheet.md` (números, fórmulas)
- `_docs/docs/CÓDIGO CÓSMICO_ Data Dictionary.md` (entidades, campos)
- `_docs/docs/CÓDIGO CÓSMICO_ UI_UX.md` (interfaces)
- `_docs/docs/CÓDIGO CÓSMICO_ ADD.md` (arquitectura)
- `_docs/docs/CÓDIGO CÓSMICO_ Monetization Spec.md` (tienda, tokens)

---

## 2. Filosofía de Diseño

### 2.1 Principio Rector: Consecuencialismo Visible

> **Toda decisión del jugador tiene consecuencias visibles y comprensibles en el sistema.**

Este principio guía cada mecánica del juego:

- Cuando el jugador terraforma un planeta, ve los efectos en la evolución de las especies
- Cuando crea una especie, observa cómo muta y se adapta (o no) al entorno
- Cuando una civilización colapsa, entiende por qué (contaminación, guerra, negligencia)
- Cuando implosiona un universo, ve exactamente qué bonificadores gana

**El jugador nunca debe preguntarse "¿por qué pasó eso?"**

### 2.2 Principio Secundario: Observador Activo

> **El jugador influye, pero no controla directamente.**

El jugador no es un dios que pulsa botones y obtiene resultados. Es una conciencia que:
- Crea las condiciones iniciales (ambiente, recursos, amenazas)
- Selecciona qué organismos se reproducen (selección artificial)
- Diseña genomas (edición genética)
- Modifica entornos (terraformación)
- Pero NO controla el comportamiento individual de cada criatura

La evolución es emergente, no dirigida. Las redes neuronales de las criaturas toman decisiones basadas en su programación genética y el entorno.

### 2.3 Principio Terciario: Colapsos como Narrativa

> **Los fracasos son contenido, no castigos.**

Cuando un ecosistema colapsa, una civilización muere, o una plaga azota un planeta:
- NO es "Game Over"
- Es una historia que se cuenta
- El Boletín narrará lo que ocurrió
- El jugador puede aprender y adaptarse
- Siempre hay una salida (a veces costosa)

El juego no castiga el fracaso, lo convierte en combustible para la narrativa emergente.

---

## 3. Qué NO Es El Juego

Para evitar confusiones de diseño, explicitamos qué NO es este producto:

| No es... | Por qué |
|----------|---------|
| **Un puzzle con solución óptima** | Los sistemas son complejos y emergentes; no hay una estrategia perfecta |
| **Un idle pasivo puro** | El jugador toma decisiones significativas que afectan el resultado |
| **Un simulador científico realista** | Es una simulación "divertida", no académica |
| **Un juego de acción en tiempo real** | Todo es asíncrono; no hay reflejos necesarios |
| **Un juego con "ganador"** | No hay final; la progresión es infinita via implosiones |

---

## 4. Tiempo y Ritmo del Juego

### 4.1 Modelo Híbrido Idle-Táctico

El juego opera en dos capas temporales:

| Capa | Escala | Interacción |
|------|--------|-------------|
| **Idle (Evolución)** | Horas a días | La evolución avanza sola |
| **Táctico (Decisiones)** | Minutos por sesión | El jugador toma acciones |

**Flujo típico:**
1. El jugador abre la app (sesión: 5-15 min)
2. Ve el progreso de sus planetas (idle avanzado mientras no jugaba)
3. Toma decisiones tácticas: terraformar, crear especie, editar genoma
4. Inicia acciones que requerirán tiempo (viajes, mutaciones)
5. Cierra la app
6. La evolución continúa en segundo plano

### 4.2 Tick del Sistema

El mundo evoluciona en **ticks** que representan:
- Un "día" en el planeta
- Ciclos de reproducción de especies
- Avance de barras de progreso

Los ticks:
- Se ejecutan en tiempo real (cuando la app está abierta o cerrada)
- Son deterministas: el mismo estado siempre produce el mismo resultado
- Se registran para poder reproducir bugs

### 4.3 Ritmo de Sesión

| Fase de sesión | Duración | Actividad |
|---------------|----------|-----------|
| **Review** | 1-2 min | Ver progreso, stats, eventos |
| **Decisión** | 3-5 min | Acciones tácticas |
| **Iniciación** | 1-2 min | Iniciar procesos que requerirán tiempo |
| **Cierre** | 1 min | Revisar estado, cerrar |

**Total: 6-10 minutos por sesión**

Frecuencia recomendada: 3-4 sesiones/día para usuarios activos.

---

## 5. Sistemas Principales (Visión Global)

El juego se organiza en **5 Dimensiones del Poder** que se desbloquean progresivamente:

| Dimensión | Desbloqueo | Rol |
|-----------|------------|-----|
| **Viaje Interestelar** | Nivel 6+ civ | Exploración, multiplaneta |
| **Diseño Genético** | 50 mutaciones | Creación de especies |
| **Guerra de Ecosistemas** | 2 planetas complejos | Competición |
| **Gestión de Civilizaciones** | Nivel 7+ | Política, multiplayer |
| **Poder Cósmico** | 100 hitos + 10 civ espaciales | Control del universo |

> **Nota:** Las mecánicas detalladas de cada dimensión están en el GDD completo. Aquí solo definimos el concepto.

### 5.1 Sistema de Niveles Evolutivos

La vida en el juego progresa por **9 niveles de complejidad**:

| Nivel | Ejemplo | Equivalente |
|-------|---------|------------|
| 1 | Bacterias | Procariotas |
| 2 | Amebas | Eucariotas |
| 3 | Esponjas | Pluricelulares simples |
| 4 | Gusanos | Pluricelulares complejos |
| 5 | Peces | Sistema nervioso |
| 6 | Mamíferos primitivos | Inteligencia incipiente |
| 7 | Civilización preindustrial | Sociedad |
| 8 | Civilización industrial | Tecnología |
| 9 | Civilización espacial | Expansión interestelar |

Cada nivel desbloquea nuevas mecánicas y opciones para el jugador.

> **Referencia:** Sistema completo de evolución, genoma y redes neuronales en GDD secciones 3.1-3.4

---

## 6. Reglas de Oro del Diseño

### 6.1 Reglas Inquebrantables

**R1: Toda decisión tiene coste real**
- Siembra recursos para terraformar → esos recursos no están en otro lado
- Crear especie consume material genético →no puedes crear infinitas
- Implosionar da bonificadores pero pierde progreso del universo actual

**R2: Toda acción tiene consecuencia visible**
- Cuando modificas un planeta, ves el cambio en la evolución
- Cuando cruzas genes, observas el resultado en la siguiente generación
- Cuando intervenís en una civilización, ves su reacción

**R3: El jugador siempre entiende por qué pasó algo**
- El Boletín explica los eventos en lenguaje natural
- Los indicadores muestran tendencias y causas
- Nunca hay "esto pasó porque sí"

**R4: No hay victoria definitiva**
- No hay "ganar" el juego
- La implosión reinicia el universo pero conserva progresión
- Siempre hay más por descubrir (nuevas especies, genes, dimensiones)

**R5: El fallo es interesante**
- Un ecosistema que colapsa genera más historia que uno estable
- Las mutaciones inesperadas son oportunidades, no bugs
- Las civilizaciones que fracasan dejan legado (ruinas, genes, leyendas)

### 6.2 Reglas de Fallo Divertido

**FD1: Colapsos generan narrativa**
- Cuando algo falla, el sistema lo explica
- El jugador puede aprender y adaptarse
- Siempre hay una salida (a veces costosa)

**FD2: Consecuencias no anticipadas**
- Una decisión que parece buena puede tener efectos secundarios
- Las especies dominantes en un planeta pueden ser débiles en otro
- Los genes raros tienen efectos únicos, no solo "más fuertes"

**FD3: Recuperación posible**
- Incluso desde un colapso económico se puede recuperar
- Las civilizaciones pueden renacer de las cenizas
- El jugador nunca queda irreversiblemente "fuera"

---

## 7. Reglas de Progresión

### 7.1 Tipos de Progresión

| Tipo | Fuente | Efecto |
|------|--------|--------|
| **Conocimiento** | Hitos presenciados | Desbloquea habilidades en árbol |
| **Genes** | Descubrimiento, tienda | Nuevas opciones de creación |
| **Bonificadores** | Implosiones | Mejoras permanentes |
| **Tokens** | Torneos, logros | Compras en tienda |

### 7.2 Ciclo Multiversal

El reinicio (implosión) es la mecánica de progresión principal:

**Qué se pierde al implosionar:**
- Planetas y civilizaciones actuales
- Especies creadas
- Estado actual del universo

**Qué se conserva:**
- Puntos de conocimiento
- Genes raros descubiertos
- Bonificadores de velocidad
- Tokens Cósmicos

**Qué se gana:**
- Bonificador nuevo basado en logros del universo anterior
- La experiencia de haber visto más de la vida

> **Referencia:** Detalles del ciclo multiversal en GDD sección 2.2

---

## 8. Reglas de Multijugador

### 8.1 Naturaleza Asíncrona

Todo el multijugador es **asíncrono**:
- No hay partidas en tiempo real
- Las guerras de ecosistemas se simulan en servidor
- Las interacciones entre civilizaciones se resuelven en diferido

### 8.2 Dimensiones Multijugador

| Dimensión | Mecánica | Interacción |
|-----------|----------|-------------|
| **Genética** | Banco genético global | Compartir/especies |
| **Guerra** | Torneos semanales | Competición |
| **Civilizaciones** | Sondas, intercambio | Diplomacia |

### 8.3 Fair Play

**Nunca se puede comprar:**
- Victorias en torneos
- Genes superiores (solo únicos, no más fuertes)
- Poder que no sea alcanzable jugando

> **Referencia:** Multijugador completo en `_docs/docs/CÓDIGO CÓSMICO_ Multiplayer Spec.md`

---

## 9. Reglas de Monetización Ética

### 9.1 Lo que se vende

- Cosméticos (skins, efectos visuales)
- Aceleradores limitados (no esenciales)
- Ranuras adicionales (planetas, banco)
- Genes raros (efectos únicos, no superiores)

### 9.2 Lo que NUNCA se vende

- Victorias en torneos
- Genes con estadísticas mejores
- Poder de manipulación cósmica
- Contenido que afecte la competencia justa

### 9.3 Anuncios

- Opcionales y no intrusivos
- Integrados como "fenómenos naturales"
- Recompensa por ver (bonus menor)

> **Referencia:** Detalles en `_docs/docs/CÓDIGO CÓSMICO_ Monetization Spec.md`

---

## 10. Riesgos de Diseño y Mitigaciones

| Riesgo | Mitigación |
|--------|------------|
| Complejidad abrumadora | Tutorial progresivo, UI contextual |
| Retención baja | Eventos frecuentes, progresión visible |
| Equilibrio difícil | Simulaciones, A/B testing, comunidad |
| Costes server | Arquitectura server-light, client-side cuando sea posible |

> **Referencia:** Riesgos completos y roadmap en GDD sección 9

---

## 11. Dependencias con Otros Documentos

| Documento | Relación |
|-----------|----------|
| `_docs/init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md` | Fuente primaria - no redundar, referenciar |
| `_docs/docs/CÓDIGO CÓSMICO_ PRD.md` | Visión de producto - coherencia con objetivos |
| `_docs/docs/CÓDIGO CÓSMICO_ Core Loops.md` | Detalle de bucles de juego |
| `_docs/docs/CÓDIGO CÓSMICO_ System Balance Sheet.md` | Fórmulas y números (no aquí) |
| `_docs/docs/CÓDIGO CÓSMICO_ Data Dictionary.md` | Entidades y campos (no aquí) |
| `_docs/docs/CÓDIGO CÓSMICO_ UI_UX.md` | Especificación de interfaces (no aquí) |
| `_docs/docs/CÓDIGO CÓSMICO_ ADD.md` | Arquitectura técnica (no aquí) |

---

## 12. Checklist de Validación

- [ ] Principios rectores claros y compartidos
- [ ] Qué NO es el juego explicitado
- [ ] Ritmo del juego definido
- [ ] Sistemas principales descritos (sin detalles técnicos)
- [ ] Reglas de oro inquebrantables
- [ ] Reglas de fallo divertido definidas
- [ ] Sistema de progresión explicado
- [ ] Multijugador conceptuado
- [ ] Monetización ética perfilada
- [ ] Riesgos identificados
- [ ] NO hay redundancia con GDD o documentos existentes
- [ ] Dependencias documentadas

---

## 13. Declaración Final

**Este documento define la filosofía y las reglas que rigen el juego. Todo diseño, implementación y decisión debe alinearse con estos principios. Las desviaciones requieren revisión del equipo de diseño.**

> "Siembra vida. Guía su destino. Trasciende el universo."

---

**Documento creado bajo sistema CANON**  
**Siguiente: Core Loops (Bucles de juego)**
