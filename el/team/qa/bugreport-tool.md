---
title: Εργαλείο αναφοράς σφαλμάτων για το OpenMandriva Lx
description: 
published: true
date: 2025-04-07T23:57:30.827Z
tags: documentation, user-guide, tools
editor: markdown
dateCreated: 2021-03-08T17:17:16.207Z
---

# Εργαλείο αναφοράς σφαλμάτων για το OpenMandriva Lx
Το απλό εργαλείο ονομάζεται om-bug-report.

## Οι συντομεύσεις
### Ανοίξτε το OM Welcome και μεταβείτε στο OM Features > *Bug report tool*

![om43-bugreportwelc.jpg](/images/om43-bugreportwelc.jpg)


## Συλλεγόμενες πληροφορίες
Το εργαλείο θα συλλέξει χρήσιμες πληροφορίες από:

- διάφορα αρχεία διαμόρφωσης (στο /etc/*)
- διάφορες καταχωρήσεις /proc (που παρέχουν πληροφορίες σχετικά με τη διαμόρφωση του πυρήνα)
- διαμόρφωση grub (το πρόγραμμα εκκίνησης)
- έξοδο lspcidrake (για λίστα συσκευών PCI)
- έξοδο lsusb (για λίστα συσκευών USB)
- έξοδο dmidecode (για πληροφορίες σχετικά με το υλικό από το BIOS)
- systemctl –failed (για αναφορά συστημάτων ή υπηρεσιών που δεν μπόρεσαν να ξεκινήσουν)
- journalctl -b (για την εμφάνιση του αρχείου καταγραφής της τρέχουσας εκκίνησης)
- rpm -qa (για την λίστα των εγκατεστημένων πακέτων)
- έκδοση gcc (για την έκδοση του μεταγλωττιστή)

![om43-bugreportpsw.jpg](/images/om43-bugreportpsw.jpg)

![om43-bugreportpopup.jpg](/images/om43-bugreportpopup.jpg)

Στη συνέχεια, θα δημιουργηθεί το αρχείο omdv-bug-report στον κατάλογο /home.

![om43-bugreportfile.jpg](/images/om43-bugreportfile.jpg)

> **Αυτό το αρχείο πρέπει να επισυνάπτεται σε κάθε αναφορά σφάλματος**.
{.is-info}

Θα βοηθήσει στην επιτάχυνση της εργασίας του bug squasher και θα απλοποιήσει την εργασία του bug reporter, παρέχοντας γρήγορα λεπτομερείς πληροφορίες.

\- 


