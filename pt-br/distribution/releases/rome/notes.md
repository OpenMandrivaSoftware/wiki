---
title: Notas do OpenMandriva ROME
description: Notas do ROME
published: true
date: 2026-04-01T09:43:34.631Z
tags: rome
editor: markdown
dateCreated: 2023-02-28T15:04:40.037Z
---

# Notas do OpenMandriva ROME


As equipes do OpenMandriva têm o prazer de anunciar a disponibilidade do **ROME**, a edição rolling do OpenMandriva destinada à maioria dos usuários.
<br>

## Mídias disponíveis
Esta versão está disponível como uma mídia live em um pendrive USB (memória flash), que pode ser baixada no formato ISO. 
Elas estão disponíveis em nossa página de [downloads](https://www.openmandriva.org/release-picking).
A instalação a partir de um pendrive USB geralmente é bastante rápida. Como sempre, a velocidade depende de vários fatores. 
Mídia live significa que você pode executar o OpenMandriva Lx diretamente de um pendrive (veja abaixo) e experimentá-lo antes de instalá-lo. 
Você também pode instalar o sistema no disco rígido, seja a partir da imagem live em execução ou do gerenciador de inicialização.

**Arquivos ISO disponíveis:**
- *x86_64 desktop KDE Plasma* completo (inclui as funcionalidades mais utilizadas, além de softwares multimídia e de escritório).
- *znver1 desktop KDE Plasma*: é para CPUs AMD (mais recentes que 2017), especialmente para os atuais processadores AMD (Ryzen, ThreadRipper, EPYC), que superam a versão genérica (x86_64) ao aproveitar novos recursos desses processadores. znver1 é destinado somente aos processadores listados (Ryzen, ThreadRipper, EPYC); não instale em nenhum outro hardware.

**Imagens de servidor disponíveis:**
Ao contrário dos arquivos ISO para desktop, as imagens de servidor são executadas somente pela linha de comando e são fornecidas como imagens de disco, em vez de imagens ISO. Dessa forma, elas podem ser usadas em plataformas de virtualização (por exemplo, OpenStack, qemu/kvm, ...) sem necessidade de instalação.
Elas também podem ser instaladas diretamente no hardware: para esse caso de uso, utilize `dd` para transferir a imagem para um dispositivo de armazenamento USB, inicialize pelo dispositivo de armazenamento e use o instalador em modo texto que pode ser encontrado no diretório pessoal do usuário `omv`.
A imagem de servidor é pré-configurada com o usuário `omv` e a senha `omv`. O `cloud-init` é compatível e pode ser usado para executar inicializações em ambientes de nuvem.
- *x86_64 minimal server* Mínima, somente via CLI, imagem para instalações de servidor. Funciona em qualquer dispositivo x86_64.
- *znver1 minimal server* Mínima, somente via CLI, imagem para instalações de servidor, especificamente otimizada para processadores AMD da série Zen (EPYC, Threadripper, Ryzen).
- *aarch64 minimal server* Mínima, somente via CLI, imagem para instalações de servidor. Funciona em qualquer dispositivo aarch64 (ARM64) compatível com inicialização via UEFI. (Imagens que utilizam diferentes carregadores de inicialização podem ser criadas com `os-image-builder`.)

<!--Imagens instaláveis são oferecidas para o Pinebook Pro, Raspberry Pi 4B, Raspberry Pi 3B+, Synquacer, Cubox Pulse e dispositivos genéricos compatíveis com UEFI (como a maioria das placas de servidor arch64)-->
<br>

## Requerimentos do sistema
O ROME requer pelo menos 2048 MB de memória e pelo menos 10 GB de espaço no disco rígido (veja abaixo os problemas conhecidos relacionados ao particionamento). Recomenda-se 20 GB para uma instalação completa do desktop Plasma.

*Hardware gráfico:*

O desktop KDE Plasma requer uma placa gráfica 3D compatível com OpenGL 2.0 ou superior. Recomendamos chips gráficos AMD, Intel, Adreno ou VC4.
<br>

## Conexão com a internet
O instalador Calamares verifica se há conexão com a Internet, mas o ROME será instalado normalmente mesmo sem ela. Basta instalar normalmente e usar o novo sistema. Para atualizar o sistema, será necessário conectá-lo temporariamente à Internet ou baixar os pacotes em outro local, transferi-los para o sistema instalado e instalar as atualizações. Sem conexão com a Internet, você pode simplesmente usar o sistema sem atualizá-lo pelo tempo que desejar.
<br>

## Máquinas Virtuais
No momento, os únicos softwares de virtualização nos quais as ISOs para desktop do OpenMandriva são testadas são o qemu e o VirtualBox. Os mesmos requisitos de hardware se aplicam ao executar em máquinas virtuais. Para o VirtualBox, você deve ter sempre pelo menos 2048 MB de memória, caso contrário o ROME não inicializará. Também para o VirtualBox, é recomendável instalar em uma máquina virtual nova, pois tentar instalar em uma máquina virtual existente pode ocasionalmente falhar.
As imagens de instalação mais recentes podem exigir que o controlador gráfico VMSVGA seja configurado para que a imagem seja exibida corretamente e inicialize adequadamente no VirtualBox.
As imagens de servidor foram testadas em hardware real, no OpenStack e em vários provedores de nuvem.
<br>

## instalador Calamares
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
No instalador Calamares do ROME, a lista de sistemas de arquivos inclui todos os sistemas de arquivos reconhecidos pelo sistema operacional por diversos motivos. Isso não significa que se deva usar qualquer um dos sistemas listados para a partição raiz (`/`). As recomendações oficiais para a raiz e para a pasta pessoal (`/home`) são `ext4` ou `btrfs`; para `boot/efi`, a recomendação é `fat32`.

`f2fs` e `xfs` estão funcionando nos testes recentes, mas são testados com muito menos frequência. Contamos com o feedback dos usuários sobre isso.
O `ext4` ainda é o sistema de arquivos mais rápido para a maioria dos casos de uso típicos, mas não possui alguns dos recursos do `btrfs` (em particular, o uso de snapshots). Como o suporte dos carregadores de inicialização a ele é limitado, o `btrfs` pode não ser uma boa escolha para alguns cenários de inicialização múltipla.

**Outros tipos de sistemas de arquivos da lista não são recomendados.**

É recomendável usar uma partição `/home` separada para que os dados do usuário possam ser preservados mesmo ao reinstalar o sistema ou atualizar para uma nova versão principal por meio de uma reinstalação. `ext4` e `btrfs` são boas opções para isso.
<br>

## Alterando o tipo de partição
Observe que o Calamares não pode converter um tipo de partição em outro e preservar os dados da partição.
Além disso, o Calamares não oferece suporte à leitura ou criação de ZFS devido a questões de licenciamento.

> Se você executar o Calamares para alterar o tipo de uma partição existente, primeiro deverá excluir a partição e recriá-la com o tipo desejado.
{.is-warning}

<br>

## NVME SSDs
SSDs NVME normalmente são reconhecidos pela ISO Live do ROME. Se, por algum motivo, não forem, temos algumas alternativas em 'Troubleshooting' no menu Grub2 da ISO que podem funcionar. São (PCIE ASPM=OFF) e (NVME APST=OFF). Esperamos que isso funcione na maioria dos hardwares. Veja mais em Errata/NVME SSDs. Esse problema, naturalmente, é muito específico de cada hardware.
<br>

## Instalador e Suporte (U)EFI
Esta versão do ROME permite inicialização e instalação com ou sem UEFI.

*Observe que o Secure Boot NÃO é suportado.*
*Observe que NÃO é recomendado misturar partições MBR e GPT.*

Se você deseja realizar uma instalação EFI em um disco MBR existente, será necessário converter a tabela de partições do disco para o esquema de particionamento GPT mais recente. Para isso, é necessário usar a ferramenta gdisk. Uma chamada típica seria `gdisk /dev/sda`: a tabela de partições existente será convertida em memória para o esquema GPT. Serão exibidos avisos sobre possível perda de dados; o disco não será alterado até que você grave a tabela de partições pressionando `w`. Recomenda-se fazer backup de todos os dados importantes.

Pode haver situações em que a conversão não possa ser realizada, geralmente devido a espaço insuficiente no início ou no final do disco para gravar a tabela de partições. Pode ser necessário excluir ou redimensionar uma partição para criar o espaço necessário. O gparted é seu amigo nessas circunstâncias.

Ainda é necessário criar uma partição `/boot/efi` para conter o equipamento de inicialização, e isso deve ser feito durante a execução do instalador Calamares. Quando o instalador chegar à etapa de particionamento, a partição `/` (raiz) deve ser removida e uma pequena partição fat32 (300 MB) deve ser criada no início do disco. A partição deve ser denominada `/boot/efi` e a flag `boot` deve ser definida. Se o espaço em disco for crítico, uma partição menor poderá ser usada, mas certifique-se de defini-la como fat32 no Calamares; caso contrário, a instalação falhará. Se você não seguir estas etapas, a instalação do bootloader falhará. Em seguida, particione o disco normalmente.

Compartilhe suas experiências nos fóruns para que possamos melhorar este aspecto da instalação.

Se você estiver instalando junto com Windows 8, 8.1, 10 ou um sistema operacional EFI semelhante, por precaução, certifique-se de ter discos de recuperação e de ter feito backup de todos os dados importantes. Nossos testes foram limitados com essa configuração, mas instalações bem-sucedidas foram realizadas sem problemas.
Agradecemos qualquer feedback sobre esse assunto.
<br>

## Inicialização através do USB
É possível inicializar esta versão a partir de um dispositivo de armazenamento USB. Para criar a mídia live/de instalação, você pode:

- Usar a ferramenta isowriter disponível em nossos repositórios:

`sudo dnf --refresh install om-imagewriter`

Recomenda-se uma unidade flash com pelo menos 4 GB de capacidade. O armazenamento persistente não é necessário. Observe que isso apagará tudo o que estiver no seu USB!

> **Usuários do Windows:**
Se você usar outras ferramentas de gravação de USB, como algumas ferramentas do Windows (por exemplo, [Rufus](https://rufus.ie/en)), deverá selecionar o modo '`dd`', caso contrário, ele truncará o nome do volume e interromperá o processo de inicialização.
O Balena Etcher é conhecido por funcionar bem para transferir imagens ISO do OpenMandriva para um dispositivo de armazenamento USB.
{.is-danger}

- Via dd
Como alternativa, você pode gravar a imagem com dd no seu pendrive USB:

`sudo dd if=<iso_name> of=<usb_drive> bs=4M conv=fdatasync status=progress`

Substitua <iso_name> pelo caminho para a ISO e <usb_drive> pelo nó de dispositivo da unidade USB, ou seja, /dev/sdb.

- O SUSE Studio ImageWriter e o Balena Etcher também foram testados e funcionam para gravar imagens ISO em dispositivos de armazenamento USB.

- O Ventoy não é totalmente compatível. Em algumas circunstâncias, pode ou não funcionar. Crie a mídia live/de instalação usando um dos métodos recomendados acima. Consulte [ROME Errata](/distribution/releases/rome/errata) para soluções alternativas para o Ventoy.
<br>

## Instalação a partir de USB
Depois de criar sua unidade USB, desligue o computador, conecte-a à porta USB e reinicie.

> Pode ser necessário desconectar/desligar monitores secundários para acessar a tela de login.
{.is-warning}


Se o computador permitir inicialização por USB, selecione o dispositivo a partir do qual deseja iniciar o computador.
Para isso, interrompa o processo normal de inicialização e acesse o menu da BIOS pressionando imediatamente a tecla indicada na mensagem exibida após o início do computador.
Geralmente, as teclas corretas são `Esc`, `Del`, `F12`, `F10`, `F9`, `F8` ou similares.
Se não tiver certeza, pesquise na internet qual tecla é necessária para seu hardware.

Quando o menu aparecer, selecione a entrada correspondente à sua unidade USB.
Entre outras opções, você verá entradas semelhantes a:

`USB some Flash Drive`
`UEFI USB some Flash Drive`

Se você tiver um computador UEFI/EFI, selecione a opção que menciona 'UEFI' e inicialize por ela; caso contrário, o instalador Calamares apresentará apenas opções de BIOS Legacy para instalação.
<br>

## Inicialização a partir de DVD
A inicialização por DVD está obsoleta, mas as ISOs do ROME ainda inicializam a partir de DVD usando inicialização Legacy ou UEFI. Caso encontre dificuldades, existem 2 soluções alternativas [aqui](https://forum.openmandriva.org/t/4377) que devem permitir a inicialização pelo DVD. Nos testes, a inicialização do ROME pelo DVD levou de 5-6 minutos. Em alguns hardwares pode demorar mais. Usar um DVD para esse fim é muito mais lento do que usar uma unidade flash USB.
<br>

## Sobre os repositórios
Temos o [om-repo-picker](/policies/repositories-tldr) também chamado Seletor de Repositórios de Software, para selecionar repositórios adicionais e aumentar a disponibilidade de pacotes.
**Não misture repositórios de diferentes versões/canais de atualização**. Isso significa, por exemplo, não usar repositórios Cooker em um sistema ROME. Se usar Rock, use apenas repositórios Rock. Isso é explicado com mais detalhes em [Plano de Lançamento e Repositórios do OpenMandriva](/policies/release-plan-and-repositories). Se você misturar repositórios de diferentes versões/canais de atualização e quebrar o computador, a solução é fazer uma nova instalação. Depois de uma instalação limpa, não faça isso novamente.
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
> **Não use o dnfdragora para atualizar seu sistema ROME**. O comando que ele utiliza é destinado às versões Rock e não está correto para o ROME.
**O Discover** foi modificado para realizar atualizações usando o dnf diretamente, ignorando seu backend habitual baseado no PackageKit. Esse é um recurso novo e ainda é considerado experimental.
{.is-danger}

A forma recomendada e comprovada de atualizar é usar a linha de comando. É muito fácil: basta copiar e colar esta sequência de comandos:

`sudo dnf clean all ; sudo dnf dsync --allowerasing`

Os usuários também podem atualizar o sistema usando 'System update', disponível no painel de menu das novas instalações ou em 'Menu de Aplicativos>System>System Update'.

Se o usuário tiver problemas com a atualização `dsync`, deverá usar este comando:

`sudo dnf clean all ; sudo dnf dsync --allowerasing 2>&1 | tee dsync.log.txt`

Isso criará o arquivo de log `dsync.log.txt`, que poderá ser anexado à publicação no fórum ou ao relatório de bug. Observe que, se você usar este comando várias vezes, o arquivo será sobrescrito a cada vez. Se precisar de vários logs de transação, renomeie o arquivo após cada execução, por exemplo `dsync1.log.txt`, `dsync2.log.txt` e assim por diante.

*Observação:* `dsync` é um alias para `distro-sync`. Os usuários do Fedora podem estar acostumados a usar `dnf up`, mas o OpenMandriva é diferente. Para instalações do Cooker e do ROME, é altamente recomendável usar `dnf dsync`.

***Observação-2**.* *Seria sensato que os usuários do ROME prestassem atenção a este tópico do fórum sobre grandes atualizações que podem exigir instruções adicionais além das listadas acima. Tentamos manter os usuários informados sobre quando as instruções básicas funcionarão ou quando algumas etapas adicionais poderão ser necessárias.*
### [Atualização principal do ROME esperada](https://forum.openmandriva.org/t/rome-major-upgrade-expected/4707)

<br>

## Servidor de som padrão alterado para PipeWire
[*Pipewire*](https://pipewire.org/) tornou-se nosso servidor de som padrão na versão atual, juntamente com o WirePlumber, substituindo o PulseAudio.
No entanto, o PulseAudio ainda está disponível em nosso repositório e você pode voltar a usá-lo a qualquer momento. Para isso, use esta sequência de comandos:

`sudo dnf rm pipewire-pulse ; sudo dnf in pulseaudio-server`

<br>

## Kernel compilado com Clang
O kernel padrão do ROME é compilado com Clang.
Há versões kernel-desktop-gcc e kernel-server-gcc disponíveis caso sejam necessárias.
<br>

## Hardware gráfico Nvidia
Isso é discutido na página de Errata do ROME
<br>

## Instalação no servidor
O OpenMandriva adota uma abordagem bastante diferente para desktops e servidores: enquanto as versões para desktop são projetadas para serem fáceis o suficiente para que até mesmo um iniciante possa utilizá-las, as versões para servidor pressupõem alguma experiência com o uso da linha de comando, pois, em um servidor típico, uma interface gráfica apenas ocupa espaço e atrapalha.

As imagens de servidor são executadas somente pela linha de comando e são fornecidas como imagens de disco, em vez de imagens ISO. Dessa forma, elas podem ser usadas em plataformas de virtualização (por exemplo, OpenStack, qemu/kvm, ...) sem necessidade de instalação.

Elas também podem ser instaladas diretamente no hardware: para esse caso de uso, utilize `dd` para transferir a imagem para um dispositivo de armazenamento USB, inicialize pelo dispositivo de armazenamento e use o instalador em modo texto que pode ser encontrado no diretório pessoal do usuário `omv`.

A imagem de servidor é pré-configurada com o usuário `omv` e a senha `omv`. O `cloud-init` é compatível e pode ser usado para executar inicializações em ambientes de nuvem.

Dentro do diretório pessoal do usuário `omv`, você encontrará um script chamado `install-openmandriva` — esse script instala a imagem de servidor em outro disco (por exemplo, se você inicializou a partir de um dispositivo USB em um hardware real e deseja instalar no armazenamento permanente). Este é um

Ele vem apenas com os serviços básicos e um servidor SSH já em execução — como administrador de servidor, espera-se que você saiba quais ferramentas precisa e quais prefere usar. A maioria dos softwares de servidor mais comuns, seja `nginx` ou `apache`, `powerdns` ou `bind`, `postgresql` ou `mariadb`, está disponível nos repositórios — a ideia é usar `dnf install` para instalar o que você precisar.
<br>

## O que fazer se eu tiver um problema
Caso tenha problemas, informe-os no [fórum de suporte em inglês](https://forum.openmandriva.org/c/support/17) usando um título descritivo e informações suficientes para que alguém possa ajudar. Ou, para obter resultados mais rápidos, entre em contato pelo [OpenMandriva Chat](team/chat). Se o problema for técnico e grave, [registre um relatório de bug](https://github.com/OpenMandrivaAssociation/distribution/issues).

<br>

## Errata
**Por favor, leia também as [ROME Errata](/distribution/releases/rome/errata).**
<br>

## Registro de alterações
Você pode dar uma olhada nas [últimas alterações](/distribution/releases/rome/new)
<br>

## Ajudando o Projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e nos testes e correções. Você é bem-vindo para se juntar a nós e ajudar nesse trabalho, que não é apenas gratificante, mas também muito divertido! Se você acha que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto a contribuições de arte e traduções. Novos colaboradores interessados nessas tarefas devem consultar a wiki para mais detalhes e saber como participar! Como alternativa, você pode usar nosso [fórum](https://forum.openmandriva.org).
<br>

## Doe para o projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}Também é necessário tempo e dinheiro para manter nossos servidores funcionando. Se puder, [faça uma doação](https://www.openmandriva.org/en/Donate) para manter as luzes acesas!
<br>

![header-tr-rome.svg](/assets/header-tr-rome.svg){.align-abstopright}