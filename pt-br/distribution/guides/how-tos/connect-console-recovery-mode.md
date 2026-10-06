---
title: Como conectar-se à internet no modo de console ou no modo de recuperação
description: 
published: true
date: 2021-09-26T21:29:39.480Z
tags: documentação, howto, guia do usuário
editor: markdown
dateCreated: 2020-07-07T08:04:15.837Z
---

# Como conectar-se à internet no modo de console ou no modo de recuperação


> Observação: este how-to pressupõe que o usuário tenha um sistema no qual a internet estava funcionando corretamente até que algo desse errado.
{: .is-info}


Às vezes, pode ser necessário inicializar no modo de console ou no modo de recuperação em vez da área de trabalho Plasma para realizar manutenção ou reparos.

![boot-advanced.jpg](/images/boot-advanced.jpg)

![boot-console-mode.jpg](/images/boot-console-mode.jpg)

![boot-recovery-mode.jpg](/images/boot-recovery-mode.jpg)


Você pode descobrir que o wifi não funciona nesses modos.

## Wifi
Para conectar-se ao wifi pela linha de comando, usamos o comando `nmcli`. Exemplo:

Para determinar a qual dispositivo conectar-se, execute este comando:

```
$ nmcli dev status
```

Isso listará todos os dispositivos de rede disponíveis. Neste exemplo, sabemos que estamos usando wifi, mas não wifi-p2p, e o comando lista o dispositivo wifi como wlp4s0, então, para conectar:

```
$ nmcli --ask dev con wlp4s0
```

Isso deverá solicitar sua senha do wifi e, em seguida, conectar você ao wifi.
Agora você pode realizar qualquer manutenção ou reparo que exija acesso à internet.

## Conexão Ethernet

Se você estiver usando uma conexão Ethernet, para conectar-se é basicamente a mesma coisa:

```
$ nmcli dev status
```

Se o seu dispositivo Ethernet estiver listado como, por exemplo, elp4s0:

```
$ nmcli dev con elp4s0
```

A opção `--ask` normalmente não é necessária, pois seu sistema já possui permissão para isso. As permissões de Wifi normalmente são separadas e exclusivas das permissões do sistema.

\-




