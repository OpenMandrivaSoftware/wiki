---
title: Registro de alterações do OpenMandriva ROME
description: 
published: true
date: 2025-04-20T09:41:38.909Z
tags: rolling, rome
editor: markdown
dateCreated: 2023-02-28T15:34:33.449Z
---

### O que há de novo em Rome
<br>

##### Registro de alterações 26.09
<br>

Anunciamento completo: [Lançamento do OpenMandriva ROME 26.09](https://www.openmandriva.org/en/news/article/2026-10-01-openmandriva-rome-26-09/)
<br>

###### KDE
\- [Plasma Desktop 6.7.5](https://kde.org/announcements/plasma/6/6.7.5/)
\- Frameworks 6.29.0
\- [KDE Gear 26.08.1](https://kde.org/announcements/gear/26.08.1/)
\- Qt 6.11.2 (and 5.15.19)
<br>

###### Outros ambientes de desktops
\- GNOME 50.3, Xfce 4.20, LXQt 2.4.0, MATE 1.28 (Com sessão Wayland experimental)
\- In the repositories: hyprland 0.56.2, cosmic 1.7.0, niri 26.04, sway 1.12, i3 4.25.1, labwc 0.20.2, Spectrwm (new)
<br>

###### Subsistema gráfico
\- [Mesa 26.2.3](http://www.mesa3d.org/)
\- O módulo de kernel aberto da NVIDIA agora é compilado diretamente no kernel; driver proprietário 610.57.04 em `non-free`
<br>

###### Núcleo
\- [Kernel](https://www.kernel.org/) 7.2.7 (e 7.3.0-rc4) compilado com clang. Versões compiladas com GCC também estão disponíveis (`kernel-desktop-gcc`)
\- [LLVM/clang 23.1.2](http://llvm.org/)
\- [gcc 16.2.0](https://gcc.gnu.org/)
\- [glibc 2.44](http://www.gnu.org/software/libc/), com suporte a implementações intercambiáveis de `malloc`
\- rpm 6.1.0, com uma nova seção opcional `%pgo` nos arquivos spec
\- grub2 2.16
\- ROCm 10.0.0
<br>

###### Aplicativos
\- Helium 0.17.2, novo navegador padrão para Plasma e LXQt (substitui o ungoogled-chromium)
\- Firefox 156.0, Thunderbird 155.0, LibreOffice 26.8.0.3
\- Krita 6.0.4 (Qt6), GIMP 3.2.4, Inkscape 1.4.4, Blender 5.2.2, OBS 32.2.2
\- WINE 11.18, Proton 11.0+20260808, DXVK 3.0.2, vkd3d 2.0
\- Suporte a Snap (`sudo dnf install snapd`), juntamente com Flatpak e AppImage
\- Ferramentas locais de IA: llama-cpp, ollama, whisper-cpp, comfyui e outras, utilizando o GGML 0.24.0 disponível em todo o sistema
<br>

##### Registro de alterações 25.04
<br>

###### KDE
\- [Plasma Desktop 6.3.4](https://kde.org/announcements/plasma/6/6.3.4) - ([and 5.27.12](https://kde.org/announcements/plasma/5/5.27.12))
\- [Frameworks 6.13.0](https://kde.org/announcements/frameworks/6/6.13.0) - ([and 5.116](https://kde.org/announcements/frameworks/5/5.116))
\- [KDE Applications 25.04.0](https://kde.org/announcements/gear/25.04.0) - ([and 23.08.5](https://kde.org/announcements/gear/23.08.5))
\- [Qt 6.9.0 - (and 5.15.15)](https://www.qt.io)
<br>

###### Subsistema gráfico
\- [Xorg  21.1.16](https://www.x.org/)
\- [Wayland 1.23.1](https://wayland.freedesktop.org/releases.html)
\- [Mesa 25.0.4](http://www.mesa3d.org/)
<br>

###### Núcleo
\- [Kernel](https://www.kernel.org/) 6.14.2 (e 6.15.0-rc2) compilado com clang. Versões compiladas com GCC também estão disponíveis
\- [systemd 257.5](https://www.freedesktop.org/wiki/Software/systemd/)
\- [LLVM/clang 19.1.7](http://llvm.org/)
\- binutils 2.44
\- [gcc 14.2.1](https://gcc.gnu.org/)
\- [glibc 2.41](http://www.gnu.org/software/libc/)
\- Java 24
<br>

###### Instalador
\- [Calamares 3.3.14](https://calamares.io)
<br>

###### Alguns aplicativos principais
\- LibreOffice Suite 25.2.3 com Qt 6 e integração com Plasma 6
\- Falkon 25.04.0
\- Chromium 135.0.7049.84 com spyware do Google desativado e suporte a JPEG-XL reativado
\- Firefox 137.0.2 com spyware desativado
\- QMPlay2 25.01.19
\- Telegram Desktop 5.13.1
\- Krita 5.2.9
\- Gimp 3.0.2
\- Digikam 8.6.0
\- SMPlayer 24.5.0
\- VLC 3.0.21
\- Virtualbox 7.1.8
\- VokoscreenNG 4.5.0
\- OBS Studio 31.0.3
<br>

### Ambientes de desktop alternativos
Os repositórios do sistema também incluem LXQt 2.2 Gnome 48.1, Mate 1.28, xfce 4.20.1, Cinnamon, icewm, i3, sway, hyprland, hypr, wayfire, budgie e outros.
<br>

###### Suporte para Flatpak
<br>

![header-tr-rome.svg](/assets/header-tr-rome.svg){.align-abstopright}