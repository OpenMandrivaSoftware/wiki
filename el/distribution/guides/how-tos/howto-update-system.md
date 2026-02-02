---
title: Πώς να ενημερώσετε το σύστημα
description: Πώς να ενημερώσετε το σύστημα Rock ή Rolling
published: true
date: 2025-08-02T19:12:19.690Z
tags: documentation, howto, user-guide
editor: markdown
dateCreated: 2021-02-19T15:43:53.051Z
---

# Πώς να ενημερώσετε το σύστημα

> Η πολιτική του OpenMandriva σχετικά με την αναβάθμιση του συστήματος είναι διαφορετική.
> **Μην** χρησιμοποιείτε το Discover για την αναβάθμιση του συστήματος.
{.is-danger}

<br>


Ανοίξτε το Konsole και εκτελέστε τις εντολές:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf distro-sync --refresh --allowerasing
```

- ή

![update-menu.png](/images/update-menu.png)


- ή

![update-60-taskmanager02.jpg](/images/update-60-taskmanager02.jpg)

- ή

![update-dnfdrake.png](/images/update-dnfdrake.png)
