---
title: How to update system
description: How to update your Rock or Rolling system
published: true
date: 2025-02-07T11:58:52.295Z
tags: documentation, howto, user-guide
editor: markdown
dateCreated: 2021-02-19T15:43:53.051Z
---

# How to update system
## How to update Rock
- To update your Rock system open Konsole and run the commands:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf upgrade
```

## How to update ROME
- To update ROME, your rolling system, open Konsole and run the commands:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf distro-sync --allowerasing
```

- or

![update-menu.png](/images/update-menu.png)

- or


![update-omwelc.jpg](/images/update-omwelc.jpg)

- or

![update-dnfdrake.png](/images/update-dnfdrake.png)
