---
title: OpenMandriva Lx 4.2 Beta Release Notes
description: 
published: true
date: 2021-09-26T20:57:22.085Z
tags: 4.2
editor: markdown
dateCreated: 2020-03-07T17:10:54.689Z
---

# OpenMandriva Lx 4.2 Beta Release Notes

> Warning: This is a [beta](/releases/software-release-life-cycle#beta) product, and it is not aimed to be used in a production environment. It is released for testing and bug hunting. It can, and probably will, have problems. If you download and test this product, please report your findings and problems in the [Forum](http://forum.openmandriva.org/) and in our [issue tracking system](http://issues.openmandriva.org/).
{.is-warning}


## Available Media
This release is available as a live media DVD or USB flash drive (memory stick), downloadable in ISO format. These are available on our [downloads page](https://www.openmandriva.org/en/download). USB flash drive installation is usually noticeably faster. As always speed depends on many factors.
*Live media* means you are able to run OpenMandriva Lx straight from a DVD or memory stick (see below) and try it before installing it. You may also install the system to hard disk either from the running live image or from the boot manager.

Available ISO files are:
- x86_64 [KDE Plasma](https://www.kde.org/plasma-desktop) desktop full featured (includes the most common used functionalities, multimedia and office software).
- znver1 Plasma: we have also built a version specifically for current AMD processors (Ryzen, ThreadRipper, EPYC) that outperforms the generic (x86_64) version by taking advantage of new features in those processors.
znver1 is for the listed processors (Ryzen, ThreadRipper, EPYC) only, do not install on any other hardware.

## System requirements

OpenMandriva Lx 4.2 requires at least 2048 MB of memory and at least 10 GB of hard drive space (see below for known issues with partitioning).

> Important Note: Graphics Hardware: 
> The KDE Plasma Desktop requires a 3D graphics card that supports OpenGL 2.0 or above.
> We recommend using AMD, Intel, Adreno or VC4 graphics chips.
{.is-warning}

## Internet Connection

Calamares Installer checks if an Internet connection is available, but OpenMandriva Lx 4 will install just fine even without. It is perfectly OK to simply install as you normally would and proceed to use your new system as normal. 
Updating such a system would require being temporarily connected to the internet or downloading the packages elsewhere and transferring them to the installed system and installing the updated packages. But as you are not connected to the internet you could simply use the system and not update for how ever long you see fit.

## Virtual Machines
At this time the only virtualization software that OMLx ISOs are tested on is VirtualBox. The same hardware requirements apply when running in virtual machines.
For VirtualBox you must **always** have at least 2048 MB of memory or OpenMandriva Lx will fail to boot.
Also for VirtualBox it is advisable to install to a fresh virtual machine, as trying to install to an existing one may occasionally fail.

## Calamares installer

Calamares is an installer framework.
By design it is very customizable, in order to satisfy a wide variety of needs and use cases. It aims to be easy, usable, beautiful, pragmatic, inclusive and distribution-agnostic.
Calamares includes an advanced partitioning feature, with support for both manual and automated partitioning operations. 
It is the first installer with an automated “Replace Partition” option, which makes it easy to reuse a partition over and over for distribution testing.
Many Linux distros use Calamares installer and each has it's own implementation and standards. The fact that something about OpenMandriva installer does not conform to user experience with another Linux distro does not mean this is a bug.

## Partitioning

At this time partitioning LVM and Raid setups with Calamares installer are not supported.
**This applies to all partitioning**, all installation on hardware: If you have a UEFI/EFI computer and your BIOS offers a choice when you boot installation media between for example:

`USB some Flash Drive`
`UEFI USB some Flash Drive`
or 
`some DVD optical_device`
`UEFI some DVD optical_device`

You have to choose the UEFI option and boot that. But know also that not all computers will do this. Some with more spartan BIOS will offer only the one option and almost always it is the correct one. So for instance if on a notebook you don't see the above choice no worries.
If you have multiple storage drives enabled they all need to have the same partition table type. They either need to all be gpt or all mbr for everything to work properly. 
On UEFI computers in multi-boot situation with multiple storage drives if you already have an existing `/boot/efi` partition you have to use that. The partitioner will not create another `/boot/efi` with proper flags and installation will result in error with no bootloader installed. Do not format you just set the mount point to `/boot/efi`. One can have many different boot loaders for different operating systems in the same `/boot/efi` partition. If there is any need to switch boot loaders that is done in BIOS settings.

## NVME SSDs

Some NVME SSDs may not be recognized by OMLx 4.2 *Live* ISO.
The *Live* ISO has 2 different workarounds for this under "Troubleshooting" in the Grub2 Menu. They are `(PCIE ASPM=OFF)` and `(NVME APST=OFF)`. We hope this works for most peoples hardware. Problem is known and being worked on by OpenMandriva developers and upstream developers. See more in [4.2/Errata#NVME SSDs](/en/releases/omlx42/beta/errata#nvme-ssds).
Hardware recognition for nvme SSDs should be considerably improved. It is known that some Samsung nvme SSDs that were not previously recognized are now with this kernel version. This issue is of course very hardware specific.

## Installer and EFI Support

This release of OpenMandriva Lx supports booting and installation with and without [UEFI](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface).
Note that secure boot is NOT supported.
If you wish to perform an EFI installation on an existing MBR disk it will be necessary to convert the disk partition table to the newer GPT partitioning scheme. To do this you need to use the gdisk tool. A typical invocation would be `gdisk /dev/sda`: the existing partition table will be converted in memory to the GPT scheme. Warnings will be issued about potential data loss, the disk will not be altered until you write the partition table by pressing <kbd>w</kbd>. You are advised to back up any important data.
There may be occasions where the conversion cannot be performed, this will usually be due to insufficient space at the beginning or end of the disk to write the partition table. It may be necessary to delete or resize a partition to create the needed space, gparted is your friend in these circumstances.  
There is still a need to create an efi partition to contain the boot equipment and this must be created while running the Calamares installer. When the installer reaches the partitioning stage the `/` (root) partition should be removed and a small (330 MB) FAT16 or FAT32 partition created at the start of the drive. If diskspace is critical then a smaller partition may be used, but be sure to set it as FAT16 or FAT32 in Calamares otherwise the installation will fail.
If you fail to observe these steps the installation of the boot loader will fail. Subsequently partition the disk in the normal way.
Please share your experiences on the forums so that we may improve this aspect of the installation.
If you are installing beside Windows 8, 8.1, 10 or similar EFI booted OS as a precaution please ensure that you have recovery disks and you have backed up any important data. 
Our testing has been limited with this configuration, but successful installations have been performed with no issues.
We would welcome any feedback in this area.

## Changing Partition Type

Please note that Calamares cannot convert one partition type to another and preserve partition data.
If you run Calamares from the live image it is not possible to change an existing partition type. Trying to do this generates an error message. 
In order to do this you must first delete the partition and recreate it as the type that you wish.

## Booting from USB

It is also possible to boot this release from an USB storage device. To transfer the live/installation image you may:

### - Use the ROSA Image Writer available from our repos

`sudo dnf --refresh install rosa-imagewriter`

Or, if you do not have OpenMandriva Lx yet, you can get ROSA Image Writer download links at [this page](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter)
At least 4 GB of flash drive capacity is recommended. Persistent storage is not necessary. Note that this **will erase** everything on your USB!

> Please do not use other usb-writing tools as some Windows tools (e.g. Rufus) truncate the volume name. This breaks the boot process.
{.is-danger}

### - Via dd

You may alternatively dd the image to your USB stick:
`$ sudo dd if=<iso_name> of=<usb_drive> bs=4M status=progress conf=fsync`

Replace `<iso_name>` with the path to the ISO and `<usb_drive>` with the device node of the USB drive, i.e. `/dev/sdb`.

SUSE Studio ImageWriter has also been tested and works for burning ISO images to USB storage device.

## Booting from ISO file

Grub2 entry, to be added in `/boot/grub2/grub.cfg`
```
submenu "OpenMandriva (64 bit)" {
        set isofile=/home/user/OpenMandrivaLx.4.2-plasma.x86_64.iso
        set isoname=OpenMandrivaLx_4.2
        loopback loop $isofile
        
        menuentry "OpenMandriva" {
                linux (loop)/boot/vmlinuz0 root=live:LABEL=${isoname} iso-scan/filename=${isofile} rd.live.image toram --
                initrd (loop)/boot/liveinitrd.img
        }
}
```

## About Repositories

We have now the [om-repo-picker](/images/omlx4.1-repo-picker.jpg) aka Software Repository Selector to select additional repositories for more package availability.
Do not mix the repositories from different release versions/update channels. This means, as an example, **do not use Cooker repositories on a Rock system**. If you use Rock, use Rock repositories only.
This is explained in more detail in [OpenMandriva Release Plan and Repositories](/doc/release-plan-and-repositories). 
**If you mix different release/update channel repositories and you break your computer the solution is to do a fresh install**. After that fresh install do not do this again.

## How to install new packages
While graphical tools (Discover, dnfdragora, etc.) are useful to find out available extra software, we strongly suggest to install packages from command line:
`$ sudo dnf --refresh install <package_name>`

## How to update the system
Please note development releases ’Update channel’ is set to Rolling by default.
The best adviced command to upgrade Rolling system is:
`$ sudo dnf clean all ; sudo dnf --allowerasing distro-sync`

## New Features and Major Changes

In order to keep current with latest changes in Linux, computer security issues, and computer code writing there are major changes in OMLx 4.2.

Major changes:
- The kernel has been updated to 5.10.2
- Qt has been updated to 5.15.2
- Plasma has been updated: Frameworks 5.77.0, Plasma Desktop 5.20.4, Applications 20.12.0
- *Read more in* [What's New](/en/releases/omlx42/new)


# Errata
See [4.2/Beta/Errata](/en/releases/omlx42/beta/errata).

