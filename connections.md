[Índice](README.md#manual-elipse-mobile)

________________________________________

# Conexões

  As conexões servem de caminho entre as fontes de dados (E3, servidor OPC, EPM, Arduino) e os objetos que estarão na tela para monitoramento e controle.
  Os tipo de conexões são:
  
  - [Elipse E3](connections.md#e3)
    - [E3 OPC-DA](connections.md#e3)
    - [E3 Nativo](connections.md#e3)
  - [Elipse SCADA](connections.md#e3)
  - [OPC-DA](connections.md#e3)
  - [Arduino](connections.md#e3)
  - [Demo](connections.md#demo)
  - [Form](connections.md#form)  
    - [Conceitos](connections.md#conceitos)  
    - [Fluxo de edição do Form](connections.md#fluxo-de-edição-do-form)  
    - [Scripts](connections.md#scripts)  
    - [Modo Offline](connections.md#modo-offline)      
  - [EPM (OPCA UA)](connections.md#epm-opca-ua#epm-opca-ua)
  
________________________________________

## Elipse E3

  A conexão com o Elipse E3 pode se dar de duas formas, via OPC-DA, onde o Elipse Mobile interpreta o E3 como qualquer outro servidor OPC ou com a conexão E3 nativa presente no Mobile, o que possibilita uma resposta melhor em função da conexão não se dar pela DCOM do Windows.
  
_______________________________________
  
### E3 OPC-DA

![e3opc](https://cloud.githubusercontent.com/assets/26389485/24060044/3744b53c-0b30-11e7-87d4-6f06cf2fcb62.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Servidor    | Nome da máquina com o Servidor E3 OPC |

____________________________________________
  
### E3 Nativo

![e3nativo](https://cloud.githubusercontent.com/assets/26389485/24060037/370bb75a-0b30-11e7-87e3-4a88a29185ab.png)

A conexão E3 nativa permite ao administrador do sistema adicionar duas máquinas servidoras (HotStandby), para que no caso de falha do servidor principal, o servidor backup é ativado e o Elipse Mobile entende esta mudança.

Para configurar esta opção, digite o nome dos servidores separados por vírgula no campo *Servidor*.

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Servidor    | Nome da(s) máquina(s) com E3 Server |
| User    | Usuário       |
| Password  | Senha       |

[Voltar para o topo](connections.md)

______________________________________

## Elipse SCADA

![scada](https://cloud.githubusercontent.com/assets/26389485/24060038/3726fee8-0b30-11e7-8d1e-ec47f2ec382f.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Servidor    | Nome da máquina com o Servidor SCADA OPC |

[Voltar para o topo](connections.md)

## OPC-DA

![opc](https://cloud.githubusercontent.com/assets/26389485/24060039/3737eca8-0b30-11e7-9934-a2a1ef19c92a.png)

  O tipo de conexão OPC-DA permite a conexão do Elipse Mobile com qualquer servidor que se utilize da tecnologia OPC-DA.
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| OPC Server program ID    |  ID do Servidor OPC  |
| Servidor    | Nome da máquina com o Servidor OPC |

[Voltar para o topo](connections.md)

_____________________________________________

## Arduino

![arduino](https://cloud.githubusercontent.com/assets/26389485/24060040/3737fd4c-0b30-11e7-874f-cd6a6cb29709.png)

  O Elipse Mobile possui uma conexão nativa com as placas Arduino, o que faz com que a configuração e comunicação com o Arduino seja mais fácil e rápida.
  
| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Port    | Porta COM em que se encotra o Arduino |
  
  
  Veja a página [Elipse Mobile Arduino](https://github.com/elipsemobile/arduino#elipse-mobile-arduino) para maiores informações.
  
 [Voltar para o topo](connections.md)
 
___________________________________

## Demo

![demo](https://cloud.githubusercontent.com/assets/26389485/24060041/3738dbd6-0b30-11e7-89f8-a3fc52e5e13c.png)

  A conexão Demo permite ao desenvolvedor da aplicação ter acesso à vários tags de demonstração. Sendo eles:
  
| Nome    | Tipo  |
| -------------   | ------------- |
| TagInternal1    | Interno       |
| TagInternal2    | Interno       |
| TagInternal3    | Interno       |
| TagDemoRandom1  | Randômico       |
| TagDemoRandom2  | Randômico       |
| TagDemoRandom3  | Randômico       |
| TagDemoRamp1  | Rampa de subida 0 - 100|
| TagDemoRamp2  | Rampa de subida 5 - 10|
| TagDemoRamp3  | Rampa de subida 20 - 30|

[Voltar para o topo](connections.md)

_________________________________________

## Form

![form](https://cloud.githubusercontent.com/assets/26389485/24060042/37392780-0b30-11e7-82f9-0d982123aa72.png)

O Elipse Mobile Forms permite a criação de formulários para serem preenchidos online ou offline.
Estes formulários podem ser usados como pequenos bancos de dados e também para fazer coletas em campo.

 * Visão geral
 * Agendamento
 * Eventos e integração

[Voltar para o topo](connections.md)

______________________________________


### Conceitos

Um formulário ou form é a representação de uma folha com respostas.
No servidor Mobile se encontra a definição do modelo de form e o armazenamento das respostas preenchidas.

No Mobile as repostas possuem campos pré-definidos e um estado que controla o fluxo de edição.
Ao ser criado o form nasce com o estado **pendente**, que significa que ele deve ser preenchido por alguém.

Cada definição de form possui uma configuração de usuários administradores ou apenas usuários.
Os administradores são aqueles que podem criar uma nova entrada (criar um form novo) e usuário são aqueles que somentem podem preencher o form, mas não podem deletar ou criar uma formulário novo.

Quando o form é criado e está pendente, qualquer usuário (grupo) do formulário pode atribuir a tarefa de preencher o formulário para si.
Sendo assim, o form entra no estado **atribuído para alguém**. Neste estado outros usuários não poderão editar este form.
Isso evita que ele seja preenchido por mais de uma pessoa ao mesmo tempo.

O modelo de preenchimento offline também se baseia neste conceito de atribuição.
Quando um usuário decide ir offline para fazer uma coleta todos os formulários que estão atribuídos para ele são armazenados no dipositivo móvel.

Depois de preenchido o formulario é enviado automaticamente para o servidor (se online) ou fica armazenado até que a operação "Conectar" seja utilizada. Ao conectar, todos os formários editados offline serão enviados para o servidor.

Depois da fase de edição existe a fase de finalização. Mesmo quando as repostas são enviadas para o servidor não significa que ele esteja pronto. Assim, a última etapa da edição consiste em marcar o form como **finalizado**.

Existe uma opção para o formulário que é **revisão**. Quando esta opção estiver marcada existe uma etapa extra após a finalização.
Esta etapa pode ser feita apenas pelos administradores do form e correspende a aprovação da coleta de dados.

O objeto possui as seguintes opções em sua criação:

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome do Form  |
| Campos    | Ver ítem [Campos](#campos) |
| Incluir fase de Revisão    | Esta opção faz com que exista uma fase adicional no fluxo do formário. |
| Script  | Ver ítem [Scripts](#scripts)|

|     |  Permissões  |
| -------------   | ------------- |
| Administradores  | Criar uma nova entrada (registro) no formulário; -Podem deletar registros; Editar campos reservados para Administradores; Aprovar/revisar respostas de formulários caso esta opção seja usada; As demais opções de usuários |
| Usuários  | Responder formulários; Atribuir (levar para edição) um formulário para si mesmo; Desistir de preencher um formulário atruibuido para si mesmo|

[Voltar para o topo](connections.md)

______________________________________

#### Campos


![campos](https://cloud.githubusercontent.com/assets/26389485/24098712/b0a03a34-0d4a-11e7-9bba-4e25e4c4f926.png) 

| Propriedade    | Função  |
| -------------   | ------------- |
| ![adicionar](https://cloud.githubusercontent.com/assets/26389485/23994544/25604f46-0a24-11e7-993d-4fbd0352950f.png)    | Adiciona um novo campo |
| ![editar](https://cloud.githubusercontent.com/assets/26389485/23994549/2585726c-0a24-11e7-8a27-c7a45e0394a7.png)    | Edita o campo selecionado na lista |
| ![apagar](https://cloud.githubusercontent.com/assets/26389485/23994550/25916202-0a24-11e7-895c-28a6473c41e3.png)    | Apaga o campo selecionado na lista |

[Voltar para o topo](connections.md)

______________________________________

##### Propriedades do campo

![prop_campo](https://cloud.githubusercontent.com/assets/26389485/24262908/54e5d8b0-0fda-11e7-97a5-4ce87934c8cf.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Texto    | Texto a ser exibido para o usuário no preenchimento do formulário |
| Nome    | Texto para identificar o campo |
| Tipo    | Ver ítem [Tipo de Campo](#tipo-de-campo) |
| Reservado para administradores    | Reserva o campo para que apenas administradores deste formulário consigam responder |

[Voltar para o topo](connections.md)

______________________________________

##### Tipo de campo

![tipo_de_campo](https://cloud.githubusercontent.com/assets/26389485/24262975/82957554-0fda-11e7-9f5f-50b81610f5e9.png)

| Tipo    | Descrição  |
| -------------   | ------------- |
| Número    | Para valores numéricos |
| Texto Curto   | Para nomes, descrições |
| Texto Longo   | Para anotações maiores, comentários |
| Digital   | True/False |
| Imagem   | Imagem enviada para o servidor |
| QRCode   | Ativa a leitura de um QRCode |
| Grupo   | Usado para fazer a separação de perguntas no form. Não salva nada no banco de dados |
| Imagem Estática   | Usado para colocar uma imagem de auxílio entre as perguntas do form. Não salva nada no banco de dados |
| Data | Entrada de uma data|

[Voltar para o topo](connections.md)

______________________________________

### Scripts

![script_form](https://cloud.githubusercontent.com/assets/26389485/24263769/ebcb4a06-0fdc-11e7-8600-f94577ba4091.png)

Os scripts do Elipse Mobile são feitos na linguagem JavaScript.
Existe vasta documentação na web sobre JavaScrit, por exemplo: https://www.w3schools.com/jsref/default.asp

* Parâmetros Globais

Os parâmetros globais disponíveis para acesso via script no Form são:

```
state          : 0=pendente, 1=Atribuído, 2=Finalizado e 3=Aprovado
assignedUser   : Usuário atribuído ao formulário
user           : 
timestamp      : Data/Hora da última atualização do Form
fields         : Local onde os campos estarão listados e organizados
```

Para o acesso destas variáveis, a sintaxe correta é:

```
form.NOME_DO_PARAMETRO
```

Exemplo:

```js
WriteTag("demo:TagInternal1", 
          form.assignedUser, 
          function(er)  { }
          );
```

* Propriedades do Campo

Dentro de cada campo, temos as propriedades:

```
value          : Valor do campo
timestamp      : Data/Hora da última atualização do campo
```

Desta forma, para se ter acesso às propriedades do campo, a sintaxe correta é:

```
form.fields.NOME_DO_CAMPO.NOME_DA_PROPRIEDADE
```

Exemplo:
```js
WriteTag("demo:TagInternal1", 
          form.fields.campo1.value, 
          function(er)  { }
          );
```

* Exemplo de script de modificação do form

Quando uma resposta é criada/edita, um evento de script de é chamado no lado do servidor.

Este evento pode ser usado para validar o form, copiar dados para outros sistema (EPM/E3) via writetag e/ou enviar um e-mail de notificação sobre alteração do form.
 
Exemplo:


```js

function OnChange(form)
{
  //Se estado for 2 então é finalizado
  if (form.state == 2/*Finalizado*/)
  {
     WriteTag("demo:TagInternal1", 
              form.fields.campo.value,
              function (er) { }
      );
  }
}

```

form.campo é o nome dado ao campo do formulário.

* Exemplo de agendamento de criação de forms

Menu -> Eventos -> + -> Script

Condição - Ser sexta feira

Condição:
```
(new Date(ValueOf("demo:_now"))).getDay() == 5
```
Esta condição precisa ter um tag do mobile.
Por isso, o tag "demo:now" foi adicionado na expressão.


Note: Sunday is 0, Monday is 1, and so on.
http://www.w3schools.com/jsref/jsref_obj_date.asp

Script

```js
SendMail("a",
 "Dia de preencher form",
 "message",
 function (er) 
 {
 });

WriteNode("form:", 
         {campo: 1}, 
         function(er){
         });

```

* Exemplo de como criar um form de acordo com o dia da semana

```
Condição:  ValueOf("demo:_now") && (new Date().getDay() == 1)
```

Script:
```js

var day = new Date().getDay();
var title = "Segunda";
var formName = "FormName";

if (formName)
{
  WriteNode(formName + ":", 
            { Diario : title }, 
              function(er)
              {
              }
            );
}

```
É possível criar outro script semelhante para outros dias.

O script roda quando o evento **entrar na condição verdadeira**.
Quando a condição for para false não acontece nada.

Além dos campos definidos pelo usuário existe campos pré-definidos e reservados.

São eles:

```
id             : Uso interno
state          : 0=pendente, 1=Atribuído, 2=Finalizado e 3=Aprovado
assignedUser    : No estado Atribuído, indica o nome do usuário 

lastupdate_at  : Momento da última atualização
lastupdate_by  : Nome do usuário que alterou o form por último


```

[Voltar para o topo](connections.md)

______________________________________


### Fluxo de edição do Form

Ao ser criado o form se encontra o estado **0=pendente**.
Qualquer usuário do form pode atribuir um registro para si com a finalidade de editá-lo. 
Estado **1=Atribuído**.
Ao concluir, o usuário passa o form para o estado **2=Finalizado**.
Ele também pode desistir de preencher o form e ele volta para o estado **0=pendente**.

Se o form estiver com a opção "etapa de revisão" então após a finalização um administrador do form precisa aprovar.
Desta forma o form passa para o estado **3=Aprovado**.

[Voltar para o topo](connections.md)

______________________________________

### Modo Offline

Quando o usuário entra no modo offline, é feito uma cópia de todas as páginas do servidor para o celular. 
Além das páginas, todos os forms atribuídos para o usuário serão copiados.
No modo offline o usuário pode editar os formularios que estão atribuídos para sí. 

Quando ele voltar ao modo online, as alterações dos formulários serão enviadas para o servidor.

[Voltar para o topo](connections.md)

________________________________________

## EPM (OPCA UA)

![ua](https://cloud.githubusercontent.com/assets/26389485/24060043/373b5e06-0b30-11e7-9029-ff3ec91bc257.png)


| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Server    | Nome da máquina com E3 Server |
| User    | Usuário       |
| Password  | Senha       |

[Voltar para o topo](connections.md)
