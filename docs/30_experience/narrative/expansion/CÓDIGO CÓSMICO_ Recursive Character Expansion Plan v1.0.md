# Recursive Character Expansion Plan v1.0

Proyecto: Codigo Cosmico - Evolucion Profunda  
Version: 1.0  
Estado: Vigente

## 1. Proposito

Escalar el elenco del universo hacia 800 personajes (200 principales y 600 secundarios) con profundidad consistente y trazabilidad canonica.

## 2. Objetivo de volumen

- Principales: 200.
- Secundarios: 600.
- Total: 800.

Regla de calidad:
- Ningun personaje sale de QA sin contradiccion interna, decision dificil y consecuencia rastreable.

## 3. Arquitectura recursiva

La expansion se ejecuta por capas que se retroalimentan:

1. Universo.
2. Galaxia.
3. Sistema.
4. Planeta.
5. Arco temporal.
6. Personaje.

Funcion recursiva por lote:

`Contexto -> Poblacion -> Profundizacion -> Integracion GD -> QA -> Correccion -> Escalado`

## 4. Distribucion macro

Escala cosmologica objetivo:
- 4 universos.
- 20 galaxias (5 por universo).
- 100 sistemas (5 por galaxia).
- 300 planetas (3 por sistema).
- 10 arcos temporales.

## 5. Distribucion de personajes por escala

Principales (200):
- Universo-nivel: 12.
- Galaxia-nivel: 48.
- Sistema-nivel: 80.
- Planeta-nivel: 60.

Secundarios (600):
- Galaxia-nivel: 120.
- Sistema-nivel: 240.
- Planeta-nivel: 240.

## 6. Reparto faccional base

Principales:
- Naturalistas: 36
- Ingenieros: 36
- Colectivo Neural: 36
- Puristas: 36
- Hibridos: 36
- Interfaccionales/sombra: 20

Secundarios:
- Naturalistas: 110
- Ingenieros: 110
- Colectivo Neural: 110
- Puristas: 110
- Hibridos: 110
- Interfaccionales/civiles: 50

## 7. Fases recursivas de ejecucion

### R0 Topologia
- Congelar registries cosmologicos y codigos de localizacion.

### R1 Plantillas
- Aplicar plantillas multiescala por tipo de entidad.

### R2 Poblacion base
- Asignar IDs, faccion, localizacion, arco temporal y rol sistemico.

### R3 Profundizacion
- Inyectar conflicto triple, contradiccion moral y coste irreversible.

### R4 Integracion
- Conectar cada personaje a eventos/cadenas/hooks de GD.

### R5 QA
- Validacion canon, terminologia, causalidad y no contradiccion.

### R6 Cierre
- Trazabilidad en decision log + release notes + gates.

## 8. Definicion de profundidad

Principal:
- 20-24 campos obligatorios.
- 2 rutas de arco posibles.
- 4 relaciones activas minimas.

Secundario:
- 12-14 campos obligatorios.
- 1 decision critica.
- 2 relaciones activas minimas.

## 9. Criterios de aceptacion por personaje

- Tiene identidad biologica y politica definida.
- Tiene conflicto interno no trivial.
- Tiene costo potencial irreversible.
- Tiene impacto en sistema, faccion o region.
- Tiene enlace a al menos un arco temporal.

## 10. Riesgos y mitigacion

Riesgo: volumen sin densidad dramatica.  
Mitigacion: QA por conflicto, no por longitud.

Riesgo: sobreconcentracion en una faccion.  
Mitigacion: cuotas por lote y rebalance automatico.

Riesgo: personajes desconectados del gameplay.  
Mitigacion: hook obligatorio por ficha.

## 11. Trazabilidad

- Canon base: `docs/30_experience/narrative/canon/`.
- Expansion seeds: `docs/30_experience/narrative/expansion/`.
- Decisiones: `docs/00_governance/decisions/decision_log.md`.

## 12. Declaracion final

La escala de personajes en Codigo Cosmico se construye como sistema vivo: no se acumulan nombres, se diseñan nodos de conflicto que alteran el universo.
