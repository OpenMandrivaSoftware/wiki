---
title: Πώς να επιδιορθώσετε ένα χαλασμένο bootloader
description: 
published: true
date: 2022-04-02T16:07:14.522Z
tags: documentation, howto, user-guide
editor: markdown
dateCreated: 2020-09-10T21:59:11.289Z
---

# Πώς να επιδιορθώσετε ένα χαλασμένο bootloader

Το OpenMandriva Lx χρησιμοποιεί το bootloader grub2, οπότε χρησιμοποιούμε εντολές grub2.
Η εντολή για να ανιχνεύσουμε τον υπολογιστή και να γράψουμε ένα ολοκληρωμένο μενού grub2 είναι:
```
$ sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```
Στις περισσότερες περιπτώσεις, αυτή η απλούστερη εντολή θα λειτουργήσει:
```
$ sudo update-grub2
```
Στη συνέχεια, για να εγκαταστήσετε το πρόγραμμα εκκίνησης grub2 στη μονάδα δίσκου από την οποία θέλετε να εκκινήσετε:
```
$ sudo grub2-install /dev/xxx
```
Αντικαταστήστε το «*xxx*» με το όνομα της μονάδας δίσκου που θέλετε ή από την οποία εκκινήσατε το OMLx, όπως `sda` ή, αν είναι μονάδα δίσκου nvme, κάτι σαν `nvme0n1`.

Για να το κάνετε αυτό, προφανώς χρειάζεστε πρόσβαση στο σύστημα OMLx. Εάν δεν έχετε εύκολη πρόσβαση, μπορείτε να δοκιμάσετε το [Rescatux](https://sourceforge.net/p/rescatux/) ή το [Super Grub2 Disk](https://sourceforge.net/p/supergrub2/). Για αυτήν την εργασία, ίσως θέλετε να δοκιμάσετε πρώτα το Super Grub2 Disk.

Για να βρείτε πώς ονομάζονται οι συσκευές αποθήκευσης ή οι μονάδες δίσκου σας, μπορείτε απλά να ανοίξετε το KDE Partition Manager ή να εκτελέσετε την εντολή από το Konsole:
```
$ sudo fdisk -l
```
<br>

### Πρόσθετες πληροφορίες:
Οι εντολές `grub2-mkconfig` και `update-grub2` χρησιμοποιούν το βοηθητικό πρόγραμμα «os-prober» για να ανιχνεύσουν τον υπολογιστή για άλλα λειτουργικά συστήματα.
Ο χρήστης μπορεί να εκτελέσει αυτήν την εντολή ανεξάρτητα για να δει αν το os-prober αναγνωρίζει σωστά όλα τα άλλα λειτουργικά συστήματα στον υπολογιστή του χρήστη. Όπως αυτό:
```
$ sudo os-prober
```

<br>

### Χρήσιμες αναγνώσεις
[Εγχειρίδιο Grub2](https://www.gnu.org/software/grub/manual/grub/html_node/index.html)
[Πώς να διασώσετε ένα GRUB 2 που δεν εκκινεί σε Linux](https://www.linux.com/training-tutorials/how-rescue-non-booting-grub-2-linux/)
Μερικές σελίδες man: [1](https://aty.sdsu.edu/bibliog/latex/debian/grub2rescue.html) [2](https://www.gnu.org/software/grub/manual/grub/html_node/GRUB-only-offers-a-rescue-shell.html)



