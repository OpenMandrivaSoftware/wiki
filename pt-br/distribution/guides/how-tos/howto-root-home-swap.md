---
title: Como criar uma home root e partição swap durante instalação do OMLx
description: 
published: true
date: 2021-09-26T22:10:40.796Z
tags: documentação, howto, guia do usuário, avançado
editor: markdown
dateCreated: 2020-03-10T15:27:21.952Z
---

# Como criar uma home root e partição swap durante instalação do OMLx

O instalador do OpenMandriva é o [Calamares](http://calamares.io/).
Ele é fácil, utilizável, bonito, pragmático, inclusivo e independente de distribuição.
O Calamares inclui um recurso avançado de particionamento, com suporte tanto para operações de particionamento manuais quanto automatizadas.

> Nota: quando você lê *Lx 4*, isso significa incluir todas as versões 4.x, como 4.0, 4.1 e 4.2. Este guia se aplica a todas as versões do OMLx, incluindo o Cooker e o Rolling, assim como à família Lx 4.
{.is-info}


Para fazer praticamente qualquer coisa que você precise com as partições, é necessário selecionar <kbd>Manual partitioning</kbd>

![root-home-swap-01.png](/images/root-home-swap-01.png)

Observe que, se você aceitar o padrão <kbd>Erase disk</kbd> ele criará apenas uma partição `/boot/efi` e uma partição `/`.
O instalador, por padrão, não cria mais automaticamente uma partição swap, porque, na maioria dos computadores modernos, a swap não é mais utilizada.

Selecione <kbd>Partição Manual</kbd>

![root-home-swap-02.png](/images/root-home-swap-02.png)

Primeiro, veremos como configurar um sistema EFI com partições separadas `/`, `/home` e `swap`, além da necessária `/boot/efi` para a inicialização EFI. Se você usar uma tabela de partições MBR, não será necessário criar uma partição `/boot/efi`.
A partição `/boot/efi` deve ser identificada com `boot`. (O particionador irá identificá-la automaticamente como `esp`.)

O primeiro passo é selecionar <kbd>New Partition Table</kbd>
Se o sistema usar inicialização EFI ou UEFI, deverá ser utilizada uma tabela de partições `GPT`.
Se for inicialização Legacy, você pode selecionar `MBR` ou `GPT`. Se não souber qual usar, selecione a opção mais atual, `GPT`. Além disso, se o usuário tiver vários discos rígidos ou SSDs, todos eles precisam usar o mesmo tipo de tabela de partições, caso contrário poderão ocorrer problemas. Portanto, todos `GPT` ou todos `MBR`.

![root-home-swap-03.png](/images/root-home-swap-03.png)

Em seguida, criaremos `/boot/efi`, `/`, `/home` e swap, nessa ordem.
O único fator crítico na ordem é que `/boot/efi` precisa ser a primeira; as demais podem estar em qualquer ordem.

`/boot/efi` normalmente é uma partição de 300 MB e precisa ser fat16 ou fat32 para funcionar. Em alguns outros instaladores, seu tipo de sistema de arquivos será chamado de vfat.

Então, nós as criamos uma de cada vez.
Selecione <kbd>Create</kbd>.

![root-home-swap-04.png](/images/root-home-swap-04.png)

Siga as etapas na caixa de diálogo e você terminará com algo semelhante a isto

![root-home-swap-06.png](/images/root-home-swap-06.png)

Se você tiver tudo como deseja, selecione <kbd>Next</kbd> e, quando a instalação estiver concluída, seu novo sistema terá partições separadas para root, home e swap.

Observe que `/boot/efi` está no topo da lista, em primeiro lugar. Isso é necessário.

> Observe que provavelmente sua partição swap nunca será utilizada. Atualmente, apenas uma pequena minoria dos usuários realmente precisa de uma partição swap. Aqueles que precisam de swap provavelmente já sabem quem são e podem adaptá-la adequadamente. Normalmente, a swap seria necessária em computadores realmente antigos, com pouca RAM para executar o Lx 4 desde o início. Quanta RAM é suficiente? O ideal é 4 GB. Temos usuários executando o Lx 4 com 2 GB. As Release Notes do Lx 4.0 e 4.1 dizem 2 GB, e o instalador Calamares requer 2 GB. Aumentar a quantidade de memória de um computador, seja ele um desktop, torre, laptop ou notebook, é relativamente fácil e barato atualmente. Portanto, se o seu computador tiver pouca memória, considere fazer um upgrade. A swap também pode continuar sendo utilizada em computadores que realizam cálculos matemáticos ou científicos muito intensos ou que executam aplicações gráficas realmente exigentes. Mas esses usuários saberão do que precisam.
{.is-info}


Esta é uma captura de tela de como a janela de diálogo <kbd>Create</kbd> deve aparecer para a sua partição `/boot/efi` em um sistema `UEFI/EFI`:

![root-home-swap-05.png](/images/root-home-swap-05.png)

\-
