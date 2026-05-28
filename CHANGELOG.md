# Changelog

> Historial de decisiones de la propuesta de auditoría GEO Mundial 2026.

## [v2.4] - 2026-05-26

**Eliminada la sección "Tesis a validar" del HTML**

- Removida §1 "Tesis a validar" de `docs/index.html`; renumeradas §2→§1 … §10→§9; ref cruzada §5→§4 (Output → Plan de difusión).
- Nuevo orden HTML: 1 El estudio en breve · 2 Titulares · 3 Hipótesis · 4 Plan de difusión · 5 Metodología · 6 Personas · 7 Estructura prompts · 8 Output · 9 Costes · Anexo A (16 personas).
- Nota: `01-proposal/01-planteamiento.md` (markdown source) mantiene su sección de tesis — pendiente de sincronizar si se desea.

## [v2.3] - 2026-05-26

**Costes API ×150 (últimas versiones de modelo) + HTML unificado**

- Todos los costes de API multiplicados **×150** sobre la línea base GPT-4o, por uso de las últimas versiones premium (mayor precio por token + tokens de razonamiento). El scraping de AIO no se multiplica (no es coste de modelo).
- Escenario B (recomendado): ~$70 → **~$10.500**. Total hard ~$250–620 → **~$7.700–18.500**.
- Add-ons ×150: Claude +$30 → +$4.500 · Perplexity +$25 → +$3.750 · AIO +$1.440 (sin cambio).
- Reframe de la comparativa: el estudio sigue por debajo de un panel YouGov/Nielsen, pero ya no se sostiene el claim "100–1.000× más barato".
- Actualizado en: `04-motores-coste.md`, `01-planteamiento.md` §10, `README.md`, `docs/index.html` §10.
- HTML (`docs/index.html`): Hipótesis reordenada a §4 (antes de Difusión) + Anexo A con las 16 fichas completas de personas (documento unificado autocontenido).

## [v2.2] - 2026-05-26

**Reordenación + nuevas secciones del planteamiento** (`01-proposal/01-planteamiento.md`)

- **Reorden**: las tesis a validar pasan a ser la sección 1 (apertura del documento).
- **Nueva sección 2 · El estudio en breve**: intro con el objetivo del estudio — cómo las IAs influyen en opinión y decisiones de compra respecto al Mundial. Explicita el mercado en juego (viajes, entradas, hospedaje, merchandising, apuestas, streaming, marcas sponsor).
- **Nueva sección 3 · Titulares que puede generar el estudio**: ejemplos agrupados por ángulo editorial (predicción, viaje, sesgo, sponsors, controversias).
- **Nueva sección 4 · Plan de difusión**: 4 fases (pre-lanzamiento con briefing a FIFA + sponsors · rueda de prensa · amplificación editorial · long tail B2B). Incluye shortlist de media partners (nacional + internacional) y KPIs de difusión.
- Decisiones pendientes ampliadas con 3 ítems de difusión (interlocutor FIFA, media partners, formato evento).

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
