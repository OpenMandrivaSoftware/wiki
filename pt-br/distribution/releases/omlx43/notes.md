---
title: Notas de lançamento do OpenMandriva Lx 4.3
description: 
published: true
date: 2023-01-05T21:28:39.589Z
tags: 4.3
editor: markdown
dateCreated: 2021-04-24T05:18:09.972Z
---

# Notas de lançamento do OpenMandriva Lx 4.3

O time do OpenMandriva Lx tem o prazer de anunciar que o **OpenMandriva Lx 4.3** está disponível.

**Mídias disponíveis**

Esta versão está disponível como mídia Live USB (pendrive), para download em formato ISO. As imagens estão disponíveis em nossa página de downloads. A instalação via USB costuma ser muito rápida. A velocidade depende de vários fatores. A mídia Live permite executar o OpenMandriva Lx diretamente do pendrive (veja abaixo) e testá-lo antes da instalação. Também é possível instalar o sistema no disco rígido a partir da imagem Live ou do gerenciador de inicialização.

- Arquivos ISO estão disponíveis:
\- *x86_64 desktop KDE Plasma* completo (inclui as funcionalidades mais utilizadas, além de softwares multimídia e de escritório).
\- *znver1 KDE Plasma desktop*: também criamos uma versão específica para os processadores AMD atuais (Ryzen, ThreadRipper, EPYC), que supera a versão genérica (x86_64) aproveitando novos recursos desses processadores. znver1 é destinado apenas aos processadores listados (Ryzen, ThreadRipper, EPYC); não instale em outro hardware.

Imagens instaláveis estão disponíveis para Pinebook Pro, Raspberry Pi 4B, Raspberry Pi 3B+, Synquacer, Cubox Pulse e dispositivos compatíveis com UEFI (como a maioria das placas de servidor aarch64).

**Requerimentos do sistema**

O OpenMandriva Lx 4.3 requer pelo menos 2048 de memória RAM e 10 GB de espaço no disco rígido (veja abaixo os problemas conhecidos relacionados ao particionamento).

*Nota importante: Hardware gráfico:*

O desktop KDE Plasma requer uma placa gráfica 3D compatível com OpenGL 2.0 ou superior. Recomendamos chips gráficos AMD, Intel, Adreno ou VC4.

**Conexão com a internet**

O instalador Calamares verifica se há uma conexão com a Internet disponível, mas o OpenMandriva Lx será instalado normalmente mesmo sem conexão. Não há problema algum em simplesmente fazer a instalação como de costume e, em seguida, utilizar o novo sistema normalmente. Para atualizar um sistema desse tipo, seria necessário conectar-se temporariamente à Internet ou baixar os pacotes em outro local, transferi-los para o sistema instalado e instalar os pacotes atualizados. Porém, como você não está conectado à Internet, pode simplesmente utilizar o sistema sem atualizá-lo pelo tempo que considerar adequado.

**Máquinas Virtuais**

Até o momento o único software de virtualização em que as imagens ISO do OMLx foram testadas é o VirtualBox. Os mesmos requerimentos de sistemas se aplicam quando rodando em máquinas virtuais. Para o VirtualBox você deverá sempre ter no mínimo 2048MB de memória ou o sistema vai falhar na inicialização. Também para o VirtualBox, é recomendável instalar em uma máquina virtual nova, pois tentar instalar em uma máquina virtual existente pode ocasionalmente apresentar falhas.

**Instalador Calamares**

O Calamares é uma estrutura de instalação. Por design, é altamente personalizável para atender a uma ampla variedade de necessidades e casos de uso. Seu objetivo é ser fácil, funcional, bonito, pragmático, inclusivo e independente da distribuição. O Calamares oferece particionamento avançado, com suporte a operações manuais e automatizadas. É o primeiro instalador com a opção automatizada “Replace Partition”, facilitando a reutilização de uma partição para testes de distribuições. Muitas distribuições Linux usam o Calamares, cada uma com sua própria implementação e padrões. Pequenas diferenças podem ser percebidas, mas isso não significa que seja um bug.

**Particionamento**

No momento, o particionamento de configurações LVM e RAID com o instalador Calamares não é compatível.

O seguinte se aplica a todos os particionamentos de todas as instalações em hardware: se você tiver um computador UEFI/EFI e o BIOS oferecer uma opção ao inicializar a mídia de instalação, por exemplo, entre:

`USB some Flash Drive`
`UEFI USB some Flash Drive`


Você deve escolher a opção UEFI e inicializá-la. Mas saiba que nem todos os computadores fazem isso. Alguns com FIRMWARE ou BIOS mais simples oferecem apenas uma opção, que quase sempre é a correta. Portanto, se em um notebook você não vir a opção acima, não se preocupe.
*Se houver várias unidades de armazenamento habilitadas, todas precisam ter o mesmo tipo de tabela de partição.* Elas devem ser todas GPT ou todas MBR para que tudo funcione corretamente.
Em computadores UEFI com vários sistemas e várias unidades de armazenamento, se já houver uma partição `/boot/efi`, use-a. O particionador não criará outra `/boot/efi` e a instalação resultará em erro sem um bootloader instalado. Não formate; apenas defina o ponto de montagem como `/boot/efi` e selecione a flag `boot`. É possível ter vários bootloaders para diferentes sistemas operacionais na mesma partição `/boot/efi`. Se for necessário trocar o bootloader, isso é feito nas configurações do FIRMWARE ou BIOS.

**Atualizando um sistema OMLx 4.2 para OMLx 4.3**

Veja [Atualizando o OMLx 4.2 para o sistema OMLx 4.3](https://forum.openmandriva.org/t/upgrading-omlx-4-2-system-to-omlx-4-3/4338)

**Tipo de sistema de arquivos**

No instalador Calamares do OMLx (todas as ramificações), a lista de sistemas de arquivos inclui todos os sistemas de arquivos reconhecidos pelo sistema operacional por diversos motivos. Isso não significa que se deva usar qualquer um dos sistemas listados para a partição raiz (`/`). `ext4` é a recomendação oficial para a raiz, enquanto fat32 é a recomendação para `boot/efi`. `f2fs` *deve* funcionar para a partição raiz se o usuário estiver usando um dispositivo de armazenamento flash (SSD). ***Exemplo***: espera-se que os usuários que instalarem um sistema operacional OMLx saibam que não devem escolher fat16 ou fat32 para a partição raiz. Da mesma forma, não se deve usar ext4 para uma partição `/boot/efi`.

`btrfs` e `xfs` não funcionarão como sistema de arquivos da partição do sistema (raiz) no OMLx 4.3. Isso será corrigido na próxima versão. Pedimos desculpas por qualquer inconveniente.

No momento, não há recomendação oficial para partições de armazenamento ou para uma partição `/home` separada. Espera-se que os usuários que utilizam partições de armazenamento separadas ou uma partição `/home` separada saibam o que estão fazendo. Para `/home`, o mais fácil é usar o mesmo sistema de arquivos da partição raiz.

**NVME SSDs**

Alguns SSDs NVMe podem não ser reconhecidos pela ISO Live do OMLx 4.3. A ISO Live possui duas soluções alternativas diferentes para esse problema em **"Troubleshooting"** no menu do Grub2. São elas **(PCIE ASPM=OFF)** e **(NVME APST=OFF)**. Esperamos que isso funcione para a maioria dos hardwares dos usuários. O problema é conhecido e está sendo investigado pelos desenvolvedores do OpenMandriva e pelos desenvolvedores do upstream. Consulte mais informações em Errata/SSDs NVMe. O reconhecimento de hardware para SSDs NVMe foi consideravelmente aprimorado no OMLx 4.3. Esse problema, é claro, é bastante específico de cada hardware.

**Instalador e Suporte EFI**

Esta versão do OpenMandriva Lx oferece suporte à inicialização e instalação com e sem UEFI.

*Observe que o Secure Boot NÃO é suportado.*
*Observe que NÃO é recomendado misturar partições MBR e GPT.*

Se você deseja realizar uma instalação EFI em um disco MBR existente, será necessário converter a tabela de partições do disco para o esquema de particionamento GPT mais recente. Para isso, é necessário usar a ferramenta gdisk. Uma chamada típica seria `gdisk /dev/sda`: a tabela de partições existente será convertida em memória para o esquema GPT. Serão exibidos avisos sobre possível perda de dados; o disco não será alterado até que você grave a tabela de partições pressionando `w`. Recomenda-se fazer backup de todos os dados importantes.

Pode haver situações em que a conversão não possa ser realizada, geralmente devido a espaço insuficiente no início ou no final do disco para gravar a tabela de partições. Pode ser necessário excluir ou redimensionar uma partição para criar o espaço necessário. O gparted é seu amigo nessas circunstâncias.

Ainda é necessário criar uma partição `/boot/efi` para conter o equipamento de inicialização, e isso deve ser feito durante a execução do instalador Calamares. Quando o instalador chegar à etapa de particionamento, a partição `/` (raiz) deve ser removida e uma pequena partição fat32 (300 MB) deve ser criada no início do disco. A partição deve ser denominada `/boot/efi` e a flag `boot` deve ser definida. Se o espaço em disco for crítico, uma partição menor poderá ser usada, mas certifique-se de defini-la como fat32 no Calamares; caso contrário, a instalação falhará. Se você não seguir estas etapas, a instalação do bootloader falhará. Em seguida, particione o disco normalmente.

Compartilhe suas experiências nos fóruns para que possamos melhorar este aspecto da instalação.

Se você estiver instalando junto com Windows 8, 8.1, 10 ou um sistema operacional EFI semelhante, por precaução, certifique-se de ter discos de recuperação e de ter feito backup de todos os dados importantes. Nossos testes foram limitados com essa configuração, mas instalações bem-sucedidas foram realizadas sem problemas.
Agradecemos qualquer feedback sobre esse assunto.

**Alterando o tipo de partição**

Observe que o Calamares não pode converter um tipo de partição em outro preservando os dados. Se você executar o Calamares a partir da imagem Live, não será possível alterar o tipo de uma partição existente.
Tentar fazer isso gera uma mensagem de erro.  Para isso, primeiro exclua a partição e recrie-a com o tipo desejado.

**Inicialização através do USB**

Também ẽ possível inicializar esta versão a partir de um dispositivo de armazenamento USB. Para transferir a imagem Live/de instalação, você pode:

- Usar o rosa-imagewriter disponível em nossos repositórios:

`sudo dnf --refresh install rosa-imagewriter`

Ou, se você não tiver o OpenMandriva Lx instalado, poderá obter os links para baixar o rosa-imagewriter [nesta página](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter). Recomenda-se uma unidade flash com capacidade de pelo menos 4 GB. O armazenamento persistente não é necessário. Observe que isso apagará tudo do seu USB!

Por favor, não use outras ferramentas de gravação USB, pois algumas ferramentas do Windows ( Rufus, por exemplo) truncam o nome do volume. Isso interrompe o processo de inicialização.

- Via dd
Como alternativa, você pode gravar a imagem com dd no seu pendrive USB:

`$ sudo dd if=<iso_name> of=<usb_drive> bs=4M conv=fdatasync status=progress`

Substitua <iso_name> pelo caminho para a ISO e <usb_drive> pelo nó de dispositivo da unidade USB, ou seja, /dev/sdb.

- O SUSE Studio ImageWriter também foi testado e funciona para gravar imagens ISO em dispositivos de armazenamento USB.

**Inicialização através do DVD**

A inicialização por DVD foi descontinuada. 
Para todas as ISOs do OMLx 4.3, existem alternativas em [Inicializando a ISO do OM Lx 4.3 a partir de DVD](https://forum.openmandriva.org/t/booting-om-lx-4-3-iso-from-dvd/4377) que permitem inicializar a partir de DVD.

**Sobre os repositórios**

Temos agora o om-repo-picker, também chamado Seletor de Repositórios de Software, para selecionar repositórios adicionais e obter mais pacotes disponíveis.  **Não misture repositórios de diferentes versões/canais de atualização**. Isso significa, por exemplo, não usar repositórios Cooker em um sistema Rock. Se você usa Rock, use apenas os repositórios Rock. Isso é explicado em mais detalhes em [Plano de Lançamento e Repositórios do OpenMandriva](https://wiki.openmandriva.org/en/policies/release-plan-and-repositories). Se você misturar repositórios de diferentes versões/canais de atualização e danificar seu computador, a solução é fazer uma instalação limpa. Depois disso, não faça isso novamente.

**Como instalar e remover pacotes**

Embora as ferramentas gráficas (Discover, dnfdragora etc.) sejam úteis para encontrar softwares adicionais disponíveis, nós recomendamos fortemente instalar pacotes pela linha de comando:

`$ sudo dnf --refresh install <package_name>`

Para remover um pacote:

`$ sudo dnf remove <package_name>`

É possível instalar ou remover vários pacotes de uma só vez. Exemplo:

`$ sudo dnf --refresh install <package_name_1> <package_name_2> <package_name_3> <package_name_4>`

Mais informações sobre gerenciamento de pacotes com dnf [aqui](https://dnf.readthedocs.io/en/latest/command_ref.html).

**Procedimento recomendado de atualização**

Embora disponibilizemos as interfaces gráficas do Discover e do dnfdragora para gerenciamento de pacotes, consideramos melhor que os usuários atualizem seu sistema OMLx 4.3/Rock pelo Konsole (ou outro terminal). É muito fácil: basta copiar e colar este comando:

`$ sudo dnf clean all ; sudo dnf upgrade`

Pressione Enter e, quando solicitado, digite a senha de root (superusuário). Recomendamos isso porque vemos muitos relatos de problemas que começam com "atualizei meu sistema com o Discover updater" ou "atualizei meu sistema com dnfdragora".


**Novos Recursos e Principais Mudanças**

Para acompanhar as mudanças mais recentes no Linux, problemas de segurança e alterações no código-fonte, há grandes mudanças no OMLx4.3rc.

*Principais mudanças*:

- O kernel foi atualizado para a versão 5.16.7
- Produtos do KDE foram atualizados: Frameworks 5.90.0, Plasma Desktop 5.23.5, KDE Gear
21.12.2
- Qt 5.15.3 com todos os patches propostos pelo KDE
- Mesa 21.3.5
- FFMPEG to 5.0
Também atualizamos alguns recursos interessantes que não estão na ISO, mas estão disponíveis em nossos repositórios:
-AMDVK 2022.Q1.2 driver oficial AMD Vulkan. É um driver alternativo e pode ser instalado simultaneamente com o RADV. Pode ser usado para melhorar o desempenho ou a estabilidade em alguns jogos no Linux.
-OBS-Studio 27.1.3 software para gravação de vídeo e transmissão ao vivo; finalmente oferece suporte à sessão Wayland. Também oferece suporte à gravação em h264 com VAAPI (codificação de vídeo acelerada por hardware) e também aplicamos patches para oferecer suporte a HEVC-x265 com VAAPI por hardware.
-Blender 3.0.1
-GIMP 2.10.30
-Audacity 3.1.3
-Firefox 96.0
-Steam 1.0.0.72
-LXQt 1.0.0

**Servidor de som padrão alterado para PipeWire**

O PipeWire tornou-se o servidor de áudio padrão na versão atual do sistema, substituindo assim o PulseAudio. No entanto, o PulseAudio ainda está disponível em nosso repositório e você pode voltar a utilizá-lo a qualquer momento.
Consulte a [*Errata do OM Lx 4.3*](https://wiki.openmandriva.org/en/distribution/releases/omlx43/errata)

Nota: O teste de som nas Configurações do Sistema do KDE não funciona com o PipeWire; ele funciona apenas com o PulseAudio.

[*Pipewire*](https://pipewire.org/)

**Kernel compilado com Clang**

A OpenMandriva disponibiliza um kernel compilado em clang. Os usuários podem instalar a mesma versão do pacote kernel-release-desktop e kernel-release-desktop-clang para comparação.

**O que fazer se eu tiver um problema**

Se tiver problemas, relate-os no [fórum de suporte em inglês](https://forum.openmandriva.org/c/en/support), com um título descritivo e informações suficientes para que alguém possa ajudar. Se o problema for técnico e grave, [relate o bug](https://github.com/OpenMandrivaAssociation/distribution/issues).

**Ajudando o Projeto**

![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e nos testes e correções. Você é bem-vindo para se juntar a nós e ajudar nesse trabalho, que não é apenas gratificante, mas também muito divertido! Se você acha que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto a contribuições de arte e traduções. Novos colaboradores interessados nessas tarefas devem consultar a wiki para mais detalhes e saber como participar! Como alternativa, você pode usar nosso [fórum](https://forum.openmandriva.org).

**Doe para o projeto**

![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}It also costs time and money to keep our servers up and running. If you can, please [donate](https://www.openmandriva.org/en/Donate) to keep the lights on!

**Leia também**
[Errata do OMLx 4.3](https://wiki.openmandriva.org/en/distribution/releases/omlx43/errata)
<br>
