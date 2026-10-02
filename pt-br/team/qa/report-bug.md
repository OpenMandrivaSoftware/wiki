---
title: Como relatar um bug
description: 
published: true
date: 2022-03-24T10:53:52.452Z
tags: documentação, qa
editor: markdown
dateCreated: 2020-03-01T21:44:55.485Z
---

# Como relatar um bug

Descrição de como registrar um relatório de bug com a máxima precisão. Dessa forma, os desenvolvedores sabem exatamente o que precisa ser feito para aplicar as correções aos nossos produtos tão queridos.

## O que são bugs?
Um bug de software é um erro, falha, defeito ou problema em um software ou sistema de computador que faz com que ele produza um resultado incorreto ou inesperado, ou se comporte de maneiras não previstas.

Os usuários do OM Lx são incentivados a registrar relatórios de bugs caso acreditem que exista um problema que necessite da atenção dos desenvolvedores. Se você tiver um problema que acredita que outros usuários possam ajudá-lo a resolver, então o local apropriado é o nosso [Fórum do OpenMandriva](https://forum.openmandriva.org/).
Se estiver em dúvida, publique no nosso fórum e alguém da equipe de QA poderá orientá-lo.

Somos um pequeno grupo formado inteiramente por voluntários, portanto, pedimos que tenha paciência e nos dê algum tempo para realizar as tarefas. E agradecemos antecipadamente por relatar problemas no OM Lx.

## Onde relatá-los?

Se quiser relatar um bug, use nosso [Rastreador de Problemas](https://github.com/OpenMandrivaAssociation/distribution/issues), mesmo que você já o tenha relatado no Matrix ou no Fórum do OpenMandriva.

- É necessária uma conta no GitHub para usar o Rastreador de Problemas.
- Clique no link **'New issue'** (para registrar um novo bug)
- Selecionar [Bug report > Get started](https://github.com/OpenMandrivaAssociation/distribution/issues/new/choose) geralmente é o link apropriado para relatórios de bugs comuns.

## Boas práticas ao relatar bugs no OpenMandriva
- Verifique se um problema semelhante já foi relatado.
Se você encontrar o mesmo problema ou um problema muito semelhante e ele ainda não tiver sido confirmado, faça isso. Isso pode ser feito usando uma breve mensagem, como "Confirmando no OM Lx 4.3 mais recente em 11 de março de 2022, totalmente atualizado".
- **Um bug, um relatório**
Algumas pessoas colocam todos os problemas que estão enfrentando em um único relatório. Por favor, registre um relatório de bug separado para cada problema.
- O GitHub Issues não é o lugar para pedir ajuda ou participar de discussões gerais.
Use o [fórum público](https://forum.openmandriva.org/) que disponibilizamos para discutir os problemas que você está enfrentando, converse sobre eles por lá e, se você concordar que o problema deve ser relatado como um bug, faça isso!
- O idioma oficial no sistema de rastreamento de bugs é o inglês.
Mas não exigimos um inglês regional específico (como o inglês britânico ou o inglês americano). Sabemos que o inglês não é a língua nativa de todos, mas esperamos que você faça o possível para escrever os relatórios em inglês. Afinal, ele é a língua franca do mundo dos negócios. Desenvolvedores, mantenedores de pacotes, a equipe de QA e outros colaboradores trabalham em inglês.
- Certifique-se de que o bug não esteja ocorrendo também no projeto upstream.
No OpenMandriva, desenvolvemos uma distribuição baseada em Linux, uma coleção de softwares que recebemos de outros projetos de software Livre e de Código Aberto. A maioria dos pacotes do OpenMandriva é compilada a partir do código-fonte upstream. O OpenMandriva também colabora com projetos upstream. Acreditamos firmemente que fazemos parte do ecossistema Linux como um todo e queremos que outras distribuições também se beneficiem do nosso trabalho.
- Os usuários são incentivados a relatar qualquer problema que acreditam que possa ser um erro, defeito, falha ou problema em um software ou sistema de computador, por menor que seja.
Até mesmo coisas como erros de digitação devem ser relatadas e corrigidas.
- Use um bom título que reflita o que você está vivenciando.
Inclua qual é o problema. Sempre informe a versão ou a edição da sua distribuição OpenMandriva em uso. Seja preciso para não desperdiçar muito tempo dos desenvolvedores na identificação do problema específico.
- Forneça a saída do console, se possível.
Se você tiver problemas para iniciar um aplicativo, por exemplo, tente iniciá-lo pela linha de comando em um emulador de terminal. Se houver uma saída com informações adicionais, envie essa saída para nós em um arquivo de texto usando um editor de texto simples, como o Kwrite ou o LeafPad. Apenas não use formatos de documentos de suítes de escritório completas (formato `.odt` no LibreOffice etc.). Os desenvolvedores preferem receber a saída do console em vez de capturas de tela ou fotografias tiradas com a câmera do smartphone ou dispositivo móvel.
- Anexe a saída do programa no console usando o prefixo `LC_ALL=C`.
Exemplo: `LC_ALL=C dnf install <some_package>` para forçar a saída do console em inglês, facilitando a compreensão pelos desenvolvedores. Se o seu computador estiver configurado para um idioma diferente do inglês, isso deve ser feito para **todos** os comandos.
- Os logs são a melhor ferramenta que temos para que os desenvolvedores tentem compreender problemas que não conseguem reproduzir.
Os logs do sistema em versões modernas do Linux são chamados de journal e podem ser acessados com o comando `journalctl`. Outros logs comuns podem ser encontrados no diretório `/var/log`. Entre eles estão dnf.log e Xorg.0.log. Se precisar de ajuda para coletar os logs relacionados ao seu problema, pergunte e alguém poderá ajudá-lo.
Nota: a ferramenta [om-bug-report](/team/qa/bugreport-tool) já inclui informações suficientes de log para muitos bugs. Se os desenvolvedores precisarem de mais informações, eles solicitarão.
- Tente garantir que todas as atualizações mais recentes estejam instaladas.
O motivo disso é que não queremos que você perca tempo quando uma correção de bug já tiver sido aplicada em uma versão atualizada do software.
- Sobre sugestões dos usuários:
Obter novas ideias e inspiração de outras pessoas é sempre bom, mas os relatórios de bugs devem se concentrar na qualidade do software.
- Inclua o arquivo `omv-bug-report.log` para fornecer informações adicionais sobre o seu sistema de computador.

## Tenho um novo pacote, uma atualização de pacote ou uma solicitação de novo recurso

Faça o seguinte:
- Registre um problema no [Rastreador de Bugs](https://github.com/OpenMandrivaAssociation/distribution/issues/new/choose)
- Selecione uma das opções:
-- *Enhancement request*
-- *Package request*
-- *Package update*
de acordo com a sua solicitação.

- Escreva 'Package Request' no título, juntamente com o nome do pacote que você gostaria que fosse compilado, atualizado, disponibilizado etc. Informe também qual número de versão você gostaria de ter.
- Insira a URL do código-fonte do pacote, ou a URL do RPM de código-fonte, no campo URL do formulário.
- Faça algumas observações no campo de descrição. Gostaria de solicitar o pacote XYZ.
- Analisaremos o site do projeto e tentaremos atender à sua solicitação.
- Acompanhe regularmente o status do seu problema. Quando aceitarmos a solicitação e o processo de compilação estiver em andamento, ela será marcada como **'IN PROGRESS'**. Quando o pacote estiver pronto, nós a marcaremos como **'RESOLVED/FIXED'**.

## Casos comuns
Abaixo, você encontrará algumas instruções sobre como registrar corretamente um bug quando se deparar com esses cenários comuns.

### Meu OpenMandriva Lx não quer iniciar um programa

O OpenMandriva Lx é uma coleção de programas de software que tentamos fazer funcionar da melhor maneira possível. É importante distinguir entre aplicativos de console e aplicativos gráficos do X-Window, que fornecem uma interface gráfica de usuário.

Aqui está o que você pode fazer para verificar se um aplicativo gráfico não inicia:
- Abra um terminal quando estiver conectado ao seu ambiente gráfico.
  Você geralmente encontrará isso em seções como *Ferramentas* ou *Ferramentas do sistema*. No ambiente de trabalho KDE Plasma, use o Konsole; no LXQt, use o LXQt Terminal.
- Tente iniciar esse aplicativo pela linha de comando. Se não souber o que digitar, tente descobrir o nome do binário que deseja iniciar. Você pode usar o gerenciador de pacotes para descobrir isso. Na maioria das vezes, ele é simplesmente o nome do pacote. Por exemplo, para iniciar o gerenciador de arquivos Dolphin no Konsole, basta digitar `dolphin` e pressionar <kbd>Enter</kbd>.
- Você também pode tentar digitar apenas as primeiras letras do aplicativo (por exemplo, `libre` para o LibreOffice) e, em seguida, pressionar a tecla <kbd>Tab </kbd>para usar o recurso de autocompletar do shell bash que está sendo executado dentro do Terminal que você acabou de abrir. Se isso não produzir nenhum efeito, tente pressionar a tecla <kbd> Tab</kbd> duas vezes rapidamente. Você deverá então ver uma lista de possíveis correspondências.
- Depois de executar o comando, se você obtiver mensagens como core dumped ou outros erros inesperados, envie essas saídas. O ideal é colocá-las em um arquivo de texto e anexar esse arquivo ao seu relatório de bug usando o link "Add an Attachment" no Bugzilla. Inclua toda a saída, incluindo o comando que você utilizou.
- Por favor, deixe-nos saber qual ambiente de desktop você está usando.
- Lembre-se: **um bug, um relatório**. Isso facilita o nosso trabalho ao lidar com os problemas um por um.

### Meu OpenMandriva Lx não inicia o ambiente gráfico

Com o OpenMandriva, usamos o Xorg como servidor para fornecer a saída gráfica ao monitor do seu computador. Caso a tela permaneça preta, tente alternar para um terminal virtual, que deve estar configurado por padrão. Você pode acessar os terminais virtuais pressionando <kbd>Ctrl + Alt + F2 </kbd> (ou `F3` até `F6`, conforme sua preferência).
Tente fazer login a partir daí e informe, em um relatório de bug, qual hardware gráfico você está utilizando. O comando a seguir deve fornecer essas informações:
`lspci -nnk | grep -EiA3 'vga|3d|display'`

Inclua o arquivo `omv-bug-report.log` para fornecer informações adicionais sobre o seu sistema de computador.

Em seu relatório de bug, informe também qual ambiente gráfico você deseja iniciar. Usamos o ambiente de trabalho KDE Plasma por padrão, mas, caso queira experimentar outro ambiente, inclua essa informação em seu relatório.


