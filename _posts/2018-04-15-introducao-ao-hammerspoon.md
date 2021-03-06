---
layout: post
title: Introdução ao Hammerspoon
excerpt: "O Hammerspoon é uma ferramenta incrível que permite a automação de algumas
tarefas usando a linguagem de programação Lua. Um dos usos mais comuns
é a organização de janelas..."
---

## Que história é essa de Hammerspoon?

O Hammerspoon é uma ferramenta incrível que permite a automação de algumas
tarefas usando a linguagem de programação Lua. Um dos usos mais comuns
é a organização de janelas:

![Organização de janelas com
o Hammerspoon]({{ "/assets/hammerspoon1.png" | absolute_url }})

Mas também dá pra fazer outras coisinhas legais que veremos à frente.

## O que eu preciso saber?

O Hammerspoon pode ser um pouco intimidante a princípio, então decidi escrever
este tutorial para deixá-lo mais acessível. Se eu for bem sucedido, você vai
conseguir usá-lo mesmo sem saber nada de programação. Só precisa gostar de
aventuras, usar bem o computador em geral e conseguir usar o Google quando
tiver dúvidas.

## Instalação

O primeiro passo, obviamente, é instalar o Hammerspoon. Tem dois jeitos de
fazer isso:

#### Modo fácil

- Baixe [a última versão](https://git.io/vpe1K) e copie o aplicativo pra pasta
  `/Aplicativos`

- Abra o aplicativo e siga as instruções pra permitir o acesso às ferramentas
  de acessibilidade

- É isso!

#### Modo ainda mais fácil

Use o [Homebrew](https://brew.sh/index_pt-br)
e o [Homebrew-Cask](https://caskroom.github.io):

    brew cask install hammerspoon

(Mais pra frente eu vou ver se escrevo um tutorial sobre eles também.)

#### Modo incrivelmente fácil

Depois de escrever este tutorial, eu acabei escrevendo um script pra facilitar
a instalação do Hammerspoon e da minha configuração:

- Abra o Terminal (aperte Command + Space para abrir o Spotlight, digite
  "Terminal" e aperte enter)

- Copie e cole esta linha:

      curl -fsSL https://git.io/vpwL7 | bash

- Aperte Enter e siga as instruções

Depois da instalação, você vai precisar permitir o acesso à acessibilidade,
como descrito acima. Aí o Hammerspoon já vai estar instalado e funcionando,
é só você usar os atalhos de teclado citados abaixo ou abrir o arquivo
`init.lua` para personalizá-los. De qualquer maneira, eu recomendo a leitura
do resto do tutorial pra ter uma ideia melhor do que está acontecendo.

## Usando o Hammerspoon

Depois de instalar e abrir o Hammerspoon, clique no ícone dele na barra de
menus e selecione "Open Config". O arquivo `~/.hammerspoon/init.lua` vai ser
aberto no seu editor padrão. O Hammerspoon simplesmente permite que você
acesse algumas ferramentas do macOS através da linguagem de programação Lua.
Isso é feito programando em Lua no arquivo `init.lua`.

Agora você tem duas opções:

- Fuçar no Google, aprender um pouco de Lua, seguir [o tutorial do próprio
  Hammerspoon](http://www.hammerspoon.org/go/) e escrever sua própria
  configuração.

- Usar uma configuração pronta. (Ou, melhor ainda, aprender um pouco de lua
  e depois *adaptar* uma configuração pronta.)

A primeira opção eu não conseguiria cobrir neste tutorial e, como eu disse,
minha intenção é que você possa usar o Hammerspoon mesmo sem saber programar.
Então vamos à segunda: usar uma configuração pronta. Para isso, eu vou usar
a melhor configuração que eu conheço: a minha! 🎉

## Organizando janelas

Um dos principais usos do Hammerspoon é organizar janelas, então vamos começar
com essa parte. Se você seguiu minhas instruções até aqui, deve estar com
o arquivo `init.lua` aberto no seu computador. Copie esta linha e cole nele:

    require "winman"

Daí pode salvar e fechar o arquivo. O que essa linha faz é importar o código
do arquivo `winman.lua`, escrito por mim. Você ainda não tem esse arquivo,
então agora precisa baixá-lo. Vamos lá:

- [Clique com o botão direito
  aqui](https://github.com/dbmrq/dotfiles/raw/master/home/.hammerspoon/winman.lua)
  e selecione "Transferir Arquivo Vinculado Como..."

- Quando aparecer a janela de salvar, aperte a tecla `/`

- Vai aparecer uma janelinha dizendo "Ir para a pasta"; digite
  `~/.hammerspoon` e clique em "Ir"

- Confirme que o título do arquivo (em "Salvar Como") é `winman.lua` e clique
  em "Salvar"

- Clique no ícone do Hammerspoon na barra de menus e selecione "Reload Config"

Se tudo deu certo, o Hammerspoon vai carregar o arquivo `winman.lua` e você já
vai poder organizar suas janelas como naquela linda fotinho! Isso é feito com
atalhos de teclado. Estes são os atalhos padrão:

Atalho   | Resultado
-------- | --------------------------------------------------------
**⌃⌥⌘↑** | Aumentar e diminuir janelas mantendo elas no topo
**⌃⌥⌘↓** | Aumentar e diminuir janelas mantendo elas embaixo
**⌃⌥⌘←** | Aumentar e diminuir janelas mantendo elas à esquerda
**⌃⌥⌘→** | Aumentar e diminuir janelas mantendo elas à direita
**⌃⌥⌘,** | Organizar janelas em cascata
**⌃⌥⌘O** | Mostrar uma faixa do Desktop (Mesa)

(`⌃⌥⌘` = Control + Option + Command)

Então vamos fazer um teste: aperte `⌃⌥⌘←` algumas vezes e veja o que acontece!

Se você quiser usar atalhos de teclado diferentes, dê uma olhada no arquivo
`winman.lua` para ver as opções!

## Pomodoro

Como eu disse no começo, o Hammerspoon pode fazer mais do que simplesmente
organizar janelas. Outro script que eu escrevi é um timer minimalista pra
[técnica Pomodoro](https://pt.wikipedia.org/wiki/Técnica_pomodoro), que eu
chamei de "Cherry Tomato". O processo pra usá-lo é igual ao descrito na seção
anterior (mas o arquivo a ser baixado é diferente, claro):

- Clique no ícone do Hammerspoon na barra de menus e selecione "Open Config"

- Adicione uma linha com o texto `require "cherry"`

- Salve e feche o arquivo `init.lua`

- [Clique com o botão direito
  aqui](https://github.com/dbmrq/dotfiles/raw/master/home/.hammerspoon/cherry.lua)
  e selecione "Transferir Arquivo Vinculado Como..."

- Quando aparecer a janela de salvar, aperte a tecla `/`

- Vai aparecer uma janelinha dizendo "Ir para a pasta"; digite
  `~/.hammerspoon` e clique em "Ir"

- Confirme que o título do arquivo (em "Salvar Como") é `cherry.lua` e clique
  em "Salvar"

- Clique no ícone do Hammerspoon na barra de menus e selecione "Reload Config"

Agora você pode apertar `⌃⌥⌘C` pra iniciar o timer. Ele vai aparecer na barra
de menus. Clique nele pra pausar ou parar a contagem. Assim como na seção
anterior, você pode editar o arquivo `cherry.lua` pra alterar o atalho de
teclado e mais algumas outras preferências. Dessa vez vou deixar você fazer
isso sozinho, com base no que eu disse até aqui.

## Slow Q

Se você leu isso tudo até aqui, é provável que já use o atalho Command + Q pra
fechar aplicativos e o atalho Command + W pra fechar janelas. Se ainda não
use, comece!

O problema é que as teclas Q e W estão uma do lado da outra, então é fácil
apertar Command + Q por engano quando, na verdade, o que você queria era
apertar Command + W. Aí você fecha o aplicativo inteiro em vez de fechar só
a janela que queria fechar! 🤦

Existem aluns aplicativos, como o CommandQ e o SlowQuitApps, dedicados
a resolver esse problema: eles fazem com que você precise segurar as teclas
Command + Q por um tempo um pouquiiiinho mais longo antes que o aplicativo
seja fechado.

E eu também escrevi um script pra fazer isso usando o Hammerspoon. Vamos lá:

- Clique no ícone do Hammerspoon na barra de menus e selecione "Open Config"

- Adicione uma linha com o texto `require "slowq"`

- Salve e feche o arquivo `init.lua`

- [Clique com o botão direito
  aqui](https://github.com/dbmrq/dotfiles/raw/master/home/.hammerspoon/slowq.lua)
  e selecione "Transferir Arquivo Vinculado Como..."

- Quando aparecer a janela de salvar, aperte a tecla `/`

- Vai aparecer uma janelinha dizendo "Ir para a pasta"; digite
  `~/.hammerspoon` e clique em "Ir"

- Confirme que o título do arquivo (em "Salvar Como") é `slowq.lua` e clique
  em "Salvar"

- Clique no ícone do Hammerspoon na barra de menus e selecione "Reload Config"

Pronto! Agora você vai ter que segurar o Command + Q por um tempinho e não vai
mais fechar seus aplicativos sem querer.

## Collage

Esse script cria uma lista das coisas que você copia, fazendo com que seja
fácil encontrá-las e colá-las depois. Eu não quero que o ícone fique
aparecendo o tempo todo e nem quero que todas as coisas que eu copio entrem na
lista, então uso o atalho Command + Shift + C (em vez de só Command + C), mas
é fácil mudar isso editando o código fonte. Eu também uso o atalho Command +
Shift + V pra redigitar o último texto copiado. Isso faz com que esse
comando possa ser usado mesmo em sites que bloqueiam o comando Command +
V (pra copiar e colar senhas, por exemplo). Ele também é útil para colar
o texto sem formatação. É como se tudo fosse digitado outra vez mesmo. [O
arquivo está
aqui.](https://github.com/dbmrq/dotfiles/raw/master/home/.hammerspoon/collage.lua)
Dessa vez vou deixar você adaptar o resto das instruções sozinho.

## Mocha

Esse script não deixa o seu computador dormir. [Aqui está
o arguivo](https://github.com/dbmrq/dotfiles/raw/master/home/.hammerspoon/mocha.lua),
agora você já consegue fazer o resto sozinho. Depois de instalá-lo, é só
apertar `⌃⌥⌘M` pra impedir o computador de entrar em repouso e depois clicar
no ícone da barra de menus pra permitir que entre outra vez.

## Mais

Se você quiser mais, pode dar uma olhada nos meus
[dotfiles](https://github.com/dbmrq/dotfiles/tree/master/home/.hammerspoon).
Lá tem mais algumas coisinhas um pouco mais obscuras, e eu sempre estou
acrescentando coisas novas. Por sinal, é uma boa ficar de olho nas mudanças
que eu faço nos scripts acima e atualizá-los de vez em quando. Vira e mexe
faço melhorias. Boa sorte!

