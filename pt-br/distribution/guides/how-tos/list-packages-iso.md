---
title: Como obter uma lista de todos os pacotes incluídos na ISO
description: 
published: true
date: 2022-04-02T15:42:47.137Z
tags: documentação, howto, guia do usuário
editor: markdown
dateCreated: 2020-03-09T19:56:46.846Z
---

# Como obter uma lista de todos os pacotes incluídos na ISO


No modo live, abra o console e digite:

```
rpm -qa|sort > pkglist-sort.txt
```
que criará um documento de texto simples no diretório `/home` do seu usuário, chamado `pkglist-sort.txt`

A lista de pacotes está ordenada de A-Z

![pkglist.jpg](/images/pkglist.jpg)

> O truque simples se aplica não apenas ao modo ISO/live, mas também aos sistemas instalados.
> Você pode executar o comando sempre que precisar.
{.is-info}


Se você quiser uma lista de todos os pacotes ordenados por data, digite:

```
rpm -qa --last > pkglist-last.txt
```

