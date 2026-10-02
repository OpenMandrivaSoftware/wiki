---
title: Como reparar o boot loader quebrado
description: 
published: true
date: 2022-04-02T16:07:14.522Z
tags: documentação, howto, guia do usuário
editor: markdown
dateCreated: 2020-09-10T21:59:11.289Z
---

# Como reparar o boot loader quebrado

O OpenMandriva Lx usa o bootloader grub2, portanto usamos os comandos do grub2.
O comando para verificar o computador e gerar um menu completo do grub2 é:
```
$ sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```
Na maioria das circunstâncias, este comando mais simples funcionará:
```
$ sudo update-grub2
```
Em seguida, para instalar o bootloader grub2 na unidade a partir da qual você deseja inicializar:
```
$ sudo grub2-install /dev/xxx
```
Onde você substitui o "*xxx*" pelo nome da unidade que deseja usar ou a partir da qual está inicializando o OMLx, como `sda` ou, se for uma unidade NVMe, algo como `nvme0n1`.

Para fazer isso, obviamente você precisa ter acesso ao seu sistema OMLx. Se não tiver acesso fácil, você pode tentar o [Rescatux](https://sourceforge.net/p/rescatux/) ou o [Super Grub2 Disk](https://sourceforge.net/p/supergrub2/). Para essa tarefa, talvez seja melhor tentar primeiro o Super Grub2 Disk.

Para descobrir como seus dispositivos de armazenamento ou unidades são identificados, basta abrir o KDE Partition Manager ou, no Konsole, executar o comando:
```
$ sudo fdisk -l
```
<br>

### Informações adicionais:
Os comandos `grub2-mkconfig` e `update-grub2` usam o utilitário chamado 'os-prober' para verificar o computador em busca de outros sistemas operacionais.
O usuário pode executar este comando independentemente para verificar se o os-prober está reconhecendo corretamente todos os outros sistemas operacionais no computador do usuário. Assim:
```
$ sudo os-prober
```

<br>

### Leituras úteis
[Grub2 manual](https://www.gnu.org/software/grub/manual/grub/html_node/index.html)
[How to Rescue a Non-booting GRUB 2 on Linux](https://www.linux.com/training-tutorials/how-rescue-non-booting-grub-2-linux/)
Some man pages: [1](https://aty.sdsu.edu/bibliog/latex/debian/grub2rescue.html) [2](https://www.gnu.org/software/grub/manual/grub/html_node/GRUB-only-offers-a-rescue-shell.html)



