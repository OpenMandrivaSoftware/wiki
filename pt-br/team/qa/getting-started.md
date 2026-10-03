---
title: QA/Começando
description: 
published: true
date: 2025-02-11T09:38:33.447Z
tags: qa, documentação
editor: markdown
dateCreated: 2020-03-02T15:35:06.431Z
---

# Começando com QA
Estamos felizes que você esteja interessado em QA.
Compilamos este documento para ajudá-lo a começar a nos ajudar a testar o OpenMandriva Lx.

Você precisará usar a linha de comando para realizar testes na maioria das vezes. Certifique-se de ter uma conta no [ABF](https://abf.openmandriva.org/) e no [Github](https://github.com/OpenMandrivaAssociation).

A comunicação diária da equipe de QA acontece no Matrix Chat `#openmandriva-cooker:matrix.org`, mas lembre-se de que este também é o espaço onde os desenvolvedores trabalham, portanto, tenha atenção à etiqueta de comunicação no chat.
Atualmente, o grupo de colaboradores do OpenMandriva é pequeno o suficiente para que desenvolvedores e a equipe de QA trabalhem juntos nas salas do Matrix. Há também um [Fórum de QA](https://forum.openmandriva.org/c/en/qa) dedicado.

Os membros da equipe de QA são incentivados a participar ativamente das reuniões semanais do TC (se possível).
</br>

### Configurando seu sistema OpenMandriva Lx 
Como você provavelmente estará trabalhando com software não testado (pelo menos com nosso sistema operacional), recomendamos fortemente que você use uma máquina dedicada ou virtual para testes. Para trabalhos de QA em hardware (recomendado, se possível), recomenda-se ter o Rolling instalado em uma partição separada, para que você tenha um sistema “estável” em outra partição caso algo dê errado durante os testes.

O software de pré-lançamento vem através dos repositórios de teste. Os pacotes no repositório Main têm precedência sobre aqueles nos outros repositórios. Os pacotes nos repositórios Unsupported e Non-Free são de responsabilidade do mantenedor do pacote, não dos desenvolvedores do OpenMandriva.

Os membros da equipe de QA precisam ter um conhecimento aprofundado do [Plano de Lançamento e Repositórios](/policies/release-plan-and-repositories) e das [Políticas de Repositórios](/policies/repository-policies). Haverá mais conteúdo à medida que documentarmos melhor o OpenMandriva Lx, mas gostamos de manter a documentação tão simples e enxuta quanto for viável.

O fluxo de trabalho para os pacotes é: Cooker > Rolling > repositório Stable. Os desenvolvedores/mantenedores de pacotes são responsáveis por iniciar os pacotes no Cooker e por movê-los para os repositórios Rolling/testing. Então, a equipe de QA assume. Portanto, todos os membros da equipe de QA são incentivados a manter um sistema Rolling onde possam realizar testes de pacotes.

Você pode adicionar os repositórios de teste com a [Interface Gráfica do Seletor de Repositórios de Software](/policies/repositories-tldr) do OpenMandriva ou pela linha de comando.

Para o repositório Main somente:

Rock system:
`sudo dnf config-manager --enable rock-testing-$ARCH`

Rolling system:
`sudo dnf config-manager --enable rolling-testing-$ARCH`

Substitua `$ARCH` pela sua arquitetura.

Para todos os repositórios de teste:

Rock system:
`sudo dnf config-manager --enable rock-testing-$ARCH rock-testing-$ARCH-unsupported rock-testing-$ARCH-restricted rock-testing-$ARCH-non-free`

Rolling system:
`sudo dnf config-manager --enable rolling-testing-$ARCH rolling-testing-$ARCH-unsupported rolling-testing-$ARCH-restricted rolling-testing-$ARCH-non-free`

Para desativar, basta substituir `--enable` por `--disable`.
</br>

### Testes de Pacotes com o Kahinah
Agora que seu sistema está configurado, é hora de votar nos pacotes. Eles funcionam? Existem problemas realmente graves?

Usamos um sistema chamado [Kahinah](https://kahinah.tsn.sh/), que utiliza votação para determinar quais pacotes devem ou não ser enviados para o repositório stable.

Faça login no Kahinah. Use seu login do Github.

Você pode ver quais pacotes estão aguardando para serem testados em **Recent Builds**. Dê um voto positivo ou negativo e informe-nos o motivo.

O procedimento atual é que os pacotes precisam de 3 votos de **“Accept”** para avançar, a menos que haja algum voto de **“Reject”**. Se houver sequer um voto de **“Reject”**, isso deve ser questionado e discutido antes de mover os pacotes. Além disso, os pacotes que ficarem parados no Kahinah sem votos por mais de 7 dias podem ser movidos devido à inação da equipe de QA. A discussão sobre isso acontece no Matrix, em `#openmandriva-cooker:matrix.org`.
</br>

### Testando novas ISOs Alpha/Beta/RC
Isso está sendo discutido [aqui](/team/qa/release-qa).
</br>

### Triagem de Novos Bugs no Rastreador de Problemas
https://github.com/OpenMandrivaAssociation/distribution/issues
Este processo está em desenvolvimento no momento. (Precisamos implementar algo para fazer a triagem dos relatórios de bugs.)