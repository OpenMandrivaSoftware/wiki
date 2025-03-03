---
title: Come configurare la stampante in OMLx
description: 
published: true
date: 2025-01-14T13:18:00.942Z
tags: documentation, howto, user-guide
editor: markdown
dateCreated: 2020-03-09T18:43:12.417Z
---

# Come configurare la stampante in OMLx
Accendi la stampante e controlla se è configurata automaticamente. Controlla se è stato installato il driver giusto.

Se la stampante è stata configurata automaticamente e si dispone del driver corretto, sei a posto.

Se non lo fosse, spegni la stampante.

Apri *Impostazioni della stampante* aka `system-config-printer`, e rimuovi la stampante.
Se il driver corretto non è stato installato automaticamente, dovrai installare un pacchetto supplementare.

In OpenMandriva Lx molto probabilmente sarà un pacchetto "task-printing" specifico per la tua stampante.
I pacchetti sono:

task-printing-canon
- task-printing-epson
- task-printing-hp
- task-printing-lexmark
- task-printing-okidata
- task-printing-misc
- Installa il pacchetto che corrisponde alla marca della tua stampante, oppure il pacchetto `task-printing-misc` se nessuno di essi corrisponde.
- Esempio utilizzando okidata:

```
$ sudo dnf install task-printing-okidata
```

Ora riaccendi la stampante, che dovrebbe quindi configurarsi automaticamente (a volte potrebbe essere necessario un riavvio).
In caso di necessità puoi chiedere aiuto [qui](https://forum.openmandriva.org/c/en/support)
Ora riaccendete la stampante, che dovrebbe configurarsi automaticamente (a volte potrebbe essere necessario riavviare la stampante per far funzionare la configurazione automatica).

Altrimenti chiedere aiuto qui [here](https://forum.openmandriva.org/c/support/17)
