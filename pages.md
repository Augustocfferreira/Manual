[Índice](README.md#manual-elipse-mobile)

# Páginas

Dentro do menu *Páginas*, é possível visualizar as páginas da aplicação, criar novas páginas e gerar QRCodes para se ter um acesso mais rápido pelo aplicativo.

No ítem *Permissões* é possível configurar quais usuários terão acesso à página selecionada. Para maiores informações, veja o capítulo de [Usuários](users.md).

# Objetos de Página

Em cada página são inseridos objetos que compõem a interface do operador com o sistema, chamados Objetos de Página.
Os seguintes objetos podem ser inseridos em uma Página:
* [Display](#display)
* [Display Link](#display-link)
* [Toggle](#toggle)
* [Pulser](#pulser)
* [Setpoint](#setpoint)
* [Page Link](#page-link)
* [Commands](#commands)
* [Form](#form)
* [Chart](#chart)
* [Group](#group)

## Display

O display é um objeto para exibição de valores, para configurá-lo deve-se preencher seus campos da seguinte forma:
  
![display](https://cloud.githubusercontent.com/assets/26389485/23960369/9a532876-0986-11e7-9d27-6cbbc1c39d6f.jpg)

| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do display|
| Imagem  | Imagem a ser exibida ao lado do valor|
| Tag  | Tag que será coletado o valor a ser exibido |
| Sufixo  | String que aparecerá ao lado do valor do tag |
| Decimais  | Número de casas decimais do valor|

[Voltar para o topo](pages.md)

## Display Link

O Display Link é um objeto que possui as mesmas funcionalidades do display e também a função de mudança de página. Para trabalhar com o Display Link, deve-se preencher seus campos da seguinte forma:
  
  ![disp_link](https://cloud.githubusercontent.com/assets/26389485/23960367/9a509958-0986-11e7-9ed7-f9afa0041c2e.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do display|
| Imagem  | Imagem a ser exibida ao lado do valor|
| Tag  | Tag que será coletado o valor a ser exibido |
| Sufixo  | String que aparecerá ao lado do valor do tag |
| Decimais  | Número de casas decimais do valor|
| Nome da Página  | Seleção da página a ser aberta¹|

*¹Caso a página não exista, é possível selecionar [Nova página...] e o mesmo irá criar uma nova página com o nome desejado.*

[Voltar para o topo](pages.md)

## Toggle

O objeto Toggle tem a funcionalidade de realizar escritas persistentes de dois valores em um tag. Para utiliza-lo deve-se configurar suas propriedades da seguinte forma:
  
  ![toggle](https://cloud.githubusercontent.com/assets/26389485/23960379/9a9305cc-0986-11e7-92e1-cc410aeeb4c3.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do toggle |
| Tag  | Tag que será utilizado para fazer a leitura e escrita de valor pelo toggle |
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |
| Valor ON  | Valor que é intepretado como verdadeiro |
| Texto ON  | Texto que é visualizado quando verdadeiro |
| Imagem ON  | Imagem que é visualizada quando verdadeiro |
| Valor OFF  | Valor que é intepretado como falso |
| Texto OFF  | Texto que é visualizado quando falso |
| Imagem OFF  | Imagem que é visualizada quando falso |

[Voltar para o topo](pages.md)
  
## Pulser
  
O Pulser permite realizar escritas quando a condição base é atendida. A escrita é realizada em um tag e o resultado/verificação do valor base é retornado através de outro tag. Para utilizá-lo deve-se configurar da seguinte maneira:
  
  ![pulser](https://cloud.githubusercontent.com/assets/26389485/23960374/9a75c304-0986-11e7-8137-5525e9e118d0.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do pulser |
| Tag leitura  | Tag utilizado para saber o retorno da escrita |
| Valor ON  | Valor que é intepretado como verdadeiro |
| Texto ON  | Texto que é visualizado quando verdadeiro |
| Imagem ON  | Imagem que é visualizada quando verdadeiro |
| Valor OFF  | Valor que é intepretado como falso |
| Texto OFF  | Texto que é visualizado quando falso |
| Imagem OFF  | Imagem que é visualizada quando falso |
| Tag escrita  | Tag que terá o valor escrito |
| Valor base  | Condição que o tag de leitura deve estar para que o Pulser escreva o valor do campo valor positivo|
| Valor positivo  | Valor a ser escrito caso o tag de leitura esteja com o mesmo valor configurado no campo valor base |
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |  

[Voltar para o topo](pages.md)

## Setpoint

O Setpoint permite realizar escrita de valores no tag. A escrita ela pode ser realizada escrevendo o valor desejado diretamente no campo de valor, ou através dos botões de incremento (setas nas extremidades do valor). Para configurá-lo deve-se fazer da seguinte maneira:

![setpoint](https://cloud.githubusercontent.com/assets/26389485/23960377/9a88096a-0986-11e7-8e9c-79d671bc0b41.jpg)

| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do setpoint |
| Imagem  | Imagem a ser exibida ao lado do valor |
| Tag  | Tag que será utilizado para fazer a leitura e escrita de valor |
| Incremento  | Valor de incremento caso o usuário opte em selecionar o valor desejado através desta opção |
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |  
| Sufixo  | String que aparecerá ao lado do valor do tag |
| Decimais  | Número de casas decimais do valor|

[Voltar para o topo](pages.md)

## Page Link

O Page Link é um objeto que a funcionalidade de mudança de página. Para configurá-lo deve-se fazer da seguinte maneira:

  ![page_link](https://cloud.githubusercontent.com/assets/26389485/23960373/9a717402-0986-11e7-90ce-adf27a484bee.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do Page Link |
| Imagem  | Imagem a ser exibida ao lado do valor |
| Nome da Página  | Seleção da página a ser aberta¹|

*¹Caso a página não exista, é possível selecionar [Nova página...] e o mesmo irá criar uma nova página com o nome desejado.*

[Voltar para o topo](pages.md)
  
## Commands

O Commands permite criar uma lista de comandos a serem realizados de acordo com uma condição prévia, sendo possível também travar os comandos baseado em uma condição da tag de leitura. A condição e o comando são realizados em tags diferentes. Para utilizar este objeto deve-se fazer a configuração da seguinte maneira:
  
  ![commands](https://cloud.githubusercontent.com/assets/26389485/23960365/9a40f8b8-0986-11e7-9ad5-9e3f25b11db4.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do objeto Commands |
| Imagem  | Imagem a ser exibida ao lado do valor |
| Zonas  | Ver ítem [Zonas](#zonas) |
| Comandos  | Ver ítem [Comandos](#comandos) |
| Interlocked | Neste campo de travamento do comando, deve-se configurar uma expressão que informe quando os comandos não podem ser utilizados. Quando true, os comandos são bloqueados, quando false, os mesmos são liberados para a utilização|
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |  
| Tag leitura  | Tag referência para o estado atual do equipamento que será comandado |
| Tag escrita  | Tag que receberá o valor do comando selecionado pelo usuário |

[Voltar para o topo](pages.md)

### Zonas

![zonas](https://cloud.githubusercontent.com/assets/26389485/23994552/2594fc78-0a24-11e7-8eb5-d27cb460e179.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| ![adicionar](https://cloud.githubusercontent.com/assets/26389485/23994544/25604f46-0a24-11e7-993d-4fbd0352950f.png)    | Adiciona uma nova zona |
| ![editar](https://cloud.githubusercontent.com/assets/26389485/23994549/2585726c-0a24-11e7-8a27-c7a45e0394a7.png)    | Edita a zona selecionada na lista |
| ![apagar](https://cloud.githubusercontent.com/assets/26389485/23994550/25916202-0a24-11e7-895c-28a6473c41e3.png)    | Apaga a zona selecionada na lista |

![prop_zonas](https://cloud.githubusercontent.com/assets/26389485/23994551/2594d018-0a24-11e7-9b77-460830cafe8c.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Texto    | Texto a ser exibido de acordo com o valor configurado no campo **Condição para exibir** |
| Condição para exibir    | Valor para que o texto configurado acima seja exibido. Value é o valor do tag leitura |

[Voltar para o topo](pages.md)

### Comandos

![comandos](https://cloud.githubusercontent.com/assets/26389485/23994553/259599e4-0a24-11e7-9d51-683cef11a1a0.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| ![adicionar](https://cloud.githubusercontent.com/assets/26389485/23994544/25604f46-0a24-11e7-993d-4fbd0352950f.png)    | Adiciona um novo comando |
| ![editar](https://cloud.githubusercontent.com/assets/26389485/23994549/2585726c-0a24-11e7-8a27-c7a45e0394a7.png)    | Edita o comando selecionado na lista |
| ![apagar](https://cloud.githubusercontent.com/assets/26389485/23994550/25916202-0a24-11e7-895c-28a6473c41e3.png)    | Apaga o comando selecionado na lista |

![prop_comandos](https://cloud.githubusercontent.com/assets/26389485/23994554/2595b032-0a24-11e7-9dc2-9e80a83596d9.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Texto    | Texto com o nome do comando a ser exibido na janela de comando |
| Condição para exibir    | Condição para que este comando seja exibido na lista de comandos |
| Valor para escrita    | Valor a ser escrito quando utilizado este comando|

[Voltar para o topo](pages.md)
  
## Form
  Mostra um Form.
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Formulário    | Formulário que será mostrado |
| Altura   | Quantos quadros de altura serão utilizados para a visualização |

[Voltar para o topo](pages.md)
  
## Chart
  
  Lançamento previsto para a versão 1.5.
  
## Group

O Group permite criar uma divisão de objetos dentro de uma página. Para utilizá-lo deve-se configurar da seguinte forma:
  
  ![group](https://cloud.githubusercontent.com/assets/26389485/23960371/9a654c0e-0986-11e7-8a57-c6879b868fcd.jpg)

[Voltar para o topo](pages.md)
