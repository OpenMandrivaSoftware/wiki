---
title: Come ottenere una lista di tutti i pacchetti presenti nella ISO
description: 
published: true
date: 2021-09-26T21:51:27.354Z
tags: howto, user-guide, troubleshooting
editor: markdown
dateCreated: 2020-04-15T09:03:58.412Z
---

# Come ottenere una lista di tutti i pacchetti presenti nella ISO


In live mode, aprire la console e digitare:

```
rpm -qa|sort > pkglist-sort.txt
```
che creerà un semplice documento di testo nella tua directory `/home` chiamato `pkglist-sort.txt`

La lista dei pacchetti è ordinata A-Z

![pkglist.jpg](/images/pkglist.jpg)

> Questo semplice trick è valido non solo in modalità ISO/Live ma anche nel sistema installato.
> Puoi lanciare il comando ogni volta ve ne sia la necessità.
{.is-info}


Se invece ti occorre una lista di tutti i pacchetti installati per data, digitare il comando:

```
rpm -qa --last > pkglist-last.txt
```

\-
Vedi anche
[How to get a list of the latest updates](/doc/guides/howto-latest-updates)



