# Orquestador de Coherencia y Balance Transversal

Proyecto: Codigo Cosmico - Evolucion Profunda  
Version: 1.0  
Estado: Vigente

## 1. Proposito

Regular coherencia, dependencias e impacto cruzado entre todos los documentos canonicos de lore y su integracion con game design.

## 2. Alcance

Incluye:
- mapa de Source of Truth por dominio,
- matriz de dependencias,
- scorecard transversal,
- protocolo de arbitraje de contradicciones,
- control de cambios y trazabilidad.

No incluye:
- nuevo lore estructural,
- rebalance numerico profundo de sistemas.

## 3. Variables maestras

- Agencia del jugador.
- Legibilidad causal.
- Riesgo irreversible.
- Misterio util.
- Carga cognitiva por fase.
- Rejugabilidad sin incoherencia.

## 4. Orden de arbitraje

Ante conflicto entre documentos:
1. Reglas del Mundo.
2. Integracion con Game Design.
3. Sistemas Narrativos.
4. Worldbuilding.
5. Vision del Mundo.
6. Cronologia/Facciones/Personajes/Misterios.
7. Moodboard.
8. Glosario (normaliza, no gobierna contenido).

## 5. Scorecard transversal

Umbral:
- PASS >= 4.0 y sin hallazgos criticos abiertos.

Criterios:
- coherencia causal,
- consistencia de limites,
- consistencia terminologica,
- continuidad temporal,
- integracion lore-gameplay,
- calidad de revelacion de misterios.

## 6. Protocolo de cambio

Todo cambio estructural debe registrar:
- documento origen,
- documentos consumidores afectados,
- riesgo,
- mitigacion,
- decision log asociado.

## 7. Gestion de gaps

Los gaps de lore se registran en:
- `docs/60_open-questions/lore-gaps-log.md`.

Severidad:
- A0 bloquea,
- A1 frena release,
- A2 deuda.

## 8. Cierre de lote

Requisitos minimos:
- trazabilidad completa,
- release notes actualizadas,
- gates en PASS,
- score transversal en umbral.

## Trazabilidad

- Decisiones: `docs/00_governance/decisions/decision_log.md` (DEC-0054).
- Lore gaps: `docs/60_open-questions/lore-gaps-log.md`.
- Plantilla de revision por lote: `docs/00_governance/canon/templates/REVIEW_TRANSVERSAL_LOTE_TEMPLATE.md`.
- Release documental: `docs/00_governance/release-notes/CÓDIGO CÓSMICO_ Release Notes.md`.

## 9. Declaracion final

Este orquestador protege la integridad del corpus: impide deriva, ordena prioridades y mantiene un universo coherente bajo expansion continua.
