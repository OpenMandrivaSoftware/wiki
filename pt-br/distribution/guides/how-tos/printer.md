---
title: Como configurar a impressora no OMLx
description: 
published: true
date: 2025-05-03T15:56:07.005Z
tags: documentação, howto, guia do usuário
editor: markdown
dateCreated: 2020-03-09T18:43:12.417Z
---

# Como configurar a impressora no OMLx
Ligue a impressora e veja se ela é configurada automaticamente. Verifique se o driver correto foi instalado.

Se a impressora foi configurada automaticamente e você tem o driver correto, está tudo pronto.

Se não foi, desligue a impressora.

Abra *Configurações da impressora*, também conhecido como `kcmshell6 kcm_printer_manager` (se estiver usando o Plasma 5, use `kcmshell5` em vez de `kcmshell6`), e remova a impressora.
Se o driver correto não tiver sido instalado por padrão, será necessário adicionar um pacote de software.

O próximo passo é determinar qual software instalar para a sua impressora.

No OpenMandriva Lx é mais provável que seja um pacote 'task-printing' específico para sua marca de impressora.
Os pacotes são:
- task-printing-canon
- task-printing-epson
- task-printing-hp
- task-printing-lexmark
- task-printing-okidata
- brlaser (para impressoras Brother)
- task-printing-misc

Instale o pacote correspondente à sua marca ou o pacote misc se nenhum deles for adequado.

Exemplo usando okidata:
```
$ sudo dnf install task-printing-okidata
```
Agora ligue a impressora novamente e ela deve ser configurada automaticamente (algumas vezes pode ser necessário reiniciar o sistema para a configuração automática funcionar).

Caso contrário busque ajuda [aqui](https://forum.openmandriva.org/c/support/17)
