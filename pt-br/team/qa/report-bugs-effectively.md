---
title: Como relatar bugs de forma eficaz
description: 
published: true
date: 2021-09-26T21:35:08.851Z
tags: howto, documentação
editor: markdown
dateCreated: 2020-03-09T15:27:16.367Z
---

# Como relatar bugs de forma eficaz

## Introdução
Qualquer pessoa que tenha escrito software para uso público provavelmente já recebeu pelo menos um relatório de bug ruim. Relatórios que não dizem nada ("Não funciona!"); relatórios que não fazem sentido; relatórios que não fornecem informações suficientes; relatórios que fornecem informações incorretas. Relatórios de problemas que acabam sendo um erro do usuário; relatórios de problemas que acabam sendo culpa de outro programa; relatórios de problemas que acabam sendo falhas de rede.

Há uma razão pela qual o suporte técnico é considerado um trabalho terrível, e essa razão são os maus relatórios de bugs. No entanto, nem todos os relatórios de bugs são desagradáveis: mantenho software livre quando não estou trabalhando para ganhar a vida e, às vezes, recebo relatórios de bugs maravilhosamente claros, úteis e informativos.

Neste texto, tentarei explicar claramente o que caracteriza um bom relatório de bug. Idealmente, gostaria que todas as pessoas no mundo lessem este texto antes de relatar qualquer bug a alguém. Certamente, gostaria que todos que relatam bugs para mim tivessem lido este texto.

Em resumo, o objetivo de um relatório de bug é permitir que o programador veja o programa falhando diante de seus olhos. Você pode mostrar isso pessoalmente ou fornecer instruções cuidadosas e detalhadas sobre como fazer o programa falhar. Se ele conseguir reproduzir a falha, tentará coletar informações adicionais até descobrir a causa. Se não conseguir reproduzi-la, terá que pedir que você colete essas informações para ele.

Nos relatórios de bugs, tente deixar muito claro quais são os fatos reais ("Eu estava no computador e isso aconteceu") e quais são especulações ("Acho que o problema pode ser este"). Deixe de fora as especulações, se quiser, mas não deixe de fora os fatos.

Quando você relata um bug, faz isso porque quer que o bug seja corrigido. Não adianta xingar o programador ou ser deliberadamente pouco prestativo: a culpa pode ser dele e o problema pode ser seu, e você pode ter razão em estar com raiva dele, mas o bug será corrigido mais rapidamente se você ajudá-lo fornecendo todas as informações de que ele precisa. Lembre-se também de que, se o programa for gratuito, o autor o disponibiliza por gentileza; portanto, se muitas pessoas forem rudes com ele, pode ser que ele deixe de se sentir disposto a ajudar.

## "Não funciona"
Dê ao programador o devido crédito por sua inteligência básica: se o programa realmente não funcionasse de jeito nenhum, ele provavelmente já teria percebido. Como ele não percebeu, isso significa que o programa está funcionando para ele. Portanto, ou você está fazendo algo diferente do que ele faz, ou seu ambiente é diferente do ambiente dele. Ele precisa de informações; fornecer essas informações é o objetivo de um relatório de bug. Quase sempre, mais informações são melhores do que menos.

Muitos programas, especialmente os gratuitos, publicam uma lista de bugs conhecidos. Se você encontrar uma lista de bugs conhecidos, vale a pena lê-la para verificar se o bug que acabou de encontrar já é conhecido ou não. Se já for conhecido, provavelmente não vale a pena relatá-lo novamente, mas, se você acredita ter mais informações do que as apresentadas no relatório da lista de bugs, talvez queira entrar em contato com o programador mesmo assim. Ele poderá corrigir o bug mais facilmente se você fornecer informações que ainda não tinha.

Este texto está repleto de orientações. Nenhuma delas é uma regra absoluta. Cada programador tem suas próprias preferências sobre como os bugs devem ser relatados. Se o programa vier acompanhado de suas próprias orientações para o relato de bugs, leia-as. Se as orientações que acompanham o programa contradisserem as orientações deste texto, siga as que acompanham o programa!

Se você não estiver relatando um bug, mas apenas pedindo ajuda para usar o programa, informe onde você já procurou a resposta para sua pergunta. ("Procurei no capítulo 4 e na seção 5.2, mas não encontrei nada que dissesse se isso é possível.") Isso permitirá que o programador saiba onde as pessoas esperam encontrar a resposta, para que ele possa tornar a documentação mais fácil de usar.

## "Me mostre"
Uma das melhores maneiras de relatar um bug é mostrá-lo ao programador. Coloque-o diante do seu computador, inicie o software dele e demonstre o que dá errado. Deixe-o observar você iniciar a máquina, executar o software, interagir com o software e observar o que o software faz em resposta às suas ações.

Eles conhecem o software como a palma da mão. Sabem em quais partes confiam e quais partes provavelmente apresentam falhas. Sabem intuitivamente o que observar. Quando o software fizer algo obviamente errado, é bem possível que já tenham percebido algo sutilmente errado antes, o que pode lhes dar uma pista. Eles podem observar tudo o que o computador faz durante a execução do teste e identificar por conta própria o que é importante.

Isso pode não ser suficiente. O programador pode decidir que precisa de mais informações e pedir que você mostre a mesma coisa novamente. Ele pode pedir que você o acompanhe passo a passo pelo procedimento, para que possa reproduzir o bug por conta própria quantas vezes quiser. Pode tentar variar o procedimento algumas vezes para verificar se o problema ocorre apenas em um caso ou em uma série de casos relacionados. Se você não tiver sorte, ele pode precisar passar algumas horas usando um conjunto de ferramentas de desenvolvimento e começar uma investigação mais aprofundada. Mas o mais importante é que o programador esteja olhando para o computador quando algo der errado. Assim que conseguir ver o problema acontecendo, ele geralmente poderá prosseguir a partir daí e começar a tentar corrigi-lo.

## "Mostre-me como me mostrar"
Esta é a era da Internet. Esta é a era da comunicação mundial. Esta é a era em que posso enviar meu software para alguém na Rússia com o toque de um botão, e essa pessoa pode me enviar comentários sobre ele com a mesma facilidade. Mas, se ela tiver um problema com meu programa, não poderá me colocar diante do computador enquanto ele falha. "Mostre-me" é uma boa opção quando possível, mas muitas vezes isso não é possível.

Se você precisar relatar um bug a um programador que não pode estar presente pessoalmente, o objetivo é permitir que ele reproduza o problema. Você quer que o programador execute sua própria cópia do programa, faça as mesmas coisas e faça com que ele falhe da mesma maneira. Quando ele conseguir ver o problema acontecendo diante de seus olhos, poderá lidar com ele.

Portanto, diga exatamente o que você fez. Se for um programa gráfico, informe quais botões você pressionou e em que ordem os pressionou. Se for um programa executado digitando um comando, mostre exatamente qual comando você digitou. Sempre que possível, forneça uma transcrição literal da sessão, mostrando os comandos que você digitou e o que o computador exibiu em resposta.

Forneça ao programador todas as entradas que conseguir imaginar. Se o programa ler um arquivo, provavelmente será necessário enviar uma cópia do arquivo. Se o programa se comunicar com outro computador pela rede, provavelmente você não poderá enviar uma cópia desse computador, mas poderá, pelo menos, informar que tipo de computador ele é e (se possível) qual software está sendo executado nele.

## "Funciona para mim. Então, o que está dando errado?"
Se você fornecer ao programador uma longa lista de entradas e ações, e ele executar sua própria cópia do programa e nada der errado, então você não forneceu informações suficientes. É possível que a falha não ocorra em todos os computadores; seu sistema e o dele podem ser diferentes de alguma forma. Também é possível que você tenha entendido errado o que o programa deveria fazer e que ambos estejam olhando exatamente para a mesma tela, mas você ache que ela está errada e ele saiba que está certa.

Portanto, descreva também o que aconteceu. Diga exatamente o que você viu. Diga por que você acha que o que viu está errado; melhor ainda, diga exatamente o que esperava ver. Se você disser "e então deu errado", terá omitido informações muito importantes.

Se você viu mensagens de erro, informe ao programador, com cuidado e precisão, quais eram elas. Elas são importantes! Neste estágio, o programador não está tentando corrigir o problema: está apenas tentando encontrá-lo. Ele precisa saber o que deu errado, e essas mensagens de erro são o melhor esforço do computador para informar isso a você. Anote os erros se não tiver outra maneira fácil de se lembrar deles, mas não vale a pena relatar que o programa gerou um erro se você também não puder informar qual foi a mensagem de erro.

Em particular, se a mensagem de erro contiver números, informe esses números ao programador. O fato de você não conseguir identificar nenhum significado neles não significa que não exista nenhum. Os números contêm todo tipo de informação que pode ser interpretada pelos programadores e provavelmente contêm pistas vitais. Os números nas mensagens de erro estão presentes porque o computador está confuso demais para relatar o erro em palavras, mas está fazendo o melhor que pode para transmitir as informações importantes de alguma forma.

Nesta etapa, o programador está efetivamente fazendo um trabalho de detetive. Ele não sabe o que aconteceu e não consegue se aproximar o suficiente para observar o problema por conta própria, então está procurando pistas que possam revelar o que aconteceu. Mensagens de erro, sequências incompreensíveis de números e até atrasos inexplicáveis são tão importantes quanto impressões digitais na cena de um crime. Guarde-as!

Se você estiver usando Unix, o programa pode ter produzido um arquivo de core dump. Core dumps são uma fonte particularmente boa de pistas, portanto, não os descarte. Por outro lado, a maioria dos programadores não gosta de receber arquivos de core enormes por e-mail sem aviso, portanto, pergunte antes de enviar um para alguém. Além disso, esteja ciente de que o arquivo de core contém um registro do estado completo do programa: quaisquer "segredos" envolvidos (talvez o programa estivesse processando uma mensagem pessoal ou lidando com dados confidenciais) podem estar contidos no arquivo de core.

## "Então tentei..."
Há muitas coisas que você pode fazer quando surge um erro ou bug. Muitas delas pioram o problema. Uma amiga minha, na escola, apagou por engano todos os documentos do Word e, antes de pedir ajuda a algum especialista, tentou reinstalar o Word e, depois, tentou executar o Defrag. Nenhuma dessas ações ajudou a recuperar os arquivos e, juntas, elas bagunçaram o disco a tal ponto que nenhum programa Undelete no mundo teria conseguido recuperar alguma coisa. Se ela simplesmente tivesse deixado tudo como estava, talvez tivesse tido alguma chance.

Usuários assim são como um mangusto encurralado: com as costas contra a parede e vendo a morte certa diante de si, ele ataca freneticamente, porque fazer alguma coisa parece necessariamente melhor do que não fazer nada. Isso não é uma atitude adequada para o tipo de problemas que os computadores produzem.

Em vez de ser um mangusto, seja um antílope. Quando um antílope se depara com algo inesperado ou assustador, ele congela. Ele fica absolutamente imóvel e tenta não chamar atenção enquanto para, pensa e descobre qual é a melhor coisa a fazer. (Se os antílopes tivessem uma linha de suporte técnico, seria nesse momento que ligariam para ela.) Então, depois de decidir qual é a atitude mais segura a tomar, ele a toma.

Quando algo der errado, pare imediatamente de fazer qualquer coisa. Não toque em nenhum botão. Olhe para a tela e observe tudo o que estiver fora do normal, e lembre-se disso ou anote. Depois, talvez comece a pressionar cuidadosamente "OK" ou "Cancelar", o que parecer mais seguro. Tente desenvolver um reflexo: se um computador fizer algo inesperado, pare.

Se você conseguir sair do problema, seja fechando o programa afetado ou reiniciando o computador, uma boa ideia é tentar fazer o problema acontecer novamente. Os programadores gostam mais de problemas que podem ser reproduzidos mais de uma vez. Programadores felizes corrigem bugs de maneira mais rápida e eficiente.

## "Acho que a modulação de táquions deve estar polarizada incorretamente"
Não são apenas os não programadores que produzem relatórios de bugs ruins. Alguns dos piores relatórios de bugs que já vi vieram de programadores, e até mesmo de bons programadores.

Trabalhei certa vez com outro programador que estava sempre encontrando bugs no próprio código e tentando corrigi-los. De vez em quando, ele encontrava um bug que não conseguia resolver e me chamava para ajudar. "O que deu errado?", eu perguntava. Ele respondia contando qual era sua opinião naquele momento sobre o que precisava ser corrigido.

Isso funcionava bem quando a opinião que ele tinha naquele momento estava correta. Isso significava que ele já havia feito metade do trabalho e que poderíamos concluir o trabalho juntos. Era eficiente e útil.

Mas muitas vezes ele estava errado. Passávamos algum tempo tentando descobrir por que determinada parte do programa estava produzindo dados incorretos e, por fim, descobríamos que não estava: havíamos passado meia hora investigando um trecho de código perfeitamente correto, enquanto o problema real estava em outro lugar.

Tenho certeza de que ele não faria isso com um médico. "Doutor, preciso de uma receita de Hydroyoyodyne." As pessoas sabem que não se deve dizer isso a um médico: você descreve os sintomas, os desconfortos e as dores, as erupções cutâneas e as febres, e deixa o médico fazer o diagnóstico sobre qual é o problema e o que fazer a respeito. Caso contrário, o médico o considera um hipocondríaco ou um maluco, e com toda razão.

É a mesma coisa com os programadores. Fornecer seu próprio diagnóstico pode ser útil às vezes, mas sempre descreva os sintomas. O diagnóstico é um complemento opcional, e não uma alternativa à descrição dos sintomas. Da mesma forma, enviar uma modificação no código para corrigir o problema é uma adição útil a um relatório de bug, mas não é um substituto adequado para ele.

Se um programador pedir informações adicionais, não as invente! Certa vez, alguém relatou um bug para mim, e pedi que ele tentasse executar um comando que eu sabia que não funcionaria. A razão pela qual pedi que ele o executasse era que eu queria saber qual de duas mensagens de erro diferentes ele retornaria. Saber qual mensagem de erro seria exibida forneceria uma pista vital. Mas ele não chegou a tentar — simplesmente me respondeu por e-mail dizendo: "Não, isso não vai funcionar". Levei algum tempo para convencê-lo a tentar de verdade.

Usar sua inteligência para ajudar o programador é ótimo. Mesmo que suas deduções estejam erradas, o programador deve agradecer pelo menos por você ter tentado facilitar o trabalho dele. Mas relate também os sintomas, ou você pode acabar tornando o trabalho dele muito mais difícil.

## "É engraçado, isso funcionou agora há pouco"
Diga "falha intermitente" a qualquer programador e observe seu rosto desanimar. Os problemas fáceis são aqueles em que a execução de uma sequência simples de ações faz com que a falha ocorra. O programador pode então repetir essas ações em condições de teste cuidadosamente observadas e acompanhar em detalhes o que acontece. Muitos problemas simplesmente não funcionam dessa maneira: haverá programas que falham uma vez por semana, ou falham uma vez a cada mil anos, ou nunca falham quando você tenta reproduzi-los na frente do programador, mas sempre falham quando você está prestes a cumprir um prazo.

A maioria das falhas intermitentes não é realmente intermitente. A maioria delas tem alguma lógica por trás. Algumas podem ocorrer quando a máquina está ficando sem memória, outras podem ocorrer quando outro programa tenta modificar um arquivo crítico no momento errado, e algumas podem ocorrer apenas na primeira metade de cada hora! (Eu realmente já vi uma dessas.)

Além disso, se você consegue reproduzir o bug, mas o programador não, pode muito bem ser que o computador dele e o seu sejam diferentes de alguma forma e que essa diferença esteja causando o problema. Certa vez, tive um programa cuja janela se enrolava até formar uma pequena bola no canto superior esquerdo da tela, onde ficava emburrada. Mas isso só acontecia em telas de 800x600; funcionava normalmente no meu monitor de 1024x768.

O programador vai querer saber tudo o que você conseguir descobrir sobre o problema. Tente reproduzi-lo em outra máquina, por exemplo. Tente duas ou três vezes e veja com que frequência ele ocorre. Se o problema acontece quando você está realizando um trabalho sério, mas não quando está tentando demonstrá-lo, pode ser que tempos de execução longos ou arquivos grandes façam o programa falhar. Tente se lembrar do máximo de detalhes possível sobre o que estava fazendo com o programa quando ele falhou e, se perceber algum padrão, mencione-o. Qualquer informação que você possa fornecer será útil. Mesmo que seja apenas probabilística (como "ele tende a travar com mais frequência quando o Emacs está em execução"), ela pode não fornecer pistas diretas sobre a causa do problema, mas pode ajudar o programador a reproduzi-lo.

Mais importante ainda, o programador vai querer ter certeza de que está lidando com uma falha realmente intermitente ou com uma falha específica da máquina. Ele vai querer saber muitos detalhes sobre o seu computador, para poder descobrir em que ele difere do computador dele. Muitos desses detalhes dependerão do programa em particular, mas uma coisa que você definitivamente deve estar preparado para fornecer são os números de versão. O número da versão do próprio programa, o número da versão do sistema operacional e, provavelmente, os números de versão de quaisquer outros programas envolvidos no problema.

## "Então carreguei o disco no meu Windows..."
Escrever com clareza é essencial em um relatório de bug. Se o programador não conseguir entender o que você quis dizer, seria como se você não tivesse dito nada.

Recebo relatórios de bugs de todo o mundo. Muitos deles vêm de pessoas que não têm o inglês como língua materna, e muitas delas pedem desculpas pelo inglês ruim. Em geral, os relatórios de bugs que vêm acompanhados de desculpas pelo inglês ruim são, na verdade, muito claros e úteis. Os relatórios menos claros vêm de falantes nativos de inglês que presumem que vou entendê-los mesmo que não façam nenhum esforço para serem claros ou precisos.

- Seja específico. Se você puder fazer a mesma coisa de duas maneiras diferentes, informe qual delas você usou. "Selecionei Carregar" pode significar "cliquei em Carregar" ou "pressionei Alt-L". Diga qual delas você fez. Às vezes, isso é importante.
- Seja detalhista. Forneça mais informações em vez de menos. Se você disser demais, o programador poderá ignorar parte delas. Se disser de menos, ele terá que voltar e fazer mais perguntas. Um relatório de bug que recebi tinha apenas uma frase; cada vez que eu pedia mais informações, a pessoa respondia com outra única frase. Levei várias semanas para obter uma quantidade útil de informações, porque elas chegavam uma frase curta de cada vez.
- Tenha cuidado com os pronomes. Não use palavras como "isso" ou referências como "a janela" quando não estiver claro a que elas se referem. Considere o seguinte: "Iniciei o FooApp. Ele exibiu uma janela de aviso. Tentei fechá-la e ele travou." Não está claro o que o usuário tentou fechar. Ele tentou fechar a janela de aviso ou o FooApp inteiro? Isso faz diferença. Em vez disso, você poderia dizer: "Iniciei o FooApp, que exibiu uma janela de aviso. Tentei fechar a janela de aviso, e o FooApp travou." Isso é mais longo e mais repetitivo, mas também é mais claro e menos sujeito a interpretações equivocadas.
- Leia o que você escreveu. Leia o relatório novamente para si mesmo e veja se você acha que está claro. Se você listou uma sequência de ações que deveria produzir a falha, tente segui-la você mesmo para verificar se não deixou passar alguma etapa.

## Sumário
- O primeiro objetivo de um relatório de bug é permitir que o programador veja a falha com os próprios olhos. Se você não puder estar com ele para fazer a falha acontecer diante dele, forneça instruções detalhadas para que ele possa reproduzi-la por conta própria.
- Caso o primeiro objetivo não seja alcançado e o programador não consiga ver a falha por conta própria, o segundo objetivo de um relatório de bug é descrever o que deu errado. Descreva tudo em detalhes. Diga o que você viu e também o que esperava ver. Anote as mensagens de erro, especialmente se elas contiverem números.
- Quando o computador fizer algo inesperado, pare. Não faça nada até estar calmo e não faça nada que você considere que possa ser perigoso.
- Você pode tentar diagnosticar a falha por conta própria, se achar que consegue, mas, mesmo assim, deverá relatar também os sintomas.
- Esteja preparado para fornecer informações adicionais se o programador precisar delas. Se ele não precisasse delas, não as pediria. Ele não está sendo deliberadamente inconveniente. Tenha os números de versão à mão, pois provavelmente serão necessários.
- Escreva com clareza. Diga o que você quer dizer e certifique-se de que isso não possa ser mal interpretado.
- Acima de tudo, seja preciso. Programadores gostam de precisão.

## *Isenção de responsabilidade*
*Na verdade, nunca vi um mangusto ou um antílope. Meus conhecimentos de zoologia podem estar incorretos.*

----

**Créditos:**
https://www.chiark.greenend.org.uk/~sgtatham/bugs.html
**Notas:**
*Copyright © 1999 Simon Tatham.*
*Este documento é* [OpenContent](https://www.opencontent.org/).
*Você deve copiar e usar esse texto sob is ternis de* [OpenContent Licence](https://www.opencontent.org/openpub/).

----

***Página também está disponível em:***
| [Português](https://www.chiark.greenend.org.uk/~sgtatham/bugs-br.html) | [简体中文](https://www.chiark.greenend.org.uk/~sgtatham/bugs-cn.html) | [Česky](https://www.chiark.greenend.org.uk/~sgtatham/bugs-cz.html) | [Dansk](https://www.chiark.greenend.org.uk/~sgtatham/bugs-da.html) | [Deutsch](https://www.chiark.greenend.org.uk/~sgtatham/bugs-de.html) | [Español](https://www.chiark.greenend.org.uk/~sgtatham/bugs-es.html) | [Français](https://www.chiark.greenend.org.uk/~sgtatham/bugs-fr.html) | [Magyar](https://www.chiark.greenend.org.uk/~sgtatham/bugs-hu.html) | [Italiano](https://www.chiark.greenend.org.uk/~sgtatham/bugs-it.html) | [日本語](https://www.chiark.greenend.org.uk/~sgtatham/bugs-jp.html) | [Nederlands](https://www.chiark.greenend.org.uk/~sgtatham/bugs-nl.html) | [Polski](https://www.chiark.greenend.org.uk/~sgtatham/bugs-pl.html) | [Русский](https://www.chiark.greenend.org.uk/~sgtatham/bugs-ru.html) | [繁體中文](https://www.chiark.greenend.org.uk/~sgtatham/bugs-tw.html) ]
