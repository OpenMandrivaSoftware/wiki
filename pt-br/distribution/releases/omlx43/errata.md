---
title: OpenMandriva Lx 4.3 Errata
description: 
published: true
date: 2022-10-13T22:30:54.262Z
tags: 4.3
editor: markdown
dateCreated: 2021-04-24T05:21:24.743Z
---

# Errata do OpenMandriva Lx 4.3 - Problemas conhecidos

> Como em qualquer lançamento, ainda existem problemas e bugs que podem não ter sido resolvidos. Esta página documenta aqueles que podem causar inconvenientes e, quando possível, detalhes sobre como contorná-los.
{.is-info}

Como em qualquer lançamento, ainda existem problemas e bugs que podem não ter sido resolvidos.
Esta página documenta aqueles que podem causar inconvenientes e, quando possível, detalhes sobre como contorná-los.
<br />

## Problemas conhecidos e soluções alternativas
<br />

### Placas de vídeo NVIDIA

Esta versão inclui o driver nouveau obtido por engenharia reversa, que oferece suporte razoavelmente bom para a maioria das placas NVIDIA.
Para alguns trabalhos com dois monitores, ele é, na verdade, melhor que o driver binário da NVIDIA, pois oferece suporte à rotação da tela em um segundo monitor, útil para monitores com telas giratórias.
Os usuários podem utilizar drivers do site da nvidia, mas eles não são suportados pelo OpenMandriva por diversos motivos.
A instalação e a manutenção de quaisquer drivers proprietários da nVidia são de exclusiva opção e responsabilidade do usuário.
Há drivers nvidia com suporte da comunidade disponíveis no repositório non-free.
<br />
### NVME SSDs

Há um problema conhecido com alguns SSDs NVMe (especialmente os mais novos) e dispositivos PCIe, no qual o SSD pode não ser reconhecido.

O problema é conhecido e está sendo investigado pelos desenvolvedores do OpenMandriva e pelos desenvolvedores do upstream.

O reconhecimento de hardware para SSDs NVMe foi consideravelmente aprimorado no OMLx 4.3.

Esse problema, é claro, é bastante específico de cada hardware.

No sistema instalado, o usuário pode querer adicionar essa solução alternativa a /etc/default/grubme executar update-grub2 para tornar a solução alternativa global. Você deve usar aquela que funcionou para você na ISO Live.

Se **(PCIE ASPM=OFF)** funcionou para você, adicione:

`pcie=aspm=off`

às linhas:

`GRUB_DECLINE_LINUX_DEFAULT`
`GRUB_DECLINE_LINUX_RECOVERY`

em:

`/etc/default/grub`

e, em seguida, execute:

`$ sudo update-grub2`

Se (NVME APST=OFF) funcionou, adicione:
`nvme_core.default_ps_max_latency_us=0`

Como sempre, os usuários são incentivados a fazer perguntas sobre qualquer coisa que não entendam em nosso [fórum](https://forum.openmandriva.org/).
<br />

### GEOIP

A configuração GEOIP automática do instalador pode não definir o fuso horário corretamente.
<br />

### Como configurar a impressora

Ligue a impressora e veja se ela é configurada automaticamente. Verifique se o driver correto foi instalado. Se a impressora foi configurada automaticamente e você tem o driver correto, ótimo, está tudo pronto.
Se não foi, desligue a impressora. Abra Configurações do Sistema>Hardware>Impressoras, também conhecido como `kcmshell5 kcm_printer_manager`, e remova a impressora.
Se o driver correto não tiver sido instalado por padrão, será necessário adicionar um pacote de software.
O próximo passo é determinar qual software adicionar para a sua impressora.
No OpenMandriva Lx, o mais provável é que seja um pacote 'task-printing' específico para a marca da sua impressora. Os pacotes são:
•task-printing-canon
•task-printing-epson
•task-printing-hp
•task-printing-lexmark
•task-printing-okidata
•task-printing-misc
Instale o pacote correspondente à sua marca ou o pacote misc se nenhuma das opções corresponder. Exemplo usando a Okidata:
$ sudo dnf install task-printing-okidata
Agora ligue a impressora novamente e ela deverá se configurar automaticamente (às vezes pode ser necessário reiniciar para que a configuração automática funcione). Se isso não acontecer, você poderá configurá-la em Configurações do Sistema>Hardware>Impressoras, também conhecido como `kcmshell5 kcm_printer_manager`.
Se ainda assim não funcionar, procure ajuda [aqui](https://forum.openmandriva.org/c/en/support).
<br />

### Descubra novos softwares

Se quiser explorar também os pacotes disponíveis em repositórios adicionais, será necessário habilitá-los por meio do Seletor de Repositórios de Software e atualizar o cache.
<br />

### Multiboot

No "mundo real", o multiboot funciona bem na maior parte do tempo, mas, quando surgem problemas, às vezes a solução é uma alternativa de contorno em vez de uma correção. Essas são apenas as realidades do multiboot.

Também não é possível atualmente para a equipe de QA do OpenMandriva testar nosso carregador de inicialização com todos os tipos de sistemas de arquivos em todas as distribuições Linux, ou mesmo nas "10 principais" distribuições Linux. O fato é que, seja ao fazer multiboot com Windows ou com outras distribuições Linux, dependemos exclusivamente dos relatos dos usuários para saber o que funciona e o que não funciona em relação ao multiboot.

Um problema conhecido encontrado com o carregador de inicialização do OMLx é que o grub2 do OpenMandriva não cria entradas de inicialização para sistemas openSUSE que utilizam o sistema de arquivos btrfs. O grub2 do OMLx funciona com sistemas openSUSE que utilizam o sistema de arquivos ext4.

Isso ocorre porque o openSUSE utiliza uma sintaxe personalizada para seus patches de btrfs nos pacotes os-prober e grub2 do openSUSE, que não são compatíveis com o código do OMLx. Atualmente, não se sabe se o carregador de inicialização do OMLx funciona ou não com o openSUSE usando outros tipos de sistemas de arquivos, como XFS ou F2FS.

A solução alternativa é que os usuários alternem entre os carregadores de inicialização nas configurações de firmware UEFI ou na BIOS. Outra alternativa pode ser usar o carregador de inicialização do openSUSE, caso ele reconheça seu sistema OpenMandriva.

À medida que os usuários relatarem problemas de multiboot, corrigiremos o que estiver ao nosso alcance. Os problemas que não pudermos corrigir serão relatados na Errata das nossas versões do OMLx.
<br />

### Servidor de som Pipewire

Alguns usuários podem ter problemas com o novo servidor de som Pipewire. Se o usuário quiser voltar ao servidor de áudio pulseaudio anterior, abra o Konsole e execute o seguinte comando de copiar e colar:

`$ sudo dnf remove pipewire-pulse ; sudo dnf install pulseaudio-server`
<br />

### Atualização do Firefox

A versão estável do OpenMandriva, também conhecida como Rock, normalmente não recebe atualizações para pacotes do sistema e da toolchain. Por causa disso e da forma como a Mozilla desenvolve o Firefox, às vezes os pacotes do Firefox deixam de ser compilados para nossa versão estável. Para os usuários preocupados em não ter a versão mais recente do Firefox, uma solução alternativa é instalar, a partir do [mozilla.org](https://www.mozilla.org/), a versão mais recente do Firefox RR (Rapid Release) ou, pelo [mozilla.org](https://support.mozilla.org/en-US/kb/switch-to-firefox-extended-support-release-esr), a versão mais recente do Firefox ESR (Extended Support Release), que recebe todas as atualizações de segurança, mas não atualizações de recursos.
<br />

### Zypper

O pacote zypper-needs-restarting pode entrar em conflito com dnf-utils se este estiver instalado.
Como solução alternativa, remova dnf-utils
<br />

### Bluetooth

Para dispositivos Bluetooth, pode ser necessário habilitar systemd bluetooth.service. Abra o Konsole
e execute:

`$ sudo systemctl start bluetooth ; sudo systemctl enable bluetooth`
<br />

## O que fazer se eu tiver um problema

Se tiver problemas, relate-os no [fórum de suporte em inglês](https://forum.openmandriva.org/c/en/support), com um título descritivo e informações suficientes para que alguém possa ajudar. Se o problema for técnico e grave, [relate o bug](https://github.com/OpenMandrivaAssociation/distribution/issues).
<br />

## Ajudando o Projeto

As equipes de desenvolvimento do OpenMandriva (Cooker & QA) estão sempre procurando novos colaboradores para ajudar na criação e manutenção de pacotes e auxiliar na correção de bugs e testes. Você é bem-vindo para se juntar a nós e ajudar neste trabalho, que não é apenas gratificante, mas também muito divertido!
Se você sente que seus talentos não estão na área de software, o grupo OpenMandriva Workshop, formado pelas equipes de arte, documentação, tradução e comunicação, está sempre aberto a receber contribuições de arte e traduções.
Novos colaboradores que queiram ajudar nessas tarefas variadas devem consultar a wiki para obter mais detalhes e saber como participar! Como alternativa, você pode usar nosso [fórum](https://forum.openmandriva.org).
Isso custa tempo e dinheiro para manter nossos servidores funcionando.
Se puder, por favor, [faça uma doação](https://www.openmandriva.org/en/Donate) para manter as luzes acesas!
<br />

**Leia também**
[Notas de lançamento do OMLx 4.3](https://wiki.openmandriva.org/en/distribution/releases/omlx43/notes)
<br>
