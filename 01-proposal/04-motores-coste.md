# Motores + coste estimado

> Versión: v2.3 · 2026-05-26
> Decisión base: 150 prompts × 16 personas = **2.400 seed unique per motor**

---

## ⚠️ Ajuste ×150 por uso de las últimas versiones de modelo

Todas las cifras de coste de API de este documento están **multiplicadas ×150** sobre la línea base GPT-4o (mayo 2026), por decisión de usar las **últimas versiones premium** de los modelos (GPT-5 Pro / o3-pro, Gemini Ultra, Claude Opus con extended thinking). El multiplicador refleja dos efectos combinados:

1. **Mayor precio por token** de las versiones premium (≈3–8× la línea base).
2. **Volumen de tokens de razonamiento** que generan los modelos con thinking (≈20–50× más tokens de salida por query).

> El **scraping de Google AIO no se multiplica ×150** — no es coste de modelo, sino de infraestructura de scraping (precio fijo por query).

---

## Decisión actual (Escenario B · Standard)

- **Motores principales**: ChatGPT (última versión) + Gemini (última versión)
- **Volumen**: 2.400 seed prompts × 2 motores = **4.800 calls** (1 run) o **14.400 calls** (3 runs)
- **Coste API total estimado**: **$7.500–18.000 USD**

---

## Pricing por modelo

Línea base GPT-4o-class (mayo 2026), prompt promedio **150 tokens input + 1.000 tokens output**, y coste efectivo ×150 con últimas versiones premium.

| Modelo | Coste/1.000 queries (base) | Coste/1.000 queries (×150, últimas versiones) |
|---|---:|---:|
| **ChatGPT (GPT-5 / o3-pro)** | $10.40 | ~$1.560 |
| **Gemini (Ultra / 2.5 Deep Think)** | $5.20 | ~$780 |
| **Claude (Opus-class + thinking)** | $15.45 | ~$2.318 |
| **Perplexity Sonar Pro** | $3.45 | ~$518 |
| **Google AIO** (scraping, sin ×150) | — | ~$100–300 |

> ⚠️ Precios fluctúan. Re-verificar antes del lanzamiento de la auditoría.

---

## Coste base (1 run, sin caching) · ×150

| Motor | Queries | Coste/1.000 | Total |
|---|---:|---:|---:|
| ChatGPT | 2.400 | $1.560 | **$3.750** |
| Gemini | 2.400 | $780 | **$1.875** |
| **Subtotal 1 run** | 4.800 | — | **~$5.600** |

---

## Coste con 3 runs (canon GEORadar) · ×150

| Motor | Queries × 3 | Total |
|---|---:|---:|
| ChatGPT | 7.200 | **$11.250** |
| Gemini | 7.200 | **$5.600** |
| **Subtotal 3 runs (sin caching)** | 14.400 | **~$16.850** |

---

## Coste con caching agresivo (3 runs) · ×150

Cacheando el persona-context (~500 tokens) se reduce 50–75% el input cost.

| Motor | Queries × 3 con cache | Total |
|---|---:|---:|
| ChatGPT | 7.200 | **~$7.500** |
| Gemini | 7.200 | **~$3.000** |
| **Subtotal con cache** | 14.400 | **~$10.500** |

✅ **Coste base recomendado (Escenario B): ~$10.500**.

---

## Add-ons opcionales · ×150

### Add-on 1 — Añadir Claude (Opus-class)
- 2.400 × 3 runs con cache → **~$4.500**
- Aporta tercer motor con sesgo distinto. Recomendado para H4 (sesgo por origen).

### Add-on 2 — Añadir Perplexity Sonar Pro
- 2.400 × 3 runs → **~$3.750**
- Motor search-first. Útil para H2 y H3 (intención logística).

### Add-on 3 — Añadir Google AI Overviews (AIO)
- 2.400 × 3 runs × ~$200/1.000 (scraping, **sin ×150**) → **~$1.440**
- Canon mayo 2026, cobertura 21% búsquedas Google. El add-on más diferencial para el press release.

### Add-on 4 — UI scraping validation (sample 10%)
- ~240 queries vía consumer UI con proxies → **~$300–500** (scraping, sin ×150)
- Valida fidelidad API↔UI.

---

## Comparativa de escenarios · ×150

| Escenario | Motores | Runs | Caching | Coste total | Recomendación |
|---|---|---:|---|---:|---|
| **A · Light** | ChatGPT + Gemini | 1 | No | **~$5.700** | PoC inicial |
| **B · Standard** ⭐ | ChatGPT + Gemini | 3 | Sí | **~$10.500** | **Recomendado v2.3** |
| **C · Robusto** | + Claude (Opus-class) | 3 | Sí | **~$15.000** | Si presupuesto permite |
| **D · Canon GEORadar** | + Claude + Perplexity + AIO | 3 | Sí | **~$20.200** | Autoridad metodológica máxima |

> **Escenario D** = LLM ×150 (~$18.750) + AIO scraping ($1.440, sin ×150) ≈ **$20.200**.

---

## Total con add-ons · ×150

| Configuración | Coste estimado |
|---|---:|
| Solo base (Escenario B) | ~$10.500 |
| + Claude (Escenario C) | ~$15.000 |
| + Claude + Perplexity | ~$18.750 |
| + Claude + Perplexity + AIO (Escenario D) | **~$20.200** |
| + todo + UI validation | **~$20.600** |

---

## Costes que NO son API (sin cambio)

| Concepto | Estimación | Owner |
|---|---|---|
| Infra orquestación | ~1 día | Eng 498A |
| Parsing + extracción de menciones | ~3 días | Data scientist |
| KPI extraction (SOV, Sentiment, Position, Premise) | ~2 días | Data scientist |
| QA humana 5% sample | $200–500 | QA / interno |
| Diseño editorial informe | ~3–5 días | Editorial Zoopa |
| Infografías | ~2–3 días | Diseño Zoopa |
| PR + outreach medios | ~1 semana | Comunicación Zoopa |

**Coste hard total (Escenario B)**: API ~$10.500 + QA ~$200–500 = **~$10.700–11.000**. Rango amplio con caching parcial: **$7.700–18.500**.

---

## Estrategia de caching técnica

### Estructura recomendada del prompt

```
[SYSTEM] (cacheable)
Eres ChatGPT respondiendo a un usuario con este perfil:
Persona: Mateo Álvarez · 28 · Buenos Aires · contador · hincha argentino...
Responde en su idioma nativo, con su tono y profundidad habituales.

[USER] (variable, no cacheable)
{prompt_seed}
```

La parte system (~500 tokens) se cachea → 50–90% reducción del input cost. Crítico para contener el coste cuando se usan modelos premium con tokens de razonamiento.

### Implementación
- **Claude**: cache control headers nativos (90% discount).
- **ChatGPT**: prompt caching automático (50% discount).
- **Gemini**: context caching API (75% discount).

Coste de implementación: ~0.5 días eng.

---

## Comparativa con estudios análogos

| Estudio | Coste típico |
|---|---:|
| YouGov omnibus survey | $15.000–40.000 |
| Nielsen panel de marca | $30.000–80.000 |
| Kantar custom research | $50.000–150.000 |
| **Esta auditoría (Escenario B · últimas versiones)** | **~$10.500 hard** + tiempo interno |
| **Esta auditoría (Escenario D con AIO)** | **~$20.200 hard** + tiempo interno |

> Aun usando las **últimas versiones premium** de los modelos, el coste se mantiene **por debajo de un panel YouGov estándar** y muy por debajo de un Nielsen/Kantar — con un dataset mucho más rico (2.400 prompts × respuestas IA × KPIs) y reutilizable.

---

## Motores considerados y descartados

| Motor | Por qué descartado |
|---|---|
| Copilot (Microsoft) | Usa GPT underneath → redundante con ChatGPT |
| Grok (xAI) | Penetración limitada fuera USA, sesgo político fuerte |
| DeepSeek | Útil para benchmark ROI pero no aporta cobertura FIFA |
| Mistral | Cuota baja en mercados objetivo |

---

## Decisiones pendientes

- [ ] **Validar pricing exacto** de las últimas versiones al momento del lanzamiento (pre-jun 2026).
- [ ] **Confirmar el multiplicador ×150** con una prueba real de 50 prompts contra los modelos premium (calibrar el coste efectivo por query).
- [ ] **Decidir si se incluye AIO** (Escenario D vs B).
- [ ] **Definir caching implementation** (clave para contener coste con modelos de razonamiento).
- [ ] **Confirmar si Claude se incluye** (Escenario C).

---

## Anexo · cálculo detallado por escenario (×150)

### Escenario A · Light
```
2.400 queries × 2 motores × 1 run = 4.800 calls
- ChatGPT: 2.400 × $1.560/1K = $3.744
- Gemini:  2.400 × $780/1K  = $1.872
TOTAL: ~$5.616
```

### Escenario B · Standard ⭐
```
2.400 × 2 motores × 3 runs = 14.400 calls, con caching
- ChatGPT: 7.200 × $1.560/1K × (caching) ≈ $7.500
- Gemini:  7.200 × $780/1K × (caching)  ≈ $3.000
TOTAL: ~$10.500
```

### Escenario C · Robusto
```
Escenario B + Claude (Opus-class):
- Claude: 7.200 × $2.318/1K × (caching 90%) ≈ $4.500
TOTAL: ~$15.000
```

### Escenario D · Canon GEORadar
```
Escenario C + Perplexity + AIO:
- Perplexity: 7.200 × $518/1K ≈ $3.750
- AIO scraping (sin ×150): 7.200 × $200/1K ≈ $1.440
TOTAL: ~$20.200
```
