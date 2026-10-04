---
title: Guia de estilo Wiki
description: 
published: true
date: 2022-01-24T19:17:12.061Z
tags: documentação, wiki
editor: markdown
dateCreated: 2020-03-07T09:08:09.534Z
---

# Guia de estilo Wiki

## Diretrizes Gerais
As seções a seguir fornecem diretrizes para a composição de frases e o uso da sintaxe.
Siga estas diretrizes para garantir que o tom dos seus documentos seja consistente com o de outras documentações do OpenMandriva.

### Composição

#### Voz
Instruções e regras usam a *voz ativa*, transmitindo confiança ao leitor sem soar exigente.
A voz ativa fornece instruções claras. Ela mostra ao leitor o que fazer e apresenta os resultados esperados.
A voz ativa deixa no leitor a impressão de que o autor acredita no trabalho escrito.

#### Evite a voz passiva, a menos que seja necessário.
A *voz passiva* é gramaticalmente correta, mas é uma barreira para a compreensão do leitor.
A voz passiva inverte a estrutura convencional da frase. Ela coloca o verbo e o objeto direto na primeira metade da frase e o sujeito principal na segunda metade da frase. Muitas vezes, uma simples reestruturação da frase a torna ativa.
Frases longas na voz passiva frequentemente exigem várias leituras até que o leitor compreenda plenamente o significado.

`ATIVA: Selecione uma senha forte para aumentar a segurança pessoal.`

`PASSIVA: A segurança pessoal é aprimorada pela seleção de uma senha forte.`

#### Conexto

Evite escrever fora de contexto.
Atenha-se cuidadosamente ao assunto do documento, capítulo, seção e parágrafo.
Use referências conforme apropriado, estruturando os documentos de modo que cada nova parte se baseie na anterior.
Evite fazer o leitor avançar no documento para compreender o contexto das partes atuais.
Forneça um link para a documentação relacionada caso o leitor possa precisar dela para esclarecimentos.

#### Ênfase

A ênfase é mais eficaz quando usada com moderação.
Use métodos de ênfase como negrito, sublinhado ou texto oblíquo para chamar a atenção para um novo termo.
Use advertências para destacar informações importantes.
Outra maneira aceitável de enfatizar um ponto é variando a estrutura das frases ou a escolha das palavras.
Os melhores redatores de documentos planejam a ênfase com antecedência, aplicando-a com consistência e cuidado em todo o documento.

#### Acurácia e Precisão

A precisão e a exatidão podem determinar o sucesso ou o fracasso de qualquer documento.
Esse princípio se aplica igualmente à precisão técnica e literária.
Escolha as palavras após considerar o maior número possível de casos de uso. Por exemplo, "ir para" não é tão preciso quanto "clicar", mas "clicar" pode não ser adequado para todas as interações com a interface. O termo "selecionar" é adequado em qualquer caso de uso e suficientemente preciso.
Não fique excessivamente preocupado em tentar abranger todos os possíveis casos de uso. Abranger casos excepcionais raros torna um documento excessivamente longo, e o leitor perde o foco.

#### Tempo verbal

Tempo verbal é o tempo em que a linguagem ocorre.
Existem três tempos verbais principais: passado, presente e futuro. Selecione um tempo verbal apropriado para o documento e mantenha-o.
Para documentação técnica, use o presente sempre que possível.
Manter o mesmo tempo verbal em cada afirmação de um documento é fundamental para a clareza.
Mantenha o mesmo tempo verbal para todas as tarefas sequenciais de um procedimento.

## Uso

### Contrações

Evite contrações, a combinação de duas palavras com um apóstrofo substituindo uma ou mais letras.
As contrações reduzem a legibilidade dos documentos e dificultam a tradução.
Outras culturas e idiomas interpretam as contrações de maneira diferente, e essa confusão entra em conflito com os objetivos do Projeto de Documentação do OpenMandriva.

### Pronomes

Pronomes são palavras que a linguagem usa para substituir sintagmas nominais específicos.
Bons escritores devem encontrar um equilíbrio entre repetir excessivamente um sintagma nominal e usar pronomes para substituir substantivos. Uma regra geral para preservar a clareza é nunca repetir a substituição de um substantivo por um pronome em duas frases consecutivas.
Os leitores de documentos técnicos precisam de lembretes constantes sobre o assunto exato que o autor está abordando. O uso excessivo de pronomes faz com que os leitores tenham que adivinhar a que assunto uma frase se refere.
Essas suposições reduzem a eficácia da documentação.

Evite a maioria dos pronomes pessoais na documentação, incluindo os seguintes:
* Pronomes pessoais subjetivos ("eu", "ele", "ela", "isso", "nós")
* Pronomes pessoais objetivos ("me", "ela", "ele", "nos")
* Pronomes pessoais possessivos ("meu", "dela", "dele", "nosso")

Também evite:
* Pronomes reflexivos, como "você mesmo" ou "ele mesmo"
* Pronomes intensivos, como "ele mesmo" ou "(você) faça isso sozinho"
* Evite o uso excessivo de "você", "seu/sua" e "alguém/de alguém".

Em algumas situações, o segundo pronome pessoal "você" e suas formas correspondentes são necessários para garantir a clareza.
Manter a voz ativa é mais importante do que evitar os pronomes pessoais de segunda pessoa. "Você" e "seu/sua" são palavras apropriadas para indicar uma ação ou posse por parte do leitor.
Pronomes indefinidos como "isso" ou "aquilo", sem um antecedente, dificultam para o leitor acompanhar o significado pretendido pelo autor.
Sempre que possível, prefira escrever um sintagma nominal exato em vez das palavras vagas "isso", "estes", "aqueles" e "aquilo".

`INCORRETO: Edite seus arquivos de configuração do yum para usar mirrors geograficamente próximos. Isso permite que você atualize seu sistema mais rapidamente.`

`CORRETO: Edite os arquivos de configuração do yum para usar mirrors geograficamente próximos, permitindo atualizações mais rápidas do sistema.`

Ao eliminar pronomes indefinidos, uma frase longa e complexa pode resultar da união de muitas orações.
Use pronomes indefinidos para dividir frases longas e melhorar a clareza, mas sempre forneça um antecedente adequado.

`INCORRETO: Mantenha seu sistema operacional atualizado com as atualizações recomendadas para melhorar a funcionalidade dos aplicativos, remover riscos de segurança e resolver automaticamente problemas de desempenho identificados em relatórios de bugs.`

`CORRETO: Mantenha seu sistema operacional atualizado com as atualizações recomendadas. Essas atualizações melhoram a funcionalidade dos aplicativos, removem riscos de segurança e resolvem automaticamente problemas de desempenho corrigidos a partir de relatórios de bugs.`

### Formação de frase

Mantenha as frases o mais curtas possível.
Eliminar palavras desnecessárias é fundamental para reforçar o significado.
Existem várias armadilhas comuns nas quais os redatores técnicos caem, resultando em frases longas.

#### Discurso Indireto

O discurso indireto refere-se ao uso de "que" para atribuir uma afirmação, fato ou sentimento em uma frase sem o uso de aspas.
Na escrita comum, ele enfraquece as afirmações de fatos.
Os redatores de documentação podem aumentar o impacto das frases removendo "que" e "o qual".

`INCORRETO: O Mandriva é um sistema operacional de código aberto que é upstream para muitos outros projetos de código aberto.`

`CORRETO: O Mandriva é um sistema operacional de código aberto upstream para muitos outros projetos de código aberto.`

#### Outras combinações de palavras desnecessárias

Evite usar a palavra desnecessária "então" após uma declaração "se".
Quando uma frase começa com uma declaração "se", coloque uma vírgula em seguida e complete a frase com uma afirmação completa.

`INCORRETO: Se um cliente de e-mail não enviar ou receber mensagens, então verifique no menu Arquivo e confirme se o modo "Trabalhar offline" está desmarcado.`

`CORRETO: Se um cliente de e-mail não enviar ou receber mensagens, verifique no menu Arquivo e confirme se o modo "Trabalhar offline" está desmarcado.`

Muitas palavras que usamos na conversa cotidiana reduzem o impacto em materiais impressos porque "deixam uma saída". São palavras que precedem verbos e substantivos para minimizar a força da frase. Esta não é uma lista exaustiva, mas redatores de documentação atentos reduzirão o uso dessas palavras e de outras de natureza semelhante.

#### Evite reduzir o impacto com palavras desnecessárias
As palavras a seguir minimizam o impacto da oração verbal ou nominal dentro de uma frase.
Outras palavras também se enquadram nessa categoria, mas esta lista curta tem como objetivo ajudar os redatores de documentação a identificar palavras dessa natureza e eliminá-las de seus textos: **deveria, poderia, pode, talvez, alguns, muitos, a maioria, numerosos, poucos, de certa forma, qualquer que seja, possivelmente, consegue, ocasionalmente e frequentemente**.

#### Variação de sentenças
Para obter o maior impacto, mantenha as primeiras e últimas frases de um parágrafo o mais curtas possível.
Variar o tamanho das frases dentro de um parágrafo e ao longo de todo o documento mantém a atenção do leitor. Um fato curto e simples é fácil de compreender e usar para analisar o assunto da frase seguinte. Não há nada de errado em usar frases mais longas para explicar ideias e conceitos complexos. Tente usar uma frase simples de síntese no final de cada parágrafo para dar aos leitores uma pausa e recapitular qualquer informação importante.
Uma frase final curta permanece com o leitor na próxima seção.

#### Uso de maiúsculas e minúsculas

Nas frases, coloque a primeira palavra em maiúscula.
Não inicie frases com o nome de um comando, pacote ou opção.

`INCORRETO: o <code>smolt </code>fornece informações sobre o hardware.`

`CORRETO: O pacote <code>smolt </code>fornece informações sobre o hardware.`

#### Pontuação

A pontuação é um componente fundamental para a compreensão de um texto.
Uma vírgula, um ponto ou um sinal de pontuação inadequado pode alterar completamente o significado de uma frase. Os sinais de pontuação são os elementos de fixação na caixa de ferramentas de um redator. Os leitores estão acostumados aos pregos e parafusos comuns, como vírgulas e pontos. Comece a usar muitas dobradiças ou braçadeiras chamativas, como ponto e vírgula ou reticências, e as notações pouco familiares facilmente distraem os leitores.
Os sinais de pontuação complexos não são universais, dificultando os esforços de tradução da documentação do OpenMandriva.

Minimize os seguintes sinais de pontuação na documentação:
* Parênteses ou "travessões"
Para compensar, reorganize a frase ou divida-a em duas ideias completas.
* Ponto e vírgula
Bom para usar somente quando duas ideias estiverem relacionadas, precisarem ser unidas para maior clareza e isso eliminar a necessidade de uma conjunção.
* Dois pontos
Se houver mais de três itens, use uma lista com marcadores para facilitar a compreensão.
* Três pontos
Não use para dar ênfase estilística... use somente para indicar uma continuação indefinida do conteúdo em um exemplo.
* Pontos de exclamação
Na redação técnica, isso é aceito para uso somente como uma advertência extremamente grave, e não para dar ênfase.
* E comercial
A palavra "and" deve ser escrita por extenso, e este símbolo deve ser reservado somente para quando fizer parte de um comando de computador.
* Barras
Não use barras como uma forma abreviada de "ele ou ela", usando he/she. Em vez disso, use as palavras "e", "ou" ou "um ou outro". As barras são comumente usadas em caminhos de arquivos, e usá-las de outra forma pode causar confusão.

## Outras questões de redação

Todo redator enfrenta obstáculos ao escrever. Às vezes, fica difícil formular algo de maneira adequada ou as palavras simplesmente não "soam bem".
É por isso que o Projeto OpenMandriva é um trabalho em equipe. Peça ajuda a outros redatores da documentação na lista de discussão ou na sala de bate-papo para resolver questões de redação e formatação.
Outro recurso que os redatores profissionais usam diariamente é afastar-se do projeto por algum tempo. Faça uma pausa e afaste-se do documento. Voltar a um trecho problemático com um olhar renovado geralmente é tudo o que é necessário para superar o obstáculo da escrita.

O objetivo geral do Projeto de Documentação do OpenMandriva é fornecer assistência aos usuários do OpenMandriva em uma linguagem fácil de entender.
Você não precisa escrever para impressionar um professor de inglês nem para demonstrar sua experiência em um determinado assunto. Frases curtas, definições frequentes de termos novos e desconhecidos e links de referência são recursos que nosso público mais aprecia.
Escreva pensando no seu público-alvo, e suas contribuições para a documentação terão o maior número de acessos de usuários que precisam de respostas.



*Créditos:
Extraído do* [Guia de Estilo do Projeto Fedora](http://Fedoraproject.org/wiki/Docs_Project_Style_Guide_-_General_Guidelines)

----
## Guia de estilo específico do wiki do OpenMandriva

Leia também [OpenMandriva wiki specific style guide](/en/team/workshop/omawiki-style-guide)





