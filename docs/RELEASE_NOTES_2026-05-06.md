# Release Notes — Anaju Neves Hub
## Versão estável · 2026-05-06

---

## 1. O que foi entregue nesta versão

| # | Task | Descrição | Status |
|---|------|-----------|--------|
| 1 | Limpeza de calendários | data/calendars.json atualizado: 3 fontes reais, labels corretos | ✅ Mergeado |
| 2 | Remoção de placeholders | ana-pessoal.ics e lucca.ics deletados do repositório | ✅ Mergeado |
| 3 | Atualização calendario-operacional.html | Kicker, heading e JS config atualizados para nomes corretos | ✅ Mergeado |
| 4 | Atualização CALENDAR_IMPORT_GUIDE.md | Mapeamento de arquivos .ics atualizado | ✅ Mergeado |
| 5 | Atualização index.html | Descrição do card de calendário corrigida | ✅ Mergeado |
| 15 | Renomear .ics genéricos | basic.ics → calendar-compromissos.ics / basic (1).ics → calendar-lm.ics | ✅ Mergeado |
| 16 | QA Release Checklist | docs/QA_RELEASE_CHECKLIST.md criado (10 seções) | ✅ Mergeado |
| 17 | Auditoria de links | Varredura em 6 HTMLs — zero links quebrados | ✅ Mergeado |
| 18 | Site Map | docs/SITE_MAP.md criado com estrutura completa | ✅ Mergeado |

---

## 2. Arquivos principais alterados

| Arquivo | Ação |
|---------|------|
| data/calendars.json | Fontes e paths atualizados |
| docs/CALENDAR_IMPORT_GUIDE.md | Mapeamento de .ics atualizado |
| calendario-operacional.html | Textos e JS config atualizados |
| index.html | Descrição do card de calendário corrigida |
| basic.ics | Renomeado para calendar-compromissos.ics |
| basic (1).ics | Renomeado para calendar-lm.ics |
| ana-pessoal.ics | Deletado (era placeholder vazio) |
| lucca.ics | Deletado (era placeholder vazio) |
| docs/QA_RELEASE_CHECKLIST.md | Criado (novo) |
| docs/SITE_MAP.md | Criado (novo) |

---

## 3. Mapeamento atual de calendários

| Calendário | Arquivo | Tipo | Status |
|-----------|---------|------|--------|
| FIAP & Afins | icalexport.ics | academic | ✅ Ativo |
| Calendar Compromissos | calendar-compromissos.ics | personal | ✅ Ativo |
| Calendar L.M. | calendar-lm.ics | shared_personal | ✅ Ativo |

Configuração completa em: `data/calendars.json`

---

## 4. Arquivos removidos / depreciados

| Arquivo | Motivo |
|---------|--------|
| ana-pessoal.ics | Era placeholder vazio — deletado |
| lucca.ics | Era placeholder vazio — deletado |
| basic.ics | Renomeado para calendar-compromissos.ics — não existe mais |
| basic (1).ics | Renomeado para calendar-lm.ics — não existe mais |

> ⚠️ Se houver qualquer referência a esses nomes em código externo ou bookmarks, atualizar para os novos nomes.

---

## 5. Como testar (QA mínimo)

Guia completo: `docs/QA_RELEASE_CHECKLIST.md`

Checklist rápido pós-merge:

- [ ] `index.html` carrega com os 7 cards e links corretos
- [ ] `calendario-operacional.html` mostra 3 fontes: FIAP & Afins, Calendar Compromissos, Calendar L.M.
- [ ] `data/calendars.json` retorna sem 404 (verificar console do browser)
- [ ] `calendar-compromissos.ics` e `calendar-lm.ics` existem no repo (verificar aba Code)
- [ ] Nenhuma referência a `basic.ics`, `ana-pessoal.ics`, `lucca.ics` em console ou rede
- [ ] `materiais.html` e `regras-fiap.html` carregam normalmente (arquivos protegidos — não alterados)

---

## 6. Limitações conhecidas

| Limitação | Contexto | Prioridade |
|-----------|----------|-----------|
| anaju-neves-hub.html contém textos "J.One Life OS" | Branding antigo ainda visível no dashboard principal | Task 20 (pendente) |
| Arquivos legado não linkados | dashboard.html, home.html, life-os.html existem mas não aparecem na navegação | Decisão de manter como referência |
| calendar-compromissos.ics sem validação automática | O arquivo existe mas não há teste automatizado de parse | Melhoria futura |

---

## 7. Próximas tasks recomendadas

| # | Task | Descrição | Prioridade |
|---|------|-----------|-----------|
| 20 | Refatorar textos anaju-neves-hub.html | Substituir "J.One Life OS" por "Anaju Neves Hub" — sem redesign, só textos | Alta |
| 21 | Conectar botões operacionais | Adicionar botões "Abrir leitor de materiais", "Guias FIAP", "Calendário operacional" no anaju-neves-hub.html | Alta |
| — | Arquivo legado | Avaliar se dashboard.html, home.html, life-os.html devem ser deletados ou mantidos | Baixa |

---

## 8. O que NÃO foi mexido

Os seguintes arquivos estão **intactos** e equivalentes ao estado pré-task:

- `data/materials.json`
- `data/rules.json`
- `data/martech.json`
- `materiais.html`
- `regras-fiap.html`
- `hub-operacional.html`
- `hub-status-atual.html`
- `anaju-neves-hub.html`
- `icalexport.ics`
- Todos os PDFs em `materiais/`

---

_Release notes geradas em 2026-05-06. Branch: fiap-testing → main._
