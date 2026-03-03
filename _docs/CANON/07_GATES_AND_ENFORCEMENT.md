# Gates de Cumplimiento

Version: 1.1

## Objetivo

Asegurar que el sistema de trabajo se cumpla siempre mediante puntos de control obligatorios.

## Gate 0 - Insumos validos

Condicion:

- Existe material base suficiente para analizar.

Bloquea si:

- No hay fuentes o son insuficientes para tomar decisiones.

## Gate 1 - Fase 0 completada

Condicion:

- Analisis con fortalezas, lagunas y riesgos finalizado.

Bloquea si:

- Se intenta abrir ronda sin mapa de ambiguedades.

## Gate 2 - Ronda activa con formato canonico

Condicion:

- Preguntas con 4 opciones + opcion abierta.

Bloquea si:

- Formato incompleto o preguntas no accionables.

## Gate 3 - Confirmacion por pregunta

Condicion:

- Cada respuesta tiene recapitulacion e integracion.

Bloquea si:

- Se avanza sin confirmar interpretacion.

## Gate 4 - Ronda cerrada

Condicion:

- Resumen final de decisiones del documento.

Bloquea si:

- Quedan dudas criticas sin resolver.

## Gate 5 - Redaccion autorizada

Condicion:

- Solo decisiones confirmadas alimentan el documento.

Bloquea si:

- Se agrega contenido no decidido.

## Gate 6 - Trazabilidad completa

Condicion:

- El documento mapea secciones clave a decisiones registradas.

Bloquea si:

- No hay trazabilidad entre ronda y contenido final.

## Gate 7 - DoD aprobado

Condicion:

- Checklist de finalizacion en estado pass.

Bloquea si:

- Falta validacion de calidad y coherencia.

## Gate 8 - Transicion controlada

Condicion:

- Cierre de fase y propuesta de siguiente documento.

Bloquea si:

- Se salta de documento sin cierre formal.

## Politica de enforcement

- Un gate en fail impide continuar.
- Todo fail debe incluir causa y accion correctiva.
- No se permite bypass sin excepcion documentada.
