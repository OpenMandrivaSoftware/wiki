---
title: Известные проблемы и ошибки OpenMandriva Lx 4.3
description: 
published: true
date: 2022-10-13T22:30:54.262Z
tags: 4.3
editor: markdown
dateCreated: 2021-04-24T05:21:24.743Z
---

# Список ошибок OpenMandriva Lx 4.3 - Известные проблемы

> Как и в любом выпуске, в этой версии могут оставаться нерешённые проблемы и ошибки. На этой странице перечислены проблемы, которые могут вызвать неудобства, а также, по возможности, описаны способы их обхода.
{.is-info}

Как и в любом выпуске, в этой версии могут оставаться нерешённые проблемы и ошибки.
На этой странице перечислены проблемы, которые могут вызвать неудобства, а также, по возможности,
описаны способы их обхода.
<br />

## Известные проблемы и способы их обхода
<br />

### Видеокарты NVIDIA

В этот выпуск включён драйвер nouveau, разработанный методом реверс-инжиниринга и обеспечивающий неплохую
поддержку большинства видеокарт NVIDIA. При работе с двумя экранами он в некоторых случаях даже лучше
проприетарного драйвера NVIDIA, поскольку поддерживает поворот изображения на втором мониторе, что полезно для
мониторов с поворотным экраном.
Пользователи могут использовать драйверы с сайта NVIDIA, но команда OpenMandriva их не поддерживает.
По ряду причин команда OpenMandriva не может обеспечивать их поддержку.
Установка и обслуживание любых проприетарных драйверов NVIDIA — исключительно личный выбор и
ответственность пользователей. 
Драйверы NVIDIA, поддерживаемые сообществом, доступны в репозитории non-free.
<br />
### SSD NVMe

Существует известная проблема с некоторыми (особенно новыми) SSD NVMe и устройствами PCIe,
из-за которой SSD может не распознаваться системой.
Проблема известна, и над её устранением работают разработчики OpenMandriva и вышестоящих
проектов.
В OMLx 4.3 распознавание SSD NVMe значительно улучшено.
Эта проблема, разумеется, во многом зависит от конкретного оборудования.

После установки системы можно добавить этот обходной способ в файл /etc/default/grub и
выполнить update-grub2, чтобы настройка применялась при каждой загрузке. Используйте тот вариант, который
успешно работал при загрузке Live ISO.
Если вам помог параметр (PCIE ASPM=OFF), добавьте:
`pcie=aspm=off`
в строки:
`GRUB_DECLINE_LINUX_DEFAULT`
`GRUB_DECLINE_LINUX_RECOVERY`
файла
`/etc/default/grub`
затем выполните:
`$ sudo update-grub2`

Если вам помог параметр (NVME APST=OFF), вместо него добавьте:
`nvme_core.default_ps_max_latency_us=0`

Как всегда, если вам что-то непонятно, не стесняйтесь задавать вопросы на нашем [форуме](https://forum.openmandriva.org/).
<br />

### GEOIP

Автоматическое определение местоположения по GEOIP в установщике может неправильно установить часовой пояс.
<br />

### Как настроить принтер

Включите принтер и проверьте, настроился ли он автоматически. Обратите внимание,
правильный ли драйвер был установлен. Если принтер настроился автоматически и драйвер
подобран правильно, всё готово к работе.
Если автоматическая настройка не произошла, выключите принтер. Откройте «Параметры системы» > «Оборудование» > «Принтеры» или выполните команду `kcmshell5 kcm_printer_manager`
и удалите принтер из списка.
Если нужный драйвер не был установлен по умолчанию, потребуется установить дополнительный пакет.
Следующий шаг — определить, какой пакет необходим для вашего принтера.
В OpenMandriva Lx это, скорее всего, будет пакет 'task-printing', соответствующий
производителю вашего принтера. Доступны следующие пакеты:
•task-printing-canon
•task-printing-epson
•task-printing-hp
•task-printing-lexmark
•task-printing-okidata
•task-printing-misc
Установите пакет для вашего производителя. Если подходящего нет, используйте task-printing-misc. Например,
для принтера Okidata выполните:
$ sudo dnf install task-printing-okidata
Теперь снова включите принтер. Он должен настроиться автоматически (иногда для
автоматической настройки требуется перезагрузка системы). Если этого не произошло, настройте принтер вручную через «Параметры системы» > «Оборудование» > «Принтеры» или с помощью команды `kcmshell5 kcm_printer_manager`.
Если проблема сохраняется, обратитесь за помощью [сюда](https://forum.openmandriva.org/c/en/support).
<br />

### Поиск новых программ

Если вы хотите просматривать пакеты из дополнительных репозиториев, сначала необходимо включить их
с помощью Software Repository Selector и обновить кеш.
<br />

### Мультизагрузка

На практике мультизагрузка в большинстве случаев работает нормально, однако при возникновении проблем
иногда приходится использовать обходные решения вместо полноценного исправления. Таковы особенности
мультизагрузки.
Кроме того, в настоящее время команда OpenMandriva QA не имеет возможности проверить совместимость нашего загрузчика со всеми
типами файловых систем во всех дистрибутивах Linux, даже если ограничиться "Топ-10". Поэтому
при использовании мультизагрузки с Windows или другими дистрибутивами Linux мы полностью полагаемся на сообщения
пользователей, чтобы понимать, какие конфигурации работают, а какие вызывают проблемы.
Одна из известных проблем загрузчика OMLx заключается в том, что OpenMandriva grub2 не
создаёт загрузочные записи для систем openSUSE, использующих файловую систему btrfs. При этом OMLx grub2
корректно работает с системами openSUSE, использующими ext4.
Причина заключается в том, что openSUSE использует собственный синтаксис в исправлениях для поддержки btrfs в пакетах os-
prober и grub2, несовместимый с кодом OMLx. В настоящее время
неизвестно, работает ли загрузчик OMLx с openSUSE при использовании других файловых систем,
таких как XFS или F2FS.
В качестве обходного решения пользователи могут переключать загрузчики в настройках UEFI или BIOS.
Другой вариант — использовать загрузчик openSUSE, если он обнаруживает установленную систему OpenMandriva.
По мере поступления сообщений от пользователей мы будем исправлять проблемы мультизагрузки, которые сможем устранить. Проблемы, которые нам не удастся исправить,
будут перечислены в разделе известных проблем и ошибок соответствующих выпусков OMLx.
<br />

### Звуковой сервер PipeWire

У некоторых пользователей могут возникнуть проблемы с новым звуковым сервером PipeWire. В таком случае можно вернуться к прежнему звуковому серверу PulseAudio. Для этого откройте Konsole, скопируйте и выполните следующую команду:

`$ sudo dnf remove pipewire-pulse ; sudo dnf install pulseaudio-server`
<br />

### Обновление Firefox

Стабильный выпуск OpenMandriva, также известный как Rock, обычно не получает обновлений системных пакетов и инструментов разработки. Из-за этого, а также особенностей разработки Firefox компанией Mozilla, иногда новые версии Firefox перестают собираться для нашего стабильного выпуска.

Пользователи, которым необходима последняя версия Firefox, могут в качестве обходного решения установить с сайта [mozilla.org](https://www.mozilla.org/) актуальную версию Firefox RR (Rapid Release) или с сайта [mozilla.org](https://support.mozilla.org/en-US/kb/switch-to-firefox-extended-support-release-esr) последнюю версию Firefox ESR (Extended Support Release), которая получает все обновления безопасности, но не обновления функциональности.
<br />

### Zypper

The package zypper-needs-restarting may conflict with dnf-utils if installed.
As a workaround remove dnf-utils.
<br />

### Bluetooth

For bluetooth devices user may need to enable systemd bluetooth.service. Open Konsole
and run:

`$ sudo systemctl start bluetooth ; sudo systemctl enable bluetooth`
<br />

## What to do if I have a problem

Should you have problems please report in the [English Support forum](https://forum.openmandriva.org/c/en/support) with a descriptive title and enough of a description and information for someone to be able to help you. If your issue is a serious technical issue then please [file a bug report](https://github.com/OpenMandrivaAssociation/distribution/issues).
<br />

## Helping the project

The OpenMandriva development teams (Cooker & QA) are always looking for new
contributors to assist in creating and maintaining packages and to assist bugfixing and
testing. You are welcome to join us and help us in this work which is not only rewarding but
also tremendous fun!
If you feel that your talents do not lie in the realm of software, then the OpenMandriva
Workshop group, which is made up from the artwork, documentation, translation and
Communication teams, is always open for the submissions of artwork and translations.
New contributors who would like to help with these wide-ranging tasks should see the wiki
for more details, and to learn how to join! Alternatively you may use our [forum](https://forum.openmandriva.org).
It also costs time and money to keep our servers up and running. If you can, please [donate](https://www.openmandriva.org/en/Donate)
to keep the lights on!
<br />

**Please read also**
[OMLx 4.3 Release Notes](https://wiki.openmandriva.org/en/distribution/releases/omlx43/notes)
<br>
