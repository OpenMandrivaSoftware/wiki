---
title: Notas de lançamento OpenMandriva Lx 6.0
description: 
published: true
date: 2026-04-01T09:39:21.945Z
tags: 6.0
editor: markdown
dateCreated: 2025-03-10T19:02:54.601Z
---

# Notas de lançamento OpenMandriva Lx 6.0

As equipes do OpenMandriva têm o prazer de anunciar a disponibilidade da edição **OpenMandriva Lx 6.0 Rock**.
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

<!--Imagens instaláveis são oferecidas para o Pinebook Pro, Raspberry Pi 4B, Raspberry Pi 3B+, Synquacer, Cubox Pulse e dispositivos genéricos compatíveis com UEFI (como a maioria das placas de servidor arch64)-->
<br>

## Requerimentos do sistema
O OpenMandriva 6.0 requer pelo menos 2048 MB de memória e pelo menos 10 GB de espaço no disco rígido (veja abaixo os problemas conhecidos relacionados ao particionamento). Recomenda-se 20 GB para uma instalação completa do desktop Plasma.

*Hardware gráfico:*
O desktop KDE Plasma requer uma placa gráfica 3D compatível com OpenGL 2.0 ou superior. Recomendamos o uso de chips gráficos AMD, Intel, Adreno ou VC4.
<br>

## Conexão com a internet
O instalador Calamares verifica se há uma conexão com a Internet disponível, mas o OpenMandriva 6.0 será instalado normalmente mesmo sem ela. Não há problema algum em simplesmente instalar como você faria normalmente e continuar usando seu novo sistema normalmente. Para atualizar esse sistema, seria necessário conectar-se temporariamente à Internet ou baixar os pacotes em outro local, transferi-los para o sistema instalado e instalar os pacotes atualizados. Mas, como você não está conectado à Internet, pode simplesmente usar o sistema e não atualizá-lo pelo tempo que considerar adequado.
<br>

## Máquinas Virtuais
No momento, os únicos softwares de virtualização nos quais as ISOs do OpenMandriva 6.0 são testadas são o qemu e o VirtualBox. Os mesmos requisitos de hardware se aplicam ao executar em máquinas virtuais. No VirtualBox, você deve sempre ter pelo menos 2048 MB de memória, caso contrário o OpenMandriva 6.0 não conseguirá inicializar. Além disso, para o VirtualBox, é recomendável instalar em uma máquina virtual nova, pois tentar instalar em uma existente pode ocasionalmente falhar.
As imagens de instalação mais recentes podem exigir a configuração do controlador gráfico VMSVGA para serem exibidas corretamente e inicializarem adequadamente no VirtualBox.
<br>

## instalador Calamares
O Calamares é uma estrutura de instalação. Por design, ele é altamente personalizável para atender a uma grande variedade de necessidades e casos de uso. Seu objetivo é ser fácil, utilizável, bonito, pragmático, inclusivo e independente de distribuição. O Calamares inclui um recurso avançado de particionamento, com suporte tanto a operações de particionamento manuais quanto automatizadas. É o primeiro instalador com uma opção automatizada de “Substituir partição”, que facilita reutilizar uma partição repetidamente para testes de distribuições. Muitas distribuições Linux utilizam o instalador Calamares e cada uma possui sua própria implementação e seus próprios padrões. O usuário pode perceber algumas pequenas diferenças, mas isso não significa que seja um bug.
<br>

## Particionamento
No momento, o particionamento de configurações LVM e RAID com o instalador Calamares não é compatível.

O seguinte se aplica a todos os particionamentos de todas as instalações em hardware: se você tiver um computador UEFI/EFI e o BIOS oferecer uma opção ao inicializar a mídia de instalação, por exemplo, entre:

`USB some Flash Drive`
`UEFI USB some Flash Drive`


Você deve escolher a opção UEFI e inicializá-la. Mas saiba também que nem todos os computadores farão isso. Alguns, com FIRMWARE ou BIOS mais simples, oferecerão apenas uma opção e, quase sempre, ela será a correta. Portanto, por exemplo, se em um notebook você não vir a opção acima, não se preocupe. *Se você tiver várias unidades de armazenamento habilitadas, todas elas precisarão ter o mesmo tipo de tabela de partições.* Todas precisam ser GPT ou todas MBR para que tudo funcione corretamente. Em computadores UEFI em uma situação de inicialização múltipla com várias unidades de armazenamento, se você já tiver uma partição `/boot/efi` existente, deverá utilizá-la. O particionador não criará outra `/boot/efi` com os sinalizadores corretos e a instalação resultará em um erro, sem nenhum gerenciador de inicialização instalado. Não formate; apenas defina o ponto de montagem como `/boot/efi` e selecione o sinalizador `boot`. É possível ter vários gerenciadores de inicialização diferentes para diferentes sistemas operacionais na mesma partição `/boot/efi`. Se for necessário alternar entre gerenciadores de inicialização, isso deve ser feito nas configurações do FIRMWARE ou BIOS.
<br>

## Tipo de sistema de arquivos
No instalador Calamares do OpenMandriva 6.0, a lista de sistemas de arquivos inclui todos os sistemas de arquivos que o sistema operacional reconhece por diversos motivos. Isso não significa que se deva utilizar qualquer um dos sistemas da lista para a partição raiz (`/`). `ext4` é a recomendação oficial para a raiz, `fat32` é a recomendação para `/boot/efi`.

`btrfs`, `f2fs` e `xfs` estão funcionando em testes recentes, mas são testados com muito menos frequência. Dependemos do feedback dos usuários para isso. Com base nos testes recentes, `btrfs` não é uma boa escolha para cenários de inicialização múltipla.

**Outros tipos de sistemas de arquivos da lista não são recomendados.**

No momento, não há uma recomendação oficial para partições de armazenamento ou para uma partição `/home` separada. Espera-se que os usuários que utilizam partições de armazenamento separadas ou uma partição `/home` separada saibam o que estão fazendo. Para `/home`, a maneira mais simples é usar `ext4` (recomendado) ou o mesmo sistema de arquivos usado na partição root.
<br>

## Alterando o tipo de partição
Observe que o Calamares não pode converter um tipo de partição em outro e preservar os dados da partição.
Além disso, o Calamares não oferece suporte à leitura ou criação de ZFS devido a questões de licenciamento.

> Se você executar o Calamares para alterar o tipo de uma partição existente, primeiro deverá excluir a partição e recriá-la com o tipo desejado.
{.is-danger}

<br>

## NVME SSDs
Os SSDs NVMe normalmente são reconhecidos pela ISO Live do OpenMandriva. Se, por algum motivo, eles não forem reconhecidos, temos algumas soluções alternativas em 'Solução de problemas' no menu Grub2 da ISO que podem funcionar. Elas são (PCIE ASPM=OFF) e (NVME APST=OFF). Esperamos que isso funcione para a maioria dos hardwares. Veja mais em Errata/SSDs NVMe. Esse problema, naturalmente, é muito específico de cada hardware.
<br>

## Instalador e Suporte EFI
Esta versão do OpenMandriva 6.0 oferece suporte à inicialização e instalação com e sem UEFI.

*Observe que o Secure Boot NÃO é suportado.*
*Observe que NÃO é recomendado misturar partições MBR e GPT.*

Se você deseja realizar uma instalação EFI em um disco MBR existente, será necessário converter a tabela de partições do disco para o novo esquema de particionamento GPT. Para isso, você precisa usar a ferramenta gdisk. Uma execução típica seria gdisk /dev/sda: a tabela de partições existente será convertida em memória para o esquema GPT. Serão exibidos avisos sobre possível perda de dados; o disco não será alterado até que você grave a tabela de partições pressionando W. É recomendável fazer backup de quaisquer dados importantes.

Pode haver situações em que a conversão não possa ser realizada; isso geralmente ocorre devido à falta de espaço no início ou no final do disco para gravar a tabela de partições. Pode ser necessário excluir ou redimensionar uma partição para criar o espaço necessário; o gparted é seu aliado nessas circunstâncias.

Ainda é necessário criar uma partição `/boot/efi` para conter os arquivos de inicialização, e isso deve ser feito enquanto o instalador Calamares estiver em execução. Quando o instalador chegar à etapa de particionamento, a partição `/` (root) deverá ser removida e uma pequena partição (300 MB) fat32 deverá ser criada no início da unidade. A partição deve ser nomeada `/boot/efi` e a flag `boot` deve ser definida. Se o espaço em disco for crítico, uma partição menor poderá ser usada, mas certifique-se de defini-la como fat32 no Calamares, caso contrário a instalação falhará. Se você não seguir essas etapas, a instalação do carregador de inicialização falhará. Em seguida, particione o disco normalmente.

Compartilhe suas experiências nos fóruns para que possamos melhorar este aspecto da instalação.

Se você estiver instalando ao lado do Windows 8, 8.1, 10 ou de um sistema operacional EFI semelhante, como precaução, certifique-se de ter discos de recuperação e de ter feito backup de quaisquer dados importantes. Nossos testes foram limitados com essa configuração, mas instalações bem-sucedidas foram realizadas sem problemas. Aceitamos qualquer feedback sobre este assunto.
<br>

## Booting através do USB
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

- O Ventoy não é totalmente compatível. Em algumas circunstâncias, pode ou não funcionar. Crie a mídia live/de instalação usando um dos métodos recomendados acima. Consulte [OMLx 6.0 Errata](/distribution/releases/omlx60/errata) para soluções alternativas para o Ventoy.
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
A inicialização por DVD está obsoleta, mas as ISOs do OpenMandriva 6.0 ainda inicializam a partir de DVD usando inicialização Legacy ou UEFI. Caso encontre dificuldades, existem 2 soluções alternativas [aqui](https://forum.openmandriva.org/t/4377) que devem permitir a inicialização pelo DVD. Nos testes, a inicialização do OpenMandriva 6.0 pelo DVD levou de 5-6 minutos. Em alguns hardwares pode demorar mais. Usar um DVD para esse fim é muito mais lento do que usar uma unidade flash USB.
<br>

## Sobre os repositórios
Temos o [om-repo-picker](/policies/repositories-tldr) também chamado Seletor de Repositórios de Software, para selecionar repositórios adicionais e aumentar a disponibilidade de pacotes.
**Não misture repositórios de diferentes versões/canais de atualização**. Isso significa, por exemplo, não usar repositórios Cooker em um sistema Rock. Se usar Rock, use apenas repositórios Rock. Isso é explicado com mais detalhes em [Plano de Lançamento e Repositórios do OpenMandriva](/policies/release-plan-and-repositories). Se você misturar repositórios de diferentes versões/canais de atualização e quebrar o computador, a solução é fazer uma nova instalação. Depois de uma instalação limpa, não faça isso novamente.
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

A forma recomendada e comprovada de atualizar é usar a linha de comando. É muito fácil: basta copiar e colar esta sequência de comandos:

`sudo dnf clean all ; sudo dnf dsync --allowerasing`

Os usuários também podem atualizar o sistema usando 'System update', disponível no painel de menu das novas instalações ou em 'Menu de Aplicativos>System>System Update'.

Se o usuário tiver problemas com a atualização `dsync`, deverá usar este comando:

`sudo dnf clean all ; sudo dnf dsync --allowerasing 2>&1 | tee dsync.log.txt`

Isso criará o arquivo de log `dsync.log.txt`, que poderá ser anexado à publicação no fórum ou ao relatório de bug. Observe que, se você usar este comando várias vezes, o arquivo será sobrescrito a cada vez. Se precisar de vários logs de transação, renomeie o arquivo após cada execução, por exemplo `dsync1.log.txt`, `dsync2.log.txt` e assim por diante.

*Nota:* `dsync` é um alias para `distro-sync`. Usuários do Fedora podem estar acostumados a usar `dnf up`, mas o OpenMandriva é diferente.
Embora possa funcionar para usuários do Rock usar `dnf up`, para instalações Cooker e ROME é altamente recomendável usar `dnf dsync`. Portanto, recomendamos que os usuários usem `dnf dsync`.

<br>

## Servidor de som padrão alterado para PipeWire
[*Pipewire*](https://pipewire.org/) tornou-se nosso servidor de som padrão na versão atual, juntamente com o WirePlumber, substituindo o PulseAudio.
No entanto, o PulseAudio ainda está disponível em nosso repositório e você pode voltar a usá-lo a qualquer momento. Para isso, use esta sequência de comandos:

`sudo dnf rm pipewire-pulse ; sudo dnf in pulseaudio-server`

<br>

## Kernel compilado com Clang
O kernel padrão do OpenMandriva 6.0 é compilado com Clang.
Há versões kernel-desktop-gcc e kernel-server-gcc disponíveis caso sejam necessárias.
<br>

## Hardware gráfico Nvidia
Isso é discutido na página de Errata do OpenMandriva 6.0.
<br>

## O que fazer se eu tiver um problema
Caso tenha problemas, informe-os no [fórum de suporte em inglês](https://forum.openmandriva.org/c/support/17) usando um título descritivo e informações suficientes para que alguém possa ajudar. Ou, para obter resultados mais rápidos, entre em contato pelo [OpenMandriva Chat](team/chat). Se o problema for técnico e grave, [registre um relatório de bug](https://github.com/OpenMandrivaAssociation/distribution/issues).
<br>

## O que há de novo
Veja [O que há de novo no OMLx 6.0](/distribution/releases/omlx60/new)
<br>

## Errata
Veja a [Errata do OMLx 6.0](/distribution/releases/omlx60/errata)
<br>

## Ajudando o Projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e nos testes e correções. Você é bem-vindo para se juntar a nós e ajudar nesse trabalho, que não é apenas gratificante, mas também muito divertido! Se você acha que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto a contribuições de arte e traduções. Novos colaboradores interessados nessas tarefas devem consultar a wiki para mais detalhes e saber como participar! Como alternativa, você pode usar nosso [fórum](https://forum.openmandriva.org).
<br>

## Doe para o projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}Também é necessário tempo e dinheiro para manter nossos servidores funcionando. Se puder, [faça uma doação](https://www.openmandriva.org/Donate) para manter as luzes acesas!
<br>

![header-tr-60.svg](/assets/header-tr-60.svg){.align-abstopright}
