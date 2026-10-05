---
title: Políticas de Repositórios
description: 
published: true
date: 2025-01-29T10:22:06.940Z
tags: políticas, cooker, qa
editor: markdown
dateCreated: 2020-03-01T19:28:40.866Z
---

# Políticas de Repositórios

## Cooker
O Cooker é uma ramificação experimental que pode apresentar problemas às vezes.

A maioria das coisas pode ser feita aqui sem problemas, incluindo atualizar para uma versão beta ou até mesmo para um snapshot git/svn/cvs/hg/qualquer outro do pacote upstream.

Para garantir que você não "surpreenda" outros desenvolvedores quebrando tudo para eles, mudanças importantes precisam ser coordenadas por um dos seguintes meios:
- apresentando-as em uma reunião do TC
- enviando um pull request no repositório e aguardando que outros o aceitem
- entrando no [canal de desenvolvimento do Cooker](https://wiki.openmandriva.org/en/team/chat#develoment-cooker-discussions) e aguardando uma resposta positiva dos outros

As mudanças que precisam de coordenação incluem, mas não se limitam a:
- substituir um componente importante do sistema por outro (por exemplo, Xorg por Wayland, Qt 5 por Qt 6, wpa_supplicant por iwd, systemd por qualquer outro sistema de init, ...); qualquer mudança desse tipo deve ser testada primeiro em um repositório pessoal.
- uma atualização que exigirá muitas reconstruções (por exemplo, atualizar o libpng para uma versão com um novo soname)
- remover um pacote utilizado por muitas coisas (por exemplo, remover o Qt 5 quando o Qt 6 estiver disponível e tiver sido estabilizado)
- mudanças que provavelmente causarão problemas no hardware de outras pessoas

O Cooker geralmente está aberto para todos os tipos de desenvolvimento, mas pode ser congelado em alguns momentos para concentrar os esforços em uma única ramificação.

## Rolling
O Rolling precisa ser utilizável por pessoas comuns o tempo todo. Coisas que causem problemas graves não podem entrar no Rolling.

Para garantir que o Rolling seja sempre utilizável:
- Tudo o que for enviado para o Rolling deve primeiro ser compilado no Cooker. Exceção: algo para o qual o Cooker já tenha uma versão mais recente da mesma coisa; por exemplo, pode fazer sentido enviar o LLVM 8.0.1 para o Rolling se o Rolling estiver na versão 8.0, mesmo quando o Cooker já tiver avançado para a ramificação 9.0.
- Os desenvolvedores enviam os pacotes para `rolling/testing` — não para `rolling/release` — quando consideram que estão prontos para uso geral. A transferência de `rolling/testing` para `rolling/release` é feita pela equipe de QA, para garantir que os pacotes tenham sido testados no ambiente Rolling.
- O Rolling normalmente não deve usar versões beta ou snapshots de software upstream. Há exceções a essa regra, por exemplo, quando o upstream está preso em um ciclo de "lançamento nunca", quando uma versão beta/snapshot é a única que funciona em nosso ambiente, por exemplo, quando a versão "estável" ainda usa Qt 4 ou Python 2, ou quando há outros bons motivos).
O Rolling entra em congelamento pouco antes de novos lançamentos serem feitos, para que as versões possam ser lançadas essencialmente como um snapshot de `rolling/release`.

## Rock
Esta é a árvore da versão estável. Ela recebe apenas atualizações importantes, como correções de segurança ou correções para travamentos do sistema.

As pessoas que desejam a versão mais recente de algo devem usar o Rolling.
Isso significa que as pessoas que usam o Rock querem algo que nunca apresente falhas; portanto, é preciso ter atenção especial ao fazer qualquer alteração no Rock.
- Tudo o que for enviado para o Rock deve primeiro ser compilado no Rolling. Exceção: algo para o qual o Cooker já tenha uma versão mais recente da mesma coisa; por exemplo, pode fazer sentido enviar o LLVM 8.0.1 para o Rock se o Rock estiver na versão 8.0, mesmo quando o Rolling já tiver avançado para a ramificação 9.0.
- Os desenvolvedores enviam os pacotes para `rock/testing` — não para `rock/release` — quando consideram que estão prontos para uso geral. A transferência de `rock/testing` para `rock/release` é feita pela equipe de QA, para garantir que os pacotes tenham sido testados no ambiente Rock.
- O Rock normalmente não deve usar versões beta ou snapshots de software upstream. Tenha ainda mais cuidado com isso do que no Rolling. Há exceções a essa regra, por exemplo, quando o upstream está preso em um ciclo de "lançamento nunca", quando uma versão beta/snapshot é a única que funciona em nosso ambiente, por exemplo, quando a versão "estável" ainda usa Qt 4 ou Python 2, ou quando há outros bons motivos.
- As atualizações normalmente não devem alterar a interface do usuário. As pessoas que usam o Rock querem algo com que estejam familiarizadas e não querem surpresas.
- **Se estiver em dúvida, não faça**. As pessoas que quiserem a atualização por algo que não seja importante devem usar o Rolling.

