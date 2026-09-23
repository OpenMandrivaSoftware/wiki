---
title: OpenMandriva Lx 5.0 Errata
description: 
published: true
date: 2025-02-12T09:23:40.726Z
tags: 5.0
editor: markdown
dateCreated: 2022-12-26T17:59:33.144Z
---

# Errata do OpenMandriva Lx 5.0 - Problemas conhecidos

> Como em qualquer lançamento, ainda existem problemas e bugs que podem não ter sido resolvidos. Esta página documenta aqueles que podem causar inconvenientes e, quando possível, detalhes sobre como contorná-los.
{.is-info}

**Leia também as [Notas do 5.0](/distribution/releases/omlx50/notes).**
<br>

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
Existe um problema conhecido com alguns SSDs NVME (especialmente os mais novos) e dispositivos PCIE, nos quais o SSD pode não ser reconhecido.
O problema é conhecido e está sendo trabalhado pelos desenvolvedores do OpenMandriva e pelos desenvolvedores upstream.

![header-tr-50.svg](/assets/header-tr-50.svg){.align-abstopright}
