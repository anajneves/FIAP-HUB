# Site Map — Anaju Neves Hub

Mapa de arquivos e estrutura de navegação atual.
Última atualização: 2026-05-08

---

## Estrutura de navegação

```
index.html  (Home — ponto de entrada)
├── anaju-neves-hub.html        → Dashboard principal
├── calendario-operacional.html → Calendário operacional (FIAP & Afins, Compromissos, L.M.)
├── hub-operacional.html        → Fluxo operacional
├── hub-status-atual.html       → Status atual do hub (Tasks 21–25)
├── materiais.html              → Leitor de materiais acadêmicos
├── regras-fiap.html            → Guias e normas FIAP
└── docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md  → Arquitetura do produto
```

---

## Arquivos HTML ativos

| Arquivo | Função | Linkado em index.html |
|---------|--------|-----------------------|
| index.html | Home / hub central | — (é a home) |
| anaju-neves-hub.html | Dashboard principal com seções | Sim |
| calendario-operacional.html | Calendário multi-fonte | Sim |
| hub-operacional.html | Fluxo e processos operacionais | Sim |
| hub-status-atual.html | Página de status atual do hub (pós Tasks 21–25, QA aprovado) | Sim |
| materiais.html | Leitor de PDFs e materiais | Sim |
| regras-fiap.html | Normas e guias FIAP | Sim |

### Arquivos HTML legado (presentes no repo, não linkados no index principal)

| Arquivo | Observação |
|---------|-----------|
| dashboard.html | Versão antiga do dashboard — manter para referência |
| home.html | Versão antiga da home — manter para referência |
| life-os.html | Nome antigo (J.One Life OS) — manter para referência |

---

## Dados (data/)

| Arquivo | Usado por |
|---------|-----------|
| data/calendars.json | calendario-operacional.html, anaju-neves-hub.html (calendário múltiplo) |
| data/materials.json | materiais.html |
| data/rules.json | regras-fiap.html, anaju-neves-hub.html (seção FIAP) |
| data/martech.json | anaju-neves-hub.html |
| data/academic.json | anaju-neves-hub.html |
| data/assets.json | uso interno |
| data/branding.json | uso interno |
| data/courses.json | uso interno |
| data/quick-links.json | uso interno |
| data/solar-plus.json | anaju-neves-hub.html (Projeto Solar+, seção FIAP) |

---

## Calendários (.ics)

| Arquivo | Calendário | Status |
|---------|------------|--------|
| icalexport.ics | FIAP & Afins (acadêmico) | Ativo ✅ |
| calendar-compromissos.ics | Calendar Compromissos (Ana pessoal) | Ativo ✅ |
| calendar-lm.ics | Calendar L.M. (Lucca) | Ativo ✅ |

---

## Documentação (docs/)

| Arquivo | Conteúdo |
|---------|----------|
| docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md | Arquitetura do produto |
| docs/CALENDAR_IMPORT_GUIDE.md | Guia de calendários e .ics |
| docs/CALENDAR_PUBLIC_LINKS.md | Links públicos autorizados dos calendários (documentação de origem) |
| docs/RELEASE_NOTES_2026-05-06.md | Release notes versão 2026-05-06 |
| docs/RELEASE_NOTES_2026-05-08.md | Release notes Tasks 20–26 e hotfix calendário (2026-05-08) |
| docs/QA_RELEASE_CHECKLIST.md | Checklist de QA antes de merge |
| docs/SITE_MAP.md | Este arquivo — mapa do site |
| docs/LIFE_OS_ARCHITECTURE.md | Arquitetura legado (J.One Life OS) — manter para referência |

---

## Links internos auditados (2026-05-06)

**Resultado: zero links quebrados.**

| Página | Links internos verificados |
|--------|---------------------------|
| index.html | hub-operacional.html ✅, calendario-operacional.html ✅, hub-status-atual.html ✅, anaju-neves-hub.html ✅, materiais.html ✅, regras-fiap.html ✅, docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md ✅ |
| hub-operacional.html | index.html ✅, materiais.html ✅, regras-fiap.html ✅ |
| calendario-operacional.html | index.html ✅, docs/CALENDAR_IMPORT_GUIDE.md ✅ |
| hub-status-atual.html | index.html ✅, materiais.html ✅, regras-fiap.html ✅ |
| materiais.html | src dinâmico via JS (sem link quebrado) ✅ |
| regras-fiap.html | materiais.html ✅ |

---

## Notas

- Arquivos legado (dashboard.html, home.html, life-os.html) são mantidos mas não aparecem na navegação principal.
- Os arquivos .ics são servidos diretamente pelo GitHub Pages como arquivos estáticos.
- Todos os arquivos de dados são JSON puros lidos por fetch() no front-end.
