---
title: Errata e OpenMandriva Lx 4.2 Alpha
description: 
published: true
date: 2021-09-26T20:55:57.359Z
tags: 4.2
editor: markdown
dateCreated: 2020-02-27T16:13:04.324Z
---

# Errata e OpenMandriva Lx 4.2 Alpha - Çështje të Njohura
> Si me çdo publikim, ka ende çështje dhe gabime që mund të mos jenë zgjidhur. Kjo faqe dokumenton ato që mund të shkaktojnë shqetësime dhe ku është e mundur detajon se si ato mund të anashkalohen.
{.is-info}


**Është e rekomanduar që të lexoni** [shënimet e versionit](https://wiki.openmandriva.org/en/releases/omlx42/alpha/notes) **më të re në uikin tonë**.

## Kartat Grafike NVIDIA
Ky version përfshin drajverin nouveau të inxhinieruar në të kundërt, i cili ofron mbështetje mesatarisht të mirë për shumicën e kartave NVIDIA. Për disa punë me ekran të dyfishtë, është në fakt më i mirë se drajveri binar NVIDIA pasi mbështet rrotullimin e ekranit në një monitor të dytë, i dobishëm për monitorët me ekrane të rrotullueshme.
Përdoruesit mund të përdorin drajverë nga uebsajti i nvidia, por ata nuk mbështeten nga OpenMandriva. Këta nuk mund të mbështeten nga OpenMandriva për një numër arsyesh.
Instalimi dhe mirëmbajtja e çdo drajveri të patentuar nVidia është vetëm opsion dhe përgjegjësi e përdoruesit.

## SSD-të NVME
Ekziston një problem i njohur me disa SSD dhe pajisje PCIE NVME (veçanërisht më të reja) ku SSD mund të mos njihet. Për ISO-në tonë *Live* ekziston një zgjidhje alternative e përshkruar në [Shënimet e Versionit](/releases/omlx41/notes).
Problemi është i njohur dhe po punohet mbi të nga zhvilluesit e OpenMandriva dhe zhvilluesit e nivelit të lartë.
Njohja e harduerit për SSD-të nvme duhet të përmirësohet ndjeshëm.
Dihet që disa SSD nvme Samsung që nuk njiheshin më parë tani janë me këtë version kernel. Kjo çështje është sigurisht shumë specifik për harduerin.

Në sistemin e instaluar, përdoruesi mund të dëshirojë ta shtojë atë zgjidhje alternative në `/etc/default/grub` dhe të ekzekutojë `update-grub2` për ta bërë zgjidhjen alternative globale. Do të përdornit atë që gjetët për të funksionuar në ISO-në *Live*.

Nëse `(PCIE ASPM=OFF)` funksionoi për ju, atëherë shtoni:
`pcie=aspm=off`
në rreshtat:
`GRUB_DECLINE_LINUX_DEFAULT`
`GRUB_DECLINE_LINUX_RECOVERY`
në
`/etc/default/grub`
dhe pastaj ekzekutoni:
`$ sudo update-grub2`

Nëse `(NVME APST=OFF)` ka funksionuar, atëherë shtoni në vend të kësaj:
`nvme_core.default_ps_max_latency_us=0`

Si gjithmonë, përdoruesit inkurajohen të bëjnë pyetje për çdo gjë që nuk e kuptojnë në [forumin](https://forum.openmandriva.org/) tonë.

## GEOIP
Cilësimet automatike të GEOIP nga instaluesi mund të mos e caktojnë saktë zonën kohore.

## Si të konfiguroni printerin
Ndizni printerin dhe shikoni nëse është konfiguruar automatikisht. Kushtojini vëmendje nëse është instaluar drajveri i duhur. Nëse printeri është konfiguruar automatikisht dhe keni drajverin e duhur, atëherë gjithçka është në rregull.
Nëse nuk është, fikeni printerin. Hapni *Cilësimet e Printerit*, të njohura edhe si `system-config-printer`, dhe hiqeni printerin.
Nëse drajveri i saktë nuk është instaluar si parazgjedhje, do të na duhet të shtojmë një paketë softuerësh.

Hapi tjetër është të përcaktoni se cilin program duhet të shtoni për printerin tuaj.

Në OpenMandriva Lx kjo ka shumë të ngjarë të jetë një paketë 'printimi detyrash' specifike për markën e printerit tuaj. Paketat janë:
- task-printing-canon
- task-printing-epson
- task-printing-hp
- task-printing-lexmark
- task-printing-okidata
- task-printing-misc

Instaloni paketën që përputhet me markën tuaj ose paketën e ndryshme nëse asnjë nuk përputhet. Shembull duke përdorur okidata:
```
$ sudo dnf install task-printing-okidata
```
Tani ndizeni përsëri printerin dhe ai duhet të konfigurohet automatikisht (ndonjëherë mund t'ju duhet të rindizni që konfigurimi automatik të funksionojë).

Nëse jo, kërkoni ndihmë [këtu](https://forum.openmandriva.org/c/en/support)

## Discover
Lidhur me softuerët në depo, Discover mund të mos shfaqë të gjitha paketat e disponueshme.
Kjo ndodh për shkak se memoria e tij e përkohshme nuk pastrohet dhe lista e depove nuk merret në nisjen e parë.
Zgjidhja është: ekzekutoni komandat
```
$ sudo rm -rf /var/cache/PackageKit/* /var/cache/app-info/*
$ sudo pkcon refresh force
```
Nëse doni të eksploroni edhe paketa shtesë të depove, do t'ju duhet t'i aktivizoni ato me anë të [Software Repository Selector](/en/doc/repositories-tldr) dhe të rifreskoni përsëri memorien e përkohshme.

## Multiboot
Në 'botën reale', nisja e shumëfishtë funksionon mirë shumicën e kohës, por kur ka probleme, ndonjëherë zgjidhja është një rrugëdalje dhe jo një zgjidhje. Këto janë thjesht realitete të nisjes së shumëfishtë.

Gjithashtu, aktualisht nuk është e mundur që OpenMandriva QA të testojë ngarkuesin tonë të nisjes me çdo lloj sistemi skedarësh në çdo shpërndarje Linux, apo edhe në shpërndarjet "Top 10" Linux. Fakti është se, pavarësisht nëse nisja e shumëfishtë bëhet me Windows apo shpërndarje të tjera Linux, ne mbështetemi ekskluzivisht në raportet e përdoruesve për të ditur se çfarë funksionon dhe çfarë jo në lidhje me nisjen e shumëfishtë.

Një problem i njohur që haset me ngarkuesin e nisjes OM Lx është se OM Lx grub2 nuk krijon hyrje nisjeje për sistemet openSUSE që përdorin sistemin e skedarëve btrfs. OM Lx grub2 funksionon me sistemet openSUSE që përdorin sistemin e skedarëve ext4.
Kjo ndodh sepse openSUSE përdor sintaksë të personalizuar për patch-et e tyre btrfs për paketat openSUSE os-prober dhe grub2 që nuk janë të pajtueshme me kodin OM Lx. Aktualisht nuk dihet nëse ngarkuesi i nisjes OM Lx funksionon/nuk funksionon me openSUSE me ndonjë lloj tjetër sistemi skedarësh si XFS ose F2FS.

Zgjidhja është që përdoruesit të ndërrojnë ngarkuesit e nisjes në cilësimet e firmware-it UEFI ose BIOS.
Alternativa mund të jetë përdorimi i ngarkuesit të nisjes openSUSE nëse ai e njeh sistemin tuaj OpenMandriva.
Ndërsa përdoruesit raportojnë probleme me nisje të shumëfishta, ne do të rregullojmë atë që jemi në gjendje të bëjmë. Problemet që nuk jemi në gjendje t'i rregullojmë do t'i raportojmë në Errata për Versionet tona OM Lx.

## Probleme të njohura mbi të cilat po punohet aktualisht

Sistemi ynë i gjurmimit të defekteve ka hasur disa probleme, prandaj po kërkojmë që raportet e reja të defekteve të paraqiten në [Forumin](https://forum.openmandriva.org/) tonë ose në [Github Issues](https://github.com/OpenMandrivaAssociation/OpenMandrivaAssociation.github.io/issues)

Gabimet e paraqitura në OpenMandriva Issue Tracker:

- [Cooker Host: VM-të VirtualBox 6.1.12 nuk ndizen](https://issues.openmandriva.org/show_bug.cgi?id=2634)

- [Rrëzim i desktopit plasma VBox (virtualbox-guest-additions)](https://issues.openmandriva.org/show_bug.cgi?id=2633)

- [Tingulli i hyrjes nuk luhet (ose nuk luhet saktë) Plasma 5.19.3, KF 5.72.0](https://issues.openmandriva.org/show_bug.cgi?id=2629)

- [Ndryshimet në pikën e montimit në KDE Partition Manager nuk shkruhen në /etc/fstab (TË GJITHA versionet e OM Lx)](https://issues.openmandriva.org/show_bug.cgi?id=2628)

- [OM-Control-Center nuk funksionon me Wayland (Cooker)](https://issues.openmandriva.org/show_bug.cgi?id=2625)

- [Përditësimi i një kerneli dege në një kernel dege tjetër me të njëjtin numër versioni dështon] (https://issues.openmandriva.org/show_bug.cgi?id=2619)

- [grub2-editor (kcm_grub2) "Ruajtja e cilësimeve të GRUB dështoi." Gabim në backend-in e DBus. (TË GJITHA versionet e OM Lx)](https://issues.openmandriva.org/show_bug.cgi?id=2618)

- [Samba nuk funksionon](https://issues.openmandriva.org/show_bug.cgi?id=2609)

Gabimet e paraqitura në Github Issues:

- [Përdoruesi duhet të fusë fjalëkalimin dy herë për wifi (apleti NM i prishur) #53](https://github.com/OpenMandrivaAssociation/OpenMandrivaAssociation.github.io/issues/53)


