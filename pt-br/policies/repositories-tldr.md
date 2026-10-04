---
title: Seletor de Repositórios de Software
description: 
published: true
date: 2024-11-27T11:00:22.530Z
tags: documentação, guia do usuário. ferramentas, howto
editor: markdown
dateCreated: 2020-03-03T17:34:57.632Z
---

# Seletor de Repositórios de Software

## Como gerenciar repositórios com o om-repo-picker

Menu de aplicativos > Seletor de Repositórios de Software (om-repo-picker)

![omrome.doc.repopicker-01.jpg](/images/omrome.doc.repopicker-01.jpg)


ou selecione o OpenMandriva repo-picker no OM Welcome

![omrome.doc.repopicker-02.jpg](/images/omrome.doc.repopicker-02.jpg)


## Fontes de mídia
Temos quatro fontes de mídia básicas: `/main`, `/extra`, `/restricted` e `/non-free`

### main
`/main` contém os pacotes principais mantidos pela equipe do OpenMandriva Lx.
Isso inclui tudo o que está presente nas imagens de instalação, bem como muitos outros aplicativos considerados importantes. O repositório `/main/release` deve estar sempre habilitado.

**Usuários comuns nunca devem habilitar** os repositórios `/testing` **em versões estáveis**.

![omrome.doc.repopicker-03.jpg](/images/omrome.doc.repopicker-03.jpg)

Se, por algum motivo, um usuário comum precisar habilitá-los, faça isso por sua própria conta e risco.

![omrome.doc.repopicker-04.jpg](/images/omrome.doc.repopicker-04.jpg)

### extra
`/extra` representa os pacotes mantidos pela comunidade. Eles não têm suporte da equipe principal do OpenMandriva Lx e dependem dos mantenedores dos pacotes para atualizá-los.
Pode haver muitos pacotes úteis e atualizados, assim como muitos que não serão instalados ou outros que serão instalados, mas não funcionarão corretamente. Os usuários são bem-vindos a usar o que encontrarem neste repositório e que esteja funcionando.
#### Como habilitar repositórios extra no om-repo-picker

![omrome.doc.repopicker-05.jpg](/images/omrome.doc.repopicker-05.jpg)

### restricted
`/restricted` contém bibliotecas que não são instaladas por padrão devido a questões legais, como problemas relacionados a patentes. 
O uso desses pacotes varia de acordo com o país. O OpenMandriva Lx não se responsabiliza pelo uso deles. Se você acredita que o uso deles não é permitido em seu país, desabilite os repositórios restricted.
#### Como habilitar repositórios restricted no om-repo-picker

![omrome.doc.repopicker-06.jpg](/images/omrome.doc.repopicker-06.jpg)

### non-free
`/non-free` contém aplicativos e drivers que são distribuídos, mas não atendem às definições de Software Livre.
Embora possamos ajustar o empacotamento desses aplicativos, não temos o código-fonte e, portanto, não podemos corrigir problemas causados por qualquer coisa neste repositório.
#### Como habilitar repositórios non-free no om-repo-picker

![omrome.doc.repopicker-07.jpg](/images/omrome.doc.repopicker-07.jpg)

### Repositórios de terceiros
Você também pode querer habilitar repositórios de terceiros

![omrome.doc.repopicker-08.jpg](/images/omrome.doc.repopicker-08.jpg)

## Após as alterações
Quando terminar de fazer suas alterações, execute o seguinte comando no console:
`$ sudo dnf clean all ; dnf clean all ; dnf repolist`

## Mais detalhes
Para obter uma explicação detalhada, leia [Plano de Lançamento e Repositórios do OpenMandriva]\(/policies/release-plan-and-repositories)

\- 

