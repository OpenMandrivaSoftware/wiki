---
title: Notes tl;dr
description: OMLx 4.1 Notes tl;dr
published: true
date: 2021-09-26T21:00:58.458Z
tags: releases, 4.1
editor: markdown
dateCreated: 2020-06-13T07:46:23.080Z
---

# OMLx 4.1 Notes tl;dr

> **It is recommended that you read the extended version of** [OpenMandriva Lx 4.1 Release Notes](/releases/omlx41/notes) **as well as the** [OpenMandriva Lx 4.1 Errata](/releases/omlx41/errata) **at our wiki**
{.is-info}


## Available Media
This release is available as a live media DVD or USB flash drive (memory stick), downloadable in ISO format.
*Live media* means you are able to run OpenMandriva Lx straight from a DVD or memory stick and try it before installing it.

##  Recommended Hardware
OpenMandriva Lx requires at least 2.0 GB of memory and at least 10 GB of hard drive space.

## Internet Connection
Calamares Installer checks if an Internet connection is available, but OpenMandriva Lx will install just fine even without. Simply install as you normally would and proceed to use your new system as normal.

## Virtual Machines
At this time the only virtualization software that OMLx ISOs are tested on is VirtualBox. The same hardware requirements apply when running in virtual machines.
For VirtualBox however you must always have at least 2048 MB of memory or the system will fail to boot.

## Installer and EFI Support
This release of OpenMandriva Lx supports booting and installation with and without UEFI.
Note that secure boot is not supported.

## Recommended file system type for manual installation
Strongly recommended is ext4 file system type. For flash memory-based storage devices we make available F2FS.
Please note that Calamares cannot convert one partition type to another and preserve partition data.
If you run Calamares from the live image it is not possible to change an existing partition type. You will need to first delete the partition and recreate it as the type that you wish.

## Booting from USB
To transfer the live/installation image you may use *ROSA Image Writer* or via *dd*.
- ROSA Image Writer is available in our repos
 `sudo dnf --refresh install rosa-imagewriter`
 or you can get it [here](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter)
 
- You may alternatively dd the image to your USB stick:
 `sudo dd if=<iso_name> of=<usb_drive> bs=4M`
 Replace `<iso_name>` with the path to the ISO and `<usb_drive>` with the device node of the USB drive, i.e. `/dev/sdb`.

*SUSE Studio ImageWriter also has been tested and works for burning ISO images to USB storage device.*

> Please do not use other usb-writing tools as some Windows tools (e.g. Rufus) truncate the volume name. This breaks the boot process.
{.is-danger}

## OpenMandriva repositories and software availability
**OMLx installed operating systems have just the /main repository enabled by default.**
For maximum availability of all software you will need to enable additional repositories called *unsupported*, *restricted*, and *non-free*.
Use the graphical utility [Software Repository Selector](https://wiki.openmandriva.org/en/doc/repositories-tldr) (om-repo-picker) to enable or disable the repo you wish to use.

While graphical tools (Discover, dnfdragora, etc.) are useful to find out available extra software, we strongly suggest to install packages from command line
 `sudo dnf --refresh install <package_name>`
 
\-
 

 
 