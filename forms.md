

## Form

![form](https://cloud.githubusercontent.com/assets/26389485/24060042/37392780-0b30-11e7-82f9-0d982123aa72.png)

O Elipse Mobile Forms permite a criação de formulários para serem preenchidos online ou offline.

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
Sendo assim, o form entra no estado **atribuído para alguém**. Neste estado, os outros usuários não poderão editar este form.
Isso evita que ele seja preenchido por mais de uma pessoa ao mesmo tempo.

O modelo de preenchimento offline também se baseia neste conceito de atribuição.
Quando um usuário decide ir offline para fazer uma coleta todos os formulários que estão atribuídos para ele são armazenados no dipositivo móvel.

Depois de preenchido o formulario é enviado automaticamente para o servidor (se online) ou fica armazenado até que a operação "Conectar" seja utilizada. Ao conectar, todos os formários editados offline serão enviados para o servidor.

Depois da fase de edição existe a fase de finalização. Mesmo quando as repostas são enviadas para o servidor não significa que ele esteja pronto. Assim, a última etapa da edição consiste em marcar o form como **finalizado**.

Existe uma opção para o formulário que é **revisão**. Quando esta opção estiver marcada existe uma etapa extra após a finalização.
Esta etapa pode ser feita apenas pelos administradores do form e correspende a aprovação da coleta de dados.

A conexão form, define o modelo de perguntas e possui as seguintes opções:

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

![form_fieldproperties](https://user-images.githubusercontent.com/26389485/30390674-4a75f28e-988d-11e7-88d2-f976a7ecd59c.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Texto    | Texto a ser exibido para o usuário no preenchimento do formulário |
| Nome    | Texto para identificar o campo |
| Tipo    | Ver ítem [Tipo de Campo](#tipo-de-campo) |
| Complemento   | Ver ítem [Complementos](#tipo-de-campo)  |
| Reservado para administradores    | Reserva o campo para que apenas administradores deste formulário consigam responder |
| Permitir que valor esteja indisponível    | Opção que permite ao usuário negar a resposta por alguma indisponibilidade  |

[Voltar para o topo](connections.md)

______________________________________

##### Tipo de campo

![forms_fieldtypes](https://user-images.githubusercontent.com/26389485/30390255-e20d7902-988b-11e7-8cfb-a98b4fd1371d.png)

| Tipo    | Descrição  |
| -------------   | ------------- |
| Número    | Para valores numéricos |
| Texto Curto   | Para nomes, descrições |
| Texto Longo   | Para anotações maiores, comentários |
| Digital   | True/False |
| Imagem   | Imagem enviada para o servidor |
| QR Code   | Ativa a leitura de um QR Code |
| QRCODE Check   | Faz a verificação através de um QR Code |
| Options   | Define opções para a seleção do usuário como um ComboBox |
| Grupo   | Usado para fazer a separação de perguntas no form. Não salva nada no banco de dados |
| Imagem Estática   | Usado para colocar uma imagem de auxílio entre as perguntas do form. Não salva nada no banco de dados |
| Data | Entrada de uma data|

[Voltar para o topo](connections.md)

______________________________________

##### Complementos

Alguns tipos de campos necessitam do campo Complemento para o seu funcionamento.

| Tipo    | Descrição  |
| -------------   | ------------- |
| Número    |  |
| Texto Curto   |  |
| Texto Longo   |  |
| Digital   |  |
| Imagem   |  |
| QR Code   |  |
| QRCODE Check   | Define qual a string que deve ser lida no QR Code. Exemplo: PT100 |
| Options   | Campo para definir as opções. Exemplo: a ; b; c |
| Grupo   |  |
| Imagem Estática   |  |
| Data |  |

Observação: O QRCODE Check não gera o QRCode para verificação. O mesmo pode ser gerado no mesmo gerador de QR Code utilizado pelas páginas ou gerado em qualquer outro gerador de QR Code.

[Voltar para o topo](connections.md)

______________________________________

### Scripts

 Quando o form é alterado, um evento de script é executado no server.
 

Este evento pode ser usado para validar o form, copiar dados para outros sistema (EPM/E3) via writetag e/ou enviar um e-mail de notificação sobre alteração do form.
 
 Ele também pode ser usado para enviar um e-mail.
 
 Existe um argumento no evento que representa o form e suas respotas.

Este parametro "form" possui as seguintes propriedades:
```
state          : 0=pendente, 1=Atribuído, 2=Finalizado e 3=Aprovado
assignedUser   : Usuário atribuído ao formulário
user           : Usuário responsável pela última alteração no formulário
timestamp      : Data/Hora da última atualização do Form
fields         : Local onde os campos estarão listados e organizados
```

Para o acesso destas variáveis, a sintaxe correta é:

Exemplo:

```js
WriteTag("demo:TagInternal1", 
          form.assignedUser, 
          function(er)  { 
           }
          );
```

* Propriedades do Campo

Dentro de cada campo, temos as propriedades:


```
value          : Valor do campo
timestamp      : Data/Hora da última atualização do campo
notApplicable  : true quando a pergunta foi marcada como not applicable
notes          : texto da anotação da pergunta.
```

Exemplo que escreve no tag "demo:TagInternal1" o valor respondido na pergunta "campo1"

```js
WriteTag("demo:TagInternal1", 
          form.fields.campo1.value, 
          function(er)  { }
          );
```

Geralmente se escreve no tag quando o form for para o estado Finalizado.

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

* Agendamento de criação de forms

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

WriteForm("form:", 
         {campo:  {value : 1 }}, 
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
