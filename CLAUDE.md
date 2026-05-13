# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

**Anaju Neves Hub** is a static, no-build-system personal dashboard for Ana Julia Neves (FIAP Marketing Digital student). It is a collection of HTML files, inline CSS/JS, and JSON data files deployed via GitHub Pages from the `main` branch. There is no npm, no framework, no bundler.

The product name is always **"Anaju Neves Hub"**. Never use J.One, Life OS, v1/v2, or any versionated names in UI text.

## How to develop and test

Since there is no build step, development is:
1. Edit HTML, JSON, or `.ics` files directly.
2. Open the file in a browser to test locally (or use any local static server, e.g. `python3 -m http.server`).
3. Verify against the QA checklist at `docs/QA_RELEASE_CHECKLIST.md` before merging to `main`.
4. GitHub Pages auto-deploys from `main` after merge.

Feature work should happen on a new branch created from `main`. Stable releases are tagged (e.g. `v1.0.0-anaju-neves-hub-stable`).

## File map

| File | Role |
|---|---|
| `index.html` | Entry point — home page linking to all sections |
| `anaju-neves-hub.html` | **Main dashboard** (v1.1 — primary file in active development) |
| `calendario-operacional.html` | Standalone calendar view |
| `hub-operacional.html` | Operational quick-access flow |
| `hub-status-atual.html` | Current hub status summary |
| `materiais.html` | PDF reader/library viewer |
| `regras-fiap.html` | FIAP rules and academic guides |
| `dashboard.html` | **Legacy** (sanitized, no credentials, keep for reference only) |
| `home.html`, `life-os.html` | **Legacy** — keep for reference, not linked from main nav |

### Data files (`data/`)

Each JSON file feeds a specific section of `anaju-neves-hub.html` via `fetch()`. Every file has a fallback constant in the HTML for graceful degradation.

| File | Feeds | Notes |
|---|---|---|
| `academic.json` | FIAP section | Profile, 7 phases, tasks with priorities and due dates |
| `materials.json` | Biblioteca | Collections of PDFs by phase; `classificationRules` governs how new items are treated |
| `rules.json` | FIAP › Guias/Normas | Practical rule cards extracted from institutional PDFs |
| `martech.json` | Cursos | MarTech extracurricular course phases and modules |
| `quick-links.json` | Links | 4 groups: Acadêmico, Cursos, Ferramentas, Projeto |
| `assets.json` | Documentos | Visual references, personal docs, logos (with `category` field) |
| `solar-plus.json` | FIAP › Solar+ | Academic project tracker |
| `calendars.json` | Calendário | Calendar source config (paths to `.ics` files); no credentials |
| `branding.json` | Internal | Product name and tagline only |
| `courses.json` | Internal | Course data reference |

### Calendar files (`.ics`)

Three files at repo root:
- `icalexport.ics` — FIAP & Afins (academic events)
- `calendar-compromissos.ics` — Personal commitments
- `calendar-lm.ics` — Calendar L.M. (sanitized: ATTENDEE emails removed in Task 42)

## Architecture of `anaju-neves-hub.html`

This single file contains all CSS, HTML structure, and JavaScript inline. Key patterns:

**State:** Single `state` object holds all loaded data and UI state. Persisted fields (done tasks, deleted tasks, filters, lowStim mode) are saved to `localStorage` under key `anaju-neves-hub`.

**Data loading:** `getJson(path, fallback)` — async, uses `cache:'no-store'`, returns the fallback constant on any error.

**Rendering:** One `render*()` function per section, called on navigation. Each function writes HTML into its `#view-*` element via `.innerHTML`. Utility functions produce HTML strings: `taskCard()`, `materialCard()`, `eventCard()`, `linkCard()`, `assetCard()`, `sourceCard()`, `martechModuleCard()`.

**Navigation:** `setView(view)` toggles `.active` on views and nav buttons, updates `location.hash`.

**Calendar parsing:** `parseICal(raw, source)` is a hand-rolled iCal parser. Events are classified by title keywords via `classifyEvent()`. `loadCalendar()` fetches all enabled sources from `calendars.json` and populates `state.events`.

**Task scoring:** `taskScore(t)` sorts by `adaptedDue/baseDue` then priority. Deleted tasks are tracked in `state.deletedTasks` (localStorage) and hidden from all views.

**Security:** `esc(s)` HTML-escapes all interpolated strings. External links always use `target="_blank" rel="noopener"`. No credentials, tokens, or personal emails are stored anywhere in the repository.

## Design system

CSS custom properties in `:root`:

```
--bg: #070707        --text: #f5f5f5
--accent: #ED145B    --warn: #f59e0b
--blue: #3b82f6      --green: #22c55e
--muted: #a1a1aa     --faint: #71717a
--line: #292933      --soft: #1d1d24
--serif: 'Newsreader'   --mono: 'JetBrains Mono'
--radius: 18px
```

Utility classes: `.card`, `.pad`, `.btn`, `.btn.primary`, `.btn.small`, `.tag`, `.item`, `.grid-2/3/4`, `.stack`, `.split`, `.row`, `.kicker`, `.progress`, `.empty`, `.filters`, `.metric`.

## Content rules

These are hard product constraints, not preferences:

- **No motivational phrases.** All text must be operational: explain function, source, or status.
- **No versionated labels** (v1/v2) visible in the UI.
- **Content hierarchy is strict:** FIAP rules/guides belong in FIAP; chapters/PDFs belong in Biblioteca; professional courses in Cursos; quick access in Links; manually added extras only in Documentos.
- **PDFs are cataloged and opened, not summarized.** Classification rules in `data/materials.json → classificationRules` govern how new items are treated.
- **Show gaps explicitly** rather than hiding incomplete data — empty states and "pending triage" tags are intentional.
- **Credentials never go in the repo.** No passwords, tokens, or private calendar URLs.

## Adding or editing content

**New task:** add to `tasks[]` in `data/academic.json` with `id`, `title`, `area`, `type`, `priority` (alta/media/baixa), `phase`, `baseDue`, `adaptedDue`, `source`, `status`, `note`.

**New material/PDF:** add to the appropriate collection in `data/materials.json → collections[].items`. Required fields: `id`, `title`, `phase`, `chapterNumber`, `discipline`, `type`, `source`, `path` (relative from repo root), `estimatedReadingMode`.

**New link:** add to the matching group in `data/quick-links.json → groups[].links` with `title`, `url`, `description`. Internal hash links use `#sectionname`.

**New rule card:** add to the correct section in `data/rules.json → sections[].rules` with `id`, `title`, `source`, `sourcePath`, `impact`, `action`, `status`, `riskLevel`.

**New asset/document:** add to `data/assets.json → assets[]` with `path`, `type`, `category` (personal/visual_reference/extra), `likelyUse`, `notes`.

## Before merging to main

Run through `docs/QA_RELEASE_CHECKLIST.md`. Key checks:
- All pages load without console errors.
- No broken links (`lucca.ics`, `basic.ics`, `ana-pessoal.ics` were deleted — ensure no references remain).
- No credentials or personal emails in any file (`grep -r "senha\|password\|login" .`).
- PDFs in `materiais/` are accessible via their paths in `materials.json`.
- GitHub Pages deploys from `main` — verify after merge.
