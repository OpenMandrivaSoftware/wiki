---
title: QA de Lançamentos do OpenMandriva
description: 
published: true
date: 2022-11-04T17:56:09.907Z
tags: versões, políticas, QA
editor: markdown
dateCreated: 2020-03-02T14:44:03.923Z
---

# QA de Lançamentos do OpenMandriva
>
> **O PROCESSO DE LANÇAMENTO**
{.is-info}


## Instalação da ISO
### Instalação
A distribuição deve inicializar a partir de um pendrive básico criado usando
`dd if="openmandriva iso" of="dev/sd*" bs=4M`

As instalações gráficas e em modo texto devem funcionar conforme especificado

O processo de instalação deve funcionar em diferentes idiomas, ou seja, não deve haver traduções ausentes.
Layouts de teclado alternativos devem funcionar.

### Instalação gráfica
A instalação gráfica deve ocorrer na resolução e profundidade de cores mais adequadas disponíveis no sistema; uma resolução mínima de 1024 x 768 deve ser suportada.

### Administração e Arte
O nome da versão deve ser o atual.
O contrato de licença deve ser exibido e sua redação deve estar correta.
As notas de lançamento devem estar atualizadas para a versão em questão e identificadas como tal.
Toda a arte deve ser a aprovada para a versão atual.

### Propriedades Gerais
Nenhuma ação de instalação que exija intervenção do usuário deve aparecer fora da tela para a resolução escolhida (botões OK; botões APLICAR etc.).
Sempre que possível, o usuário deve poder retornar à etapa anterior do processo de instalação. Quando isso não for possível, o usuário deve ser avisado de que não há como reverter ou revisar a partir da etapa seguinte (ou seja, formatação da partição).

### Hardware
A versão deve ser instalada nas plataformas de hardware designadas.

### Rede
Tanto a configuração de conexões com fio quanto sem fio deve ser possível com o mínimo de interação do usuário.

### Repositórios
\-

### X-Server
A configuração automática do X-server deve funcionar. Quando os drivers não forem funcionais para a placa instalada, o X-server deve usar o driver VESA por padrão para fornecer uma opção de segurança.

### Gerenciador de janelas
A janela escolhida deve ser instalada sem erros. Se isso falhar, um gerenciador de janelas básico alternativo deve ser oferecido. A inicialização automática do gerenciador de janelas deve ser oferecida durante a instalação.

### Impressão
O servidor cups deve ser instalado durante o processo de instalação

### Som
O servidor de som deve ser instalado automaticamente. Uma confirmação audível para o usuário deve confirmar isso. Se não houver placa de som ou se a instalação do som falhar, uma mensagem apropriada deve ser exibida.

#### Configuração do Usuário
O instalador deve solicitar a definição de uma senha de root.
O instalador deve exigir a criação de pelo menos um usuário.


## Inicialização
### Boot inicial
A tela de inicialização deve ser exibida corretamente no monitor; não deve haver deslocamento da imagem.

### Gerenciador de inicialização
O gerenciador de inicialização deve funcionar com instalações de outros sistemas operacionais.
O gerenciador de inicialização deve ser atualizado corretamente quando um kernel alternativo for instalado.
O gerenciador de inicialização deve apresentar as opções de inicialização apropriadas, no mínimo:

*Open-Mandriva Linux
Inicialização em modo de segurança (inicialização em um terminal root de usuário único)
Sistema de recuperação*

### Login Gráfico
O gerenciador de login gráfico deve exibir todos os usuários (excluindo os usuários do sistema).
O usuário selecionado deve ser aquele que fez login por último. No caso de uma nova instalação, deve ser a primeira entrada quando os usuários forem classificados em ordem alfabética (a a z).
O cursor do teclado deve iniciar na caixa de entrada de texto da senha.
Se um menu de desligamento/finalidade geral estiver incluído, todas as funções devem operar corretamente.
O gerenciador de login não deve permitir acesso ao gerenciador de janelas sem uma senha.
Deve ser possível iniciar uma sessão de login pela interface CLI a partir do gerenciador de login gráfico.

### Gerenciador de janelas
Após o login, o gerenciador de janelas escolhido deve ser iniciado sem erros.
Uma indicação visível dos dispositivos USB conectados deve ser facilmente identificável (incluindo dispositivos de rede sem fio e com fio).
No caso de discos USB, CD-ROMs e unidades de memória, todos devem ser montados corretamente para os seguintes sistemas de arquivos: ext2, ext3, ext4, fat32, ntfs3g e quaisquer drivers de sistemas de arquivos criptografados que possam estar incluídos no sistema operacional.

### Servidores
No mínimo, os servidores Samba, CUPS, SSH, NFS e FTP devem funcionar corretamente.

### Manutenção de Software
O sistema de atualização automática deve funcionar corretamente quando o acesso à internet estiver disponível

### Configuração
O Centro de Controle do Open Mandriva deve estar totalmente operacional.

### Aplicativos Gráficos Essenciais
A lista de aplicativos a seguir deve ser iniciada sem erros e apresentar o mínimo de bugs.

#### Sistema
Área de trabalho Plasma
Aplicativos de configuração do KDE
Servidor de som (o som pela rede deve funcionar)
Servidor Akonadi
Indexação de arquivos
Konsole

#### Escritório
Libre Office
Okular

#### Internet
Falkon
Firefox
Chromium
Browser Plugins
PDF support
Java
Kmail
Mozilla Thunderbird
IRC Client

#### Gerenciamento de arquivos
Dolphin
(o acesso à rede integrado também deve funcionar)
Midnight Commander

#### Editores de arquivos
Kwrite
Kate

#### Desenvolvimento
Kdevelop
Eclipse

#### Gráficos
Gwenview
Krita
DigiKam

#### Som e vídeo
...

#### Ferramentas
...

#### Utilitários
O Open Mandriva Welcome deve estar totalmente operacional.

#### Aplicativos Essenciais de Linha de Comando
mc
vim
ed
vi
nano
emacs?
Bash
sh
binutils
man
less
netstat
bind
dhclient
M4
bison
grep
awk
sed
make
Autoconf
libtool
pkgconfig
scons
rpm
urpmi
perl
python


## Critérios para aprovação do lançamento
- Todos os programas listados acima devem estar funcionais e ser capazes de abrir, processar, fechar e salvar um arquivo, quando apropriado. Não deve haver nenhum problema de segurança pendente.
- Não deve haver bugs que comprometam seriamente a funcionalidade do sistema para o usuário nos pacotes essenciais listados acima. Bugs em pacotes suplementares e em contrib que não afetem negativamente o funcionamento do sistema operacional podem ser tolerados. Os bugs que não serão tolerados são uso excessivo de disco, alto consumo de recursos do sistema, vazamentos de memória, travamento do gerenciador de janelas e qualquer forma de congelamento do sistema.
- Deve ser possível instalar um kernel diferente a partir do repositório do OM sem problemas. O script de instalação do kernel deve atualizar corretamente o gerenciador de inicialização e mostrar a disponibilidade do novo kernel na tela de inicialização. O kernel original deve ser renomeado de forma a deixar claro que este era o kernel padrão original. Os links simbólicos que apontam para o kernel padrão devem ser atualizados corretamente.
- Deve ser possível estabelecer conectividade de rede e, quando disponível, acessar a Internet. Isso deve ser possível tanto para conexões sem fio quanto para conexões com fio;
- Nenhum servidor comumente utilizado deve falhar ao iniciar;
- O sistema deve ser capaz de imprimir a partir de todos os aplicativos que oferecem esse serviço;
- O Seletor de Repositórios de Software (`om-repo-picker`) deve estar totalmente operacional;
- O sistema de empacotamento e os repositórios devem estar operacionais, incluindo a atualização automática do OpenMandriva;
- As ISOs enviadas para lançamento devem ser nomeadas e datadas corretamente.


## Checklist
A equipe de QA e os testadores são incentivados a produzir uma [checklist](https://github.com/OpenMandrivaAssociation/distribution/wiki/QA-Checklist-for-QA-and-testers) detalhada para a ISO, com uma lista dos bugs detectados.<br />
Ela deve conter casos de uso típicos, como:

1. A ISO é gravada em um pendrive
1. A tela do GRUB/de inicialização aparece
1. As opções na tela do GRUB/de inicialização funcionam
1. A ISO inicializa no multi-user.target
1. A ISO inicializa no graphical.target
1. O login automático do usuário da sessão live funciona
1. O ambiente gráfico padrão é exibido após o login automático
1. O ambiente gráfico padrão pode ser utilizado (funções básicas, como menu, gerenciador de arquivos e navegador da Web)
1. A ISO inicializa no VirtualBox
1. A ISO instala no VirtualBox

