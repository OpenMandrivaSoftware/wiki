---
title: OpenMandriva Lx 4.2 Errata
description: OMLx 4.2 Errata
published: true
date: 2021-11-23T19:28:27.518Z
tags: 4.2
editor: markdown
dateCreated: 2020-02-26T23:58:47.215Z
---

# Errata do OpenMandriva Lx 4.2 - Problemas conhecidos

> Como em qualquer lançamento, ainda existem problemas e bugs que podem não ter sido resolvidos. Esta página documenta aqueles que podem causar inconvenientes e, quando possível, detalhes sobre como contorná-los.
{.is-info}

<br>

**Por favor leia também as [Notas do OMLx 4.2](/distribution/releases/omlx42/notes).**


## Placas de vídeo NVIDIA
Este lançamento inclui o driver nouveau de engenharia reversa, que oferece suporte moderadamente bom para a maioria das placas NVIDIA. Para alguns trabalhos com telas duplas, ele é, na verdade, melhor do que o driver binário da NVIDIA, pois suporta a rotação de tela em um segundo monitor, útil para monitores com telas rotativas.
Os usuários podem utilizar os drivers disponíveis no site da NVIDIA, mas estes não são suportados pelo OpenMandriva. Existem várias razões pelas quais eles não podem ser suportados pela distribuição.
A instalação e a manutenção de quaisquer drivers proprietários da NVIDIA são exclusivamente uma opção e responsabilidade do usuário.

## NVME SSDs
Há um problema conhecido com alguns dispositivos NVME SSD (especialmente os mais recentes) e dispositivos PCIE, onde o SSD pode não ser reconhecido. 
O problema é conhecido e está sendo trabalhado pelos desenvolvedores do OpenMandriva e pelos desenvolvedores do projeto original.
O reconhecimento de hardware para SSDs NVME deve estar consideravelmente aprimorado.
Sabe-se que alguns SSDs NVME da Samsung que anteriormente não eram reconhecidos agora são, com esta versão do kernel. Este problema, naturalmente, é muito específico de hardware.

No sistema instalado, o usuário pode desejar adicionar essa solução alternativa ao arquivo `/etc/default/grub` e executar o comando `update-grub2` para torná-la global. Você deve usar a solução que encontrou funcionando na ISO *Live*.

Se `(PCIE ASPM=OFF)` funcionou para você, adicione:
`pcie=aspm=off`
às linhas:
`GRUB_DECLINE_LINUX_DEFAULT`
`GRUB_DECLINE_LINUX_RECOVERY`
em
`/etc/default/grub` 
e então execute:
`$ sudo update-grub2`

Se `(NVME APST=OFF)` funcionou, então adicione apenas:
`nvme_core.default_ps_max_latency_us=0`

Como sempre, os usuários são encorajados a fazer perguntas sobre qualquer assunto que não entendam no nosso [fórum] (https://forum.openmandriva.org/).

## GEOIP
A configuração GEOIP automática do instalador pode não definir o fuso horário corretamente.

## Como configurar a impressora
Ligue a impressora e veja se ela foi configurada automaticamente. Verifique se o driver correto foi instalado. Se a impressora foi configurada automaticamente e você tem o driver correto, ótimo, está tudo pronto.
Se não foi, desligue a impressora. Abra as *Configurações da impressora*, também acessíveis em Configurações>Hardware>Impressoras, e remova a impressora. Você também pode acessar as *Configurações da impressora* pelo Konsole (terminal) com:

```
$ kcmshell5 kcm_printer_manager
```

Se o driver correto não foi instalado por padrão. nós teremos que adicionar o pacote do software.

O próximo passo é determinar qual software instalar para a sua impressora.

No OpenMandriva Lx é mais provável que seja um pacote 'task-printing' específico para sua marca de impressora. Os pacotes são:
- task-printing-canon
- task-printing-epson
- task-printing-hp
- task-printing-lexmark
- task-printing-okidata
- task-printing-misc

Instale o pacote correspondente à sua marca ou o pacote misc se nenhum deles for adequado. Exemplo usando okidata:
```
$ sudo dnf install task-printing-okidata
```
Agora ligue a impressora novamente e ela deve ser configurada automaticamente (algumas vezes pode ser necessário reiniciar o sistema para a configuração automática funcionar).

Caso contrário busque ajuda [aqui](https://forum.openmandriva.org/c/en/support)

## Discover
Se você também quiser explorar os pacotes disponíveis em repositórios adicionais, será necessário habilitá-los por meio do [Seletor de Repositórios de Software] (/policies/repositories-tldr) e atualizar o cache.


## Localização do Firefox

Para usar idiomas diferentes do Inglês no Navegador Firefox, você precisará configurar o idioma nas Configurações do Firefox, em Idioma e Aparência.

## Multiboot
No “mundo real”, o multiboot funciona bem na maior parte do tempo, mas, quando surgem problemas, às vezes a solução é uma solução alternativa em vez de uma correção propriamente dita. Essas são simplesmente realidades do multiboot.

Além disso, atualmente não é possível para a equipe de controle de qualidade do OpenMandriva testar nosso gerenciador de inicialização com todos os tipos de sistemas de arquivos em todas as distribuições Linux, ou mesmo nas “10 principais” distribuições Linux. O fato é que, seja no multiboot com Windows ou com outras distribuições Linux, dependemos exclusivamente dos relatos dos usuários para saber o que funciona e o que não funciona em relação ao multiboot.

Um problema conhecido encontrado com o gerenciador de inicialização do OMLx é que o GRUB2 do OpenMandriva não cria entradas de inicialização para sistemas openSUSE que utilizam o sistema de arquivos Btrfs. O GRUB2 do ONLx funciona com sistemas openSUSE que utilizam o sistema de arquivos ext4.
Isso ocorre porque o openSUSE utiliza uma sintaxe personalizada em seus patches para Btrfs, presentes nos pacotes os-prober e grub2 do openSUSE, que não são compatíveis com o código do OpenMandriva Lx. Atualmente, não se sabe se o gerenciador de inicialização do OMLx funciona ou não com o openSUSE utilizando outros tipos de sistemas de arquivos, como XFS ou F2FS.

A solução alternativa é que os usuários alternem entre os gerenciadores de inicialização nas configurações do firmware UEFI ou na BIOS. Outra possibilidade é utilizar o gerenciador de inicialização do openSUSE, caso ele reconheça o seu sistema OpenMandriva. À medida que os usuários relatarem problemas de multiboot, corrigiremos aqueles que estiverem ao nosso alcance. Os problemas que não pudermos corrigir serão relatados na seção de Errata das nossas versões do OMLx.

## Zypper
O pacote zypper-needs-restarting entra em conflito com dnf-utils se este estiver instalado.
Como solução alternativa, remova dnf-utils

## Bluetooth
Para dispositivos Bluetooth, pode ser necessário habilitar systemd bluetooth.service. Abra o Konsole e execute:
```
sudo systemctl start bluetooth ; sudo systemctl enable bluetooth
```

<br>

\- 