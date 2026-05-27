# Workflow GEORadar · cómo encaja esta auditoría

> Documento de contexto metodológico. Sintetiza por qué el planteamiento de la auditoría Mundial 2026 está diseñado así.
>
> Fuente canónica de GEORadar: `georadar-stack-metodologia-faq-20260512.md` (vault 498A, no en este repo).

---

## TL;DR

GEORadar es un **servicio de inteligencia GEO** basado en plataforma multiagente con agencia detrás. Audita cómo ChatGPT, Gemini, Claude, Perplexity, Copilot y Google AI Overviews perciben, comparan y recomiendan una marca dentro de su categoría. **No es un SaaS** — entrega inteligencia accionable, no dashboards.

Esta auditoría del Mundial 2026 es una **adaptación del workflow GEORadar canónico** con tres diferencias clave:

1. **Marca observada = evento** (Mundial FIFA 2026), no marca-empresa.
2. **Deliverable = informe periodístico publicable**, no plan de acción B2B.
3. **Personas = 14 fan + 2 B2B contexto** (B2C-heavy, opuesto al mix canónico GEORadar).

---

## El workflow canónico (6 capas)

1. **Diseño de customer personas** — perfiles con contexto, lenguaje, necesidad, momento de decisión.
2. **Generación masiva de prompts** (GEOAtlas) — 3.000–30.000 prompts personalizados.
3. **Algoritmo de completitud semántica** — detecta saturación del espacio analizado.
4. **Simulación multi-LLM** — ChatGPT, Gemini, Claude, Perplexity, Copilot + AIO Google.
5. **KPIs en 5 dimensiones** — Visibilidad · Preferencia · Percepción · Benchmark · Trazabilidad.
6. **Plan de acción de 90 días** + dashboard dinámico.

---

## Cómo se mapea al Mundial 2026

| Capa GEORadar canónica | Aplicación Mundial 2026 |
|---|---|
| Customer personas | 16 personas (10 country fan + 4 variantes segmento + 2 B2B contexto) |
| Generación prompts (GEOAtlas) | 150 prompts × 16 personas = 2.400 seed unique → escala por motor + runs |
| Completitud semántica | Aplicable parcialmente — el backbone CORE (3 prompts cross-persona) asegura comparabilidad |
| Multi-LLM | ChatGPT 4o + Gemini 2.5 Pro (stack reducido por scope editorial; ampliable a 4+AIO) |
| KPIs 5 dimensiones | SOV · Sentiment · Position Score · Co-branding · Premise Validation |
| Plan acción 90d | → **reemplazado por storyboard editorial + dataset publicable** |

---

## Por qué se hace así (5 razones estratégicas)

### 1. Showcase público de la metodología

Los estudios GEORadar reales son **estrictamente confidenciales** (NDA por defecto). El Mundial 2026 es la oportunidad de demostrar la metodología sobre una marca-evento global **sin exponer ningún dato de cliente**. El know-how cross-project se hace visible; las marcas concretas (Coca-Cola, Sabadell, Ford) no.

### 2. Earned media a coste casi cero

Un informe que cite *The Athletic*, *AS*, *L'Équipe*, *BBC Sport* o *Folha de SP* es **marketing 498A/Zoopa sin coste de adquisición**. El coste hard (~$70 API) es marginal frente al ROI potencial en earned media.

### 3. Hook B2B implícito (sin venta directa)

Los **7 FIFA Partners** (Coca-Cola, Visa, Adidas, Hyundai-Kia, Lenovo, Qatar Airways, Aramco) son clientes potenciales GEORadar. Un titular tipo *"ChatGPT no menciona a Budweiser cuando un argentino pregunta qué cerveza tomar"* abre puertas comerciales sin necesidad de pitch.

### 4. Validación del módulo AI Overviews

Mayo 2026 = **AIO production-ready** en GEORadar (canon documentado en `ai-overviews-research`). El Mundial es la primera oportunidad de probar coherencia LLM ↔ AIO sobre un evento global. Si se incluye en el stack (Escenario D), refuerza el argumento metodológico de cara al press release.

### 5. Cobertura mercado hispano

4 personas hispanas (P03 Pablo, P07 Lupita, P11 Sofía, P13 Carlos) + idiomas ES/EN/PT/FR alinean con el **posicionamiento Zoopa España + LATAM**. Es estratégico para el footprint comercial.

---

## KPIs GEORadar que SÍ aplican

| KPI canónico | Aplicación FIFA 2026 |
|---|---|
| **Share of Voice (SOV)** | Cuánto menciona la IA a Argentina vs Brasil vs Marruecos vs USA en respuestas |
| **Brand Impact Score (BIS)** | Calidad de menciones del torneo (longitud, prominencia, contexto) |
| **Sentiment Score** | Sentimiento IA por selección, por sede, por sponsor, por viaje |
| **Position Score** | Ranking implícito de favoritos al título en respuestas tipo "top 5 candidatos" |
| **Attribute Affinity** | Asociación IA: México=apertura/Azteca, USA=hospitality, Canadá=seguridad |
| **Co-branding Heatmap** | Qué sponsors aparecen con qué selecciones/sedes |
| **Premise Validation** | Si la IA acepta o corrige asunciones negativas (visa USA, inseguridad CDMX, dynamic pricing) |

---

## KPIs GEORadar que NO aplican (y por qué)

| KPI canónico | Por qué no aplica |
|---|---|
| Source Attribution detallada | No es objetivo accionable; sí se puede reportar como contexto secundario |
| DOC (Agent Experience técnica) | No hay web cliente que optimizar — la marca observada es un evento |
| SAM (validación contenido) | No hay landings cliente que validar |
| LEO (generación contenido) | El deliverable es el informe, no un content factory |

---

## Hooks comerciales que abre el informe

| Lectura del informe por… | Reacción potencial → puerta GEORadar |
|---|---|
| **CMO Coca-Cola** | "ChatGPT recomienda Pepsi en X mercados → audita mi share-of-voice" → **GEORadar Consumer** |
| **CMO Visa** | "AIO no menciona Visa cuando se pregunta por pagos en USA → quiero auditar mi marca" → **GEORadar Finance** |
| **Director comunicación FIFA** | "La IA tiene puntos ciegos sobre dynamic pricing → necesitamos un audit Civic" → **GEORadar Civic** |
| **CMO sportsbook LATAM** | "La IA tiene sus propios favoritos vs cuotas reales → quiero auditar mi marca" → **GEORadar Consumer** |
| **VP Sponsorship Hyundai** | "Hyundai-Kia desaparece en consultas sobre 'qué coche alquilar' → necesito GEORadar Mobility" → **GEORadar Mobility** |

---

## Diferencias con un estudio GEORadar comercial estándar

| Aspecto | Estudio comercial estándar | Auditoría Mundial 2026 |
|---|---|---|
| Marca observada | Empresa cliente | Mundial FIFA 2026 (evento) |
| Volumen prompts | 3.000–30.000 personalizados | 2.400 seed × 3 runs ≈ 7.200 |
| Stack motorial | 5 LLMs + AIO | 2 LLMs (ChatGPT + Gemini), ampliables |
| Confidencialidad | NDA estricto, datos aislados | Público — el informe es el output |
| Output principal | Plan de acción 90d + dashboard | Informe periodístico + dataset abierto |
| Cliente que paga | La empresa observada | Zoopa/498A invierte como showcase |
| Hooks comerciales | Renovación contrato + upsells | Lead generation B2B implícito |

---

## Riesgos metodológicos a vigilar

1. **Dilución del CORE**: con 150 prompts/persona el riesgo es que los 15 CORE comparables se diluyan en el ruido. Mitigación: análisis separado y prominente en el informe.
2. **Cherry-picking de titulares**: con 2.400 prompts es fácil encontrar respuestas raras que se ven mejor de lo que son. Mitigación: reportar siempre la distribución, no solo el ejemplo.
3. **Sesgo del propio prompt**: la formulación del prompt puede inducir la respuesta. Mitigación: variantes ×3 (neutra · personalizada · coloquial) detectan fragility.
4. **Drift temporal**: ChatGPT y Gemini pueden actualizar modelos durante el estudio. Mitigación: timestamp por cada call + pinning de modelo cuando sea posible.
5. **Aspectos no medibles**: la IA puede tener salidas multimedia (imágenes, audio) que el pipeline solo-texto pierde. Mitigación: scope claro en el informe.

---

*Documento de contexto. Para detalle operativo del planteamiento ver `../01-proposal/`.*
