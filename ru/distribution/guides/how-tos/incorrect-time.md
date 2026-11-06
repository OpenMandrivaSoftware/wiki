---
title: Как устранить наиболее распространённую причину неправильного отображения времени при двойной загрузке с Windows
description: 
published: true
date: 2021-09-26T21:36:52.368Z
tags: документация, инструкции, руководство пользователя, устранение неполадок
editor: markdown
dateCreated: 2020-03-09T19:25:27.676Z
---

# Как устранить наиболее распространённую причину неправильного отображения времени при двойной загрузке с Windows

Если при двойной загрузке Linux и Windows в Linux неправильно отображается время

### Проверьте настройки системы Linux:
```
$ timedatectl
                      Local time: Tue 2018-08-21 13:11:23 CDT
                  Universal time: Tue 2018-08-21 18:11:23 UTC
                        RTC time: Tue 2018-08-21 18:11:23
                       Time zone: US/Central (CDT, -0500)
       System clock synchronized: no
systemd-timesyncd.service active: yes
                 RTC in local TZ: no
```

Обратите внимание на последнюю строку. Если в ней указано `RTC in local TZ: yes`, настройка выполнена правильно и причину проблемы следует искать в другом месте.
Однако, скорее всего, вы увидите, что для параметра RTC in local TZ установлено значение no.

### Чтобы исправить это, выполните команду:

```
$ sudo timedatectl set-local-rtc 1 --adjust-system-clock
```

> Вам потребуется ввести пароль суперпользователя root, после чего команда будет выполнена.
{.is-warning}


Для проверки повторно введите:
```
$ timedatectl
                      Local time: Tue 2018-08-21 18:15:28 CDT
                  Universal time: Tue 2018-08-21 23:15:28 UTC
                        RTC time: Tue 2018-08-21 18:15:28
                       Time zone: US/Central (CDT, -0500)
       System clock synchronized: no
systemd-timesyncd.service active: yes
                 RTC in local TZ: yes

Warning: The system is configured to read the RTC time in the local time zone.
         This mode cannot be fully supported. It will create various problems
         with time zone changes and daylight saving time adjustments. The RTC
         time is never updated, it relies on external facilities to maintain it.
         If at all possible, use RTC in UTC by calling
         'timedatectl set-local-rtc 0'.
```

Теперь всё настроено правильно.
*(Предупреждение можно проигнорировать)*
<br>

### Определения:

`RTC` = Часы реального времени, также называемые аппаратными часами или hwclock
`TZ` = Часовой пояс