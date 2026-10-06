---
title: Documentação para criação de páginas de versões
description: 
published: true
date: 2021-09-26T21:47:46.114Z
tags: documentação, wiki
editor: markdown
dateCreated: 2020-03-07T18:55:42.072Z
---

# Documentação para criação de páginas de versões

Para cada nova versão, criar:

## Lançamento final (GA)

### página principal 'Overview'

Padrão do caminho:
`/releases/omlxNN`
exemplo: /releases/omlx42

### Subpáginas
#### "O que há de novo?"
Padrão do caminho:
`/releases/omlxNN`/new'
exemplo: /releases/omlx42/new

#### 'Notas'
Padrão do caminho:
`/releases/omlxNN/notes`
example: /releases/omlx42/notes

#### 'Errata'
Padrão do caminho:
`/releases/omlxNN/errata`
example: /releases/omlx42/errata

## Versões de desenvolvimento (Alpha, Beta, RC)

### Subpáginas
Padrão do caminho:
`/releases/omlxNN/alpha`
`/releases/omlxNN/beta`
`/releases/omlxNN/rc`

`/releases/omlxNN/alpha/notes`
`/releases/omlxNN/beta/notes`
`/releases/omlxNN/rc/notes`

`/releases/omlxNN/alpha/errata`
`/releases/omlxNN/beta/errata`
`/releases/omlxNN/rc/errata`

exemplo: /releases/omlx42/alpha
exemplo: /releases/omlx42/beta
exemplo: /releases/omlx42/rc

exemplo: /releases/omlx42/alpha/notes
exemplo: /releases/omlx42/beta/notes
exemplo: /releases/omlx42/rc/notes

exemplo: /releases/omlx42/alpha/errata
exemplo: /releases/omlx42/beta/errata
exemplo: /releases/omlx42/rc/errata

## Adendo - Caminhos
Os caminhos devem estar em letras minúsculas. Use hífens para separar as palavras.
Não é permitida pontuação, exceto hífens e/ou sublinhados.

Os caminhos não podem conter os seguintes caracteres:
-Espaço (use hífens em vez disso)
-Ponto (reservado para extensões de arquivo)
-Caracteres de URL não seguros (como sinais de pontuação, aspas, símbolos matemáticos etc.)

Como frequentemente precisamos escrever o número da versão de uma versão (4.0, 4.1, 4.2 etc.), ao criar novas páginas, basta convertê-lo em `40`, `41`, `42` etc., omitindo o ponto no caminho.

