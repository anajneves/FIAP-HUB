# J.One Life OS v1 — Arquitetura

## Objetivo

Transformar o FIAP-HUB em um sistema local-first para rotina acadêmica, profissional e pessoal, sem depender de conteúdo fixo dentro do HTML.

A lógica central é simples:

```txt
fontes brutas -> interpretação -> dados normalizados -> interface
```

## Estrutura criada

```txt
life-os.html
/data
  academic.json
  calendars.json
  courses.json
  materials.json
/docs
  LIFE_OS_ARCHITECTURE.md
```

## Responsabilidade de cada arquivo

| Arquivo | Papel |
|---|---|
| `life-os.html` | Interface principal do Life OS. Carrega dados, importa calendário, renderiza módulos e salva estado local. |
| `data/academic.json` | Perfil acadêmico, fases FIAP e entregas prioritárias. |
| `data/calendars.json` | Registro seguro de fontes de calendário. Não guarda credenciais ou endereços privados. |
| `data/courses.json` | Roadmap MarTech, cursos FIAP e entregáveis práticos. |
| `data/materials.json` | Registro inteligente de biblioteca, guias, normas e materiais longos. |

## Decisões importantes

### 1. Dados privados fora do repositório público

Calendários pessoais ou externos devem ser importados localmente pela interface. O HTML público não deve guardar credenciais nem endereços privados.

### 2. PDFs longos não são lidos por padrão

PDFs de livro, capítulos extensos e materiais de aula entram como biblioteca. Eles devem ser catalogados por título, fase, disciplina, tipo e link.

### 3. Guias e normas são tratados diferente

Guias acadêmicos, normas disciplinares e documentos institucionais devem gerar regras úteis dentro do sistema:

- prazos importantes
- canais oficiais
- critérios de avaliação
- riscos acadêmicos
- procedimentos relevantes

### 4. FIAP e MarTech ficam separados

A graduação FIAP e a evolução profissional em MarTech se conectam, mas não são a mesma coisa. Por isso existem telas separadas:

- `FIAP`: entregas, fases, lives e materiais acadêmicos
- `MarTech`: cursos, skills, trilhas, portfólio e entregáveis profissionais

## Próximas melhorias recomendadas

### P0 — Segurança

- Remover do repositório público qualquer fonte privada antiga.
- Migrar dados pessoais para importação local ou repositório privado.
- Criar `.gitignore` para arquivos privados.

### P1 — Parser e indexador

- Criar script para varrer pastas de materiais.
- Gerar `materials.generated.json` automaticamente.
- Classificar arquivos por fase, disciplina e tipo.

### P2 — Calendário

- Expandir suporte a recorrência `RRULE`.
- Melhorar detecção de conflito.
- Adicionar exportação de eventos priorizados.

### P3 — UX

- Busca global.
- Página de diagnóstico do sistema.
- Cards de regra acadêmica extraída de guias.
- Modo mobile mais refinado.
- Tela de portfólio profissional.
