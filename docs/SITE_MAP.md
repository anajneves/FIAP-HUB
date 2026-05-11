# Site Map — Anaju Neves Hub

Mapa de arquivos e estrutura de navegacao atual.
Ultima atualizacao: 2026-05-11 (v1.1)

---

## Estrutura de navegacao

index.html (Home — ponto de entrada)
├── anaju-neves-hub.html → Dashboard principal (Hub v1.1)
├── calendario-operacional.html → Calendario operacional
├── hub-operacional.html → Fluxo operacional
├── hub-status-atual.html → Status atual do hub
├── materiais.html → Leitor de materiais academicos
├── regras-fiap.html → Guias e normas FIAP
└── docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md → Arquitetura do produto

---

## Arquivos HTML ativos

| Arquivo | Funcao | Linkado em index.html |
|---------|--------|-----------------------|
| index.html | Home / hub central | — (e a home) |
| anaju-neves-hub.html | Dashboard principal com 8 secoes (v1.1) | Sim |
| calendario-operacional.html | Calendario multi-fonte | Sim |
| hub-operacional.html | Fluxo e processos operacionais | Sim |
| hub-status-atual.html | Pagina de status atual (pos Tasks 21-25) | Sim |
| materiais.html | Leitor de PDFs e materiais | Sim |
| regras-fiap.html | Normas e guias FIAP | Sim |

### Arquivos HTML legado (presentes no repo, nao linkados no index principal)

| Arquivo | Observacao |
|---------|-----------|
| dashboard.html | Versao antiga (J.One Hub) — sanitizado na Task 42. Nenhuma credencial ativa. |
| home.html | Versao antiga da home — manter para referencia |
| life-os.html | Nome antigo (J.One Life OS) — manter para referencia |

---

## Dados (data/)

| Arquivo | Usado por | Status v1.1 |
|---------|-----------|-------------|
| data/academic.json | anaju-neves-hub.html | Ativo |
| data/assets.json | anaju-neves-hub.html (Documentos) | Atualizado — 10 assets com categoria |
| data/calendars.json | calendario-operacional.html, anaju-neves-hub.html | Ativo |
| data/materials.json | materiais.html, anaju-neves-hub.html | Ativo — 34/34 PDFs OK |
| data/rules.json | regras-fiap.html, anaju-neves-hub.html | Ativo |
| data/martech.json | anaju-neves-hub.html (Cursos) | Ativo |
| data/quick-links.json | anaju-neves-hub.html (Links) | Atualizado — grupo ferramentas/GoodNotes |
| data/solar-plus.json | anaju-neves-hub.html (Solar+) | Ativo |
| data/branding.json | uso interno | Ativo |
| data/courses.json | uso interno | Ativo |

---

## Calendarios (.ics)

| Arquivo | Calendario | Status v1.1 |
|---------|------------|-------------|
| icalexport.ics | FIAP & Afins (academico) | Ativo — nao alterado |
| calendar-compromissos.ics | Calendar Compromissos (Ana pessoal) | Ativo — nao alterado |
| calendar-lm.ics | Calendar L.M. | Ativo — sanitizado na Task 42 |

---

## Documentacao (docs/)

| Arquivo | Conteudo | Status v1.1 |
|---------|----------|-------------|
| docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md | Arquitetura do produto | Sem alteracao |
| docs/BACKLOG_V1_1.md | Backlog v1.1 — todos os itens concluidos | Atualizado — v1.1 concluida |
| docs/CALENDAR_IMPORT_GUIDE.md | Guia de calendarios e .ics | Sem alteracao |
| docs/CALENDAR_PUBLIC_LINKS.md | Links publicos autorizados dos calendarios | Sem alteracao |
| docs/LIFE_OS_ARCHITECTURE.md | Arquitetura legado (J.One Life OS) | Sem alteracao |
| docs/QA_RELEASE_CHECKLIST.md | Checklist de QA antes de merge | Sem alteracao (checklist v1.0) |
| docs/RELEASE_NOTES_2026-05-06.md | Release notes versao 2026-05-06 | Sem alteracao |
| docs/RELEASE_NOTES_2026-05-08.md | Release notes Tasks 20-29 + v1.1 (Tasks 33-42) | Atualizado — v1.1 documentada |
| docs/SITE_MAP.md | Este arquivo — mapa do site | Atualizado — v1.1 |

---

## Secoes do anaju-neves-hub.html (v1.1)

| Secao | View ID | Descricao |
|-------|---------|-----------|
| Visao Geral | view-visao | 6 cards de navegacao, atencao agora, proximos eventos |
| FIAP | view-fiap | Fases, entregas, Regras FIAP, Projeto Solar+ |
| Calendario | view-calendario | 3 fontes, filtros por tipo e fonte |
| Biblioteca | view-biblioteca | Filtros por fase (Fase 1, 2, 3, Guias/normas) |
| Cursos | view-martech | Cursos extracurriculares (MarTech Alura, Nano Courses) |
| Links | view-links | 4 grupos: Academico, Cursos, Ferramentas, Projeto |
| Documentos | view-documentos | 4 blocos: pessoais, extras, visuais, GoodNotes |
| Sistema | view-sistema | Dados carregados, tarefas apagadas, restaurar |

---

## Notas

- Arquivos legado (dashboard.html, home.html, life-os.html) nao aparecem na navegacao principal.
- dashboard.html sanitizado na Task 42: nenhuma credencial ativa permanece.
- calendar-lm.ics sanitizado na Task 42: ATTENDEE com e-mail pessoal removido.
- GitHub Pages publica a partir da branch main. A v1.1 esta em v1.1-anaju-neves-hub aguardando merge.
