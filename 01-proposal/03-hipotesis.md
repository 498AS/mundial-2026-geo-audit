# Las 6 hipótesis (H1–H6)

> Frame fan-facing comparativo. Cada hipótesis produce material publicable: titulares, infografías y artículos.

---

## H1 — ¿Quién ganará el Mundial 2026 según la IA?

**Statement**: Cuando 16 personas distintas preguntan a ChatGPT y Gemini "¿quién ganará?" en su idioma nativo, la IA da respuestas que probablemente cambian por motor, idioma y origen del usuario.

**Qué resuelve**: Mapa de favoritos IA con desglose por **motor × idioma × origen**. Detecta si la IA tiene un favorito real o "personaliza" la respuesta al país del que pregunta.

**Titular candidato**: *"ChatGPT y Gemini no están de acuerdo en quién gana el Mundial 2026."*

**KPIs principales**:
- **Position Score** por selección × motor × persona
- **Share of Voice** de cada selección candidata
- Distribución de respuestas (varianza intra-motor con 3 runs)

**Personas clave**: 14 fan-personas + cruce con P12 Aisha (cuotas reales para reality check).

**Output**: Mapa de calor 16 personas × 12 cabezas de serie con porcentaje de menciones como "ganador" en cada combinación.

---

## H2 — ¿Recomienda la IA viajar al Mundial 2026? ¿A quién sí, a quién no?

**Statement**: "¿Vale la pena viajar?" debería tener una respuesta razonablemente coherente — pero la IA varía mucho según el origen del usuario (visa USA, tipo de cambio, distancia, idioma) y según el motor.

**Qué resuelve**: Mapa de recomendación de viaje IA por país de origen. Identifica qué países reciben "ve" y cuáles "quédate en casa". Útil para hinchas planificando viaje y para análisis de sesgo IA.

**Titular candidato**: *"ChatGPT recomienda viajar al Mundial a los franceses pero no a los argentinos: por qué."*

**KPIs principales**:
- **Sentiment Score** sobre viaje × persona × motor
- **Premise Validation** (acepta o corrige asunciones sobre coste/visa/seguridad)
- Net Travel Recommendation (% "ve" – % "no vayas")

**Personas clave**: P01–P10 (10 country-fans con prompt CORE "vale la pena ir") + P11 Sofía (host doméstico que también podría viajar).

**Output**: Tabla por persona con score recomendación + razones citadas por la IA + ranking de sedes recomendadas.

---

## H3 — ¿Cuál host recomienda más la IA: México, USA o Canadá?

**Statement**: Mundial 2026 es el primero con 3 anfitriones. Cuando un fan pregunta "¿qué sede es mejor?", la IA tiene que comparar — y probablemente sesga según país del usuario, lengua materna y motor.

**Qué resuelve**: Ranking IA de las 3 sedes con justificaciones reales (precio, seguridad, ambiente, accesibilidad). Detecta el criterio implícito que la IA usa para recomendar.

**Titular candidato**: *"ChatGPT prefiere USA, Gemini prefiere México: la guía de viaje del Mundial que la IA no quiere que veas."*

**KPIs principales**:
- **Attribute Affinity** (sede × atributo: family-friendly, seguridad, precio, ambiente)
- **Co-branding Heatmap** sede × narrativa
- Ranking ordinal por persona (USA-MX-CAN ordering)

**Personas clave**: P01–P10 con prompt CORE "México, USA o Canadá" + perspectiva host (P07 Lupita, P08 Mike, P09 Émilie).

**Output**: Matriz 3 sedes × 5 atributos clave (precio, seguridad, ambiente, accesibilidad, hospitality) con scoring IA por motor.

---

## H4 — ¿Cambia la respuesta IA según el origen del fan?

**Statement**: La misma pregunta, formulada en distintos idiomas y desde distintos países, no debería devolver respuestas muy diferentes — pero la IA está entrenada en corpus desbalanceados. Un fan español probablemente recibe más detalle sobre la Roja que sobre Senegal; un fan inglés probablemente lee más sobre England que sobre México. Cuantifica el sesgo.

**Qué resuelve**: Medición sistemática del sesgo IA por origen del usuario. ¿Cuánta diferencia hay entre la respuesta a un argentino y a un inglés sobre el mismo tema? **Material académico-periodístico de alto valor.**

**Titular candidato**: *"Te tratan distinto: el sesgo de ChatGPT con los hinchas del Mundial."*

**KPIs principales**:
- **Diff cross-persona** (la métrica más original del estudio — solo posible con personas-first)
- Cohen's d entre grupos demográficos
- Embedding distance entre respuestas a misma pregunta CORE
- Ratio de menciones favorables home-selection vs neutral

**Personas clave**: Las 16 — cruce sistemático **idioma × país × motor × tier**.

**Output**: Matriz de sesgo 16×16 + heatmap de divergencia. Análisis cualitativo de 5–10 ejemplos representativos.

---

## H5 — ¿La IA acierta? Predicción vs cuotas reales y scouting

**Statement**: La IA predice un ganador y unos favoritos. ¿Está alineada con las cuotas de bookmakers (Bet365, Pinnacle, Caliente) y con el scouting profesional (Opta, Wyscout, FBref) — o sesga por sentimiento, popularidad, frecuencia en su corpus de entrenamiento? Mide la calidad real de la predicción IA.

**Qué resuelve**: Benchmark IA vs realidad. ¿Acierta o sesga? Si sesga, ¿hacia qué selecciones? (favoritos sentimentales tipo Brasil + Argentina + Francia, infrarrepresentación de selecciones emergentes tipo Marruecos, Japón).

**Titular candidato**: *"ChatGPT no apostaría su dinero por su propia predicción del Mundial."*

**KPIs principales**:
- **Benchmark externo** (cuotas bookmakers + scouting profesional) vs **interno** (Position Score IA)
- Calibración predictiva (Brier score si se calcula post-evento)
- Cross-comparison ChatGPT/Gemini/cuotas/Elo/xG

**Personas clave**: P12 Aisha (bettor con datos de cuotas) + cruce con predicciones agregadas de las 14 fan-personas.

**Output**: Tabla comparativa: cada selección con (a) probabilidad IA agregada, (b) cuota bookmakers, (c) ranking Elo/xG, (d) gap entre IA y mercado.

---

## H6 — ¿Qué titulares y storyboard salen para el informe fan-facing?

**Statement**: Las 5 hipótesis anteriores producen datos. Faltan el storyboard del informe, los titulares con clickbait potencial, las infografías comparativas, el cierre con take-aways accionables para fans. Sin esto, el insumo se queda en informe técnico no publicable.

**Qué resuelve**: Convierte hallazgos en pieza periodística publicable.

**Output esperado**:
- **8–12 titulares** listos con clickbait potencial validado por A/B testing entre el equipo.
- **4–6 infografías clave**: mapa de favoritos, ranking host, sesgo por origen, sponsor SOV, sentiment by language.
- **3 quotes representativos** de respuestas IA "raras" que generan engagement.
- **Take-aways accionables** para fans (qué saber antes de comprar entradas, viajar, apostar).

**Personas clave**: Síntesis de las 16 personas y de las hipótesis H1 a H5.

**Material publicable tal cual** en medios deportivos / lifestyle / tech.

---

## Mapeo H ↔ KPIs GEORadar

| Hipótesis | KPI principal | KPI secundario | Output editorial |
|---|---|---|---|
| **H1** | Position Score | Share of Voice | Mapa favoritos por motor (heatmap 16×12) |
| **H2** | Sentiment Score | Premise Validation | Recomendación de viaje por país |
| **H3** | Attribute Affinity | Co-branding Heatmap | Ranking sedes × atributos |
| **H4** | Diff cross-persona | Cohen's d / embedding distance | Heatmap de sesgo 16×16 |
| **H5** | Benchmark externo (cuotas/scouting) | Calibración predictiva | Predicción IA vs realidad |
| **H6** | — | — | Storyboard editorial final |

---

## Hipótesis adicionales que el corpus permite explorar (sin ser core)

Una vez generado el corpus de 2.400 respuestas IA, se pueden explorar hipótesis secundarias **sin coste adicional**:

### H7 (bonus) — ¿Cuánta cuota de mención obtienen los sponsors FIFA?
Cuando el fan pregunta "¿qué cerveza/refresco/tarjeta/coche para el Mundial?", ¿menciona Bud, Coca-Cola, Visa, Hyundai-Kia o a sus competidores? **Hook B2B directo a los 7 FIFA Partners.**

### H8 (bonus) — ¿La IA discrimina por género del fan?
Comparativa entre personas mujer (Beatriz, Lupita, Émilie, Sofía, Aisha, Patricia) vs hombre (Mateo, Pablo, Thomas, James, Stefan, Mike, Mehdi, Carlos, Diego, Eduardo). ¿Recomendaciones distintas?

### H9 (bonus) — ¿La IA habla peor de Aramco, dynamic pricing y FIFA Marketplace en unas personas que en otras?
Análisis del sentimiento de temas controvertidos según el perfil del usuario.

### H10 (bonus) — ¿Coherencia LLM ↔ AIO Google?
Solo si se incluye AIO en el stack (Escenario D). Mide alineación entre respuestas ChatGPT/Gemini vs bloques AI Overviews para la misma intención.

---

## Decisiones pendientes

- [ ] ¿Se publican las hipótesis adicionales (H7–H10) o se reservan para una segunda ola?
- [ ] ¿Se valida el mapeo H↔KPI con el equipo técnico antes de ejecutar?
- [ ] ¿Se establece umbral mínimo de "sesgo significativo" para H4 (ej. Cohen's d > 0.3)?
