---
title: Как установить Steam в OpenMandriva
description: 
published: true
date: 2023-04-09T18:38:38.714Z
tags: документация, инструкции, руководство пользователя
editor: markdown
dateCreated: 2020-03-09T20:59:51.458Z
---

# Как установить Steam в OpenMandriva


## Чтобы установить Steam в OpenMandriva Lx, выполните следующие действия:

### Добро пожаловать > Приложения > Игры

Нажми на Steam


![omlx43.doc.steam-01.jpg](/images/omlx43.doc.steam-01.jpg)

![omlx43.doc.steam-02.jpg](/images/omlx43.doc.steam-02.jpg)

![omlx43.doc.steam-03.jpg](/images/omlx43.doc.steam-03.jpg)

### Меню приложений > Игры > Steam

![omlx43.doc.steam-04.jpg](/images/omlx43.doc.steam-04.jpg)

![omlx43.doc.steam-05.jpg](/images/omlx43.doc.steam-05.jpg)

![omlx43.doc.steam-06.jpg](/images/omlx43.doc.steam-06.jpg)

![omlx43.doc.steam-07.jpg](/images/omlx43.doc.steam-07.jpg)

![omlx43.doc.steam-08.jpg](/images/omlx43.doc.steam-08.jpg)

![omlx43.doc.steam-09.jpg](/images/omlx43.doc.steam-09.jpg)

![omlx43.doc.steam-10.jpg](/images/omlx43.doc.steam-10.jpg)

![omlx43.doc.steam-11.jpg](/images/omlx43.doc.steam-11.jpg)

Если вы используете драйвер NVIDIA, необходимо также установить его 32-битную версию.


`$ sudo dnf clean all;dnf clean all;dnf repolist`

Затем выполните:
`$ sudo dnf install --enablerepo=rock-x86_64-non-free nvidia-32bit`
или
`$ sudo dnf install --enablerepo=rock-x86_64-non-free nvidia-legacy-32bit`










