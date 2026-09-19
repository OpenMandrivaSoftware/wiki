---
title: Errata do OpenMandriva Lx 4.2 Alpha
description: 
published: true
date: 2021-09-26T20:55:57.359Z
tags: 4.2
editor: markdown
dateCreated: 2020-02-27T16:13:04.324Z
---

# Errata do OpenMandriva Lx 4.2 Alpha - Problemas Conhecidos.
> Como em qualquer lançamento, ainda existem problemas e bugs que podem não ter sido resolvidos. Esta página documenta aqueles que podem causar inconveniência e, sempre que possível, detalha como eles podem ser contornados.
{.is-info}


**Recomenda-se que você leia as recentes** [notas de lançamento] (https://wiki.openmandriva.org/en/releases/omlx42/alpha/notes) **em nossa wiki**.

## Placas Gráficas NVIDIA
Este lançamento inclui o driver nouveau de engenharia reversa, que oferece suporte moderadamente bom para a maioria das placas NVIDIA. Para alguns trabalhos com telas duplas, ele é, na verdade, melhor do que o driver binário da NVIDIA, pois suporta a rotação de tela em um segundo monitor, útil para monitores com telas rotativas.
Os usuários podem utilizar os drivers disponíveis no site da NVIDIA, mas estes não são suportados pelo OpenMandriva. Existem várias razões pelas quais eles não podem ser suportados pela distribuição.
A instalação e a manutenção de quaisquer drivers proprietários da NVIDIA são exclusivamente uma opção e responsabilidade do usuário.

## NVME SSDs
Há um problema conhecido com alguns dispositivos NVME SSD (especialmente os mais recentes) e dispositivos PCIE, onde o SSD pode não ser reconhecido. Para nossa ISO *Live*, existe uma solução alternativa descrita nas [Notas de Lançamento](/releases/omlx41/notes).
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
Ligue a impressora e verifique se ela está configurada automaticamente. Preste atenção se o driver correto está instalado. Se a impressora foi auto configurada e você tem o driver correto, então tudo está como devido.
Se não, desligue a sua impressora. Abra *Configurações de Impressão* em `system-config-printer` remova sua impressora.
Se o driver correto não foi instalado por padrão nós teremos que adicionar um pacote de software.

O próximo passo é determinar qual software instalar para a sua impressora.

No OpenMandriva Lx é mais provável que seja um pacote 'task-printing' específico para sua marca de impressora. Os pacotes são:
- task-printing-canon
- task-printing-epson
- task-printing-hp
- task-printing-lexmark
- task-printing-okidata
- task-printing-misc

Installer o pacote que combina com a marca da sua impressora ou o pacote misc caso não tenha um pacote com a marca da impressora. Exemplo usando okidata:
```
$ sudo dnf install task-printing-okidata
```
Agora ligue a impressora novamente e ela deve ser configurada automaticamente (algumas vezes pode ser necessário reiniciar o sistema para a configuração automática funcionar).

Caso contrário busque ajuda [aqui](https://forum.openmandriva.org/c/en/support)

## Discover
Em relação aos softwares disponíveis nos repositórios, o Discover pode não exibir todos os pacotes disponíveis.

Isso ocorre porque o cache não foi limpo e a lista de repositórios não foi atualizada na primeira inicialização.

A solução alternativa é: executar os comandos
```
$ sudo rm -rf /var/cache/PackageKit/* /var/cache/app-info/*
$ sudo pkcon refresh force
```
Se você também quiser explorar os pacotes disponíveis em repositórios adicionais, será necessário habilitá-los por meio do [Seletor de Repositórios de Software] (/en/doc/repositories-tldr) e atualizar o cache novamente.

## Multiboot
No “mundo real”, o multiboot funciona bem na maior parte do tempo, mas, quando surgem problemas, às vezes a solução é uma solução alternativa em vez de uma correção propriamente dita. Essas são simplesmente realidades do multiboot.

Além disso, atualmente não é possível para a equipe de controle de qualidade do OpenMandriva testar nosso gerenciador de inicialização com todos os tipos de sistemas de arquivos em todas as distribuições Linux, ou mesmo nas “10 principais” distribuições Linux. O fato é que, seja no multiboot com Windows ou com outras distribuições Linux, dependemos exclusivamente dos relatos dos usuários para saber o que funciona e o que não funciona em relação ao multiboot.

Um problema conhecido encontrado com o gerenciador de inicialização do OpenMandriva Lx é que o GRUB2 do OpenMandriva Lx não cria entradas de inicialização para sistemas openSUSE que utilizam o sistema de arquivos Btrfs. O GRUB2 do OpenMandriva Lx funciona com sistemas openSUSE que utilizam o sistema de arquivos ext4.
Isso ocorre porque o openSUSE utiliza uma sintaxe personalizada em seus patches para Btrfs, presentes nos pacotes os-prober e grub2 do openSUSE, que não são compatíveis com o código do OpenMandriva Lx. Atualmente, não se sabe se o gerenciador de inicialização do OpenMandriva Lx funciona ou não com o openSUSE utilizando outros tipos de sistemas de arquivos, como XFS ou F2FS.

A solução alternativa é que os usuários alternem entre os gerenciadores de inicialização nas configurações do firmware UEFI ou na BIOS. Outra possibilidade é utilizar o gerenciador de inicialização do openSUSE, caso ele reconheça o seu sistema OpenMandriva. À medida que os usuários relatarem problemas de multiboot, corrigiremos aqueles que estiverem ao nosso alcance. Os problemas que não pudermos corrigir serão relatados na seção de Errata das nossas versões do OpenMandriva Lx.

## Problemas conhecidos que estão sendo corrigidos atualmente

Nosso sistema de acompanhamento de bugs apresentou alguns problemas, por isso estamos solicitando que novos relatórios de bugs sejam enviados em nosso [Fórum]  (https://forum.openmandriva.org/) ou
no [GitHub Issues](https://github.com/OpenMandrivaAssociation/OpenMandrivaAssociation.github.io/issues)

Bugs registrados no sistema de acompanhamento de problemas do OpenMandriva:

- [Host Cooker: as máquinas virtuais do VirtualBox 6.1.12 não iniciam](https://issues.openmandriva.org/show_bug.cgi?id=2634)

- [Falha do desktop Plasma no VirtualBox (virtualbox-guest-additions)](https://issues.openmandriva.org/show_bug.cgi?id=2633)

- [Som de login não reproduzido (ou reproduzido incorretamente) — Plasma 5.19.3, KF 5.72.0](https://issues.openmandriva.org/show_bug.cgi?id=2629)

- [Alterações no ponto de montagem no KDE Partition Manager não são gravadas no /etc/fstab (todas as versões do OM Lx)](https://issues.openmandriva.org/show_bug.cgi?id=2628)

- [OM-Control-Center não funciona com Wayland (Cooker)](https://issues.openmandriva.org/show_bug.cgi?id=2625)

- [A atualização de um kernel de uma ramificação para outra ramificação, com o mesmo número de versão, falha](https://issues.openmandriva.org/show_bug.cgi?id=2619)

- [grub2-editor (kcm_grub2): “Falha ao salvar as configurações do GRUB.” Erro no backend do D-Bus. (Todas as versões do OM Lx)](https://issues.openmandriva.org/show_bug.cgi?id=2618)

- [Samba não funciona](https://issues.openmandriva.org/show_bug.cgi?id=2609)

Bugs registrados no GitHub Issues:

- [Usuário precisa digitar a senha duas vezes para o Wi-Fi (applet do NetworkManager com defeito) #53](https://github.com/OpenMandrivaAssociation/OpenMandrivaAssociation.github.io/issues/53)


