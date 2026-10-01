---
title: Πώς να ενημερώσετε το κανάλι
description: 
published: true
date: 2025-03-10T18:03:06.852Z
tags: documentation, howto, user-guide, advanced
editor: markdown
dateCreated: 2020-04-28T08:42:49.215Z
---

# Πώς να ενημερώσετε το κανάλι
## Πώς να αναβαθμίσετε από Rock σε ROME (rolling)

Στους χρήστες που είναι νέοι στο OpenMandriva Lx προτείνουμε να ξεκινήσουν με την σταθερή έκδοση Rock για να μάθουν πώς λειτουργεί το σύστημα και, αν το επιθυμούν, να μεταβούν στη ROME, την έκδοση rolling.

Ως *χρήστης ROME* θα πρέπει να είστε σε θέση να χρησιμοποιείτε τη γραμμή εντολών και να γνωρίζετε τα βασικά του διαχειριστή πακέτων [dnf](/en/distribution/guides/software-management/DNF).
Επίσης, ο χρήστης πρέπει να διαβάσει και να κατανοήσει το [Πλάνο κυκλοφορίας και αποθετήρια OpenMandriva](/en/policies/release-plan-and-repositories).

Για να αναβαθμίσετε στο ROME:

- Ανοίξτε το πρόγραμμα επιλογής αποθετηρίου λογισμικού (`om-repo-picker`) 
Μενού εφαρμογών > Πρόγραμμα επιλογής αποθετηρίου λογισμικού

![omlx43.doc.repopicker-01.jpg](/images/omlx43.doc.repopicker-01.jpg)

ή επιλέξτε το πρόγραμμα επιλογής αποθετηρίου OpenMandriva στο OM Welcome

![omlx43.doc.repopicker-02.jpg](/images/omlx43.doc.repopicker-02.jpg)


- Μεταβείτε στην πρώτη ενότητα «Κανάλι ενημέρωσης».

![om4.2-repopicker-03.jpg](/images/om4.2-repopicker-03.jpg)

- Επιλέξτε «Rolling» από το αναπτυσσόμενο μενού

![om4.2-repopicker-04.jpg](/images/om4.2-repopicker-04.jpg)

Επιβεβαιώστε πατώντας OK και όταν σας ζητηθεί, εισάγετε τον κωδικό πρόσβασης root. Αυτή η διαδικασία θα διαρκέσει λίγο και το παράθυρο του προγράμματος ενδέχεται να γίνει προσωρινά αόρατο, οπότε παρακαλούμε να είστε υπομονετικοί.

Με αυτή την ενέργεια έχετε αλλάξει τα αποθετήρια από Rock σε Rolling, οπότε θέλετε να εκτελέσετε μια αναβάθμιση του συστήματος (`distro-sync`).

- Για να αναβαθμίσετε το σύστημά σας, ανοίξτε το Konsole και εκτελέστε τις εντολές:
```
$ sudo dnf clean all ; dnf clean all ; dnf repolist
$ sudo dnf --allowerasing distro-sync
```

\-
