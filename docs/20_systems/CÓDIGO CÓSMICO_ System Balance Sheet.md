# System Balance Sheet — Fórmulas y Números

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/90_archive/init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md`
- `docs/10_product/CÓDIGO CÓSMICO_ GDD-lite.md`
- `docs/10_product/CÓDIGO CÓSMICO_ Core Loops.md`
- `docs/20_systems/CÓDIGO CÓSMICO_ Data Dictionary.md`
- `docs/40_technical/CÓDIGO CÓSMICO_ Tournament System.md`
- `docs/40_technical/CÓDIGO CÓSMICO_ Multiplayer Spec.md`
- `docs/40_technical/CÓDIGO CÓSMICO_ Monetization Spec.md`

---

## 1. Propósito

Este documento establece las **fórmulas, ratios y umbrales** que rigen el balance del juego. Es la referencia para cualquier ajuste de balance.

**Principios:**
- Los números son puntos de partida, no valores finales
- Todo requiere testing y ajuste
- El balance evoluciona con feedback

> **Nota:** Documento resumido con fórmulas clave. Para valores exhaustivos, ver spreadsheet dedicado.

---

## 2. Filosofía de Balance

### 2.1 Objetivos

| Objetivo | Descripción |
|----------|-------------|
| **Oscilación** | Los sistemas no tienden a estabilidad absoluta |
| **Picos de tensión** | Momentos de decisión intensa |
| **Recuperaciones parciales** | Siempre hay salida, pero no gratis |
| **Decisiones interesantes** | Choices que se "sienten" antes de entenderse |

### 2.2 Lo que NO Buscamos

- Equilibrio perfecto
- Estabilidad eterna
- Crecimiento infinito sin consecuencias

---

## 3. Sistema de Evolución

### 3.1 Ticks y Tiempo

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| Tick base | 1 minuto | Tiempo real |
| Tick evolution | 1 tick/min | Avance evolución |
| Tick population | 1 tick/min | Cambios población |
| Tick ecosystem | 1 tick/min | Cambios ambiente |
| Accel max | 10x | Aceleración máxima |

### 3.2 Tiempos por Nivel

| Nivel | Tiempo base | Con bonus | Notas |
|-------|-------------|-----------|-------|
| 1→2 | 10 min | -10% por bonus | Bacterias → Eucariotas |
| 2→3 | 30 min | -10% | Eucariotas → Pluricelular |
| 3→4 | 1h | -10% | Simple → Complejo |
| 4→5 | 2h | -10% | Sistema nervioso |
| 5→6 | 4h | -10% | Inteligencia incipiente |
| 6→7 | 8h | -10% | Civilización |
| 7→8 | 16h | -10% | Industrial |
| 8→9 | 32h | -10% | Espacial |

**Fórmula:**
```
tiempo_nivel = tiempo_base * (1 - velocidad_bonus)
```

### 3.3 Mutaciones

| Parámetro | Valor | Rango |
|-----------|-------|-------|
| Tasa base | 0.01 | 1% por tick |
| Tasa radiación | +0.005 | Por cada unidad de radiación |
| Mutaciones viables | 70% | El resto son letales |
| Mutaciones beneficiosas | 20% | Mejoran stats |
| Mutaciones neutrales | 50% | Sin cambio |
| Mutaciones negativas | 30% | Empeoran stats |

---

## 4. Genética y Genoma

### 4.1 Genes

| Parámetro | Valor |
|-----------|-------|
| Genes por especie | 6-12 |
| Genes iniciales | 4 |
| Genes max | 12 |
| Mutación por gen | 0.001/tick |

### 4.2 Efectos de Genes

**Metabolismo:**
- Consumo base: 1-5 por individuo
- Eficiencia: 0.5-2.0x

**Resistencia:**
- Temperatura: -50°C a +50°C rango
- Radiación: 0-100 tolerancia
- Presión: 0.1-10x atmósfera

**Reproducción:**
- Rate base: 0.01-0.5 por tick
- Costo energético: 1-10 por reproducción

### 4.3 Red Neuronal (Nivel 5+)

| Parámetro | Valor |
|-----------|-------|
| Inputs | 5 (hambre, energía, peligro, temperatura, vecinos) |
| Hidden neurons | 3-8 |
| Outputs | 5 (mover, comer, huir, reproducir, atacar) |
| Mutation rate | 0.001 por generación |

---

## 5. Ecosistema

### 5.1 Variables Globales

| Variable | Rango | Óptimo | Crítico |
|----------|-------|--------|---------|
| Biodiversidad | 0-100 | 50-70 | <20 |
| Estabilidad | 0-100 | 40-60 | <20, >90 |
| Contaminación | 0-100 | <30 | >70 |
| Depredadores | 0-100 | <40 | >70 |
| Recursos | 0-100 | >50 | <20 |

### 5.2 Fórmulas de Ecosistema

**Contaminación:**
```
contaminación += residuos_diarios - digestores * población
```
- residuos_diarios: 1-10
- digestores: 1-5 por especie con gen limpiador

**Biodiversidad:**
```
biodiversidad += variedad * 0.1 - invasión * 0.05 - contaminación * 0.02
```

**Depredadores:**
```
depredadores += bioluminiscencia * 0.1 - estabilidad * 0.05
```

### 5.3 Cadenas Tróficas

| Relación | Efecto |
|----------|--------|
| Depredador come presa | -50% población presa, +10% población depredador |
| Presa detecta depredador | +30% huir, +20% esconderse |
| Competencia por recursos | -20% reproducción por competidor |

---

## 6. Terraformación

### 6.1 Parámetros Modificables

| Parámetro | Rango | Costo base |
|-----------|-------|------------|
| Temperatura | -200°C a +500°C | 10 puntos/10°C |
| Atmósfera | 0-100% | 20 puntos/10% |
| Agua | 0-100% | 15 puntos/10% |
| Gravedad | 0.1-3x | 30 puntos/0.1x |
| Radiación | 0-100 | 5 puntos/5 unidades |

### 6.2 Tiempos

| Acción | Tiempo base | Acelerable |
|--------|-------------|------------|
| Cambio menor | 1h | Sí (recursos) |
| Cambio medio | 4h | Sí |
| Cambio mayor | 12h | Sí |
| Crear atmósfera | 24h | Sí |

---

## 7. Economía y Recursos

### 7.1 Recursos del Jugador

| Recurso | Generación | Uso principal |
|---------|------------|---------------|
| Energía Cósmica | +1/tick base | Acciones generales |
| Material Genético | +5/hito | Crear especies |
| Puntos de Conocimiento | +1-15/hito | Árbol de habilidades |
| Tokens Cósmicos | Torneos/logros | Tienda |

### 7.2 Regeneración

| Recurso | Regen base | Cap |
|---------|------------|-----|
| Energía Cósmica | 1/min | 100 |
| Material Genético | 10/día | 50 |

---

## 8. Progresión

### 8.1 Puntos de Conocimiento por Hito

| Hito | Puntos |
|------|--------|
| Nueva especie creada | +1 |
| Nivel evolutivo alcanzado | +2 a +15 |
| Civilización avanzada | +10 |
| Logro especial | +5 a +20 |

### 8.2 Habilidades

| Rama | Nivel 1 | Nivel 2 | Nivel 3 |
|------|---------|---------|----------|
| Viaje | +1 parámetro terraform | +2 parámetros | Teletransporte |
| Genética | Ver NN | Editar personalidad | Herencia lamarckiana |
| Guerra | Análisis | Apuestas | Simulación paralela |
| Gestión | Predicción crisis | Diplomacia | Unificación |
| Cósmica | +10% implosión | Agujeros de gusano | Manipulación cuántica |

### 8.3 Implosión

| Nivel | Bonus | Requisitos |
|-------|-------|------------|
| I | +5% velocidad | 1 implosión |
| II | +10% | 3 implosiones |
| III | +15% | 5 implosiones |
| IV | +20% | 10 implosiones |
| V | +25% | 20 implosiones |

---

## 9. Multijugador

### 9.1 Torneos

> **Referencia operativa:** `docs/40_technical/CÓDIGO CÓSMICO_ Tournament System.md`

| Parámetro | Valor |
|-----------|-------|
| Duración | 7 días |
| Especies por inscripción | 5-10 |
| Combates por simulación | 100 |
| Tiempo simulación | 1-5 min |

### 9.2 Recompensas

| Posición | Tokens | Genes |
|----------|--------|-------|
| 1º | 100% | 1 raro |
| 2º | 75% | - |
| 3º | 50% | - |
| Último | 25% | - |

### 9.3 Banco Genético

| Parámetro | Valor |
|-----------|-------|
| Slots gratuitos | 10 |
| Slots máx | 50 |
| Downloads máximo/día | 20 |

---

## 10. Retención y Engagement

### 10.1 Targets de Balance

| Métrica | Target | Rango aceptable |
|---------|--------|------------------|
| D1 Retention | 45% | 40-50% |
| D7 Retention | 25% | 20-30% |
| D30 Retention | 15% | 10-20% |
| Sessions/día | 3.5 | 2-5 |
| Avg session | 8 min | 5-12 min |

### 10.2 Curve de Dificultad

| Fase | Días | Sensación |
|------|------|-----------|
| Early | 1-10 | Descubrimiento, perdona errores |
| Mid | 11-30 | Caos encadenado, trade-offs claros |
| Late | 31+ | Crisis sistémicas, decisiones duras |

---

## 11. Economía de Moneda

### 11.1 Tienda

| Item | Costo base | Escalado |
|------|------------|----------|
| Acelerador evolución | 50 tokens | +20% por nivel |
| Ranura planeta | 100 tokens | Fijo |
| Gen raro | 200 tokens | Único |
| Cosmético | 50-500 tokens | Variable |

### 11.2 Conversión

| Acción | Tokens |
|--------|--------|
| Victoria torneo | 100-500 |
| Logro milestone | 20-100 |
| Ver anuncio opcional | 5-10 |

---

## 12. Números Prohibidos

- Multiplicadores infinitos
- Bonos permanentes sin coste
- "Reduce a 0" absolutos
- RNG sin explicación
- Stats que excedan 0-100 sin clamp

---

## 13. Testing Recomendado

Antes de lanzar, probar:

1. **Simulación 30 días** - sin decisiones
2. **Simulación 30 días** - malas decisiones
3. **Simulación 30 días** - "optimización"
4. **Playtest** - usuarios reales

El sistema debe:
- Empeorar sin jugador
- Responder a decisiones
- Romperse si se optimiza demasiado

---

## 14. Checklist de Validación

- [ ] Fórmulas de evolución definidas
- [ ] Parámetros de mutación establecidos
- [ ] Variables de ecosistema con rangos
- [ ] Costos de terraformación definidos
- [ ] Sistema de recursos balanceado
- [ ] Progresión de habilidades clara
- [ ] Rewards de torneos proporcionales
- [ ] Targets de retención definidos
- [ ] Números prohibidos respetados
- [ ] Sin contradicciones con otros docs

---

## 15. Declaración Final

**Los valores aquí son puntos de partida. El balance es un proceso continuo que requiere monitoring, feedback y ajustes post-lanzamiento.**

---

**Documento creado bajo sistema CANON**  
**Siguiente: UI/UX Spec**
