---
title: Como compilar seu próprio software
description: 
published: false
date: 2024-01-24T01:07:05.893Z
tags: clang
editor: markdown
dateCreated: 2024-01-24T00:23:36.493Z
---

# Clang
Uma característica exclusiva do OpenMandriva é o uso do *clang* como nosso compilador principal.

> O GCC ainda está disponível, mas foi totalmente abandonado em favor do CLANG desde a versão 5.0 do OpenMandriva.
> Não é mais possível usar o gcc para compilar os módulos do kernel por exemplo! {.is-warning}

## Primeiros passos

1. Antes de compilar seu próprio software, verifique se ele já não está disponível em um de nossos repositórios.
2. Você também pode solicitar à nossa equipe que adicione o pacote pelo fórum ou diretamente no github.

## Início rápido

Você pode instalar as ferramentas básicas de desenvolvimento pelo aplicativo OM Welcome:
![om5-welcome-devtools.png](/images/om5-welcome-devtools.png)

Na linha de comando, você pode digitar:

```bash
sudo dnf install task-devel task-c-devel task-c++-devel
```

Exemplo de um comando make para compilar um software localmente em sua máquina:

## Compilador

Por padrão, os softwares podem usar o gcc como base. Você precisa tentar com o clang.
Abaixo está um exemplo de um comando make personalizado.

```bash
make CC=clang CXX=clang++ LD=ld.lld AR=llvm-ar NM=llvm-nm OBJCOPY=llvm-objcopy OBJSIZE=llvm-size STRIP=llvm-strip -C ...
```

## Empacotamento

Se quiser ir além, você está convidado a participar da nossa força-tarefa para empacotar softwares.