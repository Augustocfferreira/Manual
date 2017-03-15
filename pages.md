# Páginas

Dentro da aba Páginas, é possível gerenciar as páginas criadas na aplicação, criar mais páginas e até mesmo gerar QRCodes para fazer um acesso mais rápido pelo aplicativo.

Também é possível configurar as permissões de usuários ao acesso das páginas. Para maiores informações, veja o capítulo de [Usuários].

# Objetos de Página

Em cada Página são inseridos objetos que compõem a interface do operador com o sistema, chamados Objetos de Página.
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

## Display Link

O Display Link é um objeto que possui as mesmas funcionalidades do display e também a função de mudança de página. Para trabalhar com ele é necessário executar as seguintes configurações:
  
1.	Deve-se criar uma página que será aberta por este display link;
2.	Configurar o display link da seguinte maneira:
  
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
| Nome da Página  | Seleção da página a ser aberta |

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
  
## Pulser
  
O Pulser permite realizar escritas quando a condição base é atendida. A escrita é realizada em um tag e o resultado/verificação do valor base é retornado através de outro tag. Para utilizá-lo deve-se configurar da seguinte maneira:
  
  ![pulser](https://cloud.githubusercontent.com/assets/26389485/23960374/9a75c304-0986-11e7-8137-5525e9e118d0.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do toggle |
| Tag leitura  | Tag referência que terá o valor lido |
| Valor ON  | Valor que é intepretado como verdadeiro |
| Texto ON  | Texto que é visualizado quando verdadeiro |
| Imagem ON  | Imagem que é visualizada quando verdadeiro |
| Valor OFF  | Valor que é intepretado como falso |
| Texto OFF  | Texto que é visualizado quando falso |
| Imagem OFF  | Imagem que é visualizada quando falso |
| Tag escrita  | Tag que terá o valor escrito |
| Valor base  | Valor baixo do pulso |
| Valor positivo  | Valor alto do pulso |
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |  

## Setpoint

O Setpoint permite realizar escrita de valores no tag. A escrita ela pode ser realizada escrevendo o valor desejado diretamente no campo de valor, ou através dos botões de incremento (setas nas extremidades do valor). Para configurá-lo deve-se fazer da seguinte maneira:

![setpoint](https://cloud.githubusercontent.com/assets/26389485/23960377/9a88096a-0986-11e7-8e9c-79d671bc0b41.jpg)

| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do toggle |
| Imagem  | Imagem visível à direita do objeto|
| Tag  | Tag associado que terá o valor visualizado |
| Incremento  | Resolução dos passos para a alteração do valor |
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |  
| Sufixo  | String que aparecerá ao lado do valor do tag |
| Decimais  | Quantidade de casas decimais |


## Page Link

O Page Link é um objeto que a funcionalidade de mudança de página. Para trabalhar com ele é necessário executar as seguintes configurações:
1.	Deve-se criar uma página que será aberta pelo Page Link;
2.	Configurar o Page Link da seguinte maneira:
  
  ![page_link](https://cloud.githubusercontent.com/assets/26389485/23960373/9a717402-0986-11e7-90ce-adf27a484bee.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do toggle |
| Imagem  | Imagem visível à direita do objeto|
| Nome da Página  | Página que será aberta ao clicar no objeto |
  
## Commands

O Commands permite criar uma lista de comandos a serem realizados de acordo com uma condição previa, sendo possível também travar os comandos baseado em uma condição da tag de leitura. A condição e o comando são realizados em tags diferentes. Para utilizar este objeto deve-se fazer a configuração da seguinte maneira:
  
  ![commands](https://cloud.githubusercontent.com/assets/26389485/23960365/9a40f8b8-0986-11e7-9ad5-9e3f25b11db4.jpg)
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Subtítulo    | Subtítulo visível logo abaixo do título|
| Cor    | Definição de cor do toggle |
| Imagem  | Imagem visível à direita do objeto|
| Zonas  | ABCD1234 |
| Comandos  | ABCD1234 |
| Interlocked | ABCD1234 |
| Pedir confirmação antes da alteração  | Habilita uma confirmação do valor antes da escrita |  
| Tag leitura  | Tag referência que terá o valor lido |
| Tag escrita  | Tag que terá o valor escrito |
  
## Form
  Mostra um Form.
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Título    | Título visível no topo do objeto|
| Formulário    | Formulário que será mostrado |
| Altura   | Quantos quadros de altura serão utilizados para a visualização |
  
## Chart
  
## Group

O Group permite criar uma divisão de objetos dentro de uma página. Para utilizá-lo deve-se configurar da seguinte forma:
  
  ![group](https://cloud.githubusercontent.com/assets/26389485/23960371/9a654c0e-0986-11e7-8a57-c6879b868fcd.jpg)

