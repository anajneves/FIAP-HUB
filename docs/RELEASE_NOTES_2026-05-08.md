# Release Notes — Anaju Neves Hub — 2026-05-08

## Resumo

Esta release consolida o Hub principal como central operacional acadêmica, profissional e documental. Entre as Tasks 20 e 26 e um hotfix adicional, foram integradas todas as principais fontes de dados: FIAP, Regras e Normas, Calendários múltiplos, Projeto Solar+, Biblioteca, MarTech, Links e Documentos. O Hub passou por QA visual e de navegação sem alterações necessárias.

---

## Escopo da release

- Refatoração textual do Hub principal (Task 20);
- Integração de regras FIAP via data/rules.json (Task 21);
- Integração de calendário múltiplo via data/calendars.json (Task 22);
- Integração do Projeto Solar+ via data/solar-plus.json (Task 23);
- Atualização da Visão geral e Integridade das fontes (Task 24);
- QA visual e navegação aprovado sem alterações (Task 25);
- Atualização de hub-status-atual.html e docs/SITE_MAP.md (Task 26);
- Organização dos links públicos de calendário em docs/CALENDAR_PUBLIC_LINKS.md (hotfix).

---

## Mudanças por área

### Visão geral

- Integridade das fontes atualizada: FIAP, Regras, Calendários e Solar+ marcados como carregados;
- Métrica de próximos eventos separada do filtro da aba Calendário (commit 5b5e800);
- Textos antigos de Fase 1 e Fase 2 pendentes removidos (commit e735b56).

### FIAP

- Fases e entregas mantidas;
- Guias acadêmicos e Normas FIAP carregados via data/rules.json (commits b89d133, eb0fa89, ccf9d46);
- Projeto Solar+ integrado à seção FIAP via data/solar-plus.json (commits 375584e, 4b29779).

### Calendário

- Múltiplas fontes conectadas via data/calendars.json (commit 453eb56);
- Filtros por tipo e por fonte operacionais;
- Eventos com sourceId, sourceLabel, sourceKind e sourceColor;
- Links públicos autorizados documentados em docs/CALENDAR_PUBLIC_LINKS.md (hotfix, commits 6673295, c852323, dbb5a17).

### Biblioteca

- Materiais continuam renderizados via data/materials.json;
- PDFs mantidos como fonte operacional de leitura.

### MarTech

- Curso continua renderizado via data/martech.json;
- Fases, módulos, entregáveis e restrições preservados.

### Links

- Acessos rápidos mantidos via data/quick-links.json.

### Documentos

- Mantido como área de triagem;
- Não virou depósito de regras FIAP, Biblioteca, MarTech ou Solar+.

### Sistema

- Exportação, localStorage e controles locais preservados.

---

## QA

- Task 25 aprovada sem alterações: nenhuma correção necessária no QA visual;
- Navegação principal validada sem links quebrados;
- Auditoria de links internos registrada em docs/QA_RELEASE_CHECKLIST.md.

---

## Arquivos criados ou atualizados

| Arquivo | Tipo | Descrição |
|---------|------|----------|
| anaju-neves-hub.html | atualizado | Refatoração textual + integrações (Tasks 20–24) |
| data/solar-plus.json | criado | Fonte de dados do Projeto Solar+ |
| docs/CALENDAR_PUBLIC_LINKS.md | criado | Links públicos autorizados dos calendários (hotfix) |
| hub-status-atual.html | atualizado | Status pós Tasks 21–25, QA registrado (Task 26) |
| docs/SITE_MAP.md | atualizado | Mapa do site com novas fontes e documentação (Task 26 + hotfix) |
| docs/RELEASE_NOTES_2026-05-08.md | criado | Este arquivo (Task 27) |

---

## Estado atual

O Anaju Neves Hub está em estado estável de consolidação. As principais fontes operacionais foram conectadas e a navegação passou por QA visual. A próxima fase deve priorizar curadoria fina de conteúdo, validação de fontes oficiais e auditoria final antes de novas features.

---

## Pendências futuras

- Curadoria fina dos textos e fontes oficiais;
- Revisão de arquivos legados (dashboard.html, home.html, life-os.html);
- Auditoria final de links internos e externos;
- QA de release completo antes de novas features;
- Organização do backlog futuro.

---

## Observações

- Os links públicos de calendário foram autorizados pela Ana e documentados em docs/CALENDAR_PUBLIC_LINKS.md. Não são consumidos diretamente pelo Hub.
- O Hub continua consumindo data/calendars.json e arquivos .ics locais (icalexport.ics, calendar-compromissos.ics, calendar-lm.ics) para renderização.
- Os resultados descritos neste documento refletem o estado catalogado no Hub. Validação oficial das fontes acadêmicas é etapa futura.
