---
title: Как обновить систему
description: Как обновить систему Rock или Rolling
published: true
date: 2025-08-02T19:12:19.690Z
tags: документация, инструкции, руководство пользователя
editor: markdown
dateCreated: 2021-02-19T15:43:53.051Z
---

# Как обновить систему

> В OpenMandriva действует особый порядок обновления системы.
> **Не используйте** Discover для обновления системы.
{.is-danger}

<br>


Откройте Konsole и выполните следующие команды:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf distro-sync --refresh --allowerasing
```

- или

![update-menu.png](/images/update-menu.png)


- или

![update-60-taskmanager02.jpg](/images/update-60-taskmanager02.jpg)

- или

![update-dnfdrake.png](/images/update-dnfdrake.png)
