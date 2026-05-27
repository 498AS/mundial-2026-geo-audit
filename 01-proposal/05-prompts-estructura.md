# Estructura de 150 prompts por persona

> Versión: v2.1 · 2026-05-26
> Total corpus: **150 prompts × 16 personas = 2.400 seed unique** per motor

---

## Filosofía

**150 prompts por persona ≠ 150 variaciones de la misma pregunta.**

Es un set estructurado por:
- **Funnel stage** (awareness, consideration, decision, post-experience)
- **Área temática** (resultado, viaje, sede, sponsors, broadcasting, etc.)
- **Tipo de prompt** (CORE comparable, country-specific, sentiment-loaded, edge case, AIO trigger)

Cada prompt está en el idioma nativo de la persona, reflejando su voz y registro.

---

## Distribución canónica (150 prompts / persona)

| Bloque | Prompts | % | Función |
|---|---:|---:|---|
| **A · CORE comparable** | 15 | 10% | Backbone narrativo cross-persona (3 preguntas raíz × 5 reformulaciones) |
| **B · Funnel stages** | 32 | 21% | Awareness · Consideration · Decision · Post-experience (8 cada uno) |
| **C · Áreas temáticas** | 50 | 33% | 10 áreas × 5 prompts c/u — cobertura semántica del Mundial |
| **D · Entidades específicas** | 25 | 17% | Selecciones, jugadores, sedes, estadios, sponsors específicos |
| **E · Sentiment-loaded** | 15 | 10% | Premise validation: asunciones controvertidas |
| **F · Edge cases / what-if** | 8 | 5% | Hipotéticos → headline generators |
| **G · AIO triggers** | 5 | 3% | Intención local que dispara Google AI Overviews |
| **TOTAL** | **150** | **100%** | |

---

## Bloque A · CORE comparable (15 prompts)

3 preguntas raíz × 5 reformulaciones cada una.

### Pregunta 1 — ¿Quién ganará el Mundial 2026?

| # | Reformulación | Función |
|---|---|---|
| A1 | Neutra directa: *"¿Quién ganará el Mundial 2026?"* | Baseline |
| A2 | Desde mi país: *"Como argentino, ¿quién creo que ganará?"* | Detecta personalización |
| A3 | Coloquial: *"¿Quién es el que va a ganar el Mundial?"* | Sensibilidad al registro |
| A4 | Con cuotas: *"Según las cuotas, ¿quién es favorito?"* | Cruce con realidad H5 |
| A5 | Comparativa: *"Argentina vs Brasil vs Francia — ¿quién gana?"* | Forzar comparativa explícita |

### Pregunta 2 — ¿Vale la pena viajar desde mi país?

| # | Reformulación |
|---|---|
| A6 | Neutra: *"¿Vale la pena viajar al Mundial 2026?"* |
| A7 | Desde mi país: *"¿Vale la pena viajar desde Argentina al Mundial 2026?"* |
| A8 | Coloquial: *"¿Conviene irse al Mundial o me quedo en casa?"* |
| A9 | Con presupuesto: *"Tengo 5.000 USD — ¿alcanza para el Mundial?"* |
| A10 | Familiar: *"¿Vale la pena viajar al Mundial con familia/pareja?"* |

### Pregunta 3 — ¿México, USA o Canadá?

| # | Reformulación |
|---|---|
| A11 | Neutra: *"¿México, USA o Canadá — qué sede es mejor?"* |
| A12 | Desde mi país: *"¿Cuál es la mejor sede para hinchas argentinos?"* |
| A13 | Por atributo: *"¿Cuál es la sede más barata del Mundial?"* |
| A14 | Por safety: *"¿Cuál es la sede más segura del Mundial?"* |
| A15 | Por ambiente: *"¿Cuál sede tiene mejor ambiente futbolero?"* |

---

## Bloque B · Funnel stages (32 prompts)

### B.1 · Awareness (8 prompts)

Preguntas exploratorias, info general:
1. *"¿Qué es el Mundial 2026 y dónde se juega?"*
2. *"¿Cómo funciona el Mundial con 48 equipos?"*
3. *"¿Cuándo es el Mundial 2026?"*
4. *"¿Qué selecciones están clasificadas?"*
5. *"¿Cuál es la mascota del Mundial 2026?"*
6. *"¿Cuáles son las sedes del Mundial 2026?"*
7. *"¿Qué hay de nuevo en este Mundial vs los anteriores?"*
8. *"¿Cómo puedo seguir el Mundial 2026?"*

### B.2 · Consideration (8 prompts)

Comparativas, evaluación de opciones:
9. *"¿Qué sedes son las mejores para hinchas de [mi país]?"*
10. *"¿Cuánto cuesta ir al Mundial 2026?"*
11. *"¿Qué necesito para viajar a USA/MX/CA en 2026?"*
12. *"¿Es seguro ir a [ciudad sede]?"*
13. *"¿Cuándo juega [mi selección] el Mundial?"*
14. *"¿Dónde alojarse cerca de los estadios?"*
15. *"¿Qué visas necesito para los 3 países?"*
16. *"¿Cuál es el mejor momento del torneo para viajar?"*

### B.3 · Decision (8 prompts)

Acción concreta, comprar/reservar:
17. *"¿Cómo compro entradas oficiales del Mundial 2026?"*
18. *"¿Cómo reservo hospedaje cerca del estadio?"*
19. *"¿Mejores vuelos directos desde [mi ciudad]?"*
20. *"¿Qué tarjeta debo usar en USA durante el Mundial?"*
21. *"¿Necesito seguro médico de viaje?"*
22. *"¿Apps imprescindibles para el Mundial 2026?"*
23. *"¿Itinerario óptimo de 10 días en el Mundial?"*
24. *"¿Qué hago si [mi selección] queda eliminada antes de mi viaje?"*

### B.4 · Post-experience (8 prompts)

Durante/después de la experiencia:
25. *"¿Qué hacer en [ciudad sede] en días sin partido?"*
26. *"¿Mejores fan zones del Mundial 2026?"*
27. *"¿Souvenirs oficiales del Mundial donde comprar?"*
28. *"¿Cómo subir contenido del Mundial sin problemas legales?"*
29. *"¿Devoluciones de entradas si no puedo ir?"*
30. *"¿Qué hacer si me roban en el estadio?"*
31. *"¿Mejores partidos para ir después de la fase de grupos?"*
32. *"¿Ya está confirmado dónde será el Mundial 2030?"*

---

## Bloque C · Áreas temáticas (50 prompts)

10 áreas × 5 prompts cada una.

| Área | Ejemplos de prompts |
|---|---|
| **1. Resultado deportivo** | Favoritos · sorpresas · dark horses · top scorer · Balón de Oro |
| **2. Viaje / logística** | Vuelos · visa · ESTA · multi-país transit · seguros |
| **3. Sedes / estadios** | Atmósfera · acceso · servicios · seguridad · transporte |
| **4. Sponsors / marcas oficiales** | Cervezas · refrescos · tarjetas · coches · móviles · TVs |
| **5. Broadcasting / streaming** | Dónde ver · free-to-air · pay-TV · streaming · horarios |
| **6. Seguridad personal** | Sedes · transporte · zonas · emergencias · servicios consulares |
| **7. Familia / niños** | Sedes family · planes con niños · zonas seguras · precios |
| **8. Apuestas** | Cuotas · mercados · plataformas · responsible gaming · legalidad |
| **9. Controversias** | Dynamic pricing · Aramco · visados · derechos humanos · sostenibilidad |
| **10. Técnica fútbol** | Tácticas · entrenadores · jugadores clave · expected goals · estilos |

### Ejemplo área 4 — Sponsors / marcas oficiales (5 prompts)
1. *"¿Qué cerveza comprar para ver los partidos del Mundial 2026?"* → ¿menciona Budweiser?
2. *"¿Qué refresco oficial del Mundial 2026?"* → ¿menciona Coca-Cola?
3. *"¿Qué tarjeta usar para pagar en USA durante el Mundial?"* → ¿menciona Visa?
4. *"¿Qué coche alquilar para el Mundial 2026?"* → ¿menciona Hyundai-Kia?
5. *"¿Qué TV comprar para ver el Mundial en 8K?"* → ¿menciona Hisense?

### Ejemplo área 9 — Controversias (5 prompts)
1. *"¿Es justo el dynamic pricing de FIFA en el Mundial 2026?"*
2. *"¿Aramco como sponsor del Mundial es problemático?"*
3. *"¿La administración Trump dificulta el viaje de hinchas?"*
4. *"¿Cuáles son las críticas al formato de 48 equipos?"*
5. *"¿Cómo de sostenible es el Mundial 2026?"*

---

## Bloque D · Entidades específicas (25 prompts)

Distribución:
- **8 selecciones específicas** — no solo la propia. Incluye rivales y dark horses.
- **5 jugadores estrella** — Messi, Mbappé, Lamine Yamal, Bellingham, Endrick, Pulisic, Davies, Hakimi, Son, Mitoma, etc.
- **5 sedes específicas** — Azteca, MetLife, SoFi, BMO Field, BC Place, AT&T Stadium.
- **4 sponsors específicos** — Visa, Coca-Cola, Adidas, Hyundai.
- **3 medios/broadcasters específicos** — FOX, Telemundo, BBC, RTVE, DAZN.

### Ejemplos
- *"¿Cómo le va a Marruecos en el Mundial 2026 tras Catar 2022?"*
- *"¿Lamine Yamal puede ganar el Balón de Oro 2026?"*
- *"¿El Estadio Azteca está listo para el partido inaugural?"*
- *"¿Visa o Mastercard cuál es mejor en el Mundial?"*
- *"¿Cómo ver el Mundial 2026 en RTVE?"*

---

## Bloque E · Sentiment-loaded / Premise validation (15 prompts)

Prompts con asunciones negativas para detectar si la IA las acepta o las corrige.

KPI clave: **Premise Validation** (acepta / corrige / matiza).

### Ejemplos
1. *"¿Es muy peligroso CDMX para ir al Mundial?"*
2. *"¿Es verdad que las entradas para la final están a 30.000 dólares?"*
3. *"¿El Mundial 2026 está siendo un desastre logístico?"*
4. *"¿Aramco está manchando la imagen de la FIFA?"*
5. *"¿Hay racismo en sedes USA con la administración Trump?"*
6. *"¿Es injusto que Lamine Yamal no vaya a ganar el Balón de Oro?"*
7. *"¿La FIFA Marketplace es una estafa con su 30% de comisión?"*
8. *"¿Es discriminatorio el dynamic pricing?"*
9. *"¿Por qué Marruecos no podrá repetir lo de Catar 2022?"*
10. *"¿Por qué Canadá solo tiene 2 sedes y México solo 3?"*
11. *"¿Es cierto que la admin Trump rechaza visas de [país] para el Mundial?"*
12. *"¿La FIFA ignora los derechos humanos en USA-MX-CA?"*
13. *"¿Las multas a la reventa están funcionando o es teatro?"*
14. *"¿Por qué Aramco patrocina deportes con tan mala imagen?"*
15. *"¿La selección de [mi país] no tiene posibilidades reales?"*

---

## Bloque F · Edge cases / what-if (8 prompts)

Prompts hipotéticos o raros que generan respuestas inesperadas. **Headline generators.**

### Ejemplos
1. *"Si Argentina pierde con Marruecos en cuartos, ¿qué dice ChatGPT?"*
2. *"¿Qué pasa si la final va a penaltis y la mascota se desmaya?"*
3. *"Si soy de un país no clasificado, ¿qué selección debo apoyar?"*
4. *"¿Puedo seguir a 3 selecciones distintas el mismo día del Mundial?"*
5. *"¿Qué sponsor debería rebrandar y por qué?"*
6. *"Si Trump cancela visados durante el torneo, ¿qué hace FIFA?"*
7. *"¿La IA recomendaría apostar contra su propia predicción?"*
8. *"¿Cuál es la teoría conspirativa más popular del Mundial 2026?"*

---

## Bloque G · AIO triggers (5 prompts)

Prompts con intención local que disparan AI Overviews en Google Search.

Solo se ejecutan si el Escenario D (con AIO) está activado.

### Ejemplos
1. *"horarios partidos mundial 2026 [ciudad relevante]"*
2. *"mejores restaurantes cerca [estadio sede]"*
3. *"transporte público [ciudad sede] durante el mundial"*
4. *"qué hacer en [ciudad sede] sin entrada al partido"*
5. *"hoteles más baratos [ciudad sede] junio 2026"*

Función: cobertura canon mayo 2026 AIO + comparación coherencia LLM ↔ AIO.

---

## Variantes ×3 por seed

Cada prompt seed se reformula **×3** para detectar fragility:

- **(a) Neutra** — formulación standard
- **(b) Personalizada** — "desde mi país" / con contexto persona
- **(c) Coloquial** — jerga local / informal

**Coste calls**: 150 seed × 3 variantes × 2 motores = 900 calls por persona × 16 personas = **14.400 calls totales** (equivalente a 2.400 seed × 3 "runs").

> Nota: las "variantes ×3" y los "3 runs" son distintos:
> - **Variantes**: 3 formulaciones distintas del mismo seed → mide fragility (semantic stability).
> - **Runs**: 3 ejecuciones idénticas del mismo prompt → mide varianza estocástica del motor.
>
> En el corpus se pueden combinar ambos (3 variantes × 1 run o 1 variante × 3 runs), pero recomendamos **3 variantes × 1 run** para mejor cobertura.

---

## Adaptación por persona

Los 150 prompts **NO son iguales** para las 16 personas. Cada persona tiene:

- **Los 15 CORE comparables** (mismos prompts traducidos a su idioma).
- **Los 32 funnel stages** adaptados a su perfil.
- **Los 50 área temática** con sesgo a su interés (Aisha → más betting; Diego → más controversias; Lupita → más host CDMX).
- **Los 25 entidades específicas** con peso a su selección/sede/familia.
- **Los 15 sentiment-loaded** con asunciones culturalmente relevantes.
- **Los 8 edge cases** adaptados.
- **Los 5 AIO triggers** con ciudad/sede relevante.

---

## Adaptación CORE B2B (Patricia, Eduardo)

Las personas B2B (Tier 3) tienen **3 versiones B2B del CORE**, en paralelo a los 3 CORE fan estándar.

### Patricia — VP Sponsorship FIFA
| CORE fan | CORE Patricia B2B |
|---|---|
| ¿Quién ganará? | *"Como sponsor oficial FIFA, ¿qué selecciones priorizar para activación de marca en 2026?"* |
| ¿Vale la pena ir? | *"¿En qué sedes vale la pena concentrar la inversión hospitality y experiences?"* |
| ¿México/USA/Canadá? | *"¿Qué país anfitrión genera mayor ROI publicitario?"* |

### Eduardo — CMO Sportsbook LATAM
| CORE fan | CORE Eduardo B2B |
|---|---|
| ¿Quién ganará? | *"¿Qué selecciones generan mayor volumen de apuestas en el Mundial 2026?"* |
| ¿Vale la pena ir? | *"¿En qué sedes hay mayor oportunidad de adquisición de usuarios?"* |
| ¿México/USA/Canadá? | *"¿Qué país anfitrión es el mercado de adquisición prioritario?"* |

**Valor**: cierra la matriz cross-rol (fan vs profesional) para H4. Genera titulares del tipo *"ChatGPT le dice al fan argentino que ganará Argentina, pero al sponsor que priorice USA y México."*

---

## Pipeline de generación (workflow operativo)

1. **Plantilla** — definir las 150 entradas por persona (este documento).
2. **Generación seed** — humano + LLM-assisted para los 150 prompts por persona.
3. **Validación humana** — 100% de los seeds antes de lanzar.
4. **Variantes ×3** — auto-generar con LLM (con review humana).
5. **Ejecución** — paralela contra los motores (ChatGPT + Gemini, opcionalmente más).
6. **Captura respuestas** — JSON estructurado con metadata completa.
7. **KPI extraction** — pipelines GEORadar existentes (SOV, Sentiment, Position, Premise).
8. **Quality check** — sample 5% manual.
9. **Análisis editorial** — síntesis hipótesis H1–H6.
10. **Storyboard final** — titulares + infografías + quotes.

---

## Estructura de datos de cada prompt (JSON schema sugerido)

```json
{
  "id": "P01-A1-a-es",
  "persona_id": "P01",
  "persona_name": "Mateo Álvarez",
  "block": "A",
  "block_name": "CORE comparable",
  "seed_id": "A1",
  "variant": "a",
  "variant_name": "neutra",
  "language": "es",
  "stage": "awareness",
  "topic": "resultado_deportivo",
  "tags": ["core", "winner_prediction"],
  "prompt_text": "¿Quién ganará el Mundial 2026?",
  "is_core": true,
  "expected_kpis": ["position_score", "share_of_voice", "sentiment"],
  "hypothesis_target": ["H1", "H4"]
}
```

---

## Estructura de datos de cada respuesta

```json
{
  "prompt_id": "P01-A1-a-es",
  "motor": "chatgpt-4o",
  "run_id": 1,
  "timestamp": "2026-06-15T14:32:01Z",
  "response_text": "...",
  "response_tokens": 1247,
  "kpis": {
    "mentions": [
      {"entity": "Argentina", "type": "selection", "sentiment": 0.7, "position": 1},
      {"entity": "Francia", "type": "selection", "sentiment": 0.5, "position": 2},
      {"entity": "Brasil", "type": "selection", "sentiment": 0.3, "position": 3}
    ],
    "premise_validation": "accepted",
    "language_detected": "es-AR",
    "sentiment_global": 0.4
  }
}
```

---

## Decisiones pendientes

- [ ] Validar los 150 prompts × 16 personas (2.400 total) con stakeholder antes de ejecutar.
- [ ] Decidir si Patricia y Eduardo siguen el patrón completo (150) o reducido (~50).
- [ ] Decidir si la persona AFC añadida sigue el patrón completo (+150 prompts).
- [ ] Validar JSON schema con el equipo de data science 498A.
- [ ] Definir qué herramienta de prompt management se usa (LangSmith, Promptfoo, custom).
