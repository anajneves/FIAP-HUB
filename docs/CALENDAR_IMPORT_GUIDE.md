# Guia rápido — calendários do Anaju Neves Hub

Este guia explica quais arquivos alimentam o `calendario-operacional.html` e como atualizar cada agenda sem quebrar o hub.

## Fontes oficiais atuais

O calendário operacional lê as fontes configuradas em:

```txt
data/calendars.json
```

As fontes oficiais atuais são:

```txt
FIAP & Afins          → icalexport.ics
Calendar Compromissos → calendar-compromissos.ics
Calendar L.M.         → calendar-lm.ics
```

## O que cada calendário representa

- `FIAP & Afins`: calendário acadêmico da FIAP, lives, quizzes, desafios, atividades e compromissos relacionados.
- `Calendar Compromissos`: compromissos pessoais da Ana.
- `Calendar L.M.`: agenda L.M. relacionada ao Lucca.

## Arquivos antigos/depreciados

Estes arquivos foram placeholders temporários e não devem ser tratados como fontes oficiais:

```txt
ana-pessoal.ics
lucca.ics
```

Se ainda existirem em alguma branch antiga, ignore ou remova quando for seguro. As fontes oficiais estão em `data/calendars.json`.

## Como atualizar pelo celular

1. Abra o repositório `FIAP-HUB` no GitHub.
2. Toque no arquivo que deseja atualizar:

```txt
icalexport.ics
calendar-compromissos.ics
calendar-lm.ics
```

3. Toque no ícone de edição.
4. Apague o conteúdo atual.
5. Cole o conteúdo completo do novo arquivo `.ics`.
6. Use uma mensagem de commit clara.

Exemplos:

```txt
Update FIAP calendar
Update Calendar Compromissos
Update Calendar L.M.
```

7. Salve o commit na branch correta.

## Regra principal

O nome do arquivo precisa bater exatamente com o caminho em:

```txt
data/calendars.json
```

Se você renomear `calendar-compromissos.ics` para `Calendar Compromissos.ics`, também precisa atualizar `data/calendars.json` no mesmo commit.

## Como testar

Depois de salvar, abra:

```txt
calendario-operacional.html
```

Confirme se aparecem apenas estas fontes:

```txt
FIAP & Afins
Calendar Compromissos
Calendar L.M.
```

Se aparecer `carregado · 0`, o arquivo existe, mas não tem eventos válidos ou os eventos estão fora do período mostrado.

## Formato mínimo válido de `.ics`

```ics
BEGIN:VCALENDAR
VERSION:2.0
PRODID:-//Anaju Neves Hub//Calendar//PT-BR
CALSCALE:GREGORIAN
METHOD:PUBLISH
X-WR-CALNAME:Nome do calendário
X-WR-TIMEZONE:America/Recife
END:VCALENDAR
```

## Se der erro

Verifique:

1. Se o arquivo começa com `BEGIN:VCALENDAR`.
2. Se termina com `END:VCALENDAR`.
3. Se cada evento começa com `BEGIN:VEVENT` e termina com `END:VEVENT`.
4. Se o arquivo foi salvo com o nome correto.
5. Se o caminho em `data/calendars.json` está igual ao nome real do arquivo.
6. Se o navegador não está mostrando cache antigo. Nesse caso, recarregue a página.
