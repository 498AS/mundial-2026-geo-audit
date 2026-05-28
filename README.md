# Mundial 2026 · Auditoría GEO

> Propuesta de auditoría comparativa de cómo **ChatGPT y Gemini** representan el Mundial FIFA 2026 a hinchas de 16 países distintos. Material para informe periodístico publicable.

| | |
|---|---|
| **Cliente** | Zoopa · 498A Innovation Lab |
| **Marca observada** | Mundial FIFA 2026 |
| **Deliverable** | Informe periodístico publicable + dataset abierto |
| **Estado** | 🟡 Propuesta v2.1 — pendiente de validación interna |
| **Última actualización** | 2026-05-26 |

---

## TL;DR

- **16 customer personas** · 14 fan + 2 B2B contexto · 4 idiomas (ES · EN · PT · FR)
- **150 prompts por persona** · ~2.400 prompts seed unique per motor
- **2 motores**: ChatGPT 4o + Gemini 2.5 Pro (ampliables a Claude + Perplexity + AIO)
- **6 hipótesis** (H1–H6) con titulares editoriales pre-mapeados
- **Coste API estimado**: ~$7.500–18.000 USD (Escenario B, 3 runs, caching · últimas versiones de modelo ×150)
- **Output**: informe periodístico + 8-12 titulares + 4-6 infografías + dataset publicable

---

## Estructura del repo

```
mundial-2026-geo-audit/
├── README.md                                                     ← Este archivo
├── CHANGELOG.md                                                  ← Historial de versiones
├── 00-context/
│   ├── mundial-fifa-2026.md                                      ← Datos del torneo (sponsors, revenue, modelo de negocio)
│   └── georadar-workflow.md                                      ← Por qué encaja con metodología GEORadar
├── 01-proposal/
│   ├── 01-planteamiento.md                                       ← Propuesta canónica
│   ├── 02-personas.md                                            ← 16 personas (tabla + rationale)
│   ├── 03-hipotesis.md                                           ← H1–H6 con KPI mapping
│   ├── 04-motores-coste.md                                       ← Stack + escenarios coste
│   └── 05-prompts-estructura.md                                  ← Template de 150 prompts/persona
└── 02-original/
    └── ZOOPA_MUNDIAL2026_PROPUESTA_PERSONAS_20260521_v02.html    ← HTML original v02 (21 may 2026)
```

---

## Quick start

```bash
gh repo clone 498AS/mundial-2026-geo-audit
cd mundial-2026-geo-audit

# Orden de lectura recomendado
open README.md                                  # estás aquí
open 00-context/mundial-fifa-2026.md            # contexto del Mundial
open 00-context/georadar-workflow.md            # por qué este enfoque
open 01-proposal/01-planteamiento.md            # visión global
open 01-proposal/02-personas.md                 # las 16 personas
open 01-proposal/03-hipotesis.md                # H1–H6
open 01-proposal/04-motores-coste.md            # presupuesto
open 01-proposal/05-prompts-estructura.md       # los 150 prompts por persona
```

---

## Next steps (operativo)

| # | Tarea | Owner | Estado |
|---|---|---|---|
| 1 | Validar propuesta v2.1 con Carlos / equipo Zoopa | Carlos | 🟡 Pendiente |
| 2 | Decidir si se añade persona AFC (Japón / Arabia Saudí / Uzbekistán) | Carlos | 🟡 Pendiente |
| 3 | Definir tooling de orquestación (LangChain · script propio · GEORadar pipeline) | Eng 498A | ⏳ Bloqueado por #1 |
| 4 | Generar los 150 prompts × 16 personas (2.400 seed) | Prompt eng | ⏳ Bloqueado por #1 |
| 5 | Pipeline de ejecución contra ChatGPT + Gemini | Eng 498A | ⏳ Bloqueado por #3 |
| 6 | KPI extraction (SOV, Sentiment, Position, Premise Validation) | Data scientist | ⏳ |
| 7 | Storyboard editorial + titulares | Editorial Zoopa | ⏳ |
| 8 | Infografías | Diseño Zoopa | ⏳ |
| 9 | PR + outreach a medios | Comunicación Zoopa | ⏳ |

---

## Decisiones clave registradas

| Decisión | Versión | Detalle |
|---|---|---|
| Volumen por persona | v2.1 | 150 prompts/persona (vs 5 seeds en v2.0) |
| Stack motorial | v2.1 | ChatGPT + Gemini (vs 4 LLMs + AIO en propuesta canónica GEORadar) |
| Personas | v2.0 | 16 personas (10 country fan + 4 variantes + 2 B2B contexto) |
| Idiomas | v2.0 | ES · EN · PT · FR |
| Variantes ×3 por seed | v2.0 | Neutra · Personalizada · Coloquial |
| Hipótesis | v2.0 | 6 hipótesis fan-facing comparativas (H1–H6) |
| CORE comparable | v2.0 | 3 prompts raíz cross-persona como backbone narrativo |

Ver `CHANGELOG.md` para historial completo.

---

## Equipo

- **Carlos Ortet** — Strategy lead · CEO Zoopa · Director 498A · `carlos.ortet@zoopa.es`
- *(Pending)* — Prompt engineer
- *(Pending)* — Data scientist (KPI extraction)
- *(Pending)* — Editorial lead

---

## Referencias

- [GEORadar canonical reference](https://github.com/498AS/docs-geo) — metodología 6 módulos + KPIs por industria
- [ai-overviews-research](https://github.com/498AS/ai-overviews-research) — infra de scraping AIO Google (canon mayo 2026)
- [georadar.app](https://georadar.app) — web pública del producto
- [proceso-geo-georadar (web pública)](https://498as.github.io/proceso-geo-georadar/) — proceso cliente

---

## Licencia

Propietario · Zoopa / 498A · 2026
