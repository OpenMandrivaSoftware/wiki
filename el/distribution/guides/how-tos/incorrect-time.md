---
title: Πώς να επιλύσετε την πιο συνηθισμένη αιτία λανθασμένης ώρας σε διπλή εκκίνηση με συστήματα Windows
description: 
published: true
date: 2021-09-26T21:36:52.368Z
tags: documentation, howto, user-guide, troubleshooting
editor: markdown
dateCreated: 2020-03-09T19:25:27.676Z
---

# Πώς να επιλύσετε την πιο συνηθισμένη αιτία λανθασμένης ώρας σε διπλή εκκίνηση με συστήματα Windows

Εάν αντιμετωπίζετε πρόβλημα με λανθασμένη ώρα στο Linux σε σύστημα διπλής εκκίνησης με Windows,

### Ελέγξτε το σύστημα Linux:
```
$ timedatectl
                      Local time: Tue 2018-08-21 13:11:23 CDT
                  Universal time: Tue 2018-08-21 18:11:23 UTC
                        RTC time: Tue 2018-08-21 18:11:23
                       Time zone: US/Central (CDT, -0500)
       System clock synchronized: no
systemd-timesyncd.service active: yes
                 RTC in local TZ: no
```

Κοιτάξτε την τελευταία γραμμή. Αν είναι: `RTC in local TZ: yes`, τότε η ρύθμιση είναι σωστή και το πρόβλημα πρέπει να βρίσκεται αλλού.
Ωστόσο, το πιο πιθανό είναι να δείτε ότι η τοπική ζώνη ώρας (local TZ) είναι ρυθμισμένη στο no.

### Για να το διορθώσετε, εκτελέστε την εντολή:

```
$ sudo timedatectl set-local-rtc 1 --adjust-system-clock
```

> Θα σας ζητηθεί ο κωδικός πρόσβασης root και η εντολή θα εκτελεστεί.
{.is-warning}


Για να επαληθεύσετε, πληκτρολογήστε ξανά:
```
$ timedatectl
                      Local time: Tue 2018-08-21 18:15:28 CDT
                  Universal time: Tue 2018-08-21 23:15:28 UTC
                        RTC time: Tue 2018-08-21 18:15:28
                       Time zone: US/Central (CDT, -0500)
       System clock synchronized: no
systemd-timesyncd.service active: yes
                 RTC in local TZ: yes

Warning: The system is configured to read the RTC time in the local time zone.
         This mode cannot be fully supported. It will create various problems
         with time zone changes and daylight saving time adjustments. The RTC
         time is never updated, it relies on external facilities to maintain it.
         If at all possible, use RTC in UTC by calling
         'timedatectl set-local-rtc 0'.
```

Αυτό είναι σωστό.
*(Η προειδοποίηση μπορεί να αγνοηθεί)*
<br>

### Ορισμοί:

`RTC` = Ρολόι πραγματικού χρόνου, επίσης γνωστό ως ρολόι υλικού ή hwclock
`TZ` = Ζώνη ώρας