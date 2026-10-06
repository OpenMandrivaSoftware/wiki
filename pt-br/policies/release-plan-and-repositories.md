---
title: Plano de Lançamentos e Repositórios do OpenMandriva
description: 
published: true
date: 2025-01-07T00:10:11.182Z
tags: documentação
editor: markdown
dateCreated: 2020-02-28T17:02:32.116Z
---

# Plano de Lançamentos e Repositórios do OpenMandriva

Antes de fazer qualquer alteração relacionada aos canais de lançamento ou atualização, se você tiver a menor dúvida, pare, não faça isso e peça orientação em nosso fórum ou no Chat com a equipe do OpenMandriva

## Lançamento
Um lançamento é um conjunto de pacotes de software
reunidos para formar um sistema
operacional. Cada lançamento é identificado por sua
"versão", como *Mandriva 2009*,
*Windows XP*, *OpenMandriva Lx 2014*,
*OpenMandriva Lx 4.2*, etc. Os lançamentos também
são chamados de *Canais de Atualização*. Release,
Rock, Rolling e Cooker são diferentes
versões de lançamento/canais de atualização do
OpenMandriva Lx. A ênfase está na palavra
diferentes. **Eles não devem ser
combinados**.

## Repositórios
Repositórios são servidores que contêm conjuntos
de pacotes, literalmente arquivos .rpm. No
sistema operacional OpenMandriva, os softwares são
empacotados em arquivos .rpm que contêm os
programas e bibliotecas necessários. Esses arquivos
podem ser baixados e alguns também estão
incluídos em arquivos .iso como uma versão específica
de "lançamento" para instalação pelo usuário. Cada
versão de lançamento do OpenMandriva possui seus
próprios repositórios. Eles não são
intercambiáveis, **não os misture**. Os usuários geralmente
acessam esses arquivos com ferramentas de gerenciamento
de pacotes como o [DNF](/distribution/guides/software-management/DNF) ou, anteriormente,
o URPM. Também existem ferramentas gráficas para isso,
como o dnfdragra, o Discover e, anteriormente,
o RpmDrake.

## Plano de Lançamentos
O "Plano de Lançamentos", também conhecido como "Canais
de Atualização", é uma hierarquia de pacotes de software
agrupados (versões de lançamento) com o objetivo de
alcançar determinadas finalidades. Por exemplo, o canal
de lançamento/atualização Cooker foi projetado
especificamente para desenvolvedores trabalharem, mesmo
que acabem causando problemas. Outro exemplo é o canal
de lançamento/atualização Rock, projetado para usuários
comuns utilizarem o computador no dia a dia e desenvolvido
para não apresentar problemas (literalmente projetado para
ser "estável").

Com o lançamento do OpenMandriva Lx 4.0,
a distribuição OpenMandriva implementou um novo
plano de lançamentos para organizar melhor o fluxo
de trabalho de manutenção dos pacotes e simplificar
e acelerar o processo de lançamento. Isso é
estreitamente coordenado com nossa estrutura de
repositórios. Em um determinado sistema, use apenas
um lançamento. **Não misture lançamentos/canais de
atualização, pois é provável que ocorram conflitos
de pacotes se isso não for garantido.**

Os lançamentos também são conhecidos como "Canais de Atualização". Cada versão acima possui seus próprios repositórios. Os repositórios ou arquivos .repo são
encontrados no diretório `/etc/yum.repos.d/`. Por nome, os repositórios são, respectivamente, openmandriva-cooker, openmandriva-rolling, openmandriva-rock e openmandriva-release. 
Os repositórios são ainda definidos e nomeados de acordo com a arquitetura. Exemplo abaixo.

- **Cooker (Instável)**

Cooker é o ramo de desenvolvimento. É aqui que os desenvolvedores realizam o trabalho de desenvolvimento dos pacotes e da própria distribuição. Devido à natureza desse processo de trabalho contínuo, o Cooker apresenta problemas às vezes. Isso é normal. 
Não estamos dizendo que o Cooker *pode apresentar problemas*; estamos dizendo, com toda honestidade, que o Cooker *vai apresentar problemas*. 
Se você não está acostumado a resolver problemas em computadores em um nível muito avançado, o Cooker não é para você.

- **ROME (Rolling)**

A versão ROME (Rolling) ainda está em desenvolvimento e não foi oficialmente anunciada. Atualmente, toda a versão ROME está em fase de testes e ainda não está pronta para uso em produção.

Os desenvolvedores enviam pacotes para o ROME quando acreditam que estão prontos para uso. 
O ROME é uma versão rolling e terá os pacotes mais atualizados possíveis.
Ele foi projetado para ser um sistema funcional e utilizável. Os usuários do ROME precisam ser capazes de resolver alguns problemas por conta própria, como em qualquer versão "bleeding edge". Além disso, os usuários do ROME devem estar familiarizados e ser capazes de usar a linha de comando ou o terminal (Konsole) em algumas situações.

-   **Rock (Estável)**

Os repositórios Rock consistem em um link simbólico para a versão estável mais recente do OpenMandriva. Atualmente, o Rock está vinculado ao OM Lx 4.2. No entanto, quando o OMLx 4.3 for lançado, o Rock será automaticamente alterado para o OM Lx 4.3.

-   **Release (Estável)**

Os repositórios Release são as versões estáveis mais recentes do OpenMandriva Lx, atualmente o Lx 4.1 e 4.2. Os repositórios Release permanecem com a mesma versão. Se você instalar o OM Lx 4.2 e usar o repositório Release em vez do Rock, você permanecerá no repositório 4.2. A versão Release/Estável é destinada a usuários que preferem que as coisas permaneçam como estão e simplesmente funcionem. As atualizações de pacotes serão limitadas principalmente a correções de bugs e atualizações de segurança. Tenha em mente que qualquer versão eventualmente chegará ao EOL (End Of Life, fim de vida) e não haverá mais atualizações de nenhum tipo.

E lembre-se do seguinte: em um determinado sistema, use apenas um lançamento. 
**Não misture canais de lançamento/atualização, pois é provável que ocorram conflitos de pacotes se isso não for garantido.**

O fluxo de empacotamento agora é:
`Cooker/Instável > ROME/Rolling > Release/Estável`
*Lembre-se de que Rock é um link simbólico para a versão estável mais recente.*

## Lista de arquivos de repositório

Usando o OM Lx x86\_64 como exemplo
*z nver1 users verão znver1 em vez de x86\_64*

Cada Release acima possui seus próprios repositórios. Eles não são intercambiáveis; não os misture.

Estes são os arquivos de repositório para OpenMandriva Lx x86\_64. 
Os arquivos i686 existem apenas para a instalação ocasional de aplicativos de 32 bits, como Wine, Steam ou jogos **no 4.1**.
Recomenda-se habilitá-los somente para instalar e atualizar esses pacotes específicos e, caso contrário, mantê-los desabilitados. Caso contrário, podem ocorrer problemas estranhos, confusos e imprevistos. 
Tenha em mente que quaisquer desenvolvedores que ainda desenvolvam para 32 bits "somente" estão monumentalmente atrasados em termos de progresso técnico no Linux.

Arquivos de repositório listados em ordem alfabética, como aparecem no sistema do usuário

- **Cooker (Instável)**

`openmandriva-cooker-i686.repo`
`openmandriva-cooker-i686-source.repo`
`openmandriva-cooker-x86_64.repo`
`openmandriva-cooker-x86_64-source.repo`

- **Release (Estável)**

`openmandriva-release-i686.repo`
`openmandriva-release-i686-source.repo`
`openmandriva-release-x86_64.repo`
`openmandriva-release-x86_64-source.repo`

- **Rock (link simbólico para a versão Estável mais recente)**

`openmandriva-rock-i686.repo`
`openmandriva-rock-i686-source.repo`
`openmandriva-rock-x86_64.repo`
`openmandriva-rock-x86_64-source.repo`

- **ROME ("Rolling muito atualizado")**

`openmandriva-rolling-i686.repo`
`openmandriva-rolling-i686-source.repo`
`openmandriva-rolling-x86_64.repo`
`openmandriva-rolling-x86_64-source.repo`

*Os usuários de znver1 verão znver1 em vez de x86_64*

Os usuários normalmente não utilizam arquivos source.repo; se você não tiver motivo para usá-los, deixe-os como estão.

## Arquivos de repositório normalmente utilizados

Para simplificar, a grande maioria dos usuários x86_64 normalmente usará apenas **um** desses quatro.

Arquivos de repositório listados do mais estável primeiro/ ao menos estável por último:

`openmandriva-release-x86_64.repo`
`openmandriva-rock-x86_64.repo`
`openmandriva-rolling-x86_64.repo`
`openmandriva-cooker-x86_64.repo`

*Os usuários de znver1 verão znver1 em vez de x86_64*

## Fontes de mídia

Dentro de cada arquivo de repositório listado acima, temos estas quatro fontes ou categorias básicas de "Mídia":

- **main**

`/main` contém os pacotes principais mantidos pela equipe do OpenMandriva Lx. Isso inclui tudo o que está incluído nas imagens de instalação, além de muitos outros aplicativos considerados importantes. O repositório /main/release deve estar sempre habilitado. Se o seu sistema estiver usando o arquivo de repositório Release ou Rock, então /main/release/updates também deve estar sempre habilitado.

- **extra**

`/extra` represents "community maintained" packages. These are not supported by the core OpenMandriva Lx team, and depend on package maintainers to update it. There are many packages in extra that will not install and others that install but do not work properly. Users are welcome to use whatever they find in this repository that is working.

- **restricted**

`/restricted` contém bibliotecas que não são instaladas por padrão devido a questões legais, como problemas relacionados a patentes. 
O uso desses pacotes varia de acordo com o país. O OpenMandriva Lx não se responsabiliza pelo uso deles!
**Se você acredita que o uso deles não é permitido em seu país, desabilite os repositórios restricted**.

- **non-free**

`/non-free` contém aplicativos e drivers que são distribuídos, mas não atendem às definições de [Software Livre](https://en.wikipedia.org/wiki/The_Free_Software_Definition). Embora possamos ajustar o empacotamento desses aplicativos, "não temos o código-fonte e, portanto, não podemos corrigir problemas causados por qualquer coisa neste repositório".

## Explicação sobre o que habilitar nas categorias de repositórios

Você pode habilitar qualquer uma das opções a seguir com o Seletor de Repositórios de Software (om-repo-picker), no Lançador de Aplicativos, em Sistema. Há um guia [aqui](https://forum.openmandriva.org/t/2726).

Na prática, para qualquer uma das categorias Release escolhidas, o repositório Main deve estar sempre habilitado. Para Release (Stable) e Rock, devem ser habilitados (usando um sistema x86_64 como exemplo)

`/x86_64/main/release/`
`/x86_64/main/updates/`

*Os usuários de znver1 verão znver1 em vez de x86_64*

A decisão de usar qualquer um ou todos os repositórios Extra, Restricted ou Non-Free cabe ao usuário, mas, se optar por isso, também deverá habilitar /release e /updates para cada um.

`/x86_64/extra/release/`
`/x86_64/extra/updates/`
`/x86_64/restricted/release/`
`/x86_64/restricted/updates/`
`/x86_64/non-free/release/`
`/x86_64/non-free/updates/`

*Os usuários de znver1 verão znver1 em vez de x86_64*

Rolling e Cooker diferem pelo fato de não haver uma categoria de atualização para eles, portanto basta remover as entradas /updates da lista acima.

Para uma explicação um pouco mais detalhada, para Release/Stable e Rock, seriam habilitadas 2, 4, 6 ou, no máximo, 8 categorias de mídia. Para ROME ou Cooker, seriam habilitadas entre 1 e, no máximo, 4 categorias de mídia. Isso em circunstâncias normais. (Não existem repositórios de atualizações para ROME ou Cooker.)





