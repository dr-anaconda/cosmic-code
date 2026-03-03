# QA Editorial v1.1 — Control de Calidad Documental

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.1  
**Estado:** Borrador  
**Documentos relacionados:**
- `_docs/CANON/04_DOCUMENT_AUTHORING_STANDARD.md`
- `_docs/CANON/07_GATES_AND_ENFORCEMENT.md`
- `_docs/docs/CÓDIGO CÓSMICO_ Localization Spec.md`

---

## 1. Propósito

Establecer un sistema único de QA editorial para validar calidad, consistencia y mantenibilidad de toda la documentación del proyecto antes de cada release documental.

---

## 2. Alcance

Aplica a:

- documentos de producto,
- documentos de diseño,
- documentos operativos,
- diccionarios y especificaciones técnicas.

No reemplaza QA técnico de código ni testing funcional de software.

---

## 3. Dimensiones de Calidad

| Dimensión | Pregunta clave |
|---|---|
| Claridad | ¿se entiende sin contexto adicional? |
| Consistencia | ¿usa términos y criterios uniformes? |
| Completitud | ¿cubre todo lo necesario para su propósito? |
| No redundancia | ¿evita repetir contenido de otros documentos? |
| Trazabilidad | ¿está mapeado a decisiones y fuentes? |
| Operatividad | ¿se puede ejecutar o aplicar en equipo? |

---

## 4. Scorecard QA

Puntuar cada dimensión de 1 a 5:

- 1: crítico
- 2: insuficiente
- 3: aceptable
- 4: bueno
- 5: excelente

### 4.1 Umbral de aprobación

- Ninguna dimensión por debajo de 3.
- Promedio mínimo global: 4.0.

---

## 5. Checklist Base por Documento

- [ ] Título, versión y estado definidos
- [ ] Propósito claro
- [ ] Límites del documento definidos
- [ ] Secciones accionables, no solo descriptivas
- [ ] Riesgos y mitigaciones presentes
- [ ] Checklist de validación incluido
- [ ] Referencias cruzadas correctas
- [ ] Terminología consistente con glosario

---

## 6. Checklist Cross-Doc

- [ ] No contradice PRD
- [ ] No contradice GDD-lite
- [ ] No contradice Balance/Data Dictionary
- [ ] Referencia el documento origen en temas ya cubiertos
- [ ] No duplica bloques troncales

---

## 7. QA de Localización

- [ ] Claves i18n previstas para textos críticos
- [ ] Sin strings hardcodeados en especificaciones runtime
- [ ] Placeholders consistentes
- [ ] Terminología alineada con Localization Spec

Referencia: `_docs/docs/CÓDIGO CÓSMICO_ Localization Spec.md`.

---

## 8. QA de Estilo

Reglas editoriales:

1. Frases directas y concretas.
2. Evitar anglicismos innecesarios.
3. Evitar variaciones del mismo término sin motivo.
4. Evitar secciones sin criterios de aceptación.
5. Mantener tono profesional y consistente con el universo del proyecto.

---

## 9. Flujo de Revisión

1. Autor redacta.
2. Revisor funcional valida contenido.
3. Revisor editorial ejecuta scorecard.
4. Se registran hallazgos y acciones.
5. Se aprueba o retorna a corrección.

### 9.1 Estados

| Estado | Descripción |
|---|---|
| Draft | En redacción |
| In QA | En revisión editorial |
| Changes Requested | Requiere ajustes |
| Approved | Aprobado para release |

---

## 10. Registro de Hallazgos

Formato mínimo por hallazgo:

- ID
- Documento
- Severidad (`minor`, `major`, `critical`)
- Descripción
- Acción correctiva
- Estado

---

## 11. Gate de Release Documental

No se promueve `develop -> main` si:

- existe hallazgo crítico abierto,
- el score global es menor a 4.0,
- hay referencias rotas,
- faltan entradas de decisión para cambios significativos.

---

## 12. Métricas de QA

| Métrica | Objetivo |
|---|---|
| Hallazgos críticos abiertos | 0 |
| Hallazgos mayores por release | <= 5 |
| Tiempo medio de corrección | < 48h |
| Score promedio por documento | >= 4.0 |

---

## 13. Criterios de Aceptación

- [ ] Scorecard definida y usable
- [ ] Checklists base y cross-doc completos
- [ ] Flujo de revisión definido
- [ ] Gate de release documental definido
- [ ] Métricas de QA definidas

---

## 14. Declaración Final

QA editorial v1.1 convierte la documentación en un sistema gobernado: no solo se escribe, también se verifica, se mide y se mejora de forma continua.
