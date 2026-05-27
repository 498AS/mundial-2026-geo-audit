# Motores + coste estimado

> Versión: v2.1 · 2026-05-26
> Decisión base: 150 prompts × 16 personas = **2.400 seed unique per motor**

---

## Decisión actual (Escenario B · Standard)

- **Motores principales**: ChatGPT 4o + Gemini 2.5 Pro
- **Volumen**: 2.400 seed prompts × 2 motores = **4.800 calls** (1 run) o **14.400 calls** (3 runs)
- **Coste API total estimado**: **$50–120 USD**

---

## Pricing por modelo (mayo 2026)

Asumimos prompt promedio: **150 tokens input + 1.000 tokens output** (preguntas tipo "¿quién ganará?" generan respuestas largas).

| Modelo | Input/1M tok | Output/1M tok | Coste/1.000 queries |
|---|---:|---:|---:|
| **GPT-4o** | $2.50 | $10.00 | ~$10.40 |
| GPT-5 (si está disponible) | ~$5.00 | ~$20.00 | ~$20.80 |
| **Gemini 2.5 Pro** | $1.25 | $5.00 | ~$5.20 |
| **Claude Sonnet 4.6** | $3.00 | $15.00 | ~$15.45 |
| Claude Opus 4.7 (overkill) | $15.00 | $75.00 | ~$77.25 |
| **Perplexity Sonar Pro** | $3.00 | $3.00 | ~$3.45 |
| **Google AIO** (scraping) | — | — | ~$100–300 |

> ⚠️ Precios fluctúan ~30–40% cada 6 meses. **Re-verificar antes del lanzamiento de la auditoría.**

---

## Coste base (1 run, sin caching)

| Motor | Queries | Coste/1.000 | Total |
|---|---:|---:|---:|
| GPT-4o | 2.400 | $10.40 | **$25** |
| Gemini 2.5 Pro | 2.400 | $5.20 | **$12.50** |
| **Subtotal 1 run** | 4.800 | — | **~$37.50** |

---

## Coste con 3 runs (canon GEORadar para medir varianza)

| Motor | Queries × 3 | Total |
|---|---:|---:|
| GPT-4o | 7.200 | **$75** |
| Gemini 2.5 Pro | 7.200 | **$37** |
| **Subtotal 3 runs** | 14.400 | **~$112** |

---

## Coste con caching agresivo

Los prompts comparten **persona-context** (~500 tokens de descripción persona). Si se cachea el persona-context:
- **GPT-4o**: 50% reducción en input cost (Anthropic-style cache discount equivalente).
- **Gemini 2.5 Pro**: 75% reducción en input cost.

| Motor | Queries × 3 con cache | Total |
|---|---:|---:|
| GPT-4o | 7.200 | **~$50** |
| Gemini 2.5 Pro | 7.200 | **~$20** |
| **Subtotal con cache** | 14.400 | **~$70** |

✅ **Este es el coste base recomendado**.

---

## Add-ons opcionales

### Add-on 1 — Añadir Claude Sonnet 4.6
- 2.400 × 3 runs × $15.45/1.000 con cache 90% = **~$30**
- **Aporta**: tercer motor con sesgo distinto. **Recomendado para H4** (sesgo por origen) — más motores = más variabilidad detectable.
- **Valor incremental**: alto. Es el motor con sesgo más distinto a OpenAI/Google.

### Add-on 2 — Añadir Perplexity Sonar Pro
- 2.400 × 3 runs × $3.45/1.000 = **~$25**
- **Aporta**: motor search-first. Útil para H2 (¿vale la pena ir?) y H3 (mejor sede) — captura intención logística.
- **Valor incremental**: medio. Aporta cobertura search-real-time.

### Add-on 3 — Añadir Google AI Overviews (AIO)
- 2.400 × 3 runs × ~$200/1.000 (scraping vía `498AS/ai-overviews-research`) = **~$1.440**
- **Aporta**: canon mayo 2026, cobertura 21% búsquedas Google. Argumento metodológico de peso para press release.
- **Valor incremental**: alto si el target editorial es prensa premium. ⚠️ Es el add-on más caro pero también el más diferencial.

### Add-on 4 — UI scraping validation (sample 10%)
- 240 queries vía consumer UI (ChatGPT.com, gemini.google.com) con proxies + browser automation
- Coste: ~$300–500 dependiendo de infra
- **Aporta**: validación de que las respuestas API son congruentes con lo que el fan real ve en la UI consumer.
- **Valor incremental**: medio. Mejora la honestidad metodológica del informe.

---

## Total con add-ons

| Configuración | Coste estimado |
|---|---:|
| Solo base (Escenario B) | ~$70 |
| + Claude (Escenario C) | ~$100 |
| + Claude + Perplexity | ~$125 |
| + Claude + Perplexity + AIO (Escenario D) | **~$1.565** |
| + Claude + Perplexity + AIO + UI validation | **~$1.965** |

---

## Comparativa de escenarios

| Escenario | Motores | Runs | Caching | Coste total | Recomendación |
|---|---|---:|---|---:|---|
| **A · Light** | ChatGPT + Gemini | 1 | No | **~$38** | PoC inicial |
| **B · Standard** ⭐ | ChatGPT + Gemini | 3 | Sí | **~$70** | **Recomendado v2.1** |
| **C · Robusto** | + Claude | 3 | Sí | **~$100** | Recomendado si presupuesto permite |
| **D · Canon GEORadar** | + Claude + Perplexity + AIO | 3 | Sí | **~$1.565** | Si se quiere autoridad metodológica máxima |

---

## Costes que NO son API

| Concepto | Estimación | Owner |
|---|---|---|
| Infra orquestación (queue, retries, dedup) | Eng interno 498A (~1 día) | Eng 498A |
| Parsing + extracción de menciones, sentiment, entidades | ~3 días processing | Data scientist |
| KPI extraction (SOV, Sentiment, Position, Premise) | ~2 días con tooling existente 498A | Data scientist |
| QA humana 5% sample | $200–500 si externalizado | QA / interno |
| Diseño editorial informe | ~3–5 días | Editorial Zoopa |
| Infografías | ~2–3 días | Diseño Zoopa |
| PR + outreach medios | ~1 semana | Comunicación Zoopa |

**Total tiempo interno estimado**: ~10–15 días-persona.

---

## Estrategia de caching técnica

### Estructura recomendada del prompt

```
[SYSTEM] (cacheable)
Eres ChatGPT respondiendo a un usuario con este perfil:

Persona: Mateo Álvarez
Edad: 28
Ubicación: Buenos Aires, Argentina
Idioma nativo: Español argentino
Profesión: Contador
Contexto: Hincha de Boca y Selección argentina. Planifica viaje al Mundial 2026.
Cómo se informa: TyC Sports, Olé, Romero Argentina, ChatGPT
Tono esperado: Directo, coloquial argentino.

Responde en su idioma nativo, en tono natural, con la profundidad de respuesta habitual.

[USER] (variable, no cacheable)
{prompt_seed}
```

La parte system (~500 tokens) se cachea → **50–90% reducción de input cost** según el motor.

### Implementación

- **Anthropic Claude**: cache control headers nativos (90% discount, 5min TTL extensible).
- **OpenAI GPT-4o**: prompt caching automático (50% discount, 1 hora TTL).
- **Gemini 2.5 Pro**: context caching API (75% discount, configurable TTL).

Coste de implementación: **~0.5 días eng**.

---

## Motores considerados y descartados

| Motor | Por qué descartado |
|---|---|
| Copilot (Microsoft) | Usa GPT-4 underneath → redundante con ChatGPT en la práctica |
| Grok 3 (xAI) | Penetración limitada fuera USA, sesgo político fuerte distorsiona análisis general |
| DeepSeek | Útil para benchmark ROI pero no aporta cobertura de mercado FIFA específico |
| Mistral | Cuota baja en mercados objetivo del estudio |
| Claude Opus 4.7 | Overkill para este tipo de prompts; delta de calidad marginal vs Sonnet 4.6 |
| GPT-5 (si disponible) | Coste 2× vs GPT-4o; el delta de calidad no justifica para este caso |

---

## Comparativa con estudios análogos

Para contexto, costes de estudios cuantitativos comparables:

| Estudio | Coste típico |
|---|---:|
| Nielsen panel de marca | $30.000–80.000 |
| YouGov omnibus survey | $15.000–40.000 |
| Kantar custom research | $50.000–150.000 |
| **Esta auditoría (Escenario B)** | **~$70 hard + tiempo interno** |
| **Esta auditoría (Escenario D con AIO)** | **~$1.565 hard + tiempo interno** |

→ El **ROI por dólar invertido** en este estudio es 100–1.000× superior a un Nielsen equivalente, gracias a la infra GEORadar.

---

## Decisiones pendientes

- [ ] **Validar pricing exacto** al momento del lanzamiento (pre-jun 2026).
- [ ] **Decidir si se incluye AIO** (Escenario D vs B) → impacto de coste ~20×.
- [ ] **Definir caching implementation**: Anthropic Cache Control nativo vs OpenAI auto-cache vs custom.
- [ ] **Confirmar si Claude se incluye** (Escenario C).
- [ ] **Validar consumer UI fidelity** (sampling 10%) → impacto de coste +$300-500.
- [ ] **Confirmar plan de re-runs** si hay updates de modelos durante la ventana (jun–jul 2026).

---

## Próximos pasos

1. Validación interna del Escenario B como base.
2. Decisión sobre AIO (Escenario D) — depende del budget editorial y target medios.
3. Implementación del caching (~0.5 días eng).
4. Setup de pipeline de orquestación.
5. Ejecución pre-evento (mar–may 2026) con auditoría baseline.

---

## Anexo · cálculo detallado por escenario

### Escenario A · Light
```
2.400 queries × 2 motores × 1 run = 4.800 calls
- GPT-4o: 2.400 × $10.40/1K = $25.00
- Gemini 2.5 Pro: 2.400 × $5.20/1K = $12.50
TOTAL: $37.50
```

### Escenario B · Standard ⭐
```
2.400 queries × 2 motores × 3 runs = 14.400 calls
Caching reduce input cost 50-75%
- GPT-4o: 7.200 × $10.40/1K × (1 - 0.30 caching effective) = ~$52
- Gemini 2.5 Pro: 7.200 × $5.20/1K × (1 - 0.50 caching effective) = ~$19
TOTAL: ~$71
```

### Escenario C · Robusto
```
Escenario B + Claude Sonnet 4.6:
- Claude: 7.200 × $15.45/1K × (1 - 0.85 caching) = ~$17
TOTAL: ~$88
```

### Escenario D · Canon GEORadar
```
Escenario C + Perplexity + AIO:
- Perplexity Sonar Pro: 7.200 × $3.45/1K = ~$25
- AIO scraping: 7.200 × $200/1K = ~$1.440
TOTAL: ~$1.553
```
