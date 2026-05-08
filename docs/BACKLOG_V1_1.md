# Backlog v1.1 — Anaju Neves Hub

## Origem

Feedback real da usuária após teste da versão v1.0.0 estável.

## Regra de trabalho

A versão v1.0.0 está congelada. Tag: `v1.0.0-anaju-neves-hub-stable`.
Toda evolução deve ocorrer em branch nova, criada a partir de `main` após o congelamento.
Nenhum arquivo operacional (HTML, JSON, PDF, imagem, calendário) deve ser alterado nesta task.

---

## Itens P0 — Corrigir antes de qualquer melhoria visual

### 1. Remover controles técnicos visíveis ao usuário final

- Ocultar "Exportar JSON" e "Limpar local" do painel Sistema.
- O usuário final não deve ver controles de backend.
- Referência de experiência: Notion, Asana e plataformas visuais.
- **Tipo:** UX / Segurança operacional.

### 2. Corrigir calendário em "Todas as fontes"

- A visualização quebra ou fica estranha quando todas as fontes são selecionadas.
- **Tipo:** Bug funcional.

### 3. Investigar calendário LM

- O calendário principal LM não exibe compromissos corretamente.
- Comparar comportamento com o calendário secundário Luca.
- **Tipo:** Bug funcional.

### 4. Corrigir links quebrados

- Link "Creative Strategies" retorna 404 tentando abrir diretório/backend.
- Link de Calendário FIAP força download desnecessário.
- **Tipo:** Bug funcional.

### 5. Corrigir layout de Regras Práticas de Graduação

- Textos não cabem corretamente na tela.
- **Tipo:** Bug visual / responsividade.

---

## Itens P1 — Organização estrutural

### 1. Reorganizar Biblioteca por fases

- Materiais da Fase 1 devem aparecer apenas na Fase 1.
- Materiais da Fase 2 apenas na Fase 2.
- Materiais da Fase 3 apenas na Fase 3.
- Evitar mistura por disciplina que confunda a navegação acadêmica.
- **Tipo:** Arquitetura de informação.

### 2. Reordenar entregas pendentes

- Entregas devem seguir ordem cronológica e lógica.
- "Quiz fase 1" não pode aparecer abaixo de fase 2 ou fase 3.
- **Tipo:** Organização de dados.

### 3. Zerar progresso das fases

- Estado visual deve começar como se nada tivesse sido realizado ainda.
- **Tipo:** Estado inicial / localStorage / dados.

### 4. Remover acesso às fases 5, 6 e 7

- FIAP liberou apenas até a fase 4.
- **Tipo:** Conteúdo acadêmico.

### 5. Criar área de cursos extracurriculares

- Martech não é fase da graduação.
- Martech é curso extracurricular da Alura.
- Criar área própria para:
  - Nano courses FIAP;
  - Martech;
  - Alura.
- Ordem sugerida:
  1. FIAP graduação;
  2. Nano courses FIAP;
  3. Martech e Alura.
- **Tipo:** Arquitetura de informação.

---

## Itens P2 — UX e interface

### 1. Ajustar cabeçalho e perfil

- Remover botões "foto", "imagem" e "foto AJ".
- Manter apenas foto circular no topo da barra, ao lado do nome.
- **Tipo:** UX/UI.

### 2. Reformular Visão Geral

- A tela inicial não deve ser centrada quase exclusivamente na parte acadêmica.
- O layout dos cards de tarefas abertas, capítulos, eventos e módulos Martech foi considerado ruim.
- Criar visão mais equilibrada entre acadêmico, calendário, cursos, documentos e prioridades.
- **Tipo:** UX/UI.

### 3. Criar lixeira de tarefas

- Criar local ou estrutura para tarefas apagadas.
- **Tipo:** Nova funcionalidade / dados locais.

### 4. Transformar "Materiais anexados" em seção de extras

- Itens extras devem ter seção própria.
- **Tipo:** Organização de conteúdo.

### 5. Organizar documentos pessoais

- Carteirinha de estudante deve ir para pasta/seção Documentos.
- Não deve ficar misturada com logos ou anexos visuais.
- **Tipo:** Organização documental.

### 6. Inserir logos visualmente no layout

- Logos FIAP, Alura e IAs não devem aparecer como anexos avulsos.
- Devem ser usadas visualmente no layout quando fizer sentido.
- **Tipo:** UI / asset management.

---

## Itens P3 — Integrações e ideias futuras

### 1. GoodNotes

- Adicionar link ou bloco de integração com GoodNotes.
- Não registrar login ou senha no repositório.
- Se necessário, documentar apenas:
  > "Acesso gerenciado fora do repositório."
- **Tipo:** Integração futura.

---

## Categorização por tipo

| Item | Tipo |
|------|------|
| Remover controles técnicos | UX / Segurança operacional |
| Calendário "Todas as fontes" | Bug funcional |
| Calendário LM | Bug funcional |
| Links quebrados | Bug funcional |
| Layout Regras Práticas | Bug visual / responsividade |
| Biblioteca por fases | Arquitetura de informação |
| Ordem de entregas pendentes | Organização de dados |
| Zerar progresso das fases | Estado inicial / dados |
| Remover fases 5, 6 e 7 | Conteúdo acadêmico |
| Área extracurricular | Arquitetura de informação |
| Cabeçalho e foto | UX/UI |
| Reformular Visão Geral | UX/UI |
| Lixeira de tarefas | Nova funcionalidade |
| Seção de extras | Organização de conteúdo |
| Documentos pessoais | Organização documental |
| Logos no layout | UI / asset management |
| GoodNotes | Integração futura |

---

## Segurança e privacidade

- Não registrar credenciais pessoais no repositório.
- Não inserir senhas em docs, HTML, JSON ou comentários.
- Controles técnicos devem ser ocultados da interface final.
- O Hub deve parecer produto visual, não painel de backend.
- Qualquer integração externa (ex: GoodNotes) deve documentar apenas:
  > "Acesso gerenciado fora do repositório."

---

## Ordem sugerida de execução

| Task | Descrição |
|------|-----------|
| Task 33 | Criar branch v1.1 e congelar regra de trabalho |
| Task 34 | Remover controles técnicos visíveis e ajustar cabeçalho/foto |
| Task 35 | Corrigir calendário "Todas as fontes" e investigar LM |
| Task 36 | Corrigir links quebrados e layout de Regras Práticas |
| Task 37 | Reorganizar Biblioteca por fase |
| Task 38 | Reestruturar FIAP, Nano Courses, Martech e Alura |
| Task 39 | Reformular Visão Geral |
| Task 40 | Organizar Documentos, anexos, logos e extras |
| Task 41 | QA funcional v1.1 |

---

## Critério de aceite desta task (Task 32)

1. `docs/BACKLOG_V1_1.md` existe.
2. O backlog contém todos os pontos levantados pela usuária.
3. Nenhuma credencial pessoal aparece no arquivo.
4. `docs/SITE_MAP.md` lista `docs/BACKLOG_V1_1.md`.
5. Nenhum arquivo operacional é alterado.
6. Nenhum JSON é alterado.
7. Nenhum HTML do Hub é alterado.
8. Nenhuma feature é criada.
9. O texto deixa claro que v1.0.0 está congelada.
10. O backlog sugere ordem de execução.

---

*Backlog criado em 2026-05-08. Origem: QA real da usuária pós v1.0.0-anaju-neves-hub-stable.*
