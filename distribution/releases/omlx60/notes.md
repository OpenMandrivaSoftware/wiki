---
title: OpenMandriva Lx 6.0 Release Notes
description: 
published: true
date: 2025-06-18T20:52:09.904Z
tags: 6.0
editor: markdown
dateCreated: 2025-03-10T19:02:54.601Z
---

# OpenMandriva Lx 6.0 Release Notes

The OpenMandriva teams are pleased to announce the availability of **OpenMandriva Lx 6.0 Rock** edition.
<br>

## Available Media
This release is available as a live media USB flash drive (memory stick), downloadable in ISO format.
These are available on our [downloads](https://www.openmandriva.org/release-picking) page.
USB flash drive installation is usually noticeably fast. As always speed depends on many factors.
Live media means you are able to run OpenMandriva Lx straight from a memory stick (see below) and try it before installing it.
You may also install the system to hard disk either from the running live image or from the boot manager.

**Available ISO files:**
- *x86_64 KDE Plasma desktop* full featured (includes the most common used functionalities, multimedia and office software).
- *znver1 KDE Plasma desktop*: is for AMD CPUs (newer than 2017), notably for current AMD processors (Ryzen, ThreadRipper, EPYC), that outperforms the generic (x86_64) version by taking advantage of new features in those processors. znver1 is for the listed processors (Ryzen, ThreadRipper, EPYC)  only, do not install on any other hardware.

<!--Installable images are offered for the Pinebook Pro, Raspberry Pi 4B, Raspberry Pi 3B+, Synquacer, Cubox Pulse and generic UEFI compatible devices (such as most aarch64 server boards)-->
<br>

## System requirements
OpenMandriva 6.0 requires at least 2048 MB of memory and at least 10 GB of hard drive space (see below for known issues with partitioning). 20 GB recommended for a Plasma desktop full installation.

*Graphics Hardware:*
The KDE Plasma Desktop requires a 3D graphics card that supports OpenGL 2.0 or above. We recommend using AMD, Intel, Adreno or VC4 graphics chips.
<br>

## Internet Connection
Calamares Installer checks if an Internet connection is available, but OpenMandriva 6.0 will install just fine even without. It is perfectly OK to simply install as you normally would and proceed to use your new system as normal. Updating such a system would require being temporarily connected to the internet or downloading the packages elsewhere and transferring them to the installed system and installing the updated packages. But as you are not connected to the internet you could simply use the system and not update for how ever long you see fit.
<br>

## Virtual Machines
At this time the only virtualization software that OpenMandriva 6.0 ISOs are tested on is qemu and VirtualBox. The same hardware requirements apply when running in virtual machines. For VirtualBox you must always have at least 2048 MB of memory or OpenMandriva 6.0 will fail to boot. Also for VirtualBox it is advisable to install to a fresh virtual machine, as trying to install to an existing one may occasionally fail.
The most recent install images may need setting VMSVGA graphics controller to display correctly and properly boot in VirtualBox.
<br>

## Calamares installer
Calamares is an installer framework. By design it is very customizable in order to satisfy a wide variety of needs and use cases. It aims to be easy, usable, beautiful, pragmatic, inclusive and distribution-agnostic. Calamares includes an advanced partitioning feature, with support for both manual and automated partitioning operations. It is the first installer with an automated “Replace Partition” option, which makes it easy to reuse a partition over and over for distribution testing. Many Linux distros use Calamares installer and each has its own implementation and standards. The user may notice some small differences but it does not mean this is a bug.
<br>

## Partitioning
At this time partitioning LVM and Raid setups with Calamares installer are not supported.

The following applies to all partitioning of all installations on hardware: If you have a UEFI/EFI computer and your BIOS offers a choice when you boot installation media between for example:

`USB some Flash Drive`
`UEFI USB some Flash Drive`


You have to choose the UEFI option and boot that. But know also that not all computers will do this. Some with more spartan FIRMWARE or BIOS will offer only the one option and almost always it is the correct one. So for instance if on a notebook you don't see the above choice no worries. *If you have multiple storage drives enabled they all need to have the same partition table type.* They either need to all be GPT or all MBR for everything to work properly. On UEFI computers in multi-boot situation with multiple storage drives if you already have an existing `/boot/efi` partition you should use that. The partitioner will not create another `/boot/efi` with proper flags and installation will result in error with no bootloader installed. Do not format you just set the mount point to `/boot/efi` and  select the `boot` flag. One can have many different boot loaders for different operating systems in the same `/boot/efi` partition. If there is any need to switch boot loaders that is done in FIRMWARE or BIOS settings.
<br>

## File system type
In the Calamares installer for OpenMandriva 6.0 the file system list includes all file systems the operating system recognizes for a host of reasons. This does not mean one should use anything in the list for your root ( `/` ) partition. `ext4` is the official recommendation for root, `fat32` is the recommendation for `boot/efi`. 

`btrfs`, `f2fs` and `xfs` are working in recent tests but these are much less often tested. We rely on user feedback for this. Based on recent testing `btrfs` is not a good choice for multi-boot scenario.

**Other files system types in the list are not recommended.**

No official recommendation is made at this time for storage partitions or for a seperate `/home` partition. It is expected the users using seperate storage partitions or a seperate `/home` partition know what they are doing. For `/home` the easy way is to use `ext4` (recommended) or whatever you use for your root partition. 
<br>

## Changing Partition Type
Please note that Calamares cannot convert one partition type to another and preserve partition data.
Also, Calamares does not support reading or creating ZFS due to licensing.

> If you run Calamares to change an existing partition type you must first delete the partition and recreate it as the type that you wish.
{.is-danger}

<br>

## NVME SSDs
NVME SSDs are normally recognized by OpenMandriva Live ISO. If for some reason they are not we have couple of workarounds under 'Troubleshooting' in the ISO Grub2 Menu that may work. They are (PCIE ASPM=OFF) and (NVME APST=OFF). We hope this works for most peoples hardware. See more in Errata/NVME SSDs. This issue is of course very hardware specific. 
<br>

## Installer and EFI Support
This release of OpenMandriva 6.0 supports booting and installation with and without UEFI.

*Note that secure boot is NOT supported.*
*Note it is NOT recommended to mix MBR and GPT partitions.* 

If you wish to perform an EFI installation on an existing MBR disk it will be necessary to convert the disk partition table to the newer GPT partitioning scheme. To do this you need to use the gdisk tool. A typical invocation would be gdisk /dev/sda: the existing partition table will be converted in memory to the GPT scheme. Warnings will be issued about potential data loss, the disk will not be altered until you write the partition table by pressing w. You are advised to back up any important data.

There may be occasions where the conversion cannot be performed, this will usually be due to insufficient space at the beginning or end of the disk to write the partition table. It may be necessary to delete or resize a partition to create the needed space, gparted is your friend in these circumstances.

There is still a need to create a `/boot/efi` partition to contain the boot equipment and this must be created while running the Calamares installer. When the installer reaches the partitioning stage the `/` (root) partition should be removed and a small (300 MB) fat32 partition created at the start of the drive. The partition must be named `/boot/efi` and the `boot` flag set. If diskspace is critical then a smaller partition may be used, but be sure to set it as fat32 in Calamares otherwise the installation will fail. If you fail to observe these steps the installation of the boot loader will fail. Subsequently partition the disk in the normal way.

Please share your experiences on the forums so that we may improve this aspect of the installation.

If you are installing beside Windows 8, 8.1, 10 or similar EFI booted OS as a precaution please ensure that you have recovery disks and you have backed up any important data. Our testing has been limited with this configuration, but successful installations have been performed with no issues.
We would welcome any feedback in this area.
<br>

## Booting from USB
It is possible to boot this release from a USB storage device. To create the live/installation media you may:

- Use isowriter tool available from our repos:

`sudo dnf --refresh install om-imagewriter`

At least 4 GB of flash drive capacity is recommended. Persistent storage is not necessary. Note that this will erase everything on your USB!

> **Windows users**:
If you use other usb-writing tools as some Windows tools (e.g. [Rufus](https://rufus.ie/en)) you must select the '`dd`' mode otherwise it will truncate the volume name and break the boot process.
Balena Etcher is reported as working fine to transfer OpenMandriva ISO images to USB storage device.
{.is-danger}

- Via dd
You may alternatively dd the image to your USB stick:

`sudo dd if=<iso_name> of=<usb_drive> bs=4M conv=fdatasync status=progress`

Replace <iso_name> with the path to the ISO and <usb_drive> with the device node of the USB drive, i.e. /dev/sdb.

- SUSE Studio ImageWriter and Balena Etcher have also been tested and work to transfer ISO images to USB storage device.

- Ventoy is not fully supported. Under some circumstances it may or may not work. Please create the live/installation media choosing one among the suggested methods here above. See [OMLx 6.0 Errata](/distribution/releases/omlx60/errata) for Ventoy workarounds.
<br>

## Installing from USB
Once you have created your USB drive turn off the computer, plug it to the USB port and restart.

> You may need to disconnect/unplug any secondary monitors to be able to reach the login screen.
{.is-warning}


If your computer supports starting from USB, choose the device from which to boot your computer.
To do so, you want to interrupt the normal startup process and access the BIOS menu presented by immediately pressing the key which often is mentioned in the message after the computer starts.
Usually the correct key is `Esc`, `Del`, `F12`, `F10`, `F9` `F8`, or similar.
If you are uncertain do an internet search for what your hardware will require.

When you see the menu, select the entry matching your USB drive.
Among others, you will see entries along the lines of

`USB some Flash Drive`
`UEFI USB some Flash Drive`

If you have a UEFI/EFI computer be sure to select the one mentioning 'UEFI' and boot that, otherwise the Calamares installer will present only legacy bios options for installation.
<br>

## Booting from DVD
Booting from DVD is deprecated, still OpenMandriva 6.0 ISOs boot from DVD using Legacy or UEFI boot. Should you encounter difficulties there are 2 workarounds [here](https://forum.openmandriva.org/t/4377) that should enable one to boot from DVD. In testing booting OpenMandriva 6.0 from DVD took 5-6 minutes. This may take longer on some hardware. Using a DVD for this purpose is a lot slower than using a USB flash drive.
<br>

## About Repositories
We have [om-repo-picker](/policies/repositories-tldr) aka Software Repository Selector to select additional repositories for more package availability.
**Do not mix the repositories from different release versions/update channels**. This means, as an example, do not use Cooker repositories on a Rock system. If you use Rock, use Rock repositories only. This is explained in more detail in [OpenMandriva Release Plan and Repositories](/policies/release-plan-and-repositories). If you mix different release/update channel repositories and you break your computer the solution is to do a fresh install. After that fresh install do not do this again.
<br>

## How to install and remove packages
While graphical tools (Discover, dnfdragora, etc.) are useful to find out available extra software, we recommend users to install and remove packages from command line:

`sudo dnf --refresh install <package_name>`

To remove a package:

`sudo dnf remove <package_name>`

One may in install or remove a string of packages. Example:

`sudo dnf --refresh install <package_name_1> <package_name_2> <package_name_3> <package_name_4>`

More about package management with dnf [here](https://dnf.readthedocs.io/en/latest/command_ref.html).
<br>

## Recommended update procedure

This is very easy, just copy and paste this command string:

`sudo dnf clean all ; dnf clean all ; sudo dnf distro-sync --allowerasing --refresh`

Then press Enter key and when prompted enter your root (superuser) password.
We recommend it because we see a lot of problem reports that begin with "*I updated my system with Discover updater*" or "I *updated my system with dnfdragora*". 
<br>


## Default sound server switched to Pipewire
[*Pipewire*](https://pipewire.org/) has become our default sound server in the current system release together with WirePlumber, thus replacing PulseAudio.
However, PulseAudio is still in our repository and you can return to it at any time. To do that use this command string:

`sudo dnf rm pipewire-pulse ; sudo dnf in pulseaudio-server`

<br>

## Clang compiled kernel
The standard kernel for OpenMandriva 6.0 is clang compiled.
There are kernel-desktop-gcc and kernel-server-gcc versions available in the rare instance they are needed.
<br>

## Nvidia Graphic hardware
This is discussed in OpenMandriva 6.0 Errata page
<br>

## What to do if I have a problem
Should you have problems please report in the [English Support forum](https://forum.openmandriva.org/c/support/17) with a descriptive title and enough description and information for someone to be able to help you. Or for possible faster results contact us at [OpenMandriva Chat](/team/chat) . If your issue is a serious technical issue then please [file a bug report](https://github.com/OpenMandrivaAssociation/distribution/issues).
<br>

## What's New
See [OMLx 6.0 New](/distribution/releases/omlx60/new)
<br>

## Errata
See [OMLx 6.0 Errata](/distribution/releases/omlx60/errata)
<br>

## Helping the project
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}The OpenMandriva development teams (Cooker & QA) are always looking for new contributors to assist in creating and maintaining packages and to assist bugfixing and testing. You are welcome to join us and help us in this work which is not only rewarding but also tremendous fun! If you feel that your talents do not lie in the realm of software, then the OpenMandriva Workshop group, which is made up from the artwork, documentation, translation and Communication teams, is always open for the submissions of artwork and translations. New contributors who would like to help with these wide-ranging tasks should see the wiki for more details, and to learn how to join! Alternatively you may use our [forum](https://forum.openmandriva.org).
<br>

## Donate to the project
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}It also costs time and money to keep our servers up and running. If you can, please [donate](https://www.openmandriva.org/Donate) to keep the lights on!
<br>

![header-tr-60.svg](/assets/header-tr-60.svg){.align-abstopright}
