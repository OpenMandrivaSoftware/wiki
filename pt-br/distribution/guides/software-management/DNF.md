---
title: Usando o dnf no OpenMandriva Lx
description: 
published: true
date: 2026-04-01T08:51:38.330Z
tags: documentação, dnf, guia do usuário
editor: markdown
dateCreated: 2020-03-06T18:48:34.373Z
---

# Usando o dnf no OpenMandriva Lx

> Para obter a documentação completa e ver mais comandos, consulte a **Referência de Comandos do DNF** [[dnf5]](https://dnf5.readthedocs.io/en/latest/index.html) [[dnf4]](https://dnf.readthedocs.io/en/latest/command_ref.html)
{.is-success}


## ALguns comandos básicos

- Instalar um pacote:
`$ sudo dnf --refresh install <package_name>`

- remover um pacote:
`$ sudo dnf remove <package_name>`

- procurar repositórios para um pacote:
`$ sudo dnf search <package_name>`
Nota: 'dnf search' irá trabalhar com nomes parciais também

- limpar todos os arquivos e pacotes deixados no cache e remover os metadados dos repositórios:
`$ sudo dnf clean all ; dnf clean all`

- atualize seu sistema Rock
`$ sudo dnf --refresh upgrade `

- atualize seu sistema Rolling:
`$ sudo dnf --refresh distro-sync `

## Alguns outro comandos dnf

`autoremove`
remove os pacotes instalados como dependências que não são mais necessários pelos programas atualmente instalados.
> Tenha cuidado e preste atenção ao usar `dnf autoremove`. É absolutamente possível que isso remova algo que você não queira remover. É uma boa ideia manter uma lista dos pacotes que foram removidos automaticamente, para que você saiba quais reinstalar caso isso aconteça.
Nota: Você pode encontrar os pacotes removidos automaticamente em `/var/log/dnf.log`
{.is-warning}


`check-update`
verifica se há atualizações, mas não baixa nem instala os pacotes.

`downgrade`
reverte para a versão anterior de um pacote

`info`
fornece informações básicas sobre o pacote, incluindo nome, versão, lançamento e descrição

`reinstall`
reinstala o pacote atualmente instalado

`repolist`
lista os repositórios habilitados

## Alguns comandos podem ser abreviados

`dnf in=dnf install`
`dnf ri=dnf reinstall`
`dnf dg=dnf downgrade`
`dnf rm=dnf remove`
`dnf up=dnf upgrade`
`dnf dsync=dnf distro-sync`

## Algumas opções comuns do dnf

`--allowerasing`
Permite a remoção de pacotes instalados para resolver dependências. Esta opção pode ser usada como alternativa ao comando swap do yum, quando os pacotes a serem removidos não são definidos explicitamente. Use com cuidado, saiba o que está fazendo, caso contrário você pode danificar seu sistema.

`-b, --best`
Tenta usar as melhores versões de pacotes disponíveis nas transações. Especificamente durante o dnf upgrade, que por padrão ignora atualizações que não podem ser instaladas por motivos de dependências, essa opção força o DNF a considerar apenas os pacotes mais recentes. Ao encontrar pacotes com dependências quebradas, o DNF falhará, informando o motivo pelo qual a versão mais recente não pode ser instalada.

`--disable, --set-disabled`
Desabilita os repositórios especificados (salva automaticamente). A opção deve ser usada em conjunto com o comando config-manager (dnf-plugins-core).

`--disablerepo=<repoid>`
Desabilita repositórios específicos por meio de um ID ou de um padrão glob. Essa opção é mutuamente exclusiva com `--repo`.

`--downloadonly`
Baixa o conjunto de pacotes resolvido sem executar nenhuma transação RPM (instalação/atualização/remoção).

`--enable, --set-enabled`
Habilita os repositórios especificados (salva automaticamente). A opção deve ser usada em conjunto com o comando config-manager (dnf-plugins-core).

`--enablerepo=`<repoid>
Habilita repositórios adicionais por meio de um ID ou de um padrão glob.

`--exclude=<package_name>`
Exclui determinados pacotes da transação.

`--nobest`
Define a opção best como False, para que as transações não sejam limitadas apenas aos melhores candidatos.

`-y, --assumeyes`
Responde automaticamente "sim" a todas as perguntas.

## Mais
`$ dnf --help`
and
`$ man dnf4` or `$ man dnf5` 

O menu de ajuda leva cerca de um minuto a um minuto e meio para ser lido. A página de manual leva cerca de 3-5 minutos.
Ambos foram feitos para estar disponíveis para consulta pelos usuários enquanto utilizam o sistema e precisam encontrar rapidamente como fazer algo.

Também há páginas e documentos da wiki sobre o DNF: [Usando o gerenciador de pacotes de software DNF](https://docs.fedoraproject.org/en-US/quick-docs/dnf/), [página da wiki do Fedora](https://fedoraproject.org/wiki/DNF?rd=Dnf) e [Referência de Comandos do DNF dnf5](https://dnf5.readthedocs.io/en/latest/index.html) | [Referência de Comandos do DNF dnf4](https://dnf.readthedocs.io/en/latest/command_ref.html) | [Alterações entre DNF(4) e DNF5](https://dnf5.readthedocs.io/en/latest/changes_from_dnf4.7.html)


