---
title: Notas resumidas
description: OMLx 4.1 Notas resumidas
published: true
date: 2021-09-26T21:00:58.458Z
tags: distribuições. 4.1
editor: markdown
dateCreated: 2020-06-13T07:46:23.080Z
---

# OMLx 4.1 Notas resumidas

> **é recomendado que você leia a versão estendida das** [Notas de Lançamento do OpenMandriva Lx 4.1](/releases/omlx41/notes) **assim como a** [Errata OpenMandriva Lx 4.1](/releases/omlx41/errata) **em nossa wiki**
{.is-info}


## Mídias disponíveis
Este lançamento está disponível como uma mídia live em DVD ou disco flash USB (pendrive), para download no formato ISO.
*Mídia Live* significa que você pode rodar o OpenMandriva Lx sireto do DVD ou pendrive e testar antes de instalar.

##  Hardware Recomendado
OpenMandriva Lx precisa de pelo menos 2.0 GB de memória e 10 GB de espaço no disco rígido.

## Conexão com a internet
O Instalador Calamares verifica se uma conexão com a internet está disponível, mas o OpenMandriva vai instalar tranquilamente mesmo que não tenha. Apenas instale como você normalmente instalaria e comece a usar seu novo sistema.

## Máquinas Virtuais
Até o momento o único software de virtualização em que as imagens ISO do OMLx foram testadas é o VirtualBox. Os mesmos requerimentos de sistemas se aplicam quando rodando em máquinas virtuais.
Para o VirtualBox, contudo, você deverá sempre ter no mínimo 2048MB de memória ou o sistema vai falhar na inicialização.

## Instalador e Suporte EFI
Esse lançamento do OpenMandriva Lx suporta boot e instalação com e sem UEFI.
Note que o boot seguro não é suportado.

## Tipo de sistema de arquivos recomendado para instalação manual
O sistema de arquivos mais recomendado para o uso é o ext4. Para dispositivos de armazenamento baseados em memórias flash temos disponível o F2FS..
Tenha em menteo que o Calamares não pode converter um tipo de partição em outro e preservar as informações.
Se você iniciar o Calamares a partir de uma imagem live não é possível mudar um tipo de partição existente. Você precisará apagar a partição existente primeiro para depois recriar ela no tipo desejado.

## Inicialização através do USB
Para transferir a imagem live/instalação você pode usar *ROSA Image writer* ou via *dd*.
- ROSA Image Write está disponível em nossos repositórios
 `sudo dnf --refresh install rosa-imagewriter`
 ou você pode conseguí-lo [aqui](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter)

- Como alternativa, você pode gravar a imagem com dd no seu pendrive USB:
 `sudo dd if=<iso_name> of=<usb_drive> bs=4M`
 Substitua`<iso_name>` com o caminho da ISO e `<usb_drive>` com o node do dispositivo USB, exemplo. `/dev/sdb`.

*SUSE Studio ImageWriter também foi testado e funciona para a gravação das imagens ISO em dispositivos de armazenamento USB.*

> Não use outras ferramentas de gravação USB, pois algumas ferramentas do Windows ( Rufus, por exemplo) truncam o nome do volume. Isso interrompe o processo de inicialização. 
{.is-danger}

## Repositório do OpenMandriva e disponibilidade de software
**Quando instalado o sistema operacional OMLx possupi apenas o repositório /main habilitado por padrão.**
Para a disponibilidade de todos os programas você precisará habilitar os repositórios adicionais chamados *unsupported*, *restricted*, and *non-free*.
Use o utilitário gráfico [Software Repository Selector](https://wiki.openmandriva.org/en/doc/repositories-tldr) (om-repo-picker) para habilitar ou desabilitar o repositório que desejar.

Ainda que as ferramentas gráficas (Discover, dnfdragora, etc.) sejam úteis para descobrir programas extras disponíveis, nós recomendamos a instalação de pacotes através da linha de comando
 `sudo dnf --refresh install <package_name>`

\-



