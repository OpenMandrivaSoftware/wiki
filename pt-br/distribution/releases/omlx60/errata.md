---
title: OpenMandriva Lx 6.0 Errata
description: OpenMandriva Lx 6.0 Errata
published: true
date: 2025-08-06T05:38:25.995Z
tags: 6.0
editor: markdown
dateCreated: 2025-03-10T20:01:31.755Z
---

# Errata do OpenMandriva Lx 6.0 - Problemas conhecidos

> Como em qualquer lançamento, ainda existem problemas e bugs que podem não ter sido resolvidos. Esta página documenta aqueles que podem causar inconvenientes e, quando possível, detalhes sobre como contorná-los.
{.is-info}

**Leia também as [Notas do 6.0](/distribution/releases/omlx60/notes).**
<br>

## Problemas conhecidos e soluções alternativas
<br>

### Steam
O lançador/loja de jogos Steam está disponível nos repositórios `non-free` [*(1)*](https://wiki.openmandriva.org/en/policies/repositories-tldr#non-free) do OpenMandriva, mas é conhecido por travar na primeira inicialização, apresentando a mensagem `steamwebhelper` não está respondendo.

Como o Steam não é Open Source, não podemos corrigir isso - mas esperamos que uma versão corrigida do Steam esteja disponível em breve. Enquanto isso, há uma solução alternativa: encerre o processo `steamwebhelper` (se você não souber como fazer isso, basta reiniciar e iniciar o Steam novamente).

A segunda inicialização e todas as seguintes funcionarão.
<br>

### Placas de vídeo NVIDIA
Membros da comunidade disponibilizaram drivers proprietários da Nvidia. O driver `nvidia` contém o driver de produção mais recente.
Leia também [suporte às versões dos pacotes do driver NVIDIA](https://forum.openmandriva.org/t/5217)

O usuário pode instalar o driver pelo módulo OpenMandriva Welcome.
Lembre-se de que as pessoas que disponibilizam esses pacotes estão oferecendo voluntariamente seu tempo e conhecimento. Pode haver um atraso entre um novo kernel e as compilações dos pacotes Nvidia correspondentes.

> Estes pacotes são específicos para o kernel. No momento, eles não serão instalados se houver uma versão de kernel mais recente instalada no sistema do que a versão do kernel para a qual este software foi compilado.
Há mais informações [aqui](https://forum.openmandriva.org/t/about-nvidia-proprietary-driver-software/4770) e [aqui](https://forum.openmandriva.org/t/installing-nvidia-proprietary-drivers-in-rome/4742).
{.is-warning}

<br>

#### Problemas conhecidos (todos os pacotes nvidia):
1. O código é fechado. Não podemos corrigir nada que esteja errado com o código. A Nvidia terá que fazer isso.

2. A tela de inicialização do Plymouth pode não funcionar,

3. Os terminais virtuais podem não funcionar,

4. O Kscreenlocker pode não funcionar,

5. Se o usuário usar `kernel-rc-desktop`, será necessário instalar `nvidia-kmod-rc-desktop`. Ou `kernel-rc-server`, então `nvidia-kmod-rc-server`.

Se o usuário tiver um problema com o desempenho gráfico dos drivers proprietários da Nvidia, o OpenMandriva não poderá fazer nada a respeito. Os contatos são o [fórum de desenvolvedores Linux da Nvidia](https://forums.developer.nvidia.com/c/gpu-graphics/linux/148). O OpenMandriva pode lidar apenas com problemas relacionados ao empacotamento deste software de 3a e se ele instala ou não.
<br>

6. Provavelmente também está relacionado às placas gráficas Nvidia:
> Pode ser necessário desconectar/desligar monitores secundários para acessar a tela de login.
{.is-warning}

Veja também [#2072](https://github.com/sddm/sddm/issues/)
<br>

<br>

### Como instalar o X11 no sistema Plasma6 Wayland
#### Para usuário do Plasma6:

`sudo dnf in task-plasma6-x11 --refresh`

Isso dá ao usuário uma opção para comparar o X11 com o Wayland. Sabe-se que existem alguns problemas com o Wayland no Plasma 6. Esta é uma maneira útil de determinar se o problema está de fato relacionado ao Wayland ou não. Essencial para solicitações de suporte no fórum do OM e relatórios de bugs. Também é útil caso, por algum motivo, o Wayland não funcione para o usuário.

### Como instalar o Waylando no sistema Plasma6 X11
#### Para usuário do Plasma6:

`sudo dnf in task-plasma6-wayland --refresh`

Isso dá aos usuários uma opção para comparar o Wayland com o X11.


### NVME SSDs
Os SSDs NVME normalmente são reconhecidos pela ISO Live do OpenMandriva. Se, por algum motivo, não forem, temos algumas soluções alternativas em "Troubleshooting", no menu Grub2 da ISO, que podem funcionar. São (PCIE ASPM=OFF) e (NVME APST=OFF). Esperamos que isso funcione para o hardware da maioria das pessoas.
Este problema é, naturalmente, muito específico do hardware.

Quando ocorre, este problema é causado por firmware com bugs em dispositivos NVMe. Se o fabricante do dispositivo fornecer uma atualização de firmware, talvez seja interessante verificar se isso corrige o problema sem precisar desativar o ASPM.

ASPM (Active State Power Management) pode reduzir o consumo de energia dos dispositivos NVMe - portanto, desativá-lo não é recomendado, a menos que seja necessário.

No sistema instalado, o usuário pode adicionar esta solução alternativa a `/etc/default/grub` e executar update-grub2 para tornar a solução global. Você usaria aquela que funcionou na ISO Live.

Se (PCIE ASPM=OFF) funcionou para você, então adicione:
`pcie=aspm=off` às linhas:
`GRUB_DECLINE_LINUX_DEFAULT`
`GRUB_DECLINE_LINUX_RECOVERY`
em
`/etc/default/grub`
e depois execute:
`$ sudo update-grub2`

Se (NVME APST=OFF) funcionou, adicione:
`nvme_core.default_ps_max_latency_us=0`

Como sempre, os usuários são incentivados a fazer perguntas sobre qualquer coisa que não entendam em nosso [fórum](https://forum.openmandriva.org/).
<br>

### Instalando a partir do Ventoy
**Este problema deve ser corrigido no momento da escrever.**

Solução alternativa anterior, se necessário:

Copie o arquivo .iso do OpenMandriva desejado para a partição Ventoy do pendrive Ventoy. Inicialize por ela.

1. Abra o Konsole (terminal) e `cd /run/initramfs/omdv/LiveOS`
2. digite `ls` e verifique se `squashfs.img` está presente
3. Deixe o Konsole (terminal) aberto nesse diretório
4. Abra o instalador Calamares e instale seu novo sistema

Desde que esse diretório esteja aberto e `ls` mostre que `squashfs.img` está presente, o usuário poderá instalar o OMLx desejado inicializado a partir do pendrive Ventoy.

Se isso não funcionar, então talvez o seguinte funcione:

1. Abra o Konsole (terminal), faça `cd` para “/run/initramfs/omdv/LiveOS”,
então
`cp squashfs.img /live`
Você precisa fazer esta etapa imediatamente após inicializar a ISO 'Live' ou a pasta `/run/initramfs/omdv/LiveOS` desaparecerá ou, de alguma forma, deixará de ser reconhecida. Depois de executar `cp`, essa pasta desaparecerá. Em seguida:
2. `$ sudo mkdir /run/initramfs/omdv/LiveOS`
3. `$ sudo cp /live/squashfs.img /run/initramfs/omdv/LiveOS`
4. Para verificar:
```
 $ ls -la /run/initramfs/omdv/LiveOS
total 2867796
drwxr-xr-x 2 root root         60 Oct 19 20:30 .
drwxr-xr-x 3 root root         60 Oct 19 20:29 ..
-r--r--r-- 1 root root 2936623104 Oct 19 20:30 squashfs.img
```
5. Instalar o OpenMandriva
<br>

### GEOIP
A configuração automática de GEOIP do instalador pode não definir corretamente o fuso horário (se ele tentar adivinhar sua localização com base no seu endereço IP).
Se detectar seu fuso horário incorretamente, basta selecionar manualmente o fuso horário correto.
<br>

### Como configurar a impressora
Ligue a impressora e veja se ela é configurada automaticamente. Preste atenção para verificar se o driver correto foi instalado. Se a impressora foi configurada automaticamente e você possui o driver correto, ótimo, está tudo pronto.
Se não foi, desligue a impressora. Abra Configurações do Sistema>Hardware>Impressoras ou execute no terminal (Konsole):

`kcmshell6 kcm_printer_manager`

(se estiver usando o Plasma 5, use `kcmshell5` em vez de `kcmshell6`) e remova sua impressora na caixa de diálogo da interface.
Se o driver correto não foi instalado por padrão, será necessário adicionar um pacote de software.
O próximo passo é determinar qual software (se houver) adicionar para sua impressora.
No OpenMandriva Lx, o mais provável é o pacote 'task-printing' específico para a marca da sua impressora. Os pacotes são:

•task-printing-canon
•task-printing-epson
•task-printing-hp
•task-printing-lexmark
•task-printing-okidata
•task-printing-misc

Instale o pacote correspondente à sua marca ou o pacote misc se nenhum deles for adequado. Exemplo usando okidata:

`sudo dnf install task-printing-okidata`

Ligue a impressora novamente e ela deverá ser configurada automaticamente (às vezes pode ser necessário reiniciar para que a configuração automática funcione). Se não funcionar, você pode configurá-la em Configurações do Sistema>Hardware>Impressoras ou executar no terminal (Konsole):

`kcmshell6 kcm_printer_manager`.

**Um método alternativo para configurar uma impressora no OpenMandriva é usar o CUPS (https://localhost:631/ como URL no navegador)**. *Para alguns hardwares, isso pode funcionar melhor.*

Se não encontrar ajuda [aqui](https://forum.openmandriva.org/c/en/support).

**Nota:** Se você tiver problemas para configurar uma impressora conectada por USB, pode ser útil remover os pacotes `usbmuxd` e `ipp-usb`. Remover `ipp-usb` significa que você não poderá usar o driver "driverless".
<br>

### Descubra novos softwares
Se você também quiser explorar pacotes de repositórios adicionais, será necessário habilitá-los por meio do [Software Repository Selector](/en/policies/repositories-tldr) e atualizar o cache. Para atualizar o cache, você pode usar a opção `--refresh`, desta forma:

`sudo dnf --refresh install foo_package`

Ou você pode usar `dnf clean all` como:

`sudo dnf clean all ; sudo dnf install foo_package`

<br>

### Controlador gráfico no VirtualBox 7.0.x
As imagens de instalação OMLX mais recentes podem exigir que o controlador VMSVGA seja definido para inicializar corretamente no VirtualBox 7.0.x.
<br>

### Som no VirtualBox 7.0.x
Alguns usuários relatam problemas com som entrecortado ou com travamentos no pacote OM VirtualBox 7.0.x.
Este problema parece estar relacionado ao hardware dos usuários. Os desenvolvedores estão cientes desse problema e procurando ativamente uma solução. Os usuários devem ter em mente que o som no VirtualBox é uma emulação e o processo está sujeito a problemas periódicos. *Assim, o uso do VirtualBox para multimídia provavelmente apresentará problemas periódicos.*
<br>

### Multiboot
No mundo real, o multiboot funciona bem na maior parte do tempo, mas quando há problemas, às vezes a solução é uma alternativa, em vez de uma correção. Essas são simplesmente as realidades do multiboot.
Além disso, atualmente não é possível para a equipe de QA do OpenMandriva testar nosso bootloader com todos os tipos de sistemas de arquivos em todas as distribuições Linux, ou mesmo nas "10 principais" distribuições Linux. O fato é que, seja no multiboot com Windows ou com outras distribuições Linux, dependemos exclusivamente dos relatos dos usuários para saber o que funciona e o que não funciona em relação ao multiboot.
Um problema conhecido encontrado com o bootloader OMLx é que o OpenMandriva grub2 não cria entradas de inicialização para sistemas openSUSE que usam o sistema de arquivos btrfs. O OMLx grub2 funciona com sistemas openSUSE que usam o sistema de arquivos ext4.
Isso ocorre porque o openSUSE usa uma sintaxe personalizada para seus patches de btrfs nos pacotes openSUSE os-prober e grub2 que não é compatível com o código do OMLx. Atualmente não se sabe se o bootloader OMLx funciona com o openSUSE com outros tipos de sistemas de arquivos, como XFS ou F2FS.
A solução alternativa é usar as configurações do firmware UEFI ou do BIOS para alternar os bootloaders para o bootloader do openSUSE.

À medida que os usuários relatarem problemas de multiboot, corrigiremos o que pudermos. Os problemas que não conseguirmos corrigir serão relatados na Errata dos lançamentos do OpenMandriva.
<br>

### Servidor de som PipeWire
Alguns usuários podem ter problemas com o novo servidor de som PipeWire. Se o usuário quiser voltar ao servidor de áudio pulseaudio anterior, abra o Konsole e execute o seguinte comando de copiar e colar:

`$ sudo dnf remove pipewire-pulse ; sudo dnf install pulseaudio-server`
<br>

### Zypper
O pacote `zypper-needs-restarting` entra em conflito com `dnf-utils` se este estiver instalado.
Como solução alternativa, remova `dnf-utils`.
<br>

### Bluetooth
Para dispositivos Bluetooth, pode ser necessário habilitar systemd bluetooth.service. Abra o Konsole
e execute:

`$ sudo systemctl enable --now bluetooth`
<br>

### SystemSettings
Alguns módulos nas Configurações do Sistema podem não ser exibidos corretamente na primeira inicialização.
Eles serão exibidos no próximo login.
<br>


## O que fazer se eu tiver um problema
Se tiver problemas, informe-os no [fórum de suporte em inglês](https://forum.openmandriva.org/c/en/support) com um título descritivo e uma descrição e informações suficientes para que alguém possa ajudá-lo. Ou, para obter resultados potencialmente mais rápidos, entre em contato conosco no [OpenMandriva Chat](https://wiki.openmandriva.org/en/team/chat). Se o problema for um problema técnico sério, então [registre um relatório de bug](https://github.com/OpenMandrivaAssociation/distribution/issues).
<br>

## Ajudando o Projeto
![om-donate-32px.png](/assets/om-donate-32px.png){.align-left}As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e auxiliar na correção de bugs e testes. Você é bem-vindo para se juntar a nós e ajudar neste trabalho, que não é apenas gratificante, mas também muito divertido!
Se você sente que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto a receber contribuições de arte e traduções.
Novos colaboradores que queiram ajudar nessas tarefas variadas devem consultar a wiki para obter mais detalhes e saber como participar! Como alternativa, você pode usar nosso [fórum](https://forum.openmandriva.org).
Isso custa tempo e dinheiro para manter nossos servidores funcionando.
Se puder, por favor, [faça uma doação](https://www.openmandriva.org/Donate) para manter as luzes acesas!
<br>

![header-tr-60.svg](/assets/header-tr-60.svg){.align-abstopright}
