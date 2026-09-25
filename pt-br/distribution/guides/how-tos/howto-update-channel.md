---
title: Como atualizar o canal
description: 
published: true
date: 2025-03-10T18:03:06.852Z
tags: documentação, howto, guia do usuário, avançado
editor: markdown
dateCreated: 2020-04-28T08:42:49.215Z
---

# Como atualizar o canal
## Como atualizar do Rock para o ROME (rolling)

Para usuários novos no OpenMandriva Lx, sugerimos começar com a versão estável Rock para aprender como o sistema funciona e, depois, se desejar, migrar para o ROME, a edição rolling.

Como usuário do *ROME*, você deve saber usar a linha de comando e conhecer o básico do gerenciador de pacotes [dnf](/en/distribution/guides/software-management/DNF). O usuário também precisa ler e compreender o [Plano de lançamentos e repositórios do OpenMandriva](/en/policies/release-plan-and-repositories).

Para atualizar para o ROME:

- Abra o Seletor de Repositórios de Software (`om-repo-picker`)
Menu de aplicativos > Seletor de Repositórios de Software

![omlx43.doc.repopicker-01.jpg](/images/omlx43.doc.repopicker-01.jpg)

ou selecione o OpenMandriva repo-picker no OM Welcome

![omlx43.doc.repopicker-02.jpg](/images/omlx43.doc.repopicker-02.jpg)


- Vá para a primeira seção 'Atualizar canal'.

![om4.2-repopicker-03.jpg](/images/om4.2-repopicker-03.jpg)

- Selecione 'Rolling' no menu suspenso

![om4.2-repopicker-04.jpg](/images/om4.2-repopicker-04.jpg)

confirme clicando em OK e, quando solicitado, digite sua senha do root. Isso levará algum tempo e a janela do programa poderá ficar momentaneamente invisível, portanto, tenha paciência.

Com essa ação, você alterou os repositórios de Rock para Rolling e agora deve realizar uma atualização do sistema (`distro-sync`).

- Para atualizar seu sistema, abra o Konsole e execute os comandos:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf --allowerasing distro-sync
```

\-
