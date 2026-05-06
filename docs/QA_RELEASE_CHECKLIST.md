# QA Release Checklist — Anaju Neves Hub

Use este checklist antes de cada merge para main.
Data da última revisão: 2026-05-06

---

## 1. Home (index.html)

- [ ] Página carrega sem erros de console
- [ ] Todos os 7 cards aparecem com título e descrição corretos
- [ ] Links dos cards apontam para os arquivos corretos
- [ ] Identidade visual preservada (fundo escuro, fonte Newsreader, accent #ED145B)
- [ ] Responsivo em mobile (< 768px)
- [ ] Nenhum texto "J.One Life OS" ou "Life OS" visível

## 2. Calendário (calendario-operacional.html)

- [ ] Página carrega sem erros de console
- [ ] 3 fontes de calendário aparecem: FIAP & Afins, Calendar Compromissos, Calendar L.M.
- [ ] data/calendars.json lido corretamente (sem 404)
- [ ] Arquivos .ics existem: icalexport.ics, calendar-compromissos.ics, calendar-lm.ics
- [ ] Eventos carregados ou mensagem de fallback exibida
- [ ] Link "Entrada" aponta para index.html
- [ ] Link "Como atualizar calendários" aponta para docs/CALENDAR_IMPORT_GUIDE.md

## 3. Materiais (materiais.html)

- [ ] Página carrega sem erros de console
- [ ] data/materials.json carregado (sem 404)
- [ ] Lista de materiais renderiza corretamente
- [ ] Links para PDFs abrem ou exibem erro amigável se ausentes
- [ ] Nenhum link apontando para basic.ics ou lucca.ics

## 4. Regras FIAP (regras-fiap.html)

- [ ] Página carrega sem erros de console
- [ ] data/rules.json carregado (sem 404)
- [ ] Conteúdo de regras renderiza corretamente
- [ ] Link para materiais.html funciona

## 5. Hub Operacional (hub-operacional.html)

- [ ] Página carrega sem erros de console
- [ ] Links internos: index.html, materiais.html, regras-fiap.html — todos funcionais
- [ ] Nenhum link apontando para arquivo inexistente

## 6. Status Atual (hub-status-atual.html)

- [ ] Página carrega sem erros de console
- [ ] Links internos: index.html, materiais.html, regras-fiap.html — todos funcionais
- [ ] Informações de status renderizam corretamente

## 7. Links internos — auditoria rápida

- [ ] Nenhum href aponta para ana-pessoal.ics (deletado)
- [ ] Nenhum href aponta para lucca.ics (deletado)
- [ ] Nenhum href aponta para basic.ics ou basic (1).ics (renomeados)
- [ ] docs/ANAJU_NEVES_HUB_PRODUCT_ARCHITECTURE.md existe e abre
- [ ] docs/CALENDAR_IMPORT_GUIDE.md existe e abre
- [ ] dashboard.html, home.html, life-os.html são legado — não linkados no index principal (OK)

## 8. Mobile

- [ ] index.html responsivo em 375px
- [ ] calendario-operacional.html legível em mobile
- [ ] Nenhum overflow horizontal nas páginas principais

## 9. PDFs (pasta materiais/)

- [ ] PDFs presentes no repo e acessíveis via GitHub Pages
- [ ] materiais.html lista os arquivos corretamente

## 10. GitHub Pages

- [ ] Deploy ativo após merge (verificar Actions tab)
- [ ] URL pública carrega index.html corretamente
- [ ] Nenhum arquivo 404 no console do browser ao navegar

---

## Legenda

| Símbolo | Significado |
|---------|-------------|
| [ ] | A verificar |
| [x] | OK |
| [!] | Problema encontrado — registrar abaixo |

## Problemas encontrados

_(preencher manualmente durante o QA)_
