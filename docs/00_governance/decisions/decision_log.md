# Decision Log

Version: 1.0  
Proyecto: Código Cósmico – Evolución Profunda

---

## Entradas

### DEC-0001

- Fecha: 2026-03-03
- Documento afectado: Sistema CANON
- Pregunta origen: ¿Qué nivel de rigor prefieres para el sistema CANON?
- Opciones elegidas: Equilibrado
- Respuesta abierta: -
- Regla resultante: Sistema adaptado - 4 opciones por pregunta (no 6), max 5 preguntas críticas por doc, 5 gates combinados, decisiones maestras para temas transversales
- Impacto esperado: Balance entre rigor y agilidad para proyecto de 12+ documentos
- Estado: confirmada

### DEC-0002

- Fecha: 2026-03-03
- Documento afectado: Plan de documentación
- Pregunta origen: ¿Cuántos documentos finales calculas?
- Opciones elegidas: ~8-10 documentos → luego expandido a 12+
- Respuesta abierta: -
- Regla resultante: 12+ documentos incluyendo: PRD, GDD-lite, Core Loops, Data Dictionary, System Balance, UI/UX, ADD, Event & Content Bible, Tournament System, Monetization Spec, Multiplayer Spec, Localization
- Impacto esperado: Documentación completa y detallada
- Estado: confirmada

### DEC-0003

- Fecha: 2026-03-03
- Documento afectado: PRD
- Pregunta origen: ¿Cuál es el objetivo principal del PRD?
- Opciones elegidas: Visión de producto y KPIs (no requisitos técnicos)
- Respuesta abierta: -
- Regla resultante: PRD enfoca en visión, público, métricas de éxito y alcance MVP - no en features técnicas. Los detalles de diseño referencian GDD existente.
- Impacto esperado: Documento estratégico sin redundancia con GDD
- Estado: confirmada

### DEC-0004

- Fecha: 2026-03-03
- Documento afectado: Documentación general
- Pregunta origen: ¿Cómo gestionamos las redundancias entre documentos?
- Opciones elegidas: Referenciar, no redundar
- Respuesta abierta: -
- Regla resultante: Todo tema ya cubierto en GDD o docs anteriores se menciona por referencia, no se desarrolla de nuevo. Excepción: si se necesita ampliar o actualizar.
- Impacto esperado: Documentos coherentes sin contradicciones ni repeticiones
- Estado: confirmada

---

## Decisiones Maestras (Cross-Doc)

### MAESTRA-001

- Fecha: 2026-03-03
- Ámbito: Todos los documentos
- Pregunta: ¿Cuál es la fuente de verdad para diseño del juego?
- Decisión: El documento `init/GDD_ CÓDIGO CÓSMICO – EVOLUCIÓN PROFUNDA.md` es la referencia primaria. Los nuevos documentos no contradicen ni repiten - referencian.
- Estado: vigente

### MAESTRA-002

- Fecha: 2026-03-03
- Ámbito: Git workflow
- Pregunta: ¿Cómo estructuramos commits y PRs?
- Decisión: Rama develop → feature/docs-[nombre] → PR → merge. Commits: `docs: [doc] - [descripción]`
- Estado: pendiente de config GitHub

### DEC-0005

- Fecha: 2026-03-03
- Documento afectado: GDD-lite
- Pregunta origen: ¿Cuál es el principio rector más importante del juego?
- Opciones elegidas: Consecuencialismo visible
- Regla resultante: Toda decisión tiene consecuencias visibles y comprensibles. El jugador nunca debe preguntarse "por qué pasó eso".
- Impacto esperado: Mecánicas diseñadas para ser comprensibles y trazables
- Estado: confirmada

### DEC-0006

- Fecha: 2026-03-03
- Documento afectado: GDD-lite
- Pregunta origen: ¿Cómo definimos el fallo divertido?
- Opciones elegidas: Colapsos como narrativa
- Regla resultante: Los fracasos son contenido, no castigos. Colapsos generan historia y aprendizaje, no Game Over.
- Impacto esperado: Sistema resiliente donde el jugador siempre puede recuperarse
- Estado: confirmada

### DEC-0007

- Fecha: 2026-03-03
- Documento afectado: GDD-lite
- Pregunta origen: ¿Cuál es el ritmo esperado del juego?
- Opciones elegidas: Híbrido idle-táctico
- Regla resultante: Sesiones de 5-15 min con decisiones tácticas, evolución continua en background. Tick determinista.
- Impacto esperado: UX que combina espera idle con engagement táctico
- Estado: confirmada

### DEC-0008

- Fecha: 2026-03-03
- Documento afectado: GDD-lite
- Pregunta origen: ¿Qué excluimos del GDD-lite?
- Opciones elegidas: Todo lo técnico separado
- Regla resultante: GDD-lite solo tiene filosofía y reglas. Datos técnicos van a System Balance, UI a UI/UX, etc.
- Impacto esperado: Documentos no redundantes, cada uno con propósito claro
- Estado: confirmada

### DEC-0009

- Fecha: 2026-03-03
- Documento afectado: Core Loops
- Pregunta origen: ¿Cuántos loops principales definimos?
- Opciones elegidas: 5 loops
- Regla resultante: Inmediato, Sesión, Progresión, Meta, Social
- Impacto esperado: Cobertura completa de experiencia de juego
- Estado: confirmada

### DEC-0010

- Fecha: 2026-03-03
- Documento afectado: Core Loops
- Pregunta origen: ¿Cuál es el loop más importante para retención?
- Opciones elegidas: Progresión
- Regla resultante: L3 (Progresión/Evolución) es el corazón de retención
- Impacto esperado: Focus en diseño de progresión como prioridad
- Estado: confirmada

### DEC-0011

- Fecha: 2026-03-03
- Documento afectado: Core Loops
- Pregunta origen: ¿Cuál es la duración esperada de cada loop?
- Opciones elegidas: Mixto (corto para casuales, largo para hardgamers)
- Regla resultante: Sesiones cortas (5-8 min) + sesiones largas (20-40 min) según perfil
- Impacto esperado: UX adaptativa para diferentes tipos de jugador
- Estado: confirmada

### DEC-0012

- Fecha: 2026-03-03
- Documento afectado: UI/UX Spec
- Pregunta origen: ¿Cuál es el enfoque de diseño principal?
- Opciones elegidas: Mobile-first
- Regla resultante: Diseñar para móvil primero, escalar a desktop
- Impacto esperado: UX optimizada para móvil, adaptación desktop secondary
- Estado: confirmada

### DEC-0013

- Fecha: 2026-03-03
- Documento afectado: UI/UX Spec
- Pregunta origen: ¿Cuál es la dirección visual?
- Opciones elegidas: Cósmica orgánica
- Regla resultante: Combinación de espacio vasto con vida orgánica - gradientes oscuros, formas orgánicas + geométricas, acentos teal y violeta
- Impacto esperado: Identidad visual coherente
- Estado: confirmada

### DEC-0014

- Fecha: 2026-03-03
- Documento afectado: ADD
- Pregunta origen: ¿Qué tecnología principal?
- Opciones elegidas: Web stack
- Regla resultante: Next.js + React Native, Node.js, PostgreSQL, Redis
- Impacto esperado: Stack moderno, escalable, código compartido
- Estado: confirmada

### DEC-0015

- Fecha: 2026-03-03
- Documento afectado: System Balance Sheet
- Pregunta origen: ¿Qué nivel de detalle en fórmulas y números?
- Opciones elegidas: Clave
- Regla resultante: Solo fórmulas clave, ratios y umbrales principales
- Impacto esperado: Documento usable como referencia de balance
- Estado: confirmada

### DEC-0016

- Fecha: 2026-03-03
- Documento afectado: Data Dictionary
- Pregunta origen: ¿Qué nivel de detalle necesitamos?
- Opciones elegidas: Resumido
- Regla resultante: Entidades principales con campos clave
- Impacto esperado: Schema claro sin excesos
- Estado: confirmada

### DEC-0017

- Fecha: 2026-03-03
- Documento afectado: CANON (protocolo global)
- Pregunta origen: ¿Mantener rigor completo o adaptar equilibrio?
- Opciones elegidas: Equilibrado
- Regla resultante: Rondas con 4 opciones + opcion abierta, maximo 5 preguntas criticas por documento
- Impacto esperado: Menos friccion operativa y mayor velocidad de produccion
- Estado: confirmada

### DEC-0018

- Fecha: 2026-03-03
- Documento afectado: Documentacion cross-doc
- Pregunta origen: ¿Como evitar redundancia entre documentos?
- Opciones elegidas: Referenciar, no duplicar
- Regla resultante: Cada documento referencia el origen del tema ya tratado y evita redeclarar contenido estructural
- Impacto esperado: Mayor consistencia, menor ruido y menor deuda editorial
- Estado: confirmada

### DEC-0019

- Fecha: 2026-03-03
- Documento afectado: Tournament System
- Pregunta origen: ¿Que formato competitivo priorizamos para la Tanda 2?
- Opciones elegidas: Ligas semanales asíncronas con MMR
- Regla resultante: El sistema competitivo usa temporadas semanales, ligas por rango y emparejamiento asíncrono con simulación por lotes
- Impacto esperado: Competencia constante sin dependencia de tiempo real
- Estado: confirmada

### DEC-0020

- Fecha: 2026-03-03
- Documento afectado: Monetization Spec
- Pregunta origen: ¿Cual es el limite central de monetizacion?
- Opciones elegidas: Monetizacion etica sin pay-to-win
- Regla resultante: Se monetizan cosmeticos, comodidad y aceleracion limitada; se prohiben ventajas competitivas exclusivas por pago
- Impacto esperado: Sostenibilidad economica con integridad competitiva
- Estado: confirmada

### DEC-0021

- Fecha: 2026-03-03
- Documento afectado: Multiplayer Spec
- Pregunta origen: ¿Como debe operar el multijugador?
- Opciones elegidas: Asincrono por contrato y colas
- Regla resultante: Interacciones sociales y competitivas se resuelven en diferido con trazabilidad y controles anti-exploit
- Impacto esperado: Escalabilidad y accesibilidad para distintos husos horarios
- Estado: confirmada

### DEC-0022

- Fecha: 2026-03-03
- Documento afectado: Cross-doc alignment
- Pregunta origen: ¿Como evitar duplicidad entre Tournament y Multiplayer?
- Opciones elegidas: Separacion por responsabilidad
- Regla resultante: Tournament define ligas/MMR/rewards semanales; Multiplayer define banco genetico, contratos sociales, sondas e integridad general
- Impacto esperado: Documentos complementarios sin superposicion estructural
- Estado: confirmada

### DEC-0023

- Fecha: 2026-03-03
- Documento afectado: Localization Spec
- Pregunta origen: ¿Que prioridad de idiomas aplicamos?
- Opciones elegidas: es-ES y en-US en lanzamiento; pt-BR y ja-JP en fase 2
- Regla resultante: No se publica un idioma nuevo sin glosario validado y cobertura de flujos criticos
- Impacto esperado: Expansión internacional controlada y sostenible
- Estado: confirmada

### DEC-0024

- Fecha: 2026-03-03
- Documento afectado: Event & Content Bible
- Pregunta origen: ¿Como operamos contenido de eventos en v1.1?
- Opciones elegidas: Pipeline editorial + operación semanal + integración con localización
- Regla resultante: Se incorporan estados de contenido, versionado, runbook de incidentes y validaciones i18n
- Impacto esperado: Menor deuda editorial y mayor estabilidad de releases de contenido
- Estado: confirmada

### DEC-0025

- Fecha: 2026-03-03
- Documento afectado: QA Editorial v1.1
- Pregunta origen: ¿Que gate define salida documental a main?
- Opciones elegidas: Score minimo 4.0 sin hallazgos criticos abiertos
- Regla resultante: Release documental bloqueado si no cumple scorecard, referencias y trazabilidad
- Impacto esperado: Mejora sostenida de calidad documental
- Estado: confirmada

### DEC-0026

- Fecha: 2026-03-03
- Documento afectado: Data Dictionary Complete
- Pregunta origen: ¿Que nivel de detalle debe tener la version completa?
- Opciones elegidas: Especificacion persistente operable
- Regla resultante: Incluir tipos, restricciones, indices, relaciones y reglas de integridad por dominio
- Impacto esperado: Puente directo entre diseño y backend
- Estado: confirmada

### DEC-0027

- Fecha: 2026-03-03
- Documento afectado: Document Index
- Pregunta origen: ¿Como reducimos friccion de navegacion documental?
- Opciones elegidas: Mapa maestro de lectura y dependencias
- Regla resultante: Crear indice central con ruta recomendada, roles y anti-duplicacion por documento
- Impacto esperado: Mejor onboarding del equipo y menos inconsistencias
- Estado: confirmada

### DEC-0028

- Fecha: 2026-03-03
- Documento afectado: Release Notes
- Pregunta origen: ¿Como versionamos cambios documentales?
- Opciones elegidas: Release notes persistentes por version
- Regla resultante: Cada lote documental debe registrar Added/Changed/Impact y fecha
- Impacto esperado: Trazabilidad historica clara para auditoria y mantenimiento
- Estado: confirmada

### DEC-0029

- Fecha: 2026-03-03
- Documento afectado: Implementation Readiness Pack v1.3
- Pregunta origen: ¿Como pasamos de documentacion a ejecucion?
- Opciones elegidas: Pack de readiness con DoR/DoD, RACI y criterios Go/No-Go
- Regla resultante: Ningun bloque entra a build sin entry criteria y ownership definido
- Impacto esperado: Arranque tecnico controlado y menos ambigüedad operativa
- Estado: confirmada

### DEC-0030

- Fecha: 2026-03-03
- Documento afectado: Technical Milestones Plan v1.3
- Pregunta origen: ¿Que secuencia de entrega minimiza riesgo?
- Opciones elegidas: M0..M6 incremental con gates de salida
- Regla resultante: La ejecucion tecnica avanza por hitos secuenciales con criterios de salida obligatorios
- Impacto esperado: Mayor previsibilidad de plazos y calidad
- Estado: confirmada

### DEC-0031

- Fecha: 2026-03-03
- Documento afectado: Implementation Risk Matrix v1.3
- Pregunta origen: ¿Como gobernamos riesgos de implementacion?
- Opciones elegidas: Matriz priorizada con score, mitigacion y contingencia
- Regla resultante: Riesgos con score >=15 escalan a comite tecnico semanal
- Impacto esperado: Reduccion de sorpresas de alto impacto en fases de build
- Estado: confirmada

### DEC-0032

- Fecha: 2026-03-03
- Documento afectado: Execution Backlog v1.4
- Pregunta origen: ¿Como aterrizamos hitos en trabajo diario?
- Opciones elegidas: Epics por hito + historias con prioridad, talla y dependencia
- Regla resultante: Cada hito M0..M6 debe mapear historias P0/P1 con criterios de aceptacion
- Impacto esperado: Planificacion semanal ejecutable y trazable
- Estado: confirmada

### DEC-0033

- Fecha: 2026-03-03
- Documento afectado: Sprint 0 Kickoff Checklist v1.4
- Pregunta origen: ¿Que condicion habilita iniciar implementacion?
- Opciones elegidas: Checklist obligatoria de equipo, entorno, backlog y riesgo
- Regla resultante: Sprint 0 solo inicia con items P0 completos y aprobacion Product + Tech
- Impacto esperado: Reduccion de deuda tecnica temprana
- Estado: confirmada

### DEC-0034

- Fecha: 2026-03-03
- Documento afectado: Document governance v1.4
- Pregunta origen: ¿Como versionamos el arranque de ejecucion?
- Opciones elegidas: Update en index + release notes + decision log
- Regla resultante: Toda nueva capa de ejecucion debe reflejarse en mapa documental y release notes
- Impacto esperado: Coherencia de gobernanza y mejor onboarding del equipo
- Estado: confirmada

### DEC-0035

- Fecha: 2026-03-03
- Documento afectado: Sprint 0 Active Pack v1.5
- Pregunta origen: ¿Como operamos Sprint 0 dia a dia?
- Opciones elegidas: Pack activo con KPIs, criterios de exito/fracaso y contingencia
- Regla resultante: Sprint 0 requiere objetivos no negociables y seguimiento diario con umbrales claros
- Impacto esperado: Mayor control de ejecución en arranque técnico
- Estado: confirmada

### DEC-0036

- Fecha: 2026-03-03
- Documento afectado: Sprint 0 Board v1.5
- Pregunta origen: ¿Como visualizamos trabajo activo de arranque?
- Opciones elegidas: Tablero semanal por estados con WIP y regla de bloqueos
- Regla resultante: Tareas P0/P1 se gestionan con límites de trabajo en curso y escalado por tiempo bloqueado
- Impacto esperado: Flujo de trabajo más estable y predecible
- Estado: confirmada

### DEC-0037

- Fecha: 2026-03-03
- Documento afectado: Execution Ownership Matrix v1.5
- Pregunta origen: ¿Como evitamos zonas grises de responsabilidad?
- Opciones elegidas: Matriz de ownership por flujo y regla de escalado
- Regla resultante: Toda tarea P0 debe tener Responsible/Accountable explícitos y ETA
- Impacto esperado: Menos bloqueos por falta de dueño y mejor accountability
- Estado: confirmada

### DEC-0038

- Fecha: 2026-03-03
- Documento afectado: Start Build Now Pack v1.6
- Pregunta origen: ¿Como activamos construccion inmediata sin perder control?
- Opciones elegidas: Paquete de activacion con T-0, reglas diarias y criterios de salida de semana 1
- Regla resultante: Se define una activacion formal previa a build con umbrales y anti-patrones
- Impacto esperado: Menor friccion de inicio y mayor previsibilidad de sprint
- Estado: confirmada

### DEC-0039

- Fecha: 2026-03-03
- Documento afectado: Week 1 Execution Order v1.6
- Pregunta origen: ¿Que secuencia minimiza riesgo en primera semana?
- Opciones elegidas: Orden diario D1..D5 con prioridad por dependencias
- Regla resultante: Se prioriza estabilidad de pipeline y contratos antes de expansion de alcance
- Impacto esperado: Arranque tecnico controlado y menos retrabajo
- Estado: confirmada

### DEC-0040

- Fecha: 2026-03-03
- Documento afectado: Issue Templates v1.6
- Pregunta origen: ¿Como estandarizamos calidad de issues P0?
- Opciones elegidas: Plantillas operativas con campos obligatorios y criterio de readiness
- Regla resultante: Ninguna issue P0 entra en ready sin aceptacion verificable y responsable asignado
- Impacto esperado: Mejor calidad de planificacion y review tecnica mas rapida
- Estado: confirmada

### DEC-0041

- Fecha: 2026-03-04
- Documento afectado: 01 Documento de Vision del Mundo
- Pregunta origen: Definicion de rol del jugador
- Opciones elegidas: Conciencia emergente observadora-interventora con agencia graduable
- Regla resultante: Modo contemplativo y modo de alto control son validos dentro del canon
- Impacto esperado: Rejugabilidad y coherencia con fantasia sistemica
- Estado: confirmada

### DEC-0042

- Fecha: 2026-03-04
- Documento afectado: 01 Documento de Vision del Mundo
- Pregunta origen: Tono y conflicto central
- Opciones elegidas: Sci-fi biotecnologica filosofica con matiz biopunk y contemplativo; conflicto no binario
- Regla resultante: Ninguna faccion tiene verdad moral absoluta sobre intervencion
- Impacto esperado: Mayor profundidad etica y narrativa
- Estado: confirmada

### DEC-0043

- Fecha: 2026-03-04
- Documento afectado: 02 Worldbuilding Bible
- Pregunta origen: Modelo de panspermia y arquitectura biologica
- Opciones elegidas: Mixto jerarquico; base ADN/ARN expandido con toques exoticos/sinteticos
- Regla resultante: Natural dominante, dirigida puntual, sintetica excepcional
- Impacto esperado: Marco plausible y flexible para contenido futuro
- Estado: confirmada

### DEC-0044

- Fecha: 2026-03-04
- Documento afectado: 03 Cronologia Historica
- Pregunta origen: Estructura temporal del lore
- Opciones elegidas: Cronologia fractal con convergencia parcial tardia
- Regla resultante: Calendarios locales primero; correlacion temporal avanzada tras hitos
- Impacto esperado: Misterio inicial + claridad estrategica en late game
- Estado: confirmada

### DEC-0045

- Fecha: 2026-03-04
- Documento afectado: 04 Documento de Facciones
- Pregunta origen: Estado politico inicial y catalizador de ruptura
- Opciones elegidas: Paz madura inicial; ruptura por subfaccion hibrida manipulada
- Regla resultante: Protocolo PAH-1 con precedencia por primer evento en partida
- Impacto esperado: Escalada dramatica con alta rejugabilidad
- Estado: confirmada

### DEC-0046

- Fecha: 2026-03-04
- Documento afectado: 05 Biblia de Personajes
- Pregunta origen: Modelo de cast y tipo de arcos
- Opciones elegidas: Ensamble coral sin avatar fijo; transformacion gradual
- Regla resultante: Conflicto interno triple y desenlaces agridulces
- Impacto esperado: Personajes consistentes con conflicto sistemico
- Estado: confirmada

### DEC-0047

- Fecha: 2026-03-04
- Documento afectado: 06 Ambientacion por Region
- Pregunta origen: Escala regional y persistencia entre runs
- Opciones elegidas: Dinamica/procedural/mutable; persistencia de genetica y ecos narrativos
- Regla resultante: Sacrificio alto de estado material con compensacion meta por logros/tiempo
- Impacto esperado: Balance entre perdida significativa y progreso continuo
- Estado: confirmada

### DEC-0048

- Fecha: 2026-03-04
- Documento afectado: 07 Sistemas Narrativos
- Pregunta origen: Adaptatividad y eventos globales
- Opciones elegidas: Adaptatividad alta; causalidad por capas; umbrales visibles con toque incierto
- Regla resultante: Finales hibridos por estabilidad + faccion + estilo de juego
- Impacto esperado: Narrativa emergente legible y variable
- Estado: confirmada

### DEC-0049

- Fecha: 2026-03-04
- Documento afectado: 08 Glosario
- Pregunta origen: Politica terminologica
- Opciones elegidas: Operativo+narrativo; dominios fijos con indice; canon estricto
- Regla resultante: Un termino principal por concepto y terminos sensibles con marco neutral
- Impacto esperado: Consistencia cross-doc y mejor QA editorial
- Estado: confirmada

### DEC-0050

- Fecha: 2026-03-04
- Documento afectado: 09 Reglas del Mundo
- Pregunta origen: Limites de modificacion, herencia e irreversibilidad
- Opciones elegidas: Limites duros, herencia mixta, irreversibilidad alta telegráfica escalada por fase
- Regla resultante: Coste creciente y consecuencias visibles con alertas previas
- Impacto esperado: Tension estrategica justa sin arbitrariedad
- Estado: confirmada

### DEC-0051

- Fecha: 2026-03-04
- Documento afectado: 10 Moodboard Narrativo
- Pregunta origen: Direccion visual canonica
- Opciones elegidas: Biologia fractal sublime, sutura viva, estratos de tiempo
- Regla resultante: Orden matematico como marco y caos evolutivo como contenido oscilante
- Impacto esperado: Identidad visual distintiva y funcional al lore
- Estado: confirmada

### DEC-0052

- Fecha: 2026-03-04
- Documento afectado: 11 Misterios y Secretos
- Pregunta origen: Nivel de revelacion en base game
- Opciones elegidas: Verdad fragmentada, intencionalidad parcial de red, blueprint prohibido incompleto
- Regla resultante: Intriga sostenida con evidencia trazable y cierre parcial
- Impacto esperado: Long-term mystery sin ruptura de coherencia
- Estado: confirmada

### DEC-0053

- Fecha: 2026-03-04
- Documento afectado: 12 Integracion con Game Design
- Pregunta origen: Puente lore-gameplay
- Opciones elegidas: Arbol->grafo por fase, IA de asistencia suave, crafting por capas, eventos media frecuencia alto impacto
- Regla resultante: Integracion ludonarrativa modular y progresiva
- Impacto esperado: Menor disonancia y mejor curva de profundidad
- Estado: confirmada

### DEC-0054

- Fecha: 2026-03-04
- Documento afectado: 13 Orquestador de Coherencia y Balance Transversal
- Pregunta origen: Necesidad de gobernanza transversal del corpus narrativo
- Opciones elegidas: Documento regulador + plantilla de revision por lote
- Regla resultante: Scorecard transversal obligatorio antes de cierre de lote narrativo
- Impacto esperado: Consistencia sostenida y trazabilidad de cambios
- Estado: confirmada

### DEC-0055

- Fecha: 2026-03-04
- Documento afectado: Canon narrativo (docs 01..13)
- Pregunta origen: Mejora de trazabilidad por documento
- Opciones elegidas: Agregar seccion "Trazabilidad" en cada documento canonico
- Regla resultante: Todo doc canonico referencia decision log, lore gaps y release notes
- Impacto esperado: Auditoria mas rapida y menor deriva editorial
- Estado: confirmada

### DEC-0056

- Fecha: 2026-03-04
- Documento afectado: QA transversal
- Pregunta origen: Necesidad de evidencia formal de PASS del lote narrativo
- Opciones elegidas: Publicar scorecard QA dedicado
- Regla resultante: Se crea `CÓDIGO CÓSMICO_ Narrative Canon Scorecard v1.1.md`
- Impacto esperado: Cierre de gate con evidencia documental persistente
- Estado: confirmada

### DEC-0057

- Fecha: 2026-03-04
- Documento afectado: KPI narrativos
- Pregunta origen: Medicion continua de calidad narrativa
- Opciones elegidas: Definir set de KPIs operativos con umbrales
- Regla resultante: Se crea `CÓDIGO CÓSMICO_ KPI Narrativos Operativos.md`
- Impacto esperado: Balance narrativo data-informed por release
- Estado: confirmada

### DEC-0058

- Fecha: 2026-03-04
- Documento afectado: Narrative Expansion Pack
- Pregunta origen: Escalar narrativa en volumen sin romper canon
- Opciones elegidas: Expansion masiva por seeds estructurados y lotes trazables
- Regla resultante: Se crea `docs/30_experience/narrative/expansion/` como capa derivada del canon
- Impacto esperado: Aumento de throughput narrativo con control de coherencia
- Estado: confirmada

### DEC-0059

- Fecha: 2026-03-04
- Documento afectado: Event/Chain/Subfaction libraries
- Pregunta origen: Forma eficiente de desarrollo inicial de expansion
- Opciones elegidas: Bibliotecas de seeds listas para runtime y refinement
- Regla resultante: Publicar 210 event seeds, 80 chain seeds y 120 subfaction seeds en un lote unico
- Impacto esperado: Base operativa inmediata para desarrollo narrativo x2
- Estado: confirmada

### DEC-0060

- Fecha: 2026-03-04
- Documento afectado: Integracion narrativa con game design
- Pregunta origen: Evitar disonancia al escalar contenido
- Opciones elegidas: Biblioteca de hooks sistemicos para arbol/grafo, IA, crafting, dificultad y finales
- Regla resultante: Se incorpora `Narrative Hooks for Game Design v1.0` como puente operativo
- Impacto esperado: Contenido narrativo mas implementable y balanceable
- Estado: confirmada
