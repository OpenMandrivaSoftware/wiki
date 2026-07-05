---
title: Mirroring
description: 
published: true
date: 2025-02-02T13:22:44.309Z
tags: documentation
editor: markdown
dateCreated: 2020-03-14T19:10:14.516Z
---

# Mirroring
## List of mirrors

> 📊 **Live reliability ranking** (auto-generated, daily): see **[Mirror status](https://mirror.openmandriva.org/status)** for per-mirror availability and freshness.
{.is-info}

### Mirmon (Mirrors manager)
![Website](https://img.shields.io/website?label=MirMon%20status&url=https%3A%2F%2Fmirmon.openmandriva.org)
From here you can see if a mirror is regularly up to date
- https://mirmon.openmandriva.org/

### Mirrorbits (nearby mirror redirector)
![Website](https://img.shields.io/website?label=Mirrorbits%20status&url=https%3A%2F%2Fmirror.openmandriva.org%2FREADME.txt%3Fstats)
You can see where the mirrors are distributed around the world.
- http://mirror.openmandriva.org?mirrorstats

## Get the closest mirror
Mirrorbits can redirect automatically to the closest mirror from your location, here is an example with a simple txt file available on repositories:
- Immediate redirection: http://mirror.openmandriva.org/release_current/README.txt 
- Visual representation http://mirror.openmandriva.org/release_current/README.txt?mirrorlist

## Mirror topology

OpenMandriva uses a flat topology: **every mirror syncs directly from the origin (ABF)**. There are no intermediate tiers, so a lagging mirror never propagates staleness to others, and every mirror can be as fresh as the source.

> **End users don't need to pick a mirror.** Point your tools at **`mirror.openmandriva.org`** (Mirrorbits): it redirects to the nearest healthy mirror and falls back to ABF if a file is missing. Live per-mirror reliability is on the [Mirror status](https://mirror.openmandriva.org/status) page.
{.is-info}

## Setting up a mirror
If you want to support us by setting up a mirror for OpenMandriva Lx, sync directly from our origin (ABF distribution) so your mirror stays as fresh as the source:
- `rsync -av rsync://abf-downloads.openmandriva.org/openmandriva/ /local/path/`
> Don't forget the ''TIME.txt'' file. It is needed by Mirmon and Mirrobits to work correctly.
>
> At least '''600GB''' of free disk space is needed
{.is-warning}


## T0 mirror

Our T0 mirror, ABF, is where packages are compiled and distributed. There are much  packages on it than on our other mirrors, such as source and debug packages, old release packages, personal repositories etc. 

Its content can be explored with this address:

- http://abf.openmandriva.org

Mirrorbits will always redirect to ABF if a file doesn't exist in any mirror. For instance: 
- http://mirror.openmandriva.org/release_current/README.txt 
- http://mirror.openmandriva.org/release_current/README.txt?mirrorlist