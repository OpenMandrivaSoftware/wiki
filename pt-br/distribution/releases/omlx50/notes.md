---
title: Notas de lançamento OpenMandriva Lx 5.0
description: 
published: true
date: 2024-08-29T07:47:55.753Z
tags: 5.0
editor: markdown
dateCreated: 2022-12-26T18:06:59.977Z
---

# Notas de lançamento OpenMandriva Lx 5.0

O time do OpenMandriva Lx tem o prazer de anunciar a disponibilidade do **OpenMandriva Lx 5.0**.
<br>

## Mídias disponíveis
Esta versão está disponível como mídia Live USB (pendrive), para download em formato ISO. As imagens estão disponíveis em nossa página de downloads. A instalação via USB costuma ser muito rápida. A velocidade depende de vários fatores. A mídia Live permite executar o OpenMandriva Lx diretamente do pendrive (veja abaixo) e testá-lo antes da instalação. Também é possível instalar o sistema no disco rígido a partir da imagem Live ou do gerenciador de inicialização.

**Arquivos ISO disponíveis:**
- *x86_64 desktop KDE Plasma* completo (inclui as funcionalidades mais utilizadas, além de softwares multimídia e de escritório).
- *znver1 KDE Plasma desktop*: também criamos uma versão específica para os processadores AMD atuais (Ryzen, ThreadRipper, EPYC), que supera a versão genérica (x86_64) aproveitando novos recursos desses processadores. znver1 é destinado apenas aos processadores listados (Ryzen, ThreadRipper, EPYC); não instale em outro hardware.

Imagens instaláveis estarão disponíveis para Pinebook Pro, Raspberry Pi 4B, Raspberry Pi 3B+, Synquacer, Cubox Pulse e dispositivos compatíveis com UEFI (como a maioria das placas de servidor aarch64).
<br>

## Requerimentos do sistema
O OpenMandriva Lx 5.0 requer pelo menos 2048 MB de memória e *pelo menos* 10 GB de espaço no disco rígido, recomenda-se 20 GB para uma instalação completa do desktop Plasma.

*Observação importante: Hardware gráfico:*
O desktop KDE Plasma requer uma placa gráfica 3D compatível com OpenGL 2.0 ou superior. Recomendamos o uso de chips gráficos AMD, Intel, Adreno ou VC4.
<br>

## Conexão com a internet
O instalador Calamares verifica se há uma conexão com a Internet disponível, mas o OpenMandriva 5.0 será instalado normalmente mesmo sem ela. Não há problema algum em simplesmente instalar como você faria normalmente e continuar usando seu novo sistema normalmente. Para atualizar esse sistema, seria necessário conectar-se temporariamente à Internet ou baixar os pacotes em outro local, transferi-los para o sistema instalado e instalar os pacotes atualizados. Mas, como você não está conectado à Internet, pode simplesmente usar o sistema e não atualizá-lo pelo tempo que considerar adequado.
<br>

## Máquinas Virtuais
No momento, os únicos softwares de virtualização nos quais as ISOs do OpenMandriva 5.0 são testadas são no VirtualBox. Os mesmos requisitos de hardware se aplicam ao executar em máquinas virtuais. No VirtualBox, você deve sempre ter pelo menos 2048 MB de memória, caso contrário o OMLx 5.0 não conseguirá inicializar. Além disso, para o VirtualBox, é recomendável instalar em uma máquina virtual nova, pois tentar instalar em uma existente pode ocasionalmente falhar.
A ISO do GNOME pode exigir que o controlador gráfico VMSVGA seja configurado para que seja exibida corretamente e inicialize adequadamente no VirtualBox, assim como pode ocorrer com as imagens de instalação mais recentes.
<br>

## Instalador Calamares
O Calamares é uma estrutura de instalação. Por design, é altamente personalizável para atender a uma ampla variedade de necessidades e casos de uso. Seu objetivo é ser fácil, funcional, bonito, pragmático, inclusivo e independente da distribuição. O Calamares oferece particionamento avançado, com suporte a operações manuais e automatizadas. É o primeiro instalador com a opção automatizada “Replace Partition”, facilitando a reutilização de uma partição para testes de distribuições. Muitas distribuições Linux usam o Calamares, cada uma com sua própria implementação e padrões. Pequenas diferenças podem ser percebidas, mas isso não significa que seja um bug.
<br>

## Particionamento
No momento, o particionamento de configurações LVM e RAID com o instalador Calamares não é compatível.

O seguinte se aplica a todos os particionamentos de todas as instalações em hardware: se você tiver um computador UEFI/EFI e o BIOS oferecer uma opção ao inicializar a mídia de instalação, por exemplo, entre:

`USB some Flash Drive`
`UEFI USB some Flash Drive`


Você deve escolher a opção UEFI e inicializá-la. Mas saiba que nem todos os computadores fazem isso. Alguns com FIRMWARE ou BIOS mais simples oferecem apenas uma opção, que quase sempre é a correta. Portanto, se em um notebook você não vir a opção acima, não se preocupe.
*Se houver várias unidades de armazenamento habilitadas, todas precisam ter o mesmo tipo de tabela de partição.* Elas devem ser todas GPT ou todas MBR para que tudo funcione corretamente.
Em computadores UEFI com vários sistemas e várias unidades de armazenamento, se já houver uma partição `/boot/efi`, use-a. O particionador não criará outra `/boot/efi` e a instalação resultará em erro sem um bootloader instalado. Não formate; apenas defina o ponto de montagem como `/boot/efi` e selecione a flag `boot`. É possível ter vários bootloaders para diferentes sistemas operacionais na mesma partição `/boot/efi`. Se for necessário trocar o bootloader, isso é feito nas configurações do FIRMWARE ou BIOS.
<br>


## Tipo de sistema de arquivos
No instalador Calamares do OpenMandriva 5.0, a lista de sistemas de arquivos inclui todos os sistemas de arquivos que o sistema operacional reconhece por diversos motivos. Isso não significa que se deva utilizar qualquer um dos sistemas da lista para a partição raiz (`/`). `ext4` é a recomendação oficial para a raiz, `fat32` é a recomendação para `/boot/efi`.

`btrfs`, `f2fs` e `xfs` estão funcionando em testes recentes, mas são testados com muito menos frequência. Dependemos do feedback dos usuários para isso. Com base nos testes recentes, `btrfs` não é uma boa escolha para cenários de inicialização múltipla.

**Outros tipos de sistemas de arquivos da lista não são recomendados.**

No momento, não há uma recomendação oficial para partições de armazenamento ou para uma partição `/home` separada. Espera-se que os usuários que utilizam partições de armazenamento separadas ou uma partição `/home` separada saibam o que estão fazendo. Para `/home`, a maneira mais simples é usar `ext4` (recomendado) ou o mesmo sistema de arquivos usado na partição root.
<br>

## NVME SSDs
Os SSDs NVMe normalmente são reconhecidos pela ISO Live do OpenMandriva 5.0. Se, por algum motivo, eles não forem reconhecidos, temos algumas soluções alternativas em 'Solução de problemas' no menu Grub2 da ISO que podem funcionar. Elas são (PCIE ASPM=OFF) e (NVME APST=OFF). Esperamos que isso funcione para a maioria dos hardwares. Veja mais em Errata/SSDs NVMe. Esse problema, naturalmente, é muito específico de cada hardware.
<br>

## Instalador e Suporte EFI
Esta versão do OpenMandriva 5.0 oferece suporte à inicialização e instalação com e sem UEFI.

*Observe que o Secure Boot NÃO é suportado.*
*Observe que NÃO é recomendado misturar partições MBR e GPT.*

Se você deseja realizar uma instalação EFI em um disco MBR existente, será necessário converter a tabela de partições do disco para o esquema de particionamento GPT mais recente. Para isso, é necessário usar a ferramenta gdisk. Uma chamada típica seria `gdisk /dev/sda`: a tabela de partições existente será convertida em memória para o esquema GPT. Serão exibidos avisos sobre possível perda de dados; o disco não será alterado até que você grave a tabela de partições pressionando `w`. Recomenda-se fazer backup de todos os dados importantes.

Pode haver situações em que a conversão não possa ser realizada, geralmente devido a espaço insuficiente no início ou no final do disco para gravar a tabela de partições. Pode ser necessário excluir ou redimensionar uma partição para criar o espaço necessário. O gparted é seu amigo nessas circunstâncias.

Ainda é necessário criar uma partição `/boot/efi` para conter o equipamento de inicialização, e isso deve ser feito durante a execução do instalador Calamares. Quando o instalador chegar à etapa de particionamento, a partição `/` (raiz) deve ser removida e uma pequena partição fat32 (300 MB) deve ser criada no início do disco. A partição deve ser denominada `/boot/efi` e a flag `boot` deve ser definida. Se o espaço em disco for crítico, uma partição menor poderá ser usada, mas certifique-se de defini-la como fat32 no Calamares; caso contrário, a instalação falhará. Se você não seguir estas etapas, a instalação do bootloader falhará. Em seguida, particione o disco normalmente.

Compartilhe suas experiências nos fóruns para que possamos melhorar este aspecto da instalação.

Se você estiver instalando junto com Windows 8, 8.1, 10 ou um sistema operacional EFI semelhante, por precaução, certifique-se de ter discos de recuperação e de ter feito backup de todos os dados importantes. Nossos testes foram limitados com essa configuração, mas instalações bem-sucedidas foram realizadas sem problemas.
Agradecemos qualquer feedback sobre esse assunto.
<br>

## Alterando o tipo de partição
Observe que o Calamares não pode converter um tipo de partição em outro preservando os dados da partição. Se você executar o Calamares para alterar um tipo de partição existente, primeiro deverá excluir a partição e recriá-la com o tipo desejado.
<br>

## Inicialização através do USB
É possível inicializar esta versão a partir de um dispositivo de armazenamento USB. Para criar a mídia live/de instalação, você pode:

- Usar a ferramenta isowriter disponível em nossos repositórios:

`sudo dnf --refresh install rosa-imagewriter`

Ou, se você não tiver o OpenMandriva Lx instalado, poderá obter os links para baixar o rosa-imagewriter [nesta página](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter).
Recomenda-se uma unidade flash com capacidade de pelo menos 4 GB. O armazenamento persistente não é necessário. Observe que isso apagará tudo do seu USB!

> Não use outras ferramentas de gravação USB, pois algumas ferramentas do Windows ( Rufus, por exemplo) truncam o nome do volume. Isso interrompe o processo de inicialização. 
{.is-danger}

- Via dd
Como alternativa, você pode gravar a imagem com dd no seu pendrive USB:

`sudo dd if=<iso_name> of=<usb_drive> bs=4M conv=fdatasync status=progress`

Substitua <iso_name> pelo caminho para a ISO e <usb_drive> pelo nó de dispositivo da unidade USB, ou seja, /dev/sdb.

- O SUSE Studio ImageWriter e o Balena Etcher também foram testados e funcionam para gravar imagens ISO em dispositivos de armazenamento USB.
<br>

## Inicialização a partir de DVD
A inicialização por DVD está obsoleta, mas as ISOs do OpenMandriva 5.0 ainda inicializam a partir de DVD usando inicialização Legacy ou UEFI. Caso encontre dificuldades, existem 2 soluções alternativas [aqui](https://forum.openmandriva.org/t/4377) que devem permitir a inicialização pelo DVD. Nos testes, a inicialização do OMLx 5.0 pelo DVD levou de 5-6 minutos. Em alguns hardwares pode demorar mais. Usar um DVD para esse fim é muito mais lento do que usar uma unidade flash USB.
<br>

## Sobre os repositórios
Temos o [om-repo-picker](/policies/repositories-tldr) também chamado Seletor de Repositórios de Software, para selecionar repositórios adicionais e aumentar a disponibilidade de pacotes.
**Não misture repositórios de diferentes versões/canais de atualização**. Isso significa, por exemplo, não usar repositórios Cooker em um sistema OMLx 5.0. Se usar Rock, use apenas repositórios Rock. Isso é explicado com mais detalhes em [Plano de Lançamento e Repositórios do OpenMandriva](/policies/release-plan-and-repositories). Se você misturar repositórios de diferentes versões/canais de atualização e quebrar o computador, a solução é fazer uma nova instalação. Depois de uma instalação limpa, não faça isso novamente.
<br>

## Como instalar e remover pacotes
Embora as ferramentas gráficas (Discover, dnfdragora etc.) sejam úteis para encontrar softwares adicionais disponíveis, recomendamos instalar e remover pacotes pela linha de comando:

`sudo dnf --refresh install <package_name>`

Para remover um pacote:

`sudo dnf remove <package_name>`

É possível instalar ou remover vários pacotes de uma só vez. Exemplo:

`sudo dnf --refresh install <package_name_1> <package_name_2> <package_name_3> <package_name_4>`

Mais informações sobre gerenciamento de pacotes com dnf [aqui](https://dnf.readthedocs.io/en/latest/command_ref.html).
<br>

## Procedimento recomendado de atualização
Isso é muito fácil, basta copiar e colar esta sequência de comandos:

`sudo dnf clean all ; sudo dnf --allowerasing distro-sync`

Pressione Enter e, quando solicitado, digite a senha de root (superusuário).
Recomendamos isso porque vemos muitos relatos de problemas que começam com "*atualizei meu sistema com o Discover updater*" ou "*atualizei meu sistema com dnfdragora*".
<br>


## Servidor de som padrão alterado para PipeWire
[*Pipewire*](https://pipewire.org/) tornou-se nosso servidor de som padrão, juntamente com o WirePlumber, substituindo o PulseAudio.
No entanto, o PulseAudio ainda está disponível em nosso repositório e você pode voltar a usá-lo a qualquer momento. Para isso, use esta sequência de comandos:

`sudo dnf remove pipewire-pulse ; sudo dnf install pulseaudio-server`

<br>

## Kernel compilado com Clang
O kernel padrão do OpenMandriva Lx 5.0 é compilado com clang.

Há versões kernel-desktop-gcc e kernel-server-gcc disponíveis caso sejam necessárias.
<br>

## Hardware gráfico Nvidia
Isso é discutido na página de Errata do OpenMandriva Lx 5.0.
<br>

## O que fazer se eu tiver um problema
Caso tenha problemas, informe-os no [fórum de suporte em inglês](https://forum.openmandriva.org/c/support/17) usando um título descritivo e informações suficientes para que alguém possa ajudar. Ou, para obter resultados mais rápidos, entre em contato pelo [OpenMandriva Chat](team/chat). Se o problema for técnico e grave, [registre um relatório de bug](https://github.com/OpenMandrivaAssociation/distribution/issues).

<br>

## Errata
Por favor, leia também as [OpenMandriva Lx 5.0 Errata](/distribution/releases/omlx50/errata).
<br>

## O que há de novo
Você pode dar uma olhada nas [últimas alterações](/distribution/releases/omlx50/new)
<br>

## Ajudando o Projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e nos testes e correções. Você é bem-vindo para se juntar a nós e ajudar nesse trabalho, que não é apenas gratificante, mas também muito divertido! Se você acha que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto a contribuições de arte e traduções. Novos colaboradores interessados nessas tarefas devem consultar a wiki para mais detalhes e saber como participar! Como alternativa, você pode usar nosso [fórum](https://forum.openmandriva.org).
<br>

## Doe para o projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}Também é necessário tempo e dinheiro para manter nossos servidores funcionando. Se puder, [faça uma doação](https://www.openmandriva.org/en/Donate) para manter as luzes acesas!
<br>

![header-tr-50.svg](/assets/header-tr-50.svg){.align-abstopright}
