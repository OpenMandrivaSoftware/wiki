---
title: Ferramenta de relatório de bugs do OpenMandriva Lx
description: 
published: true
date: 2025-04-07T23:57:30.827Z
tags: documentação, guia do usuário. ferramentas
editor: markdown
dateCreated: 2021-03-08T17:17:16.207Z
---

# Ferramenta de relatório de bugs do OpenMandriva Lx
A ferramenta simples é chamada om-bug-report.

## Os atalhos
### Abra o OM Welcome e navegue até OM Features > *Bug report tool*

![om43-bugreportwelc.jpg](/images/om43-bugreportwelc.jpg)


## Informações coletadas
A ferramenta coletará informações úteis de:

- vários arquivos de configuração (em /etc/*`)
- várias entradas de /proc (que permitem obter informações sobre a configuração do kernel)
- configuração do GRUB (o programa de inicialização)
- saída do `lspcidrake` (para listar dispositivos PCI)
- saída do lsusb (para listar dispositivos USB)
- saída do dmidecode (para obter informações sobre o hardware a partir da BIOS)
- systemctl --failed (para informar sobre sistemas ou serviços que não foram iniciados)
- journalctl -b (para exibir o log da inicialização atual)
- rpm -qa (para listar pacotes instalados)
- gcc version (para a versão do compilador)

![om43-bugreportpsw.jpg](/images/om43-bugreportpsw.jpg)

![om43-bugreportpopup.jpg](/images/om43-bugreportpopup.jpg)

Em seguida, será criado o arquivo omdv-bug-report no seu diretório /home

![om43-bugreportfile.jpg](/images/om43-bugreportfile.jpg)

> **Este arquivo deve ser anexado a qualquer bugreport**.
{.is-info}

Isso ajudará a agilizar o trabalho de quem corrige os bugs e simplificará o trabalho de quem os relata, fornecendo rapidamente informações detalhadas.

\- 


