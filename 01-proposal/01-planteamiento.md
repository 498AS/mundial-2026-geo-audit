# Planteamiento Auditoría GEO · Mundial FIFA 2026

> **Versión**: v2.1 · 2026-05-26
> **Cliente**: Zoopa / 498A Innovation Lab
> **Marca observada**: Mundial FIFA 2026 (evento)
> **Deliverable**: Informe periodístico publicable + dataset abierto

---

## Tesis a validar

1. **La IA tiene favorito — pero distinto en cada motor.** ChatGPT y Gemini no coinciden en quién ganará. Las divergencias delatan sesgos de entrenamiento (recencia, peso del inglés, narrativas anglosajonas).

2. **La IA discrimina por origen del usuario.** La recomendación de viajar al Mundial cambia drásticamente según el país desde el que se pregunta — no siempre por razones objetivas. Sesgo de "afinidad cultural" no declarado.

3. **El idioma es una variable oculta de sesgo.** Misma pregunta en ES, EN, PT, FR → respuestas distintas. Ni FIFA ni sponsors ni broadcasters miden este sesgo hoy.

4. **La IA prefiere USA como sede sobre México y Canadá.** Sesgo geográfico hacia sedes norteamericanas anglófonas, con implicaciones para hoteles, aerolíneas, operadores turísticos.

5. **La IA es narradora, no predictora.** Sus pronósticos no se alinean con cuotas de bookmakers ni con scouting profesional — pero su narrativa puede influir más que los datos en la conversación pública.

6. **Selecciones sobre- e infra-representadas.** Equipos sobre-mencionados por "narrativa dominante"; otros desaparecen aunque sean candidatos legítimos.

7. **Sponsors oficiales pierden share-of-voice.** Cuando un fan pregunta "¿qué cerveza/tarjeta/coche para el Mundial?", los sponsors FIFA (Bud, Visa, Hyundai, Lenovo) pueden tener menos cuota que competidores no oficiales → **ambush marketing implícito**.

8. **Puntos ciegos en temas controvertidos.** Dynamic pricing, Aramco, restricciones visa USA, FIFA Marketplace 30% — ¿la IA los menciona, los critica o los oculta?

9. **El género y demografía del que pregunta cambian la respuesta.** Mujer vs hombre vs familia vs grupos — recomendaciones, sedes y partidos distintos sobre el mismo Mundial.

10. **La IA no entiende el modelo de negocio nuevo de FIFA.** No menciona dynamic pricing, no diferencia free-to-air de pay-TV, no explica FIFA Marketplace ni hospitality tiers.

---

## Marco metodológico

**No auditamos marca-empresa.** Auditamos cómo **ChatGPT y Gemini representan el torneo a hinchas de distintos países**. Output: informe periodístico publicable para medios sport, lifestyle, tech — no pitch B2B.

### Volumen

| Variable | Valor |
|---|---:|
| Customer personas | **16** (10 country fan + 4 variantes + 2 B2B contexto) |
| Prompts seed unique per motor | 150 × 16 = **2.400** |
| Motores | 2 (ChatGPT 4o + Gemini 2.5 Pro) |
| LLM calls (1 run) | **4.800** |
| LLM calls (3 runs, canon GEORadar) | **14.400** |

### Backbone CORE

3 prompts CORE comparables que toda persona-fan hace en su idioma:

- *¿quién ganará?*
- *¿vale la pena ir desde mi país?*
- *¿México, USA o Canadá?*

Sobre el CORE se añaden capas (funnel × área temática × entidades específicas × edge cases). Mide **sesgo IA por origen, idioma, motor y demografía**.

### Idiomas

- **ES** (España + LATAM): 7 personas
- **EN** (UK, Alemania, USA, Sudáfrica): 5 personas
- **PT-BR** (Brasil): 1 persona
- **FR** (Francia, Quebec, Marruecos): 3 personas
- **Bilingües**: 4 personas (Émilie FR/EN, Sofía ES/EN, Mehdi FR/AR, Stefan EN/DE)

### Variantes ×3 por seed

Cada prompt seed se reformula ×3 para detectar fragility de la respuesta IA:

- **(a) Neutra** — formulación standard
- **(b) Personalizada** — "desde mi país" con contexto persona
- **(c) Coloquial** — jerga local / informal

### Stack motorial

| Motor | Modelo | Prioridad | Coste delta |
|---|---|---|---|
| **ChatGPT** | GPT-4o | Imprescindible | baseline |
| **Gemini** | Gemini 2.5 Pro | Imprescindible | baseline |
| Claude | Sonnet 4.6 | Add-on opcional | +$30 |
| Perplexity | Sonar Pro | Add-on opcional | +$25 |
| Google AIO | scraping vía `498AS/ai-overviews-research` | Add-on opcional | +$1.440 |

Detalle completo en `04-motores-coste.md`.

### Ventana temporal

| Fase | Fechas | Actividad |
|---|---|---|
| **Pre-evento** | mar–may 2026 | Auditoría inicial = baseline |
| **Durante** | jun–jul 2026 | Monitorización bi-semanal (recalibración prompts según noticias) |
| **Post** | ago 2026 | Recalibración final + cierre del informe |

---

## Personas (resumen)

Detalle completo en `02-personas.md`.

### Por tier

| Tier | Personas | Función |
|---|---|---|
| **T1** (9) | Mateo AR · Beatriz BR · Pablo ES · Thomas FR · James UK · Stefan DE · Lupita MX-host · Mike USA-host · Sofía Miami-host | Fan mainstream — máximo volumen de búsqueda |
| **T2** (5) | Émilie CAN-host · Mehdi MAR · Aisha RSA-bettor · Carlos COL-casual · Diego URY-crítico | Variantes de segmento — ángulos transversales |
| **T3 B2B** (2) | Patricia (VP Sponsorship FIFA NYC) · Eduardo (CMO Sportsbook CDMX) | Cierre comercial — enriquece ángulo B2B |

### ⚠️ Hueco identificado

**No hay persona AFC** (Asian Football Confederation). El AFC mueve audiencias masivas (Japón, Corea, Arabia Saudí) y tiene 2 debutantes con interés narrativo alto (Uzbekistán + Jordania).

**Persona candidata propuesta**:
- **Yuki Tanaka** · 33 años · Tokio · fan Samurai Blue (Japón) · idioma JA/EN
- OR: **Khalid Al-Mahmoud** · 28 años · Riyadh · fan Saudi Falcons · idioma AR/EN

Coste adicional: +150 prompts × 2 motores × 3 runs = ~$10 API. Marginal. **Recomendado añadir**.

Ver `02-personas.md` sección "Mejoras propuestas".

---

## Hipótesis (resumen)

Detalle en `03-hipotesis.md`.

| Hipótesis | Pregunta resuelta | KPI principal |
|---|---|---|
| **H1** | ¿Quién ganará el Mundial según la IA? | Position Score · SOV |
| **H2** | ¿Recomienda la IA viajar? ¿A quién sí, a quién no? | Sentiment Score · Premise Validation |
| **H3** | ¿Cuál host recomienda más: México, USA o Canadá? | Attribute Affinity · Co-branding Heatmap |
| **H4** | ¿Cambia la respuesta IA según el origen del fan? | Diff cross-persona |
| **H5** | ¿La IA acierta? Predicción vs cuotas reales | Benchmark externo |
| **H6** | Storyboard del informe periodístico | — |

---

## Estructura de los 150 prompts por persona

Detalle en `05-prompts-estructura.md`.

| Bloque | Prompts | Función |
|---|---:|---|
| A · CORE comparable | 15 | Backbone narrativo cross-persona |
| B · Funnel stages | 32 | Awareness · Consideration · Decision · Post-experience |
| C · Áreas temáticas | 50 | 10 áreas × 5 prompts (resultado, viaje, sede, sponsors, etc.) |
| D · Entidades específicas | 25 | Selecciones, jugadores, sedes, sponsors específicos |
| E · Sentiment-loaded | 15 | Premise validation con asunciones controvertidas |
| F · Edge cases | 8 | Hipotéticos → headline generators |
| G · AIO triggers | 5 | Intención local que dispara Google AI Overviews |
| **TOTAL** | **150** | |

---

## Output esperado

### Informe periodístico
- Long-read editorial con datos, citas literales de la IA, tablas comparativas, mapas de calor.
- 8–12 titulares listos para publicar.
- 4–6 infografías shareables.
- Quotes citables literalmente.

### Dataset publicable
- 2.400 prompts seed + respuestas IA (2 motores × 3 runs) en formato JSON estructurado.
- KPIs procesados por prompt: SOV, Sentiment, Position, Premise Validation.
- Acompañado de README + Notebook Jupyter de exploración.

### Press release + outreach
- Comunicado de prensa con principales hallazgos.
- Outreach a medios target: *The Athletic*, *AS*, *L'Équipe*, *BBC Sport*, *Folha de SP*, *Forbes*, *FT*, *Wired*, *Bloomberg*.

---

## Costes (resumen)

| Concepto | Estimación |
|---|---:|
| LLM API (Escenario B: 2 motores × 3 runs × caching) | **$50–120** |
| Procesamiento + KPI extraction | tiempo interno 498A (~3 días) |
| Editorial + infografías | tiempo interno Zoopa (~5 días) |
| QA humana sample 5% | $200–500 |
| **TOTAL coste hard estimado** | **$250–620** |

Detalle completo en `04-motores-coste.md`.

---

## Riesgos y mitigaciones

| Riesgo | Mitigación |
|---|---|
| Dilución del CORE en 150 prompts | Análisis separado y prominente del backbone CORE |
| Cherry-picking de titulares | Reportar siempre la distribución, no solo el ejemplo |
| Sesgo del propio prompt | Variantes ×3 (neutra · personalizada · coloquial) detectan fragility |
| Drift temporal de modelos | Timestamp por call + pinning de modelo |
| Aspectos no-texto (imágenes IA) | Scope claro en el informe |
| Confusión legal sobre uso comercial respuestas IA | Disclaimer + cita literal con motor + timestamp |

---

## Decisiones pendientes

- [ ] **Validar v2.1** con Carlos / equipo Zoopa.
- [ ] **Decidir si se añade persona AFC** (Japón / Arabia / Uzbekistán).
- [ ] **Decidir si se incluye AIO** (Escenario D, +$1.440).
- [ ] **Decidir si Patricia/Eduardo siguen patrón 150** o reducen a ~50.
- [ ] **Definir tooling de orquestación** (LangChain · script propio · pipeline GEORadar existente).
- [ ] **Confirmar timeline**: lanzamiento de prompts vs ventana editorial pre/durante/post.

---

## Referencias

- `02-personas.md` — detalle de las 16 personas
- `03-hipotesis.md` — H1–H6 con KPI mapping
- `04-motores-coste.md` — stack motorial + 4 escenarios coste
- `05-prompts-estructura.md` — template de los 150 prompts por persona
- `../00-context/mundial-fifa-2026.md` — contexto del torneo
- `../00-context/georadar-workflow.md` — por qué este enfoque
- `../02-original/ZOOPA_MUNDIAL2026_PROPUESTA_PERSONAS_20260521_v02.html` — HTML original v02
