# Release Notes — Anaju Neves Hub — 2026-05-08

## Resumo

Esta release consolida o Hub principal como central operacional acadêmica, profissional e documental. Entre as Tasks 20 e 26 e um hotfix adicional, foram integradas todas as principais fontes de dados: FIAP, Regras e Normas, Calendários múltiplos, Projeto Solar+, Biblioteca, MarTech, Links e Documentos. O Hub passou por QA visual e de navegação sem alterações necessárias.

---

## Escopo da release (Tasks 20–29)

- Refatoração textual do Hub principal (Task 20);
- Integração de regras FIAP via data/rules.json (Task 21);
- Integração de calendário múltiplo via data/calendars.json (Task 22);
- Integração do Projeto Solar+ via data/solar-plus.json (Task 23);
- Atualização da Visão geral e Integridade das fontes (Task 24);
- QA visual e navegação aprovado sem alterações (Task 25);
- Atualização de hub-status-atual.html e docs/SITE_MAP.md (Task 26);
- Organização dos links públicos de calendário em docs/CALENDAR_PUBLIC_LINKS.md (hotfix);
- QA funcional completo com correção de PDFs e links internos (Task 29).

---

## Task 29 — QA Funcional Real (2026-05-08)

**PDFs:** 34/34 funcionando após correção de paths em data/materials.json.
**Links internos:** #martech e #documentos corrigidos via setView().
**Assets:** IMG-20260425-WA0003.jpg exibida no avatar. ✓
**Links externos:** target="_blank" e rel="noopener" em todos. ✓

---

---

# Release Notes — Anaju Neves Hub v1.1 — 2026-05-11

## Resumo executivo

A v1.1 transforma o Hub em uma interface mais organizada, segura e usável. Separa claramente FIAP graduação, Cursos extracurriculares, Biblioteca, Calendário, Documentos e Sistema. Remove controles técnicos expostos. Adiciona lixeira de tarefas, organiza documentos por categoria e aplica security scrub nos arquivos legados.

**Branch de trabalho:** v1.1-anaju-neves-hub
**Versão estável anterior preservada em:** tag v1.0.0-anaju-neves-hub-stable

---

## Escopo da v1.1 (Tasks 33–42)

| Task | Descrição | Status |
|------|-----------|--------|
| Task 33 | Criar branch v1.1, congelar regra de trabalho | ✅ Concluído |
| Task 34 | Limpar cabeçalho, foto e controles técnicos | ✅ Concluído |
| Task 35 | Corrigir calendário "Todas as fontes" e Calendar L.M. | ✅ Concluído |
| Task 36 | Corrigir links quebrados e layout de Regras FIAP | ✅ Concluído |
| Task 37 | Reorganizar Biblioteca por fase | ✅ Concluído |
| Task 38A | Separar FIAP graduação de Cursos extracurriculares | ✅ Concluído |
| Task 38B | Integrar MarTech / Alura como cursos separados | ✅ Concluído |
| Task 39A | Reformular Visão Geral | ✅ Concluído |
| Task 39B | Adicionar lixeira de tarefas (deletedTasks via localStorage) | ✅ Concluído — commit 5f5fd79 |
| Task 40A | Organizar Documentos, assets e GoodNotes | ✅ Concluído — commits c2c5c01, d67d672, e6e5c35 |
| Task 40B | Catalogar documentos pessoais e assets visuais | ✅ Concluído — commit 947a398 |
| Task 41 | QA visual e funcional v1.1 | ✅ Concluído — commit 5c92cbc |
| Task 42 | Security scrub de arquivos legados e calendar-lm.ics | ✅ Concluído — commits 6726a43, 2a2159a |

---

## Principais mudanças da v1.1

### Visão Geral redesenhada (Task 39A)

- Cards de navegação para todas as 6 seções: FIAP, Calendário, Biblioteca, Cursos, Links, Documentos.
- Bloco "Atenção agora" com tarefas abertas priorizadas.
- Bloco "Próximos eventos" integrado ao calendário.
- Bloco "Fontes carregadas" mostrando status das fontes.

### Lixeira de tarefas (Task 39B)

- Botão "Apagar" em cada tarefa da seção FIAP.
- Tarefas apagadas ficam ocultas nas listagens (FIAP e Visão Geral).
- Estado persiste via localStorage (chave deletedTasks).
- Seção "Tarefas apagadas" com botão "Restaurar" adicionada à seção Sistema.

### Calendário corrigido (Task 35)

- Todas as fontes não quebram mais o layout.
- Calendar L.M. carrega com fallback claro se vazio.
- Filtros por tipo e por fonte funcionam na lista e na grade.

### Biblioteca por fase (Task 37)

- Filtros separados por coleção: Fase 1, Fase 2, Fase 3, Guias/normas.
- Materiais não se misturam entre fases.

### Cursos separados da graduação FIAP (Tasks 38A/38B)

- Seção "Cursos" dedicada a Cursos Extracurriculares.
- MarTech — Alura aparece como curso extracurricular.
- Nano Courses FIAP aparece como "aguardando catalogação".
- Nenhum desses conteúdos aparece como fase da graduação.

### Documentos organizados (Tasks 40A/40B)

- 4 blocos: Documentos pessoais, Materiais extras, Referências visuais e logos, GoodNotes.
- renderDocumentos() usa byCategory() para filtrar por personal, visual_reference, extra.
- GoodNotes adicionado sem credenciais, com link para site público.
- 10 assets catalogados em data/assets.json com category, likelyUse, notes.

### Segurança — Security scrub (Tasks 41/42)

- Task 41: E-mail pessoal hardcoded removido de dashboard.html (commit 5c92cbc).
- Task 42 — dashboard.html (commit 6726a43): Bloco "CREDENCIAIS ACADÊMICAS" removido. Propriedades login e senha eliminadas. Senha mascarada eliminada. Bloco convertido para "ACESSOS EXTERNOS" com URLs públicas.
- Task 42 — calendar-lm.ics (commit 2a2159a): 4 linhas ATTENDEE com e-mail pessoal removidas. 192 VEVENTs intactos.

---

## Confirmação de ausência de credenciais

| Padrão | Resultado |
|--------|-----------|
| senha | ✅ Ausente em anaju-neves-hub.html |
| password | ✅ Ausente no repositório |
| AnaJulia3101 | ✅ Ausente no repositório |
| anajuliamedicina | ✅ Ausente em dashboard.html e calendar-lm.ics |
| CREDENCIAIS ACADÊMICAS | ✅ Ausente no repositório |

Residual registrado: RM571965 permanece como badge de perfil na barra lateral de dashboard.html — contexto não-sensível (número de matrícula exibido em cabeçalho de app). Não é campo de login.

---

## Pendências conhecidas

1. Confirmação visual de 13274b5c14834c7e8a56532b2d05ca35.pdf — catalogado como student_id_candidate. Aguarda confirmação manual antes de exibir como carteirinha.
2. Sanitização ampla de outros e-mails em .ics — outros eventos em calendar-lm.ics podem conter e-mails de terceiros como ATTENDEE. Avaliar apenas se o repo for tornado público.
3. Organização física de pastas/assets (Task 40C) — não executada. Avaliar se necessário.
4. dashboard.html legado — ainda presente. Pode ser removido em task futura se decidido.

---

## Checklist pré-merge para main

- [x] Branch correta: v1.1-anaju-neves-hub
- [x] main intacta
- [x] Tag v1.0.0-anaju-neves-hub-stable intacta
- [x] Hub anaju-neves-hub.html abre sem erro crítico
- [x] Todas as 8 seções abrem
- [x] Cards da Visão Geral navegam corretamente
- [x] Tarefas: concluir, reabrir, apagar e restaurar funcionam
- [x] PDFs da Biblioteca abrem sem 404
- [x] Links internos por hash funcionam
- [x] Links externos usam target="_blank" e rel="noopener"
- [x] Calendário renderiza sem quebrar layout
- [x] Biblioteca por fase filtra corretamente
- [x] Cursos separados da graduação FIAP
- [x] Documentos organizados em 4 blocos
- [x] GoodNotes sem credenciais
- [x] Security grep limpo
- [x] QA aprovado (Task 41)
- [x] Security scrub aplicado (Task 42)

---

## Commits principais da v1.1

| Commit | Descrição |
|--------|-----------|
| 5f5fd79 | Finalize task trash behavior (Task 39B) |
| c2c5c01 | Add category field to assets for document grouping (Task 40A) |
| d67d672 | Add ferramentas group with GoodNotes to quick-links (Task 40A) |
| e6e5c35 | Organize documents assets and GoodNotes (Task 40A) |
| 947a398 | Catalog personal documents and visual assets (Task 40B) |
| 5c92cbc | QA v1.1 functional polish (Task 41) |
| 6726a43 | Scrub legacy credentials and calendar metadata — dashboard.html (Task 42) |
| 2a2159a | Scrub legacy credentials and calendar metadata — calendar-lm.ics (Task 42) |

---

*Release v1.1 — Anaju Neves Hub. 2026-05-11.*


---

# Hotfix v1.1.1 — Anaju Neves Hub — 2026-05-11

## Resumo

Correções pós-release da v1.1.0 identificadas via QA real no GitHub Pages. Branch: `hotfix/v1.1.1-post-release-qa`. Nenhuma tag alterada. Nenhum PDF, imagem ou .ics alterado.

---

## Bugs corrigidos

| Fix | Descrição |
|-----|-----------|
| 1 | Sidebar: `.note` com `overflow:hidden` e `z-index:1`; sidebar com `padding-bottom:80px` e `overflow:hidden` para não sobrepor conteúdo ativo |
| 2 | Calendário: header com mês/ano e botões Anterior/Próximo via `state.calendarMonthOffset` |
| 3 | Calendário: ícone 📅 substituído por label textual `CAL` (mono, sem dependência de emoji) |
| 4 | Low-stim: CSS real implementado — reduz gradientes, sombras, animações e contraste agressivo |
| 5 | Calendário: auto-reset de `eventFilter` quando filtro de tipo salvo no localStorage resulta em 0 eventos |
| 6 | Documentos: `assetCard()` renderiza botão "Abrir" para arquivos PDF |
| 7 | Biblioteca: badge de páginas não exibido quando `pageCount` é `null` |
| 8 | Tarefas: feedback visual via `showToast()` ao concluir, reabrir, apagar e restaurar |

## Arquivos alterados

- `anaju-neves-hub.html` — único arquivo modificado
- `docs/RELEASE_NOTES_2026-05-08.md` — registro da hotfix

## Segurança

- senha: ausente ✅
- password: ausente ✅
- AnaJulia3101: ausente ✅
- anajuliamedicina: ausente ✅
- CREDENCIAIS ACADÊMICAS: ausente ✅

## Commit

`Hotfix v1.1.1 post-release QA` — branch `hotfix/v1.1.1-post-release-qa`

---

*Hotfix v1.1.1 — Anaju Neves Hub. 2026-05-11.*

---

# Hotfix v1.1.2 — Anaju Neves Hub — 2026-05-15

## Resumo

Limpeza visual e semântica de documentos. Branch: `hotfix/v1.1.2-visual-content-cleanup`. Nenhuma tag alterada. Nenhum PDF acadêmico, imagem ou .ics alterado.

---

## Problemas corrigidos

| Fix | Descrição |
|-----|-----------|
| 1 | **Documentos — assets visuais**: Logos e banners removidos da seção Documentos. `renderDocumentos()` agora filtra categorias `interface_asset` e `hidden_asset`. Seção "Referências visuais e logos" removida da UI. |
| 2 | **Materiais extras — arquivos internos**: Arquivos de arquitetura interna, prompts, MHTML e screenshots filtrados da UI. Seção Materiais extras mostra apenas documentos institucionais relevantes. |
| 3 | **Toast atravessando tela**: `showToast()` recebeu `max-width:320px` e `white-space:normal;word-wrap:break-word`. Toast não atravessa mais a tela nem cobre sidebar. |
| 4 | **Calendário — visual redesenhado**: Layout substituído por `.calendar-shell` (grid 1.4fr/0.8fr). Grade com `.cal-days` 7 colunas sem overflow horizontal. Chips menores com `overflow:hidden`. Lista lateral limitada a 10 eventos futuros. Dia atual destacado com borda rosa. || 5 | **Task 49A — Documentos**: Arquivos internos (`UX DESIGNER.txt`, `Curso MarTech.txt`, `docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md`) catalogados como `hidden_asset` em `data/assets.json`. Não aparecem em Documentos. Mensagem vazia de extras corrigida para “Nenhum material extra visível no momento.” |

## Arquivos alterados

- `anaju-neves-hub.html` — CSS do calendário, renderDocumentos(), renderCalendario(), showToast()
- `data/assets.json` — categorias interface_asset e hidden_asset adicionadas; 3 arquivos internos catalogados como hidden_asset (Task 49A)
- `docs/RELEASE_NOTES_2026-05-08.md` — registro desta hotfix

## Segurança

- senha: ausente ✅
- password: ausente ✅
- AnaJulia3101: ausente ✅
- anajuliamedicina: ausente ✅
- CREDENCIAIS ACADÊMICAS: ausente ✅

## Commits

| Commit | Descrição |
|--------|-----------|
| 32bbbb5 | v1.1.2 — Reclassifica assets visuais como interface_asset/hidden_asset |
| d4b2f83 | Hotfix v1.1.2 visual content cleanup |
| 22cbd86 | Task 49A — Cataloga arquivos internos como hidden_asset em assets.json |
| 7066a88 | Task 49A — Corrige renderDocumentos() e mensagem vazia de extras |

## Pendências para v1.2

- Confirmação visual de `13274b5c14834c7e8a56532b2d05ca35.pdf` como carteirinha de estudante.
- Uso visual de assets FIAP (Artboard-1.webp) em área específica FIAP/Biblioteca.
- Uso visual de logo Alura (4975968.png) em seção Cursos/MarTech.
- Organização física de pastas/assets (Task 40C pendente).
- Catálogo completo de Nano Courses FIAP quando disponível.

---

*Hotfix v1.1.2 — Anaju Neves Hub. 2026-05-15.*
