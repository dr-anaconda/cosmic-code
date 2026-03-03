# Localization Spec — Internacionalización y Calidad Lingüística

**Proyecto:** Código Cósmico – Evolución Profunda  
**Versión:** 1.0  
**Estado:** Borrador  
**Documentos relacionados:**
- `docs/30_experience/CÓDIGO CÓSMICO_ UI_UX.md`
- `docs/30_experience/CÓDIGO CÓSMICO_ Event & Content Bible.md`
- `docs/00_governance/qa/CÓDIGO CÓSMICO_ QA Editorial v1.1.md`

---

## 1. Propósito

Definir el sistema de localización del proyecto para garantizar:

1. coherencia terminológica entre idiomas,
2. calidad narrativa equivalente,
3. velocidad de actualización de textos,
4. escalabilidad para nuevas regiones.

Este documento cubre i18n y l10n de contenido, UI y mensajes de sistema. No cubre compliance legal regional profunda.

---

## 2. Alcance y Prioridad de Idiomas

### 2.1 Idiomas objetivo

| Fase | Idioma | Código |
|---|---|---|
| Lanzamiento | Español | `es-ES` |
| Lanzamiento | Inglés | `en-US` |
| Fase 2 | Portugués Brasil | `pt-BR` |
| Fase 2 | Japonés | `ja-JP` |

### 2.2 Política de expansión

- No añadir nuevo idioma sin glosario validado.
- No publicar traducción parcial de flujo crítico.
- Priorizar cobertura completa de onboarding y eventos de alto impacto.

---

## 3. Arquitectura i18n

### 3.1 Estructura de claves

Formato recomendado:

`dominio.seccion.elemento.contexto`

Ejemplos:

- `ui.dashboard.header.day_label`
- `event.eco.collapse.title`
- `tournament.league.bronze.description`

Reglas:

- Sin claves ambiguas (`title1`, `misc_text`).
- Sin copiar texto fuente como clave.
- Mantener claves estables entre versiones.

### 3.2 Organización de archivos

```text
app/locales/
  es-ES.json
  en-US.json
  pt-BR.json
  ja-JP.json
```

Por ahora se define la convención; la implementación de runtime está en arquitectura técnica.

---

## 4. Estilo Lingüístico por Idioma

### 4.1 Español

- Registro claro y técnico accesible.
- Tono cósmico, observacional.
- Evitar barroquismo en UI de acción rápida.

### 4.2 Inglés

- Conciso y directo.
- Terminología científica consistente.
- Evitar idioms difíciles de trasladar.

### 4.3 Reglas globales

- Mantener intención original, no traducción literal ciega.
- Conservar placeholders y variables sin alterar.
- Ajustar longitud para UI móvil.

---

## 5. Glosario Maestro

| Término canon | es-ES | en-US | Nota |
|---|---|---|---|
| Implosión | Implosión | Implosion Cycle | término núcleo |
| Tokens Cósmicos | Tokens Cósmicos | Cosmic Tokens | moneda principal |
| Banco Genético | Banco Genético | Genetic Bank | sistema social |
| Estabilidad | Estabilidad | Stability | métrica ecosistema |
| Colapso | Colapso | Collapse Event | evento crítico |

Regla: cualquier término nuevo entra al glosario antes de llegar a producción.

---

## 6. Placeholders y Variables

### 6.1 Formato permitido

- `%{variable}`
- `{variable}`

Ejemplo:

`"Has alcanzado el día %{day} en %{planet_name}"`

### 6.2 Reglas

- No traducir nombre de placeholder.
- Respetar orden cuando el idioma lo exija.
- Permitir pluralización contextual.

---

## 7. Pluralización y Género

### 7.1 Pluralización

Definir variantes por idioma:

- `one`
- `other`

Ejemplo:

```json
{
  "event.pending": {
    "one": "Tienes 1 evento pendiente",
    "other": "Tienes %{count} eventos pendientes"
  }
}
```

### 7.2 Género y neutralidad

- Priorizar formulaciones neutrales cuando sea natural.
- Evitar construcciones que no escalen a otros idiomas.

---

## 8. Reglas de UI Localizada

1. Diseñar componentes para expansión de texto del 30%.
2. No truncar textos críticos sin fallback.
3. Botones CTA deben mantener legibilidad en pantallas pequeñas.
4. Mensajes de error deben estar localizados y accionables.

### 8.1 Presupuesto de longitud

| Tipo de texto | Presupuesto recomendado |
|---|---|
| Botón | 8-20 caracteres |
| Título de card | 20-55 caracteres |
| Resumen evento | 60-140 caracteres |
| Toast | 30-90 caracteres |

---

## 9. Pipeline de Localización

1. Redacción fuente (es-ES)
2. Validación editorial
3. Extracción de claves
4. Traducción por idioma
5. QA lingüística y QA UI
6. Integración y release

### 9.1 Reglas operativas

- No aceptar traducciones sin revisión humana.
- Versionar cambios por lote.
- Mantener changelog de textos críticos.

---

## 10. QA de Localización

Checklist por build:

- [ ] No hay claves faltantes.
- [ ] No hay placeholders rotos.
- [ ] No hay hardcoded strings en flujo principal.
- [ ] UI no se rompe por expansión de texto.
- [ ] Terminología coincide con glosario.

Métricas objetivo:

| Métrica | Objetivo |
|---|---|
| Claves faltantes por build | 0 |
| Errores de placeholder | 0 |
| Bugs de overflow de texto | < 1% de pantallas críticas |
| Incidencias terminológicas | < 3 por release |

---

## 11. Riesgos y Mitigaciones

| Riesgo | Mitigación |
|---|---|
| Inconsistencia terminológica | glosario maestro obligatorio |
| Coste alto de traducción | priorización por criticidad |
| Bugs de UI por texto largo | QA visual multiidioma |
| Retrasos de release | congelar texto antes de cut-off |

---

## 12. Criterios de Aceptación

- [ ] Idiomas de lanzamiento definidos
- [ ] Convención de claves definida
- [ ] Glosario inicial definido
- [ ] Pipeline operativo documentado
- [ ] QA y métricas definidas
- [ ] Sin contradicciones con UI/UX y Event Bible

---

## 13. Declaración Final

La localización en Código Cósmico no es traducción tardía: es un sistema de diseño lingüístico que protege claridad, tono y jugabilidad en todos los idiomas objetivo.
