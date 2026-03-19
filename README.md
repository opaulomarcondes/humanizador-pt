# Humanizador PT

Skill para Claude Code que detecta e elimina os padrões de escrita artificial em textos em português brasileiro, tornando o conteúdo gerado por IA indistinguível de texto humano.

---

## O que é

Textos gerados por modelos de linguagem carregam marcadores reconhecíveis: aberturas sycophantes, encerramentos formulaicos, jargão corporativo, nominalização excessiva, frases lineares repetidas, bullets onde deveria haver prosa analítica. Em português brasileiro, esses padrões têm características próprias que não são endereçadas pelas ferramentas desenvolvidas para o inglês.

Esta skill identifica 24 padrões específicos do português e os corrige em três passagens sequenciais: humanização inicial, auditoria crítica e reescrita final. O resultado é um texto que preserva o conteúdo e a intenção originais enquanto elimina o que o entrega como produção automática.

O repositório inclui também um sistema de contexto de voz — um arquivo `CONTEXT-TEMPLATE.md` que o usuário preenche com suas próprias diretrizes de tom, vocabulário e restrições editoriais. A skill carrega esse contexto e aplica as regras personalizadas em adição aos 24 padrões genéricos.

---

## Instalação

### No app do Claude (chat mode)

1. Acesse **Personalizar → Habilidades → +**
2. Selecione a opção **Copiar um arquivo ZIP**
3. Faça download do arquivo `humanizador-pt.skill` [deste repositório](https://github.com/opaulomarcondes/humanizador-pt/releases)
4. Cole o arquivo no campo solicitado

### Via Claude Code

```bash
git clone https://github.com/opaulomarcondes/humanizador-pt ~/.claude/skills/humanizador-pt
```

Ou copie manualmente o arquivo `SKILL.md` para `~/.claude/skills/humanizador-pt/SKILL.md`.

---

## Uso

No Claude Code, acione a skill com qualquer variação de:

```
/humanize este texto
/humanizador
humanize o texto abaixo
remova os padrões de IA
reescreva em tom mais natural
está soando muito de chatbot — corrija
```

Cole o texto a seguir do acionamento. A skill aplicará as três passagens e retornará o texto humanizado.

---

## Os 24 padrões

A skill endereça quatro categorias de marcadores artificiais:

**Padrões de abertura e encerramento** cobrem as assinaturas mais óbvias: abertura sycophant, encerramento formulaico, repetição parafraseada do pedido e disclaimers desnecessários que tratam o interlocutor como incapaz de discernimento.

**Padrões de vocabulário** incluem o uso de "crucial" (que deve ceder lugar a "fundamental", "essencial" ou "determinante"), jargão corporativo vazio, anglicismos evitáveis, nominalização excessiva, advérbios inflacionados e superlativos vazios.

**Padrões de transição e formatação** cobrem o uso automático de "Além disso,", "Por outro lado," e "Nesse contexto,", bem como excesso de negrito, listas onde a prosa seria mais adequada, cabeçalhos para cada parágrafo, travessões longos em excesso e emojis em textos formais.

**Padrões de sintaxe e argumento** endereçam o que é mais difícil de ver mas mais fácil de sentir: frases lineares repetidas sem subordinação, voz passiva sem agente, frases de alerta decorativo, generalizações sem referência e a ausência de análise crítica onde o texto apenas descreve.

---

## Contexto de voz personalizado

Os 24 padrões endereçam marcadores genéricos de IA. Mas cada autor, empresa ou instituição tem suas próprias restrições editoriais — palavras que evita, tom que prefere, estruturas que são marca registrada da sua voz.

O arquivo `contexts/CONTEXT-TEMPLATE.md` define a estrutura para você criar o seu próprio perfil de voz. Preencha-o com suas diretrizes e referencie-o ao acionar a skill:

```
/humanize o texto abaixo usando também o contexto de voz em contexts/meu-contexto.md
```

A skill carregará as regras personalizadas e as aplicará em adição aos 24 padrões.

---

## Abordagem

A humanização ocorre em três passagens sequenciais. A primeira aplica os 24 padrões sistematicamente. A segunda audita o resultado com o olhar de quem lê pela primeira vez — "este trecho ainda soa como IA?" A terceira reescreve o que a auditoria identificou. O processo preserva sempre o conteúdo factual, a terminologia técnica da área, a posição argumentativa central e a voz de citações atribuídas a terceiros.

---

## Créditos

Desenvolvido a partir do repositório [blader/humanizer](https://github.com/blader/humanizer) (MIT License), que por sua vez se baseia no guia [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) mantido pelo WikiProject AI Cleanup.

Esta versão é uma adaptação independente para o português brasileiro, com padrões específicos da língua e um sistema de contexto de voz personalizável.

---

## Licença

MIT
