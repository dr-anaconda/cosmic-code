# Monetization Spec — Especificación de Monetización Ética

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/docs/CÓDIGO CÓSMICO_ PRD.md`
- `_docs/docs/CÓDIGO CÓSMICO_ GDD-lite.md`
- `_docs/docs/CÓDIGO CÓSMICO_ System Balance Sheet.md`

---

## 1. Propósito

Definir el sistema económico de monetización del juego bajo tres límites no negociables:

1. Sin pay-to-win.
2. Sin fricción abusiva para progresar.
3. Con transparencia de valor para el jugador.

Este documento cubre catálogo, precios, anuncios opcionales, experimentación económica y guardrails de diseño.

---

## 2. Principios Rectores

### 2.1 Lo que sí monetizamos

- Cosméticos
- Comodidad de gestión
- Aceleración limitada no determinante
- Contenido estético de temporada

### 2.2 Lo que nunca monetizamos

- Victoria en torneos
- Ventaja estadística exclusiva en PvP
- Bloqueo de mecánicas troncales detrás de pago
- RNG opaco con probabilidad oculta

### 2.3 Regla de equivalencia

Si un recurso premium da ventaja de tiempo, debe existir vía de obtención por juego normal con esfuerzo razonable.

---

## 3. Arquitectura de Monedas

| Moneda | Tipo | Origen | Uso |
|---|---|---|---|
| Tokens Cósmicos | Principal | Juego + torneos + compras | Tienda general |
| Créditos de Laboratorio | Progresión | Gameplay | Sistemas internos |
| Fragmentos Estéticos | Temporada | Pase/eventos | Cosméticos |

Reglas:

- Los torneos premian tokens no premium.
- Los tokens comprados y ganados comparten valor de uso.
- No existen monedas duplicadas con conversión confusa.

---

## 4. Catálogo de Tienda

### 4.1 Categorías

1. **Cosméticos**
   - skins de UI
   - efectos de planeta
   - marcos de perfil

2. **Comodidad**
   - slots extra de carga
   - presets de laboratorio
   - filtros avanzados

3. **Aceleración limitada**
   - boosts de tiempo con tope diario
   - tickets de reintento (no en ranking)

4. **Temporada**
   - pase de temporada
   - bundle temático

### 4.2 Matriz de legalidad de ítems

| Ítem | Permitido | Justificación |
|---|---|---|
| Skin visual | Sí | Estético |
| Slot adicional de banco | Sí | Comodidad |
| Acelerador diario capado | Sí | No rompe competencia |
| Gen exclusivo con mejor estadística | No | Pay-to-win |
| Multiplicador de MMR | No | Rompe integridad |

---

## 5. Diseño de Precios

### 5.1 Bandas de precio

| Banda | Precio referencia | Tipo de producto |
|---|---:|---|
| Micro | 0.99-2.99 | cosmético simple |
| Medio | 3.99-7.99 | pack de comodidad |
| Alto | 9.99-19.99 | bundle de temporada |

### 5.2 Reglas de pricing

- Máximo 1 bundle destacado por semana.
- No más de 3 pop-ups comerciales por sesión.
- No usar countdown falso.
- Mostrar ahorro real vs compra separada.

### 5.3 Regionalización

- Aplicar precios por región vía storefront.
- Revisar PPP trimestral.
- Evitar anclas de precio engañosas entre regiones.

---

## 6. Pase de Temporada

### 6.1 Estructura

| Track | Acceso | Contenido |
|---|---|---|
| Free | Todos | recursos base + cosméticos menores |
| Premium | Pago | cosméticos exclusivos + comodidad |

### 6.2 Reglas

- El track free debe ser atractivo por sí mismo.
- El premium no otorga poder competitivo exclusivo.
- Recompensas de temporada deben tener identidad visual clara.

---

## 7. Anuncios con Recompensa

### 7.1 Política de anuncios

- Solo opt-in.
- Nunca interrumpir combate ni flujo crítico.
- Máximo de visualizaciones recompensadas por día.

### 7.2 Recompensas permitidas

| Recompensa | Límite |
|---|---|
| Tokens básicos | bajo |
| Aceleración temporal corta | capada |
| Reintento no competitivo | limitado |

### 7.3 Recompensas prohibidas

- MMR
- Recompensas exclusivas de ranking
- Recursos premium de alto impacto sin tope

---

## 8. Guardrails Anti Pay-to-Win

Checklist de validación por nuevo ítem:

- [ ] ¿Da ventaja directa en ranking?
- [ ] ¿Excluye a jugadores no pagadores?
- [ ] ¿Rompe equilibrio temporal del loop?
- [ ] ¿Tiene alternativa jugable razonable?

Si cualquier respuesta es "sí" en las dos primeras, el ítem se rechaza.

---

## 9. Experimentación Económica

### 9.1 Qué se puede testear

- Precio de cosméticos
- Orden de oferta en tienda
- Bundle composition
- Fricción de checkout

### 9.2 Qué no se puede testear

- Ventaja competitiva por pago
- Probabilidades opacas en monetización
- Cambios de valor sin comunicación

### 9.3 Métricas de experimento

| Métrica | Objetivo |
|---|---|
| Conversión a pago | > 3% |
| ARPPU | >= objetivo PRD |
| Rechazo de oferta | controlado |
| Quejas de justicia | < 2% |

---

## 10. Integración con Competitivo

Reglas de separación:

1. La tienda no altera el resultado determinista de torneos.
2. Recompensas de pago no modifican MMR.
3. Beneficios de comodidad no cambian poder base de especie.

Referencias:
- `_docs/docs/CÓDIGO CÓSMICO_ Tournament System.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Multiplayer Spec.md`

---

## 11. Riesgos y Mitigaciones

| Riesgo | Mitigación |
|---|---|
| Percepción de monetización agresiva | límites de exposición + transparencia |
| Inflación de moneda | sumideros equilibrados + caps diarios |
| Canibalización del track free | contenido free robusto por temporada |
| Efecto pay-to-win percibido | auditoría de ítems y matriz de legalidad |

---

## 12. Operación y Gobernanza

### 12.1 Cadencia de revisión

- Revisión semanal de KPIs comerciales.
- Revisión quincenal de fairness.
- Revisión mensual de pricing regional.

### 12.2 Roles

| Rol | Responsabilidad |
|---|---|
| Product | estrategia económica |
| Game Design | impacto sistémico |
| Data | experimentación y resultados |
| Community | percepción de justicia |

---

## 13. Criterios de Aceptación

- [ ] Catálogo completo y segmentado
- [ ] Matriz de legalidad definida
- [ ] Reglas de anuncios opt-in definidas
- [ ] Guardrails anti pay-to-win operativos
- [ ] Métricas económicas y de fairness definidas
- [ ] Sin contradicciones con PRD, Balance y Multiplayer

---

## 14. Declaración Final

La monetización de Código Cósmico debe sostener el producto sin comprometer la integridad competitiva ni la confianza del jugador. Rentabilidad y justicia deben escalar juntas.
