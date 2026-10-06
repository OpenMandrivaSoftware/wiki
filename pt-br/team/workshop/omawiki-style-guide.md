---
title: Guia de estilo específico do wiki do OpenMandriva
description: 
published: true
date: 2022-01-24T19:15:25.305Z
tags: howto, políticas, wiki, documentação
editor: markdown
dateCreated: 2020-03-13T11:27:11.684Z
---

# Guia de estilo específico do wiki do OpenMandriva
> Leia primeiro [Guia geral de estilo do wiki](/en/team/workshop/wiki-style-guide)
{.is-danger}

## Regras específicas do wiki do OpenMandriva

> Esta página está em desenvolvimento e será atualizada ao longo do tempo, assim que eu encontrar algum motivo para adicionar mais dicas.
{.is-info}


### Imagens
Capturas de tela e imagens comuns inseridas nas páginas do wiki devem ser carregadas **somente** na pasta `/images`.
Essa é a finalidade para a qual a pasta foi criada.

O nome do arquivo de imagem não deve conter:
- Espaços (use hífens em vez disso)
- Sublinhados (use hífens em vez disso)
- Ponto (reservado para extensões de arquivo)
- Caracteres de URL não seguros (como sinais de pontuação, aspas, símbolos matemáticos etc.)

Sempre que possível, renomeie o arquivo de imagem para algo significativo e relacionado à página ou ao que está sendo mostrado.

### Caminhos
Os caminhos devem estar em letras minúsculas. Use hífens para separar as palavras.
Não é permitida pontuação, exceto hífens e/ou sublinhados.
-- Observação: mesmo que sejam *tecnicamente* permitidos, o padrão do wiki do OpenMandriva é usar hífens em vez de sublinhados.
Não é necessário usar o título completo da página no caminho: ele pode, e deve, ser abreviado quando possível.

Caminhos não podem conter os seguintes caracteres:
- Espaços (use hífens em vez disso)
- Ponto (reservado para extensões de arquivo)
- Caracteres de URL não seguros (como sinais de pontuação, aspas, símbolos matemáticos etc.)

Como frequentemente precisamos escrever o número da versão de uma versão (4.0, 4.1, 4.2 etc.), ao criar novas páginas, basta convertê-lo em `40`, `41`, `42` etc., omitindo o ponto no caminho.

Se a página se chamar "*How to foo bar whatever*", o caminho deve ser `/doc/guides/howto-something`
Não use `how-to`, `howtos`, `how-tos` etc.

### Fluxo de trabalho de tradução
Para uma melhor organização, mantenha o caminho original em inglês inalterado, alterando apenas o prefixo do código do idioma. Assim, `en/home` se tornará `fr/home`, `it/home` etc.
Como outro exemplo, `/en/doc/guides/howto-list-packages-iso` se tornará `/it/doc/guides/howto-list-packages-iso` e o seu **título da página** traduzido (que é algo completamente diferente do caminho) será "*Come ottenere una lista di tutti i pacchetti presenti nella ISO*"
Tenha em mente que o caminho é uma convenção; o título da página pode ser o que for adequado no próprio idioma.
A ação acima, no entanto, é simplificada e realizada automaticamente ao clicar no ícone de *Idioma* <i class="v-icon mdi mdi-web"></i>no canto superior direito da página.

\-






