---
title: Instalar o OpenMandriva Lx
description: 
published: true
date: 2025-04-30T09:48:16.196Z
tags: 
editor: markdown
dateCreated: 2021-10-02T20:03:48.871Z
---

***Se você tiver alguma dúvida antes de instalar o OpenMandriva Lx, pergunte no [OpenMandriva Chat](https://wiki.openmandriva.org/en/team/chat) ou no [Fórum de Suporte do OpenMandriva](https://forum.openmandriva.org/c/support/17).*** As pessoas podem estar em fusos horários diferentes, portanto, aguarde um tempo para receber uma resposta.

# 1\. Transfira a imagem baixada para um pendrive USB

Para transferir a imagem live/de instalação para um dispositivo de armazenamento USB, você pode usar:   om-imagewriter, KDE isoimagewriter, SUSE Studio ImageWriter ou a linha de comando dd.

*Usuários do Windows:*  
Se você usar outras ferramentas de gravação USB, como algumas ferramentas do Windows (por exemplo, Rufus), deverá selecionar o modo `dd`; caso contrário, o nome do volume será truncado e o processo de inicialização será interrompido. 
O Balena Etcher é conhecido por funcionar corretamente para transferir imagens ISO do OpenMandriva para dispositivos de armazenamento USB.

# 2\. Inicializar a partir de um pendrive USB

A maioria dos computadores inicializa automaticamente a partir de um pendrive USB. Basta conectá-lo e ligar ou reiniciar o computador. Você deverá ver um menu solicitando que escolha entre as diferentes opções.

Se o computador não inicializar automaticamente a partir do USB, tente manter pressionada a tecla F12 durante a inicialização ou pressione ESC. Na maioria dos computadores, isso permitirá selecionar o dispositivo USB em um menu de inicialização específico do sistema.

F12 e ESC são as teclas mais comuns para abrir o menu de inicialização do sistema, mas F2 e F10 também são alternativas comuns. Se não tiver certeza, procure uma mensagem breve durante a inicialização do sistema — geralmente ela informa qual tecla pressionar para abrir o menu de inicialização.

Caso contrário, tente descobrir a tecla correta na internet ou não hesite em pedir ajuda em nosso fórum ou sala de bate-papo.

## Inicializar a partir de DVD
A inicialização a partir de DVD está obsoleta.

# 3\. Iniciar o modo live do OpenMandriva Lx

Primeiro, será solicitado que você inicie o modo live. Ele será iniciado automaticamente após 30 segundos. O modo live pode ser usado para testar a distribuição sem alterar o conteúdo do disco ou para instalar a distribuição.

![1](https://forum.openmandriva.org/uploads/default/optimized/2X/8/8c9727b79d2d14b3bbd0855fd324602ed1b3ff8f_2_690x283.jpeg)

Nesse menu, você pode alterar o idioma e o layout do teclado. Isso não afeta o layout do teclado nem o idioma da instalação propriamente dita, que serão solicitados posteriormente.
 

![2](https://forum.openmandriva.org/uploads/default/optimized/2X/5/542eb029a442b16f20ddabc2b689789badd39332_2_690x322.jpeg)

Observe que o layout de teclado padrão do modo live é US QWERTY, portanto pode ser difícil definir uma senha de usuário para a instalação sem verificar os caracteres digitados. O número de idiomas e layouts disponíveis no modo live é muito limitado, mas há muito mais opções durante a instalação propriamente dita.

![3](https://forum.openmandriva.org/uploads/default/optimized/2X/d/dc104372eed37891b803654bbe9af53fcc7dc844_2_690x322.png)

# 4\. Bem-vindo ao modo live do OpenMandriva Lx

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/f/f834e3ba9e2380e64bdfdaa6cdb2a0f85a22905e_2_667x500.jpeg)

você pode fechar ou minimizar com segurança a janela de boas-vindas para exibir os ícones da área de trabalho.

Quando estiver pronto para iniciar a instalação, clique no ícone “Instalar o OpenMandriva Lx”.

![image](https://forum.openmandriva.org/uploads/default/original/2X/1/152f47602da6aaec3baade2c95341ae57837247d.png)

# 5\. Preparando a instalação

Primeiro, escolha seu idioma e clique em Avançar.

![6](https://forum.openmandriva.org/uploads/default/optimized/2X/3/3ec3e0ddc0ad5c6b95d95814d54f7bd6268555ce_2_690x369.png)

Em seguida, escolha seu fuso horário de acordo com esta [lista](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List), clicando no mapa ou usando o menu. Depois, verifique se o idioma, os números e as datas estão configurados corretamente e clique em Avançar.

![7](https://forum.openmandriva.org/uploads/default/optimized/2X/b/b012db7a20f89cf37474ab6b36e4476b50e1aa01_2_690x369.jpeg)

Primeiro, será solicitado que você selecione o layout do teclado. Se o instalador não identificar corretamente o layout padrão, você poderá modificá-lo e verificá-lo no campo “Testar layout do teclado”.

![8](https://forum.openmandriva.org/uploads/default/optimized/2X/6/6ffe4b3c63507fb964e06fb3679893997180bf63_2_690x369.png)

Agora vem o momento mais importante da instalação, pois trata-se de como o sistema será instalado no seu disco rígido. Dependendo de você já ter ou não um ou mais sistemas operacionais instalados no disco, o Calamares poderá oferecer:

Algumas opções automatizadas:

-   Reduza uma partição existente e instale o OpenMandriva Lx junto com qualquer outro sistema operacional já disponível no seu sistema. Se você tiver uma partição do Windows, esta é a opção que você pode escolher para manter esse sistema operacional. (recomendado para iniciantes)
-   Use uma partição existente e ela substituirá todos os arquivos e/ou o sistema operacional dessa partição por uma nova instalação do OpenMandriva Lx. (usuários avançados)
-   Use o disco inteiro e será criada uma única partição onde tudo será instalado sob a raiz (administrador ou superusuário); todas as outras partições serão removidas. (iniciantes)

E a opção manual:

-   Este método oferece a liberdade de definir qualquer opção, qualquer sistema de arquivos e qualquer tabela de partições, mas também deixa inteiramente por sua conta a possibilidade de comprometer completamente a instalação. Certifique-se de saber o que está fazendo. Outra página será criada para o particionamento avançado. (usuários experientes)

Junto com a opção selecionada, há uma opção para arquivo de swap (haverá um tópico específico sobre swap). A menos que você saiba o que está fazendo, usar um arquivo de swap é uma boa opção.
 

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/4/438b7613cbcc876b9baa212e0300071490d70ce7_2_690x143.png)

Marque a opção “criptografar o sistema” se quiser adicionar uma camada de segurança aos seus dados. O sistema solicitará a senha definida sempre que você iniciar o sistema.

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/d/d0cf1db41fef4319988fa69e1e11154479761477_2_690x163.png)

Crie uma conta de usuário, dê um nome ao seu computador e defina uma senha de administrador (também chamada de senha de root) ou marque “usar a mesma senha para a conta de administrador”

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/e/e46e539f893a10323d4c7bef786ac4d49807fd9f_2_690x349.png)

Depois de verificar o resumo da instalação, você pode clicar em Instalar

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/9/92932b3faacc4819d5120defad361a7722d3be59_2_690x455.png)

Aguarde a conclusão do processo de instalação.

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/d/dd3cb650845245a372d776b1eade5b8763fc7158_2_690x455.jpeg)

Quando terminar, clique em Concluído e reinicie o computador (você também pode marcar “Reiniciar agora”).

![image](https://forum.openmandriva.org/uploads/default/optimized/2X/8/8d89ea930a3998a90533d7cedb6b354d8840725d_2_690x455.png)

Depois que o computador for reiniciado, você poderá aproveitar o OpenMandriva Lx.

# Notas

[Fonte original (fórum)](https://forum.openmandriva.org/t/h/4223)

Leia também:
* [Como criar as partições root, home e swap durante a instalação](/en/distribution/guides/how-tos/howto-root-home-swap)
* [Como obter uma lista de todos os pacotes incluídos nas ISOs](/en/distribution/guides/how-tos/list-packages-iso)
