---
title: Espelhamento
description: 
published: true
date: 2025-02-02T13:22:44.309Z
tags: Documentação
editor: markdown
dateCreated: 2020-03-14T19:10:14.516Z
---

# Mirroring
## Lista dos espelhos

> 📊 **Ranking de confiabilidade em tempo real** (gerado automaticamente, diariamente): consulte o **[Status dos mirrors](https://mirror.openmandriva.org/status)** para verificar a disponibilidade e a atualização de cada mirror.
{.is-info}

### Mirmon (Gerenciador de Espelhos)
![Website](https://img.shields.io/website?label=MirMon%20status&url=https%3A%2F%2Fmirmon.openmandriva.org)
Aqui você consegue verificar se um espelho está atualizando regularmente.
- https://mirmon.openmandriva.org/

### Mirrorbits (redirecionamento para espelho mais próximo)
![Website](https://img.shields.io/website?label=Mirrorbits%20status&url=https%3A%2F%2Fmirror.openmandriva.org%2FREADME.txt%3Fstats)
Você pode ver como os espelhos estão distribuídos ao redor do mundo.
- http://mirror.openmandriva.org?mirrorstats

## Encontre o espelho mais próximo
O Mirrorbits pode redirecionar automaticamente para o servidor espelho mais próximo da sua localização. Aqui está um exemplo com um simples arquivo txt disponível nos repositórios:
- Redirecionamento Imediato: http://mirror.openmandriva.org/release_current/README.txt 
- Representação Visual  http://mirror.openmandriva.org/release_current/README.txt?mirrorlist

## Topologia do espelho

O OpenMandriva utiliza uma topologia plana: **cada espelho sincroniza diretamente a partir da origem (ABF)**. Não há níveis intermediários, portanto, um mirror atrasado nunca propaga dados desatualizados para os demais, e cada mirror pode estar tão atualizado quanto a fonte.

> **Os usuários finais não precisam escolher um mirror.** Aponte suas ferramentas para **`mirror.openmandriva.org`** (Mirrorbits): ele redireciona para o mirror saudável mais próximo e recorre ao ABF caso um arquivo esteja ausente. A confiabilidade de cada mirror em tempo real está disponível na página de [Status dos mirrors](https://mirror.openmandriva.org/status).
{.is-info}

## Configurando um espelho
Se você quiser nos apoiar configurando um espelho para o OpenMandriva Lx, sincronize diretamente a partir da nossa origem (distribuição ABF) para que seu espelho permaneça tão atualizado quanto a fonte:
- `rsync -av rsync://abf-downloads.openmandriva.org/openmandriva/ /local/path/`
> Não esqueça o arquivo ''TIME.txt''. Ele é necessário para que o Mirmon e Mirrobits funcionar corretamente.
>
> Pelo menos '''600GB''' de espaço livre no disco é necessário
{.is-warning}


## Espelho T0

Nosso espelho T0, ABF, é onde os pacotes são compilados e distribuídos. Há muito mais pacotes nele do que em nossos outros espelhos, como código-fonte e pacotes de depuração, pacotes de versões antigas, repositórios pessoais etc.

Seus conteúdos podem ser explorados através do endereço:

- http://abf.openmandriva.org

O Mirrorbits sempre redirecionará para o ABF se um arquivo não existir em nenhum dos servidores espelho. Por exemplo:
- http://mirror.openmandriva.org/release_current/README.txt 
- http://mirror.openmandriva.org/release_current/README.txt?mirrorlist