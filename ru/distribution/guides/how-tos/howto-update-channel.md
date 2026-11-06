---
title: Как изменить канал обновлений
description: 
published: true
date: 2025-03-10T18:03:06.852Z
tags: документация, инструкции, руководство пользователя
editor: markdown
dateCreated: 2020-04-28T08:42:49.215Z
---

# Как изменить канал обновлений
## Как перейти с Rock на ROME (непрерывные обновления)

Пользователям, впервые знакомящимся с OpenMandriva Lx, мы рекомендуем начать со стабильного выпуска Rock, чтобы освоить работу с системой. В дальнейшем при желании можно перейти на ROME - редакцию с непрерывными обновлениями.

Как *пользователь ROME*, вы должны уметь работать с командной строкой и знать основы использования пакетного менеджера [dnf](/en/distribution/guides/software-management/DNF).
Также необходимо прочитать и понять документ [План выпусков и репозитории OpenMandriva](/en/policies/release-plan-and-repositories).

Для перехода на ROME:

- Откройте инструмент выбора репозиториев Software Repository Selector (`om-repo-picker`)
Меню приложений > Выбор репозиториев

![omlx43.doc.repopicker-01.jpg](/images/omlx43.doc.repopicker-01.jpg)

или выберите OpenMandriva repo-picker в приложении OM Welcome

![omlx43.doc.repopicker-02.jpg](/images/omlx43.doc.repopicker-02.jpg)


- Перейдите в самый первый раздел «Канал обновлений».

![om4.2-repopicker-03.jpg](/images/om4.2-repopicker-03.jpg)

- Выберите «Rolling» в раскрывающемся списке

![om4.2-repopicker-04.jpg](/images/om4.2-repopicker-04.jpg)

Подтвердите выбор, нажав ОК и при появлении запроса введите пароль суперпользователя root. Процесс может занять некоторое время, а окно программы может временно исчезнуть с экрана. Дождитесь завершения операции.

После этого репозитории Rock будут заменены на Rolling. Теперь необходимо выполнить обновление системы (`distro-sync`).

- Чтобы обновить систему, откройте Konsole и выполните следующие команды:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf --allowerasing distro-sync
```

\-
