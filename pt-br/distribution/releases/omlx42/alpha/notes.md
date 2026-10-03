---
title: Notas de Lançamento OpenMandriva Lx 4.2 Alpha
description: 
published: true
date: 2021-09-26T20:56:22.393Z
tags: 4.2
editor: markdown
dateCreated: 2020-03-07T19:54:49.634Z
---

# Notas de Lançamento OpenMandriva Lx 4.2 Alpha

> AVISO: Este é um produto de desenvolvimento [alpha](/releases/software-release-life-cycle#alpha), e não deve ser aplicado em ambientes de produção. Ele é lançado para fins de teste e procura de bugs. Pode, e provavelmente vai ter, problemas. Se baixar e testar esse produto, por favor reportar suas descobertas no [Fórum](http://forum.openmandriva.org/) e em nosso [Github Issues](https://github.com/OpenMandrivaAssociation/OpenMandrivaAssociation.github.io/issues).
{.is-warning}


## Mídias disponíveis
Esta versão está disponível como DVD de mídia Live ou pendrive USB (dispositivo de armazenamento), para download no formato ISO. Esses arquivos estão disponíveis em nossa [página de downloads] (https://www.openmandriva.org/en/download). A instalação a partir de um pendrive USB geralmente é consideravelmente mais rápida. Como sempre, a velocidade depende de vários fatores.
*Live media* significa que você pode executar o OpenMandriva Lx diretamente a partir de um DVD ou pendrive (veja abaixo) e experimentá-lo antes de instalá-lo. Você também pode instalar o sistema no disco rígido, seja a partir da imagem Live em execução ou pelo gerenciador de inicialização.

Arquivos ISO estão disponíveis:
- x86_64 [KDE Plasma] (https://www.kde.org/plasma-desktop) ambiente de desktop completo e repleto de recursos (inclui as funcionalidades mais utilizadas, além de softwares multimídia e de escritório).
- znver1 Plasma: também compilamos uma versão especificamente para os atuais processadores AMD (Ryzen, ThreadRipper e EPYC), que oferece desempenho superior à versão genérica (x86_64) ao aproveitar novos recursos presentes nesses processadores.
znver1 é para os processadores listados (Ryzen, ThreadRipper, EPYC) somente, nao instale em nenhum outro hardware.

## Requerimentos do sistema

O OpenMandriva Lx 4.2 requer pelo menos 2,0 GB de memória RAM e 10 GB de espaço no disco rígido (veja abaixo os problemas conhecidos relacionados ao particionamento).

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

## instalador Calamares

O Calamares é um framework de instalação.
Por definição, ele é altamente personalizável, de modo a atender a uma ampla variedade de necessidades e casos de uso. Seu objetivo é ser fácil de usar, acessível, bonito, pragmático, inclusivo e independente da distribuição.
O Calamares inclui um recurso avançado de particionamento, com suporte tanto para operações de particionamento manuais quanto automatizadas.
Ele é o primeiro instalador a oferecer uma opção automatizada de “Substituir partição”, que facilita reutilizar uma partição repetidamente para testar diferentes distribuições.
Muitas distribuições Linux utilizam o instalador Calamares, e cada uma possui sua própria implementação e seus próprios padrões. O fato de algo no instalador do OpenMandriva não corresponder à experiência do usuário com outra distribuição Linux não significa que seja um bug.

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

Alguns SSDs NVMe podem não ser reconhecidos pela ISO *Live* do OMLx 4.2.
A ISO *Live* possui 2 soluções para isso em “Troubleshooting”, no menu do Grub2. Elas são `(PCIE ASPM=OFF)` e `(NVME APST=OFF)`. Esperamos que isso funcione com a maioria dos hardwares. O problema é conhecido e está sendo resolvido pelos desenvolvedores do OpenMandriva e do projeto upstream. Veja mais em [4.2/Errata#NVME SSDs](/releases/omlx42/errata/nvme-ssds).
O reconhecimento de SSDs nvme  mais recentes deve ser consideravelmente melhor. Sabe-se que alguns SSDs NVMe da Samsung que antes não eram reconhecidos agora funcionam com esta versão do kernel. Esse problema é específico por  hardware.

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

## Inicializando atravẽs do USB

Também ẽ possível inicializar esta versão a partir de um dispositivo de armazenamento USB. Para transferir a imagem Live/de instalação, você pode:

### - Usar o ROSA image Writer disponível em nossos repositórios

`sudo dnf --refresh install rosa-imagewriter`

Ou, se você não tiver o OpenMandriva Lx instalado, poderá obter os links para baixar o ROSA Image Writer [nesta página](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter).
Recomenda-se uma unidade flash com capacidade de pelo menos 4 GB. O armazenamento persistente não é necessário. Observe que isso **apagará** tudo do seu USB!

> Não use outras ferramentas de gravação USB, pois algumas ferramentas do Windows ( Rufus, por exemplo) truncam o nome do volume. Isso interrompe o processo de inicialização. 
{.is-danger}

### - Via dd

Como alternativa, você pode usar dd para gravar a imagem no seu pendrive:
`$ sudo dd if=<iso_name>of=<usb_drive> bs=4M status=progress conf=fsync`

Substitua`<iso_name>` com o caminho da ISO e `<usb_drive>` com o node do dispositivo USB, exemplo. `/dev/sdb`.

O SUSE Studio ImageWriter também foi testado e funciona para gravar imagens ISO em dispositivos de armazenamento USB.

## Inicializando atravẽs do arquivo ISO

Entrada do Grub2 a ser adicionada em `/boot/grub2/grub.cfg`
```
submenu "OpenMandriva (64 bit)" {
        set isofile=/home/user/OpenMandrivaLx.4.2-plasma.x86_64.iso
        set isoname=OpenMandrivaLx_4.2
        loopback loop $isofile

        menuentry "OpenMandriva" {
                linux (loop)/boot/vmlinuz0 root=live:LABEL=${isoname} iso-scan/filename=${isofile} rd.live.image toram --
                initrd (loop)/boot/liveinitrd.img
        }
}
```

## Sobre os repositórios

Temos agora o [om-repo-picker](/policies/images/repositoriesomlx4.1-tldrrepopiker.jpg) também chamado Seletor de Repositórios de Software, para selecionar repositórios adicionais e aumentar a disponibilidade de pacotes.
**Não misture repositórios de diferentes versões/canais de atualização**. Isso significa, por exemplo, não usar repositórios Cooker em um sistema Rock. Se usar Rock, use apenas repositórios Rock. Isso é explicado com mais detalhes em [Plano de Lançamento e Repositórios do OpenMandriva](/doc/release-plan-and-repositories). 
**Se você misturar repositórios de diferentes versões/canais de atualização e quebrar o computador, a solução serã fazer uma nova instalação.**. Depois de uma instalação limpa, não faça isso novamente.

## Como instalar novos pacotes
Mesmo que as ferramentas gráficas (Discover, dnfdragora, etc.) sejam úteis para descobrir programas extras disponíveis, nós recomendamos a instalação de pacotes através da linha de comando
`$ sudo dnf --refresh install <package_name>`

## Como atualizar o sistema
Observe que, nas versões de desenvolvimento, o ‘Update channel’ está definido como Rolling por padrão.
O comando recomendado para atualizar um sistema Rolling é:
`$ sudo dnf clean all ; sudo dnf --allowerasing distro-sync`

## Novos Recursos e Principais Mudanças

Para acompanhar as mudanças mais recentes no Linux, problemas de segurança e alterações no código-fonte, há grandes mudanças no OMLx4.2.

Principais mudanças:
- O kernel foi atualizado para a versão 5.7.8
- Qt foi atualizado para o 5.15.0
- Produtos do Plasma foram atualizados: Frameworks 5.72.0, Plasma Desktop 5.19.3, Applications 20.04.3
- *Leia mais em* [Novidades](/en/releases/omlx42/new)


# Errata
Veja [4.2/Alpha/Errata](/en/releases/omlx42/alpha/errata).


.

