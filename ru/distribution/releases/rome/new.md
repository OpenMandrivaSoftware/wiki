---
title: Список изменений OpenMandriva ROME
description: 
published: true
date: 2025-04-20T09:41:38.909Z
tags: непрерывные обновления, rome
editor: markdown
dateCreated: 2023-02-28T15:34:33.449Z
---

### Что нового в ROME
<br>

##### Changelog 26.09
<br>

Полный анонс: [Выпуск OpenMandriva ROME 26.09](https://www.openmandriva.org/en/news/article/2026-10-01-openmandriva-rome-26-09/)
<br>

###### KDE
- [Plasma Desktop 6.7.5](https://kde.org/announcements/plasma/6/6.7.5/)
- Frameworks 6.29.0
- [KDE Gear 26.08.1](https://kde.org/announcements/gear/26.08.1/)
- Qt 6.11.2 (и 5.15.19)
<br>

###### Другие рабочие окружения
- GNOME 50.3, Xfce 4.20, LXQt 2.4.0, MATE 1.28 (с экспериментальным сеансом Wayland)
- В репозиториях: hyprland 0.56.2, cosmic 1.7.0, niri 26.04, sway 1.12, i3 4.25.1, labwc 0.20.2, Spectrwm (новинка)
<br>

###### Графическая подсистема
- [Mesa 26.2.3](http://www.mesa3d.org/)
- Открытый модуль ядра NVIDIA теперь включён в состав ядра; проприетарный драйвер версии 610.57.04 доступен в репозитории `non-free`
<br>

###### Ядро
- [Ядро Linux](https://www.kernel.org/) 7.2.7 (и 7.3.0-rc4), скомпилированное с помощью Clang. Также доступны версии, собранные с помощью GCC (`kernel-desktop-gcc`)
- [LLVM/Clang 23.1.2](http://llvm.org/)
- [GCC 16.2.0](https://gcc.gnu.org/)
- [glibc 2.44](http://www.gnu.org/software/libc/) с поддержкой взаимозаменяемых реализаций `malloc`
- rpm 6.1.0 с новым необязательным разделом `%pgo` в spec-файлах
- grub2 2.16
- ROCm 10.0.0
<br>

###### Приложения
- Helium 0.17.2 — новый браузер по умолчанию для Plasma и LXQt, (заменивший ungoogled-chromium)
- Firefox 156.0, Thunderbird 155.0, LibreOffice 26.8.0.3
- Krita 6.0.4 (Qt6), GIMP 3.2.4, Inkscape 1.4.4, Blender 5.2.2, OBS 32.2.2
- WINE 11.18, Proton 11.0+20260808, DXVK 3.0.2, vkd3d 2.0
- Поддержка Snap (`sudo dnf install snapd`) наряду с Flatpak и AppImage
- Инструменты локального ИИ: llama-cpp, ollama, whisper-cpp, comfyui и другие, использующие общесистемную библиотеку GGML 0.24.0
<br>

##### Список изменений 25.04
<br>

###### KDE
- [Plasma Desktop 6.3.4](https://kde.org/announcements/plasma/6/6.3.4) - ([и 5.27.12](https://kde.org/announcements/plasma/5/5.27.12))
- [Frameworks 6.13.0](https://kde.org/announcements/frameworks/6/6.13.0) - ([и 5.116](https://kde.org/announcements/frameworks/5/5.116))
- [KDE Applications 25.04.0](https://kde.org/announcements/gear/25.04.0) - ([и 23.08.5](https://kde.org/announcements/gear/23.08.5))
- [Qt 6.9.0 - (и 5.15.15)](https://www.qt.io)
<br>

###### Графическая подсистема
- [Xorg 21.1.16](https://www.x.org/)
- [Wayland 1.23.1](https://wayland.freedesktop.org/releases.html)
- [Mesa 25.0.4](http://www.mesa3d.org/)
<br>

###### Ядро
- [Ядро Linux](https://www.kernel.org/) 6.14.2 (и 6.15.0-rc2), скомпилированное с помощью Clang. Также доступны версии, собранные с помощью GCC
- [systemd 257.5](https://www.freedesktop.org/wiki/Software/systemd/)
- [LLVM/Clang 19.1.7](http://llvm.org/)
- binutils 2.44
- [GCC 14.2.1](https://gcc.gnu.org/)
- [glibc 2.41](http://www.gnu.org/software/libc/)
- Java 24
<br>

###### Установщик
\- [Calamares 3.3.14](https://calamares.io)
<br>

###### Некоторые основные приложения
- Офисный пакет LibreOffice 25.2.3 с интеграцией Qt 6 и Plasma 6
- Falkon 25.04.0
- Chromium 135.0.7049.84 с исправлениями, отключёнными механизмами слежения Google и восстановленной поддержкой JPEG-XL
- Firefox 137.0.2 с исправлениями и отключёнными механизмами слежения
- QMPlay2 25.01.19
- Telegram Desktop 5.13.1
- Krita 5.2.9
- GIMP 3.0.2
- digiKam 8.6.0
- SMPlayer 24.5.0
- VLC 3.0.21
- VirtualBox 7.1.8
- VokoscreenNG 4.5.0
- OBS Studio 31.0.3
<br>

### Альтернативные рабочие окружения
В системных репозиториях также доступны LXQt 2.2, GNOME 48.1, MATE 1.28, Xfce 4.20.1, Cinnamon, IceWM, i3, Sway, Hyprland, Hypr, Wayfire, Budgie и другие.
<br>

###### Поддержка Flatpak
<br>

![header-tr-rome.svg](/assets/header-tr-rome.svg){.align-abstopright}