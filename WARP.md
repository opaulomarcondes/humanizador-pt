# Humanizador PT — Integração com Warp

Este arquivo documenta como usar a skill Humanizador PT diretamente no terminal [Warp](https://www.warp.dev) via Claude Code.

---

## Pré-requisito

Claude Code instalado e configurado:

```bash
npm install -g @anthropic/claude-code
```

A skill instalada em `~/.claude/skills/humanizador-pt/` (ver README.md).

---

## Uso direto no terminal

Com o Claude Code ativo no Warp, acione a skill passando o texto via pipe ou como argumento:

```bash
# Via pipe a partir de um arquivo
cat meu-texto.md | claude "/humanize o texto abaixo"

# Via pipe com saída para arquivo
cat rascunho.md | claude "/humanize o texto abaixo" > revisado.md

# Texto curto diretamente no prompt
claude "/humanize: O documento foi elaborado com o objetivo de fornecer informações cruciais sobre o tema."
```

---

## Aliases recomendados

Adicione ao seu `.zshrc` ou `.bashrc` para agilizar o uso recorrente:

```bash
# Humanizar arquivo e imprimir no terminal
alias humanize='f() { cat "$1" | claude "/humanize o texto abaixo"; }; f'

# Humanizar arquivo e salvar versão revisada
alias humanize-save='f() { cat "$1" | claude "/humanize o texto abaixo" > "${1%.md}-humanizado.md" && echo "Salvo: ${1%.md}-humanizado.md"; }; f'

# Humanizar com contexto de voz personalizado
alias humanize-ctx='f() { cat "$1" | claude "/humanize o texto abaixo usando também o contexto em contexts/$2"; }; f'
```

Uso após configurar os aliases:

```bash
humanize rascunho.md
humanize-save proposta.md
humanize-ctx email.md meu-contexto.md
```

---

## Workflow típico

Para documentos longos, o processo recomendado é trabalhar por seção:

```bash
# Extrair seção específica, humanizar e revisar
sed -n '/## Introdução/,/## /p' documento.md | claude "/humanize o texto abaixo"
```

Para integração com o processo de escrita no VSCode ou Cursor, o Claude Code pode ser acionado diretamente do terminal integrado usando os mesmos comandos.

---

## Nota sobre o modelo

A humanização de textos não exige o modelo mais capaz — o modelo padrão (Sonnet) é suficiente para aplicar os 24 padrões e realizar as três passagens. Reserve o modelo mais capaz (Opus) para textos em que a reescrita criativa é mais intensa ou quando o resultado da passagem padrão não for satisfatório.
