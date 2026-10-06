---
title: Como obter uma lista das atualizações mais recentes
description: 
published: true
date: 2021-09-26T21:33:27.191Z
tags: documentação, howto, guia do usuário
editor: markdown
dateCreated: 2020-03-09T19:41:11.057Z
---

# Como obter uma lista das atualizações mais recentes
Às vezes, as atualizações podem causar algum tipo de mau funcionamento e, nesse caso, pode ser útil ter em mãos uma lista das atualizações mais recentes enquanto se procura a origem do problema.

Vamos começar com uma lista completa, da qual podemos obter algumas informações úteis.

O principal comando é

```
rpm -qa --last
```

que exibe este tipo de lista:
.

    korganizer-17.12.2-1-omv2015.0.x86_64         Thu 15 Mar 2018 05:27:48 PM CET
    incidenceeditor-17.12.2-1-omv2015.0.x86_64    Thu 15 Mar 2018 05:27:48 PM CET
    lib64vdpau-drivers-17.3.6-1-omv2015.0.x86_64  Thu 15 Mar 2018 05:27:47 PM CET
    lib64korganizer_core5-17.12.2-1-omv2015.0.x86_64 Thu 15 Mar 2018 05:27:47 PM CET
    spectacle-17.12.2-1-omv2015.0.x86_64          Thu 15 Mar 2018 05:27:45 PM CET
    locales-en-2.27-9-omv2015.0.x86_64            Thu 15 Mar 2018 05:27:45 PM CET
    kdf-17.12.2-1-omv2015.0.x86_64                Thu 15 Mar 2018 05:27:44 PM CET
    task-plasma-5.10.5-4-omv2015.0.x86_64         Thu 15 Mar 2018 05:27:43 PM CET
    okular-tiff-17.12.2-1-omv2015.0.x86_64        Thu 15 Mar 2018 05:27:43 PM CET


Observação: A lista pode ser muito longa e algumas linhas podem não ser incluídas.
Para ter certeza de que todas serão exibidas, facilitar a leitura ou fornecê-la como anexo, é útil converter a saída do console em um documento de texto.

_Exemplo_:
```
rpm -qa --last > rpmlast.txt
```
Um documento `rpmlast.txt` será criado no seu diretório /home.

Você pode querer especificar um nome de arquivo diferente sempre que executar o comando acima, para obter um novo arquivo e não sobrescrever o anterior.

_Exemplo_:
```
rpm -qa --last > rpmlast_20180315.txt
```

O documento também pode ser salvo no formato ".csv" (Comma Separated Value), para ser facilmente importado em uma planilha
_por exemplo no Calc_:

```
rpm -qa --last> rpmlast_20180315.csv
```

A lista pode conter muitas linhas, mas você pode restringi-la indicando a data.

_Exemplo_:
```
rpm -qa --last | grep Mar
``` 
fornece as atualizações feitas em março. Para saber como abreviar o mês, basta consultar o documento criado com o comando principal mostrado acima.

Você também pode restringir sua pesquisa a um dia específico:

_Exemplo_:
```
rpm -qa --last | grep Thu\ 15\ Mar
```

.