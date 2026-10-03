---
title: Como atualizar o sistema
description: Como atualizar seu sistema Rock ou Rolling
published: true
date: 2025-08-02T19:12:19.690Z
tags: documentação, howto, guia do usuário
editor: markdown
dateCreated: 2021-02-19T15:43:53.051Z
---

# Como atualizar o sistema

> A política de atualização do sistema OpenMandriva é diferente.
> **Nãot** use o Discover para atualização do sistema.
{.is-danger}

<br>


Abra o Konsole e execute os comandos:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf distro-sync --refresh --allowerasing
```

- ou

![update-menu.png](/images/update-menu.png)


- ou

![update-60-taskmanager02.jpg](/images/update-60-taskmanager02.jpg)

- ou

![update-dnfdrake.png](/images/update-dnfdrake.png)
