# KPI Narrativos Operativos

Proyecto: Codigo Cosmico - Evolucion Profunda  
Version: 1.1  
Estado: Vigente

## 1. Proposito

Definir indicadores narrativos medibles para cerrar el bucle entre diseno de lore, experiencia de jugador y QA editorial.

## 2. KPI canonicos

### KPI-01 Claridad causal percibida
- Definicion: porcentaje de jugadores que declaran entender por que ocurrio un evento critico.
- Formula: respuestas positivas en encuesta post-evento / total respuestas.
- Objetivo: >= 80%.
- Alerta: < 70%.

### KPI-02 Eventos ignorados por sesion
- Definicion: proporcion de eventos narrativos no abiertos ni resueltos.
- Formula: eventos ignorados / eventos mostrados.
- Objetivo: <= 20%.
- Alerta: > 30%.

### KPI-03 Repeticion percibida de contenido
- Definicion: percepcion de repeticion en loops narrativos.
- Formula: encuesta de repeticion alta / total respuestas.
- Objetivo: <= 15%.
- Alerta: > 25%.

### KPI-04 Tasa de resolucion de eventos de tension
- Definicion: porcentaje de eventos S3+ resueltos activamente por el jugador.
- Formula: eventos S3+ resueltos / eventos S3+ activados.
- Objetivo: >= 75%.
- Alerta: < 60%.

### KPI-05 Divergencia inter-run
- Definicion: porcentaje de partidas con al menos dos hitos narrativos distintos frente a la run anterior.
- Formula: runs con divergencia >= 2 / total runs comparables.
- Objetivo: >= 65%.
- Alerta: < 50%.

### KPI-06 Coherencia terminologica editorial
- Definicion: incidencias QA por uso de termino no canonico en documentos/eventos.
- Formula: incidencias terminologicas / lote.
- Objetivo: <= 3 por lote.
- Alerta: > 6 por lote.

### KPI-07 Retencion por narrativa (D7)
- Definicion: retorno de jugadores que activaron al menos un arco narrativo relevante.
- Formula: usuarios narrativamente activos que vuelven en D7 / usuarios narrativamente activos en D0.
- Objetivo: >= 25%.
- Alerta: < 18%.

### KPI-08 Señales previas a irreversibilidad
- Definicion: porcentaje de decisiones irreversibles precedidas por alerta valida.
- Formula: decisiones irreversibles con alerta / total irreversibles.
- Objetivo: 100%.
- Alerta: < 98%.

## 3. Cadencia de revision

- Revision semanal de tendencia.
- Revision por release narrativo.
- Gate de bloqueo si KPI-08 cae por debajo de umbral.

## 4. Integracion con QA transversal

Este documento alimenta:
- `docs/00_governance/canon/templates/REVIEW_TRANSVERSAL_LOTE_TEMPLATE.md`.
- `docs/00_governance/qa/CÓDIGO CÓSMICO_ Narrative Canon Scorecard v1.1.md`.

## 5. Declaracion final

Lo narrativo tambien se balancea con datos: estos KPI convierten la calidad percibida del lore en una disciplina verificable y accionable.
