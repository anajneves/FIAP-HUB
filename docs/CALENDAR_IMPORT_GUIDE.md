# Guia rápido — substituir calendários `.ics`

Este guia explica como trocar os arquivos vazios de calendário pelos arquivos reais sem quebrar o Anaju Neves Hub.

## Arquivos usados pelo calendário operacional

O arquivo `calendario-operacional.html` lê as fontes configuradas em:

```txt
data/calendars.json
```

Hoje os arquivos esperados são:

```txt
icalexport.ics      → calendário FIAP
ana-pessoal.ics     → calendário pessoal da Ana
lucca.ics           → calendário do Lucca
externo.ics         → calendário externo opcional
```

## Como substituir pelo celular

1. Abra o repositório `FIAP-HUB` no GitHub.
2. Toque no arquivo que deseja substituir, por exemplo:

```txt
ana-pessoal.ics
```

3. Toque no ícone de edição.
4. Apague todo o conteúdo atual.
5. Cole o conteúdo completo do novo arquivo `.ics`.
6. No campo de commit, use um título claro:

```txt
Update Ana personal calendar
```

ou:

```txt
Update Lucca calendar
```

7. Salve o commit direto na branch `main`.

## Importante

Não mude o nome dos arquivos, porque o calendário operacional procura exatamente estes caminhos:

```txt
ana-pessoal.ics
lucca.ics
```

Se o nome mudar, será necessário atualizar também `data/calendars.json`.

## Como testar

Depois de salvar, abra:

```txt
calendario-operacional.html
```

Confirme se a fonte aparece como carregada:

```txt
Ana / pessoal · carregado
Lucca · carregado
```

Se aparecer carregado com `0`, o arquivo existe, mas não tem eventos válidos.

## Regra de organização

- Calendário FIAP fica em `icalexport.ics`.
- Calendário pessoal da Ana fica em `ana-pessoal.ics`.
- Calendário do Lucca fica em `lucca.ics`.
- Qualquer agenda extra deve ir para `externo.ics` ou ser importada localmente pela interface.

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
5. Se o navegador não está mostrando versão antiga em cache. Nesse caso, recarregue a página.