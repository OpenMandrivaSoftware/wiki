---
title: Notas resumidas
description: OMLx 4.2 Notas resumidas
published: true
date: 2021-09-26T20:42:01.256Z
tags: 4.2, Lançamentos
editor: markdown
dateCreated: 2020-07-15T10:08:13.956Z
---

# OMLx 4.2 Notas resumidas

> **é recomendado que você leia a versão estendida das** [Notas de Lançamento do OpenMandriva Lx 4.2](/releases/omlx42/notes) **assim como a** [Errata OpenMandriva Lx 4.2](/releases/omlx42/errata) **em nossa wiki**
{.is-info}


## Mídias disponíveis
Este lançamento está disponível como uma mídia live em DVD ou disco flash USB (pendrive), para download no formato ISO.
*Mídia Live* significa que você pode rodar o OpenMandriva Lx sireto do DVD ou pendrive e testar antes de instalar.

##  Hardware Recomendado
OpenMandriva Lx precisa de pelo menos 2048 MB de memória e 10 GB de espaço no disco rígido.

## Conexão com a internet
O Instalador Calamares verifica se uma conexão com a internet está disponível, mas o OpenMandriva vai instalar tranquilamente mesmo que não tenha. Apenas instale como você normalmente instalaria e comece a usar seu novo sistema.

## Máquinas Virtuais
Até o momento o único software de virtualização em que as imagens ISO do OMLx foram testadas é o VirtualBox. Os mesmos requerimentos de sistemas se aplicam quando rodando em máquinas virtuais.
Para o VirtualBox você deverá sempre ter no mínimo 2048MB de memória ou o sistema vai falhar na inicialização.

## Instalador e Suporte EFI
Esse lançamento do OpenMandriva Lx suporta boot e instalação com e sem UEFI.
Note que o boot seguro não é suportado.

## Tipo de sistema de arquivos recomendado para instalação manual
O sistema de arquivos mais recomendado para o uso é o ext4. Para dispositivos de armazenamento baseados em memórias flash temos disponível o F2FS..
Tenha em menteo que o Calamares não pode converter um tipo de partição em outro e preservar as informações.
Se você iniciar o Calamares a partir de uma imagem live não é possível mudar um tipo de partição existente. Você precisará apagar a partição existente primeiro para depois recriar ela no tipo desejado.

## Inicialização através do USB
Para transferir a imagem live/instalação você pode usar *rosa-imagewriter* ou via *dd*.
- rosa-imagewriter está disponível em nossos repositórios
 `sudo dnf --refresh install rosa-imagewriter`
 ou você pode conseguí-lo [aqui](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter)

- Alternativamente, você pode dd a imagem em seu dispositivo USB
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

 <br>

## Errata
-- **Placas gráficas NVIDIA**
Essa distribuição incluí os drivers nouveau construídos com engenharia reversa.
Os usuários podem usar os drivers diretamente do site da NVIDIA, mas eles não tem suporte pelo OpenMandriva. A instalação e manutenção de qualquer driver proprietário é de opção e responsabilidade unicamente do usuário.

-- **NVME SSDs**

Alguns SSDs NVMe podem não ser reconhecidos pela ISO Live do OMLx 4.2.

A ISO Live possui duas soluções alternativas para esse problema. Veja mais detalhes em [4.2/Errata#NVME SSDs](https://wiki.openmandriva.org/en/releases/omlx42/errata#nvme-ssds).

--**GEOIP**
A configuração automática de GEOIP pelo instalador pode não definir o fuso horário corretamente.

--**Como configurar uma impressora**
O OMLx fornece alguns pacotes “task-printing” específicos para a marca da sua impressora, caso ela não seja configurada automaticamente.

Instale o pacote correspondente à marca da sua impressora ou, caso nenhuma opção específica esteja disponível, instale o pacote “misc”.


<br>

## Ajudando o Projeto
![om-donate.svg](/images/om-donate.svg){.align-left}Se você quiser ajudar o projeto e apoiar o OpenMandriva, considere [juntar-se à nossa equipe](https://www.openmandriva.org/en/article/get-involved) ou fazer uma [doação](https://www.openmandriva.org/donate) para manter as luzes acesas!



