# Changelog

> Historial de decisiones de la propuesta de auditoría GEO Mundial 2026.

## [v2.1] - 2026-05-26

**Cambios mayores**
- **Volumen escalado**: pasa de 5 prompts seed por persona (80 total) a **150 prompts por persona** (2.400 seed unique per motor).
- **Stack motorial confirmado**: ChatGPT 4o + Gemini 2.5 Pro como base. Claude + Perplexity + AIO quedan como add-ons opcionales con coste calculado.
- **Coste API recalculado**: ~$50–120 USD para Escenario B (2 motores, 3 runs, con caching).
- Repo reestructurado en `00-context/`, `01-proposal/`, `02-original/`.

**Decisiones pendientes**
- ¿Se añade persona AFC (Japón / Arabia Saudí / Uzbekistán)? Recomendado para cerrar hueco de confederación.
- ¿Se incluye Google AIO en el stack? Coste adicional ~$1.440 pero invoca canon GEORadar mayo 2026.
- ¿Patricia y Eduardo siguen patrón 150 con CORE B2B-adaptado, o reducido a ~50 prompts cada uno?

**Documentación nueva**
- `00-context/mundial-fifa-2026.md` — datos completos del torneo, modelo de negocio, sponsors, derechos TV.
- `00-context/georadar-workflow.md` — explicación de por qué este planteamiento encaja con la metodología GEORadar canónica.
- `01-proposal/01-planteamiento.md` — propuesta canónica actualizada.
- `01-proposal/02-personas.md` — overview tabular de las 16 personas + propuestas de mejora.
- `01-proposal/03-hipotesis.md` — H1–H6 con mapeo a KPIs GEORadar.
- `01-proposal/04-motores-coste.md` — 4 escenarios de coste (Light · Standard · Robusto · Canon GEORadar).
- `01-proposal/05-prompts-estructura.md` — distribución de los 150 prompts en 7 bloques (A–G).

---

## [v2.0] - 2026-05-21

**HTML inicial** `ZOOPA_MUNDIAL2026_PROPUESTA_PERSONAS_20260521_v02.html`

- 16 personas detalladas con ficha completa: descripción, demográficos, prioridades, objetivos, pain points, memories, 5 prompts semilla.
- 6 hipótesis (H1–H6) con titulares editoriales pre-mapeados.
- 2 motores definidos: ChatGPT + Gemini.
- 4 idiomas: ES · EN · PT · FR.
- 80 prompts seed totales (5 × 16), expansibles a ~480 con variantes ×3 × 2 motores.
- Tag CORE introducido (3 prompts comparables cross-persona).
- Tier system (T1 mainstream, T2 variantes, T3 B2B contexto).

---

## [v1.0] - 2026-05-15 (estimado)

**Brainstorm inicial**

- 10 country fans (Argentina, Brasil, España, Francia, UK, Alemania, México, USA, Canadá, Marruecos).
- 4 segment variants (familia hispana Miami, apostadora Sudáfrica, casual Colombia, crítico Uruguay).
- 2 B2B contexto (VP Sponsorship FIFA, CMO Sportsbook LATAM).
- Concepto general validado: auditoría fan-facing comparativa, deliverable periodístico.
