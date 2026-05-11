# Backlog v1.1 — Anaju Neves Hub

## Origem

Feedback real da usuária após teste da versão v1.0.0 estável.

## Regra de trabalho

A versão v1.0.0 está congelada. Tag: v1.0.0-anaju-neves-hub-stable.
Toda evolução deve ocorrer em branch nova, criada a partir de main após o congelamento.
Nenhum arquivo operacional (HTML, JSON, PDF, imagem, calendário) deve ser alterado nesta task.

---

## Status geral da v1.1

Todas as tasks do backlog foram concluídas.
Branch de trabalho: v1.1-anaju-neves-hub
Pronta para merge/release.

---

## Itens P0 — Concluídos

### 1. [x] Remover controles técnicos visíveis ao usuário final (Task 34)

- "Exportar JSON" e "Limpar local" removidos do painel Sistema.
- Interface não expõe mais controles de backend.

### 2. [x] Corrigir calendário em "Todas as fontes" (Task 35)

- Layout corrigido quando todas as fontes estão selecionadas.

### 3. [x] Investigar e corrigir calendário LM (Task 35)

- Calendar L.M. exibe fallback claro quando vazio ou sem eventos futuros.

### 4. [x] Corrigir links quebrados (Task 36)

- Link "Creative Strategist" corrigido para #documentos (interno).
- Link de Calendário FIAP corrigido.

### 5. [x] Corrigir layout de Regras Práticas de Graduação (Task 36)

- Overflow corrigido, texto legível.

---

## Itens P1 — Concluídos

### 1. [x] Reorganizar Biblioteca por fases (Task 37)

- Fase 1 filtra somente Fase 1, Fase 2 somente Fase 2, Fase 3 somente Fase 3.
- Guias e normas separados.

### 2. [x] Reordenar entregas pendentes (Tasks 38A/39A)

- Entregas ordenadas por prioridade e prazo via taskScore().

### 3. [x] Criar área de cursos extracurriculares (Tasks 38A/38B)

- Seção "Cursos Extracurriculares" separada da graduação FIAP.
- MarTech — Alura categorizado como extracurricular.
- Nano Courses FIAP: aguardando catalogação.

---

## Itens P2 — Concluídos

### 1. [x] Ajustar cabeçalho e perfil (Task 34)

- Botões técnicos de foto removidos.
- Avatar circular preservado com fallback "AJ".

### 2. [x] Reformular Visão Geral (Task 39A)

- 6 cards de navegação: FIAP, Calendário, Biblioteca, Cursos, Links, Documentos.
- Blocos: "Atenção agora", "Próximos eventos", "Fontes carregadas".

### 3. [x] Criar lixeira de tarefas (Task 39B)

- Botão "Apagar" em cada tarefa.
- deletedTasks salvo em localStorage.
- Seção Sistema com "Tarefas apagadas" e botão "Restaurar".

### 4. [x] Transformar "Materiais anexados" em seção de extras (Task 40A)

- Bloco "Materiais extras" criado na seção Documentos.

### 5. [x] Organizar documentos pessoais (Tasks 40A/40B)

- Bloco "Documentos pessoais" criado.
- Carteirinha candidata catalogada como category: personal.

### 6. [x] Inserir logos visualmente no layout (Tasks 40A/40B)

- Logos e imagens separados em "Referências visuais e logos".

---

## Itens P3 — Concluídos

### 1. [x] GoodNotes (Task 40A)

- Bloco "GoodNotes" adicionado na seção Documentos.
- Link externo para https://www.goodnotes.com/ com target="_blank" rel="noopener".
- Nenhuma credencial registrada.

---

## Segurança — Auditoria concluída (Tasks 41/42)

- Bloco "CREDENCIAIS ACADEMICAS" removido de dashboard.html (commit 6726a43).
- Propriedades login e senha removidas de dashboard.html.
- Senha mascarada eliminada de dashboard.html.
- E-mail pessoal removido das linhas ATTENDEE de calendar-lm.ics (commit 2a2159a).
- Nenhuma credencial presente em anaju-neves-hub.html, JSONs ou docs.

---

## Ordem de execução — Concluída

| Task | Descrição | Status |
|------|-----------|--------|
| Task 33 | Criar branch v1.1 e congelar regra de trabalho | Concluído |
| Task 34 | Remover controles técnicos e ajustar cabeçalho/foto | Concluído |
| Task 35 | Corrigir calendário "Todas as fontes" e LM | Concluído |
| Task 36 | Corrigir links quebrados e layout de Regras Práticas | Concluído |
| Task 37 | Reorganizar Biblioteca por fase | Concluído |
| Task 38A/38B | Reestruturar FIAP, Nano Courses, MarTech e Alura | Concluído |
| Task 39A/39B | Reformular Visão Geral e criar lixeira de tarefas | Concluído |
| Task 40A/40B | Organizar Documentos, assets e GoodNotes | Concluído |
| Task 41 | QA funcional v1.1 | Concluído |
| Task 42 | Security scrub de arquivos legados e calendar-lm.ics | Concluído |
| Task 43 | Consolidar documentação e checklist de release | Concluído |

---

## Pendências abertas (para v1.2 ou task futura)

1. Confirmação visual de 13274b5c14834c7e8a56532b2d05ca35.pdf — catalogado como student_id_candidate. Aguarda confirmação manual da Ana.
2. Sanitização ampla de outros e-mails em .ics — avaliar apenas se o repositório for tornado público.
3. Task 40C — Organização física de pastas/assets — não executada. Avaliar se necessário.
4. Remoção ou arquivamento de dashboard.html legado — ainda presente. Decidir em task futura.

---

*Backlog criado em 2026-05-08. Atualizado em 2026-05-11 — v1.1 concluída.*
