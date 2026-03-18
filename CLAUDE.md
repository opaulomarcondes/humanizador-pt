# Humanizador PT

Este repositório contém uma skill para Claude Code. Não é um projeto de desenvolvimento e não possui servidores, scripts executáveis, dependências ou configurações de build.

## O que este repositório é

Um conjunto de arquivos markdown que definem um skill de humanização de texto em português brasileiro. O arquivo principal é `SKILL.md`.

## Como usar

Este repositório deve ser instalado no diretório de skills do Claude Code:

```
~/.claude/skills/humanizador-pt/
```

Uma vez instalado nesse local, a skill fica disponível automaticamente em qualquer projeto aberto com Claude Code. Para acionar, use qualquer variação de:

```
humanize o texto abaixo
remova os padrões de IA
reescreva em tom mais natural
```

## Arquivos deste repositório

- `SKILL.md` — definição da skill (leia este arquivo para entender os 24 padrões)
- `README.md` — documentação de instalação e uso
- `WARP.md` — integração com o terminal Warp
- `contexts/CONTEXT-TEMPLATE.md` — template para contexto de voz personalizado
- `LICENSE` — MIT
- `.gitignore` — ignora arquivos de contexto pessoal por padrão

## O que não fazer

Não tente executar, compilar ou servir nada neste repositório. Não há `package.json`, `requirements.txt`, `Makefile` nem qualquer outro arquivo de configuração de projeto — isso é intencional.
