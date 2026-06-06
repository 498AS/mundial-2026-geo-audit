# CLAUDE.md · mundial-2026-geo-audit

> Contexto que Claude Code carga automáticamente al abrir este repo. Léelo entero antes de hacer cambios.

## Qué es este repo

Propuesta de **auditoría GEO del Mundial FIFA 2026** para Zoopa / 498A Innovation Lab. Mide cómo **ChatGPT y Gemini** representan el torneo a hinchas de 16 países, en 4 idiomas. Deliverable: informe periodístico publicable + dataset abierto.

- Cliente: **Zoopa · 498A Innovation Lab**
- Marca observada: Mundial FIFA 2026 (evento, no marca-empresa)
- Versión actual: **v2.5** (ver `CHANGELOG.md`)

---

## ⚠️ Regla crítica · doble formato paralelo

El contenido vive en **dos formatos que NO se generan uno del otro**:

| Formato | Ubicación | Para qué |
|---|---|---|
| Fuente markdown | `01-proposal/*.md` + `00-context/*.md` | Editable, base canónica del contenido |
| Documento publicado | `docs/index.html` | HTML imprimible servido por GitHub Pages |

**Si cambias contenido, debes actualizar AMBOS.** La divergencia entre `.md` y `docs/index.html` es el principal gotcha del repo.

Antes de hacer un cambio:
1. Identifica si afecta solo a uno o a ambos.
2. Hazlo en los dos sitios.
3. Verifica con `grep` que los strings clave aparecen donde deben (especialmente cifras, presupuestos, números de hipótesis).

---

## Mapa de archivos

```
.
├── README.md                              ← Punto de entrada
├── CHANGELOG.md                           ← Historial de versiones (v1.0 → v2.5)
├── CLAUDE.md                              ← Este archivo
├── .gitignore                             ← Ignora HTML sueltos en root
├── 00-context/
│   ├── mundial-fifa-2026.md               ← Datos del Mundial (sponsors, revenue, modelo de negocio)
│   └── georadar-workflow.md               ← Por qué este enfoque encaja con GEORadar
├── 01-proposal/                           ← FUENTE MARKDOWN
│   ├── 01-planteamiento.md                ← Propuesta canónica (tesis, estudio, titulares, hipótesis, difusión, costes...)
│   ├── 02-personas.md                     ← 16 personas (tabla + rationale)
│   ├── 03-hipotesis.md                    ← H1–H6 con KPI mapping
│   ├── 04-motores-coste.md                ← Stack + escenarios coste (×150 últimas versiones)
│   └── 05-prompts-estructura.md           ← Template de 150 prompts/persona
├── 02-original/
│   └── ZOOPA_MUNDIAL2026_..._v02.html     ← Snapshot histórico — NO EDITAR
└── docs/                                  ← Publicado por GitHub Pages
    ├── index.html                         ← Planteamiento (live)
    ├── informe.html                       ← INFORME del estudio · v2 junio 2026
    └── informe.pdf                        ← Versión PDF del informe
```

---

## Flujo de publicación

GitHub Pages sirve `docs/index.html` en https://498as.github.io/mundial-2026-geo-audit/.

```bash
# Cualquier push a main que toque docs/ → Pages reconstruye solo en ~1 min
git add <archivos específicos>
git commit -m "..."
git push
```

Verificación opcional del rebuild:
```bash
gh api repos/498AS/mundial-2026-geo-audit/pages/builds/latest --jq '.status,.commit'
```

---

## Convenciones

- **CHANGELOG**: añade entrada al hacer cambios significativos, sube versión semántica (parche para tweaks, minor para nuevas secciones/decisiones).
- **Commits**: en inglés, descripción concisa orientada al "por qué", footer:
  ```
  Co-Authored-By: Claude Opus 4.7 (1M context) <noreply@anthropic.com>
  ```
- **❌ NO uses `git add -A`** — hay HTML sueltos en root (descargas) que están en `.gitignore` pero conviene añadir archivos por nombre explícito para evitar accidentes.
- **Idioma del contenido**: ES por defecto (cliente Zoopa, mercado español + LATAM); EN para código.
- **Estilo**: McKinsey / Smart Brevity (conciso, accionable, sin emojis en doc técnico salvo que se pida).

---

## Estado actual (v2.5) · snapshot de decisiones

| Variable | Valor |
|---|---|
| Personas | **16** (10 country-fan + 4 variantes + 2 B2B contexto) |
| Prompts por persona | **150** |
| Total seed prompts unique | **2.400** |
| Motores | ChatGPT 4o + Gemini 2.5 Pro (últimas versiones premium) |
| Multiplicador coste API | **×150** sobre línea base GPT-4o |
| Coste API Escenario B (recomendado) | **~$10.500** |
| Idiomas | ES · EN · PT-BR · FR |
| Hipótesis | H1–H6 + bonus H7–H11 (climática) |
| Hueco identificado | Falta persona **AFC** (Japón / Arabia / Uzbekistán) — recomendado añadir |

### Hipótesis temáticas clave
- **H1** quién gana · **H2** ¿vale la pena viajar? · **H3** mejor host (incl. clima) · **H4** sesgo por origen · **H5** IA vs cuotas reales · **H6** storyboard.
- **Eje climático (v2.5)**: el calor extremo (35–45 °C en México, Texas, sur USA) inclina la recomendación de la IA hacia Canadá. Capturado en tesis #11, H3 (Climate Bias Index), grupo de titulares "Clima y calor extremo", y H11 bonus.

---

## Checklist antes de pushear

- [ ] ¿Cambié solo `.md`? Considera si también va al HTML (Anexo A o §correspondiente).
- [ ] ¿Cambié solo `docs/index.html`? Considera si también va al `.md` fuente.
- [ ] ¿Añadí entrada al `CHANGELOG.md` con la nueva versión?
- [ ] ¿Mi commit usa archivos específicos (no `git add -A`)?
- [ ] Si el cambio toca `docs/`, recuerda: Pages auto-publica en ~1 min.

---

## No-go's

- ❌ NO editar `02-original/ZOOPA_MUNDIAL2026_..._v02.html` — es el snapshot histórico del HTML original v02 (21 may 2026).
- ❌ NO usar `git add -A` — acaba metiendo HTML sueltos en root.
- ❌ NO romper la sincronía `.md` ↔ HTML sin documentarlo en CHANGELOG.
- ❌ NO commitear datos sensibles (API keys, datasets confidenciales de clientes GEORadar).
- ❌ NO renumerar secciones del HTML sin actualizar también las cross-references internas (`ver §N`).

---

## Referencias externas

- **Repo público**: https://github.com/498AS/mundial-2026-geo-audit
- **Web publicada**: https://498as.github.io/mundial-2026-geo-audit/
- **GEORadar canónico** (interno vault 498A): `georadar-stack-metodologia-faq-20260512.md`
- **AI Overviews research** (Pages canon mayo 2026): https://github.com/498AS/ai-overviews-research

---

*Última actualización: 2026-05-26 · v2.5 · mantenedor original: Carlos Ortet (carlos.ortet@zoopa.es)*
