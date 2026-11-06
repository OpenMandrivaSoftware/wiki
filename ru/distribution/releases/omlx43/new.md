---
title: Новое в OpenMandriva Lx 4.3
description: 
published: true
date: 2022-02-06T01:29:24.862Z
tags: 4.3
editor: markdown
dateCreated: 2021-04-24T05:14:24.001Z
---

# Новое в OpenMandriva Lx 4.3

Рекомендуется прочитать последние [примечания к выпуску](/distribution/releases/omlx43/notes) на нашей вики.

## Что нового в OpenMandriva Lx 4.3?
OpenMandriva Lx 4.3 — это новая версия от Ассоциации OpenMandriva. [Кодовое имя](/policies/codename) Dysprosium.

## Основные особенности

### KDE

- Frameworks 5.90.0 [*(подробнее)*](https://kde.org/announcements/frameworks/5/5.90.0/)
- Plasma 5.23.5 [*(подробнее)*](https://kde.org/announcements/plasma/5/5.23.5/)
- KDE Gear 21.12.2 [*(подробнее)*](https://kde.org/announcements/gear/21.12.1/)
- Qt 5.15.3 [*(подробнее)*](https://www.qt.io)

### Графическая подсистема

- Xorg 21.1.3
- Wayland 1.20.0 [*(подробнее)*](https://wayland.freedesktop.org/releases.html)
- Mesa 21.3.5 [*(подробнее)*](http://www.mesa3d.org/)

### Ядро

- Kernel 5.16.7 [*(подробнее)*](https://www.kernel.org/)
- systemd 249 [*(подробнее)*](https://www.freedesktop.org/wiki/Software/systemd/)
- LLVM/clang 13.0.0 [*(подробнее)*](http://llvm.org/)
- binutils 2.37
- gcc 11.2 [*(подробнее)*](https://gcc.gnu.org/)
- glibc 2.34 [*(подробнее)*](http://www.gnu.org/software/libc/)
- Java 17
- Zstandard — новый алгоритм сжатия в реальном времени, обеспечивающий высокую степень сжатия, реализованный в нашем ядре, обеспечивает более быструю загрузку

OpenMandriva предоставляет ядро Linux, скомпилированное с помощью Clang. Для сравнения пользователи могут установить пакеты `kernel-release-desktop` и `kernel-release-desktop-clang` одной и той же версии.

### Установщик

- Calamares 3.2.39 [*(подробнее)*](https://calamares.io)

### Applications

- LibreOffice 7.3.0
- Falkon 3.2
- Firefox 96
- Браузер Chromium стабильная версия 97 (и бета 98, dev 99)
- Krita 5.0.2
- Gimp 2.10.30
- Calligra Suite 3.2.1
- Digikam 7.5
- SMPlayer 21.10.0
- VLC 3.0.16
- Virtualbox 6.1.32
- OBS Studio 27.1.3

Портирование на aarch64 (64-разрядные процессоры ARM) завершено, что позволяет создавать [энергоэффективные "замены" ПК менее чем за 150 $](https://videos.openmandriva.org/videos/watch/4e135a39-4232-4d85-999c-e349ba8a7bd9).
Установочные образы доступны для PinebookPro, Raspberry Pi 4B и 3B+, Rock Pi 4A, 4B и 4C, Synquacer, Cubox Pulse и универсальных устройств, совместимых с UEFI, таких как большинство серверных плат aarch64. Вскоре дополнительная аппаратная поддержка aarch64 улучшится. Этот порт также позволяет нам впервые сделать ориентир на смартфон — образ, работающий на PinePhone, доступен (но пока не рассматривается как окончательный вариант).

\- 



