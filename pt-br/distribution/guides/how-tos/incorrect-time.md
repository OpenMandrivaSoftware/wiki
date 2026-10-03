---
title: Como resolver a causa mais comum de horário incorreto em sistemas com dual boot e Windows
description: 
published: true
date: 2021-09-26T21:36:52.368Z
tags: documentação, howto, guia do usuário, resolução de problemas
editor: markdown
dateCreated: 2020-03-09T19:25:27.676Z
---

# Como resolver a causa mais comum de horário incorreto em sistemas com dual boot com Windows

Se você tiver um problema de horário no Linux com um sistema com windows em dual boot,

### Cheque seu sistema Linux:
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

Observe a última linha. Se ela for: `RTC in local TZ: yes`, a configuração está correta e o problema deve estar em outro lugar.
Mas, muito provavelmente, você verá que o fuso horário local está definido como no.

### Para consertar isso, rode o comando:

```
$ sudo timedatectl set-local-rtc 1 --adjust-system-clock
```

> Será solicitado a senha root, e o após o comando será executado.
{.is-warning}


Para verificar, digite de novo:
```
$ timedatectl
                      Hora Locar: Ter 2018-08-21 18:15:28 CDT
                  Hora universal: Tue 2018-08-21 23:15:28 UTC
                        Hora RTC: Tue 2018-08-21 18:15:28
                       Fuso horário: US/Central (CDT, -0500)
       Relógio do sistema sincronizado: não
systemd-timesyncd.service ativo: sim
                 RTC no fuso horário local: sim
Aviso: O sistema está configurado para ler a hora do RTC no fuso horário local.
Esse modo não pode ser totalmente suportado. Ele causará diversos problemas com alterações de fuso horário e ajustes de horário de verão. A hora do RTC nunca é atualizada; ela depende de recursos externos para mantê-la. 
Se possível, use o RTC em UTC digitando
'timedatectl set-local-rtc 0'.
```

Isso está correto.
*(O aviso pode ser ignorado.)*
<br>

### Definições:

`RTC` = Relógio de Tempo Real, também chamado de relógio de hardware ou hwclock
`TZ` = Fuso horário