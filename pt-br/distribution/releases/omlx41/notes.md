---
title: Notas de lançamento do OpenMandriva Lx 4.1
description: 
published: true
date: 2021-09-26T21:02:54.401Z
tags: 4.1
editor: markdown
dateCreated: 2020-02-28T12:18:34.424Z
---

# Notas de lançamento do OpenMandriva Lx 4.1
As equipes do OpenMandriva Lx têm o prazer de anunciar a disponibilidade da edição **OpenMandriva Lx 4.1**. [Codename](/en/releases/codename) Mercury

## Mídias disponíveis

Esta versão está disponível como DVD de mídia Live ou pendrive USB (dispositivo de armazenamento), para download no formato ISO. Esses arquivos estão disponíveis em nossa [página de downloads] (https://www.openmandriva.org/en/download). A instalação a partir de um pendrive USB geralmente é consideravelmente mais rápida. Como sempre, a velocidade depende de vários fatores.
*Live media* significa que você pode executar o OpenMandriva Lx diretamente a partir de um DVD ou pendrive (veja abaixo) e experimentá-lo antes de instalá-lo.

Arquivos ISO estão disponíveis:
- [KDE Plasma] (https://www.kde.org/plasma-desktop) ambiente de desktop completo e repleto de recursos (inclui as funcionalidades mais utilizadas, além de softwares multimídia e de escritório).
- znver1 Plasma: também compilamos uma versão especificamente para os atuais processadores AMD (Ryzen, ThreadRipper e EPYC), que oferece desempenho superior à versão genérica (x86_64) ao aproveitar novos recursos presentes nesses processadores.
znver1 é para os processadores listados (Ryzen, ThreadRipper, EPYC) somente, não instale em nenhum outro hardware.

## Hardware Recomendado

O OpenMandriva Lx 4.1 requer pelo menos 2,0 GB de memória RAM e 10 GB de espaço no disco rígido (veja abaixo os problemas conhecidos relacionados ao particionamento).

>Nota importante — Hardware gráfico:
>O ambiente de desktop KDE Plasma requer uma placa gráfica 3D compatível com OpenGL 2.0 ou superior.
>Recomendamos o uso de chips gráficos AMD, Intel, Adreno ou VC4.
{.is-warning}


## Conexão com a internet

O instalador Calamares verifica se há uma conexão com a Internet disponível, mas o OpenMandriva Lx 4 será instalado normalmente mesmo sem conexão. Não há problema algum em simplesmente fazer a instalação como de costume e, em seguida, utilizar o novo sistema normalmente.
Para atualizar um sistema desse tipo, seria necessário conectar-se temporariamente à Internet ou baixar os pacotes em outro local, transferi-los para o sistema instalado e instalar os pacotes atualizados. Porém, como você não está conectado à Internet, pode simplesmente utilizar o sistema sem atualizá-lo pelo tempo que considerar adequado.

## Máquinas Virtuais
Até o momento o único software de virtualização em que as imagens ISO do OMLx foram testadas é o VirtualBox. Os mesmos requerimentos de sistemas se aplicam quando rodando em máquinas virtuais.
Para o VirtualBox você deverá **sempre** ter no mínimo 2048MB de memória ou o sistema vai falhar na inicialização.
Também para o VirtualBox, é recomendável instalar em uma máquina virtual nova, pois tentar instalar em uma máquina virtual existente pode ocasionalmente apresentar falhas.

## Instalador Calamares

O Calamares é um framework de instalação.
Por definição, ele é altamente personalizável, de modo a atender a uma ampla variedade de necessidades e casos de uso. Seu objetivo é ser fácil de usar, acessível, bonito, pragmático, inclusivo e independente da distribuição.
O Calamares inclui um recurso avançado de particionamento, com suporte tanto para operações de particionamento manuais quanto automatizadas.
Ele é o primeiro instalador a oferecer uma opção automatizada de “Substituir partição”, que facilita reutilizar uma partição repetidamente para testar diferentes distribuições.
Muitas distribuições Linux utilizam o instalador Calamares, e cada uma possui sua própria implementação e seus próprios padrões. O fato de algo no instalador do OpenMandriva não corresponder à experiência do usuário em  outra distribuição Linux não significa que seja um bug.

## Particionamento

No momento, o particionamento de configurações LVM e RAID com o instalador Calamares não é suportado.
**Isso se aplica a todos os tipos de particionamento** e a todas as instalações em hardware: se você possui um computador com UEFI/EFI e a BIOS oferece, ao inicializar a mídia de instalação, uma opção entre, por exemplo:

`USB alguma coisa Flash Drive`
`UEFI USB alguma coisa Flash Drive`
or 
`alguma coisa DVD optical_device`
`UEFI alguma coisa DVD optical_device`

Você deve escolher a opção UEFI e inicializá-la. Mas saiba também que nem todos os computadores oferecem essa opção. Alguns computadores com BIOS mais simples oferecerão apenas uma opção e, quase sempre, ela será a correta. Portanto, por exemplo, se você não encontrar a opção mencionada acima em um notebook, não se preocupe.
Se você tiver vários discos de armazenamento habilitados, todos eles precisam usar o mesmo tipo de tabela de partição. Todos devem usar GPT ou todos devem usar MBR para que tudo funcione corretamente.
Em computadores com UEFI, em uma situação de multi-boot com vários discos de armazenamento, se você já tiver uma partição `/boot/efi` existente, deverá utilizá-la. O particionador não criará outra partição `/boot/efi` com as flags corretas, e a instalação resultará em um erro, sem que o gerenciador de inicialização  seja instalado.
Não formate essa partição; apenas defina o ponto de montagem como `/boot/ef`i.
É possível ter vários bootloaders de diferentes sistemas operacionais na mesma partição `/boot/efi`. Se houver necessidade de alternar entre os bootloaders, isso deverá ser feito nas configurações da BIOS.

## NVME SSDs

Alguns SSDs NVMe podem não ser reconhecidos pela ISO *Live* do OMLx 4.1.
A ISO *Live* possui duas soluções alternativas para esse problema em "Troubleshooting", no menu do Grub2. Elas são `(PCIE ASPM=OFF)` e `(NVME APST=OFF)`. Esperamos que isso funcione com a maioria dos hardwares. O problema é conhecido e está sendo trabalhado pelos desenvolvedores do OpenMandriva e pelos desenvolvedores upstream. Veja mais em [4.1/Errata](/en/releases/omlx41/errata#nvme-ssds).
A versão OM Lx 4.1 inclui o kernel 5.5.0, e o reconhecimento de hardware para SSDs NVMe deve estar consideravelmente melhorado. Sabe-se que alguns SSDs NVMe da Samsung que anteriormente não eram reconhecidos agora são reconhecidos com essa versão do kernel. Esse problema, naturalmente, é muito específico do hardware.

## Instalador e Suporte EFI

Esta versão do OpenMandriva Lx suporta inicialização e instalação com e sem [UEFI](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface).
Observe que a inicialização segura NÃO é suportada.

Se deseja realizar uma instalação EFI em um disco com MBR existente, será necessário converter a tabela de partições do disco para o esquema de particionamento GPT. Para fazer isso, você precisa usar a ferramenta gdisk. Um comando padrão  seria `gdisk /dev/sda`: a tabela de partições existente será convertida na memória para o esquema GPT. Avisos serão emitidos sobre a possível perda de dados; o disco não será alterado até que você grave a tabela de partições pressionando <kbd>w1</kbd>. Recomenda-se fazer backup de quaisquer dados importantes.

Podem haver ocasiões em que a conversão não possa ser realizada, geralmente devido à falta de espaço no início ou no final do disco para gravar a tabela de partições. Pode ser necessário excluir ou redimensionar uma partição para criar o espaço necessário; o gparted pode ser útil nessas circunstâncias.
Ainda é necessário criar uma partição EFI para conter o assistente de inicialização, e isso deve ser feito durante a instalação pelo Calamares. Quando o instalador chegar à etapa de particionamento, a partição `/` (raiz) deve ser removida e uma pequena partição (330 MB) FAT16 ou FAT32 deve ser criada no início do disco. Se o espaço em disco for crítico, uma partição menor pode ser usada, mas certifique-se de configurá-la como FAT16 ou FAT32 no Calamares; caso contrário, a instalação falhará.
Se você não seguir essas etapas, a instalação do carregador de inicialização falhará. Posteriormente, particione o disco normalmente.
Compartilhe suas experiências nos fóruns para que possamos melhorar esse aspecto da instalação.
Se você estiver instalando ao lado do Windows 8, 8.1, 10 ou sistema operacional semelhante com inicialização EFI, como precaução, certifique-se de ter discos de recuperação e de ter feito backup de todos os dados importantes.
Nossos testes com essa configuração foram limitados, mas instalações bem-sucedidas foram realizadas sem problemas.
Agradecemos qualquer feedback nessa área.

## Alterando o tipo de partição

Observe que o Calamares não pode converter um tipo de partição em outro preservando os dados. 
Se você executar o Calamares a partir da imagem Live, não será possível alterar o tipo de uma partição existente. Tentar fazer isso gera uma mensagem de erro. 
Para isso, primeiro exclua a partição e recrie-a com o tipo desejado.

## Tipo de sistema de arquivos recomendado para instalação manual

É altamente recomendado o sistema de arquivos [ext4](https://en.wikipedia.org/wiki/Ext4), pois temos observado menos problemas e ele funciona em uma ampla variedade de hardwares.
Para dispositivos de armazenamento baseados em memória flash (basicamente SSDs), disponibilizamos o [F2FS](https://en.wikipedia.org/wiki/F2FS), e os relatos são em sua maioria positivos.
Os usuários também podem usar [XFS](https://en.wikipedia.org/wiki/XFS) ou [Btrfs](https://en.wikipedia.org/wiki/Btrfs), embora tenham sido relatados alguns problemas com BTRFS.
Nenhum outro tipo de sistema de arquivos deve ser usado para a partição de instalação.

## Inicialização através do USB

Também ẽ possível inicializar esta versão a partir de um dispositivo de armazenamento USB. Para transferir a imagem Live/de instalação, você pode:

### - Usar o ROSA image Writer disponível em nossos repositórios

`sudo dnf --refresh install rosa-imagewriter`

Ou, se você não tiver o OpenMandriva Lx instalado, poderá obter os links para baixar o ROSA Image Writer [nesta página](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter).
Recomenda-se uma unidade flash com capacidade de pelo menos 4 GB. O armazenamento persistente não é necessário. Observe que isso **apagará** tudo do seu USB!

> Não use outras ferramentas de gravação USB, pois algumas ferramentas do Windows ( Rufus, por exemplo) truncam o nome do volume. Isso interrompe o processo de inicialização. 
{.is-danger}

### - Via dd

Como alternativa, você pode usar o dd para gravar a imagem no seu pendrive:
`$ sudo dd if=<iso_name>of=<usb_drive>bs=4M`

Substitua`<iso_name>` com o caminho da ISO e `<usb_drive>` com o node do dispositivo USB, exemplo. `/dev/sdb`.

O SUSE Studio ImageWriter também foi testado e funciona para gravar imagens ISO em dispositivos de armazenamento USB.

## Inicializando atravẽs do arquivo ISO

Entrada do Grub2 a ser adicionada em `/boot/grub2/grub.cfg`
```
submenu "OpenMandriva (64 bit)" {
        set isofile=/home/user/OpenMandrivaLx.4.1-plasma.x86_64.iso
        set isoname=OpenMandrivaLx_4.1
        loopback loop $isofile

        menuentry "OpenMandriva" {
                linux (loop)/boot/vmlinuz0 root=live:LABEL=${isoname} iso-scan/filename=${isofile} rd.live.image toram --
                initrd (loop)/boot/liveinitrd.img
        }
}
```

## Sobre os repositórios

Agora temos o [om-repo-picker](/en/doc/repositories-tldr), também conhecido como Software Repository Selector, para selecionar repositórios adicionais e obter maior disponibilidade de pacotes.

Não misture os repositórios de diferentes versões/canais de atualização. Isso significa, por exemplo, **não use os repositórios Cooker em um sistema Rock**. Se você usa Rock, use apenas os repositórios Rock.
Isso é explicado em mais detalhes no [Plano de Lançamento e Repositórios do OpenMandriva](/en/doc/release-plan-and-repositories).
**Se você misturar repositórios de diferentes versões/canais de atualização e danificar seu computador, a solução é fazer uma instalação limpa.** E depois dessa instalação limpa, não faça isso novamente.

## Repositório do OpenMandriva e disponibilidade de software

Os sistemas operacionais OMLx instalados têm o repositório principal habilitado por padrão.

Também existem repositórios chamados unsupported, restricted e non-free. Para obter a máxima disponibilidade de todos os softwares, o usuário deve usar esses repositórios.
Os vários repositórios são explicados [aqui](/en/doc/release-plan-and-repositories).

O usuário pode usar o utilitário gráfico [Software Repository Selector](/en/doc/repositories-tldr) para selecionar ou desmarcar os repositórios que deseja usar.

## Novos Recursos e Principais Mudanças

Para acompanhar as mudanças mais recentes no Linux, problemas de segurança e alterações no código-fonte, há grandes mudanças no OMLx4.1.

Principais mudanças:
- O kernel foi atualizado para a versão 5.5.0
- Qt foi atualizado para o 5.14.1
- Produtos do Plasma foram atualizados: Frameworks 5.66, Plasma Desktop 5.17.5, Applications 19.12.1
- Zypper como alternativa de gerenciador de pacotes
- Mais alternativas de desktops estão disponíveis

Aplicativos da marca OpenMandriva:
- Desktop Presets (om-feeling-like): Ferramenta para personalizar a aparência do ambiente de trabalho Plasma do OpenMandriva para que sua aparência e comportamento sejam semelhantes aos de outros sistemas aos quais você pode estar acostumado
- Update Configuration (om-update-config): Ferramenta para configurar atualizações automáticas

## Atualização a partir de uma versão anterior
Atualmente, é recomendada uma instalação limpa.
Se ainda assim quiser tentar fazer uma atualização, certifique-se de ter um backup de todos os seus dados.

> Observe: ferramentas gráficas como o Discover e o dnfdragora não atualizarão o OMLx 4.0 para o OMLx 4.1. Nenhum desses gerenciadores gráficos de pacotes possui a capacidade de realizar esse tipo de atualização, chamada de "distribution upgrade". **Tentar fazer isso danificará seu sistema**.
{.is-danger}


Isso requer um `dnf --allowerasing distro-sync` e não um `dnf upgrade`. Além disso, existem algumas complicações adicionais de dependências que exigem que isso seja um procedimento único realizado pela linha de comando, conforme descrito a seguir:
 ```
$ sudo dnf remove java-12-openjdk && sudo dnf --refresh --best --allowerasing distro-sync
```

Há mais alterações e detalhes explicados [aqui](https://forum.openmandriva.org/t/3313)


# Errata
Veja [4.1/Errata](/releases/omlx41/errata).

# Ajudando o Projeto
![om-donate.svg](/images/om-donate.svg){.align-left}As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e também na correção de bugs e nos testes. Você é bem-vindo para se juntar a nós e ajudar neste trabalho, que não é apenas gratificante, mas também muito divertido!

Se você sente que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto ao envio de trabalhos artísticos e traduções. Novos colaboradores que gostariam de ajudar nessas tarefas tão variadas devem consultar a wiki para obter mais detalhes e saber como participar! Como alternativa, você pode usar nosso [Fórum](http://forum.openmandriva.org/).

Isso também exige tempo e dinheiro para manter nossos servidores funcionando. Se puder, faça uma [doação](https://www.openmandriva.org/donate) para manter as luzes acesas!
