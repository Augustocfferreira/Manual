# Conexões

  As conexões servem de caminho entre as fontes de dados (E3, servidor OPC, EPM, Arduino) e os objetos que estarão na tela para monitoramento e controle.
  Os tipo de conexões são:

## Elipse E3

  A conexão com o Elipse E3 pode se dar de duas formas, via OPC-DA, onde o Elipse Mobile interpreta o E3 como qualquer outro servidor OPC ou com a conexão E3 nativa presente no Mobile, o que possibilita uma resposta melhor em função da conexão não se dar pela DCOM do Windows.
  
### E3 OPC-DA

![e3opc](https://cloud.githubusercontent.com/assets/26389485/24060044/3744b53c-0b30-11e7-87d4-6f06cf2fcb62.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Servidor    | Nome da máquina com o Servidor OPC |
| Testar   | Testa a conexão foi configurada corretamente |
  
### E3 Nativo

![e3nativo](https://cloud.githubusercontent.com/assets/26389485/24060037/370bb75a-0b30-11e7-87e3-4a88a29185ab.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome    | Nome da conexão  |
| Servidor    | Nome da máquina com o Servidor OPC |
| User    | Usuário       |
| Password  | Senha       |
| Testar   | Testa a conexão foi configurada corretamente |

## Elipse SCADA

![scada](https://cloud.githubusercontent.com/assets/26389485/24060038/3726fee8-0b30-11e7-8d1e-ec47f2ec382f.png)

## OPC-DA

![opc](https://cloud.githubusercontent.com/assets/26389485/24060039/3737eca8-0b30-11e7-9934-a2a1ef19c92a.png)

  O tipo de conexão OPC-DA permite a conexão do Elipse Mobile com qualquer servidor que se utilize da tecnologia OPC-DA.

## Arduino

![arduino](https://cloud.githubusercontent.com/assets/26389485/24060040/3737fd4c-0b30-11e7-874f-cd6a6cb29709.png)

  O Elipse Mobile possui uma conexão nativa com as placas Arduino, o que faz com que a configuração e comunicação com o Arduino seja mais fácil e rápida.
  Veja a página [Elipse Mobile Arduino](https://github.com/elipsemobile/arduino#elipse-mobile-arduino) para maiores informações.

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

## Form

![form](https://cloud.githubusercontent.com/assets/26389485/24060042/37392780-0b30-11e7-82f9-0d982123aa72.png)

O Elipse Mobile Forms permite a criação de formulários para serem preenchidos online ou offline.
Estes formulários podem ser usados como pequenos bancos de dados e também para fazer coletas em campo.

 * Visão geral
 * Agendamento
 * Eventos e integração

### Conceitos

Um formulário ou form é a representação de uma folha com respostas.
No servidor Mobile se encontra a definição do modelo de form e o armazenamento das respostas preenchidas.
Um formulário também pode ser visto como uma tabela de banco de dados aonde cada linha representa um formulário e cada coluna a pergunta deste formulário.

No Mobile as repostas possuem campos pré-definidos e um estado que controla o fluxo de edição.
Ao ser criado o form nasce com o estado **pendente**, que significa que ele deve ser preenchido por alguém.

Cada definição de form possui a definição de usuários administradores ou apenas usuários.
Os administradores são aqueles que podem criar novas entradas no banco (criar um form novo) e usuário são aqueles que somentem podem preencher o form, mas não podem deletar ou criar uma formulário novo.

Quando o form é criado e está pendente, qualquer usuário (grupo) do formulário pode atribuir a tarefa de preencher o formulário para si.
Sendo assim o form entra no estado **atribuído para alguém**. Neste estado outros usuários não poderão editar este form. Isso evita que ele seja preenchido por mais de uma pessoa ao mesmo tempo.

O modelo de preenchimento offline também se baseia neste conceito de atribuição.
Quando um usuário decide ir offline para fazer uma coleta todos os formulários que estão atribuídos para ele são armazenados no dipositivo móvel.

Depois de preenchido o formulario é enviado automaticamente para o servidor (se online) ou fica armazenado até que a operação "Conectar" seja utilizada. Ao conectar, todos os formários editados offline serão enviados para o servidor.

Depois da fase de edição existe a fase de finalização. Mesmo quando as repostas são enviadas para o servidor não significa que ele esteja pronto. Assim, a última etapa da edição consiste em marcar o form como **finalizado**.

Existe uma opção para o formulário que é **revisão**. Quando esta opção estiver marcada existe uma etapa extra após a finalização.
Esta etapa pode ser feita apenas pelos administradores do form e correspende a aprovação da coleta de dados.

Cada form do Elipse Mobile representa uma tabela.

Para criar um form vá em _Menu -> Conexões -> "+" -> Form_

Entre com o nome do formulário:

#### Tipos de campos

 * Número
 Para valores numéricos
 
 * Texto Curto
 Para nomes, descrições
 
 * Texto Longo
 Para anotações maiores, comentários
 
 * Digital
 True/False
 
 * Imagem
 Imagem enviada para o servidor
 
 * QRCode
 Ativa a leitura de um qrcode
 
 * Grupo
 Usado para fazer a separação de perguntas no form. Não salva nada no banco de dados.
 
 * Imagem estática
 Usado para colocar uma imagem de auxílio entre as perguntas do form. Não salva nada no banco de dados.
 
 * Data
Entrada de uma data.

#### Fase de revisão 
[X] Incluir fase de revisão
Esta opção faz com que exista uma fase adicional no fluxo do formário.

#### Permissões
Administradores podem: 
 - Criar uma nova entrada (registro) no formulário
 - Podem deletar registros
 - Editar campos reservados para Administradores
 - Aprovar/revisar respostas de formulários caso esta opção seja usada
 - As demais opções de usuários

Usuários podem:
 - Responder formulários
 - Atribuir (levar para edição) um formulário para si mesmo
 - Desistir de preencher um formulário atruibuido para si mesmo
 
### Fluxo de edição do Form

Ao ser criado o form se encontra o estado **0=pendente**.
Qualquer usuário do form pode atribuir um registro para si com a finalidade de editá-lo. 
Estado **1=Atribuído**.
Ao concluir, o usuário passa o form para o estado **2=Finalizado**.
Ele também pode desistir de preencher o form e ele volta para o estado **0=pendente**.

Se o form estiver com a opção "etapa de revisão" então após a finalização um administrador do form precisa aprovar.
Desta forma o form passa para o estado **3=Aprovado**.

### Scripts

Os scripts do Mobile são feitos na linguagem Javascript.

Existe vasta documentação na web, por exemplo:
https://www.w3schools.com/jsref/default.asp


## Script de agendamento de criação de forms

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

#### Script para criar um form de acordo com o dia da semana

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



### Script no evento de modificação do form

Quando uma resposta é criada/edita, um evento de script de é chamado no lado do servidor.

Este evento pode ser usado para :
 * Validar o form
 * Copiar dados para outros sistema (EPM/E3) via writetag
 * Enviar um e-mail de notificação sobre alteração do form
 
Exemplo:


```js

function OnChange(args)
{
  //Se estado for 2 então é aprovado
  if (args._state == 2/*aprovado*/)
  {
     WriteTag("demo:TagInternal1", 
              args.campo.toString(),
              function (er) { }
      );
  }
}

```

args.campo é o nome dado ao campo do formulário.

Além dos campos definidos pelo usuário existe campos pré-definidos e reservados.

São eles:

```
_id             : Uso interno
_lastupdate_at  : Momento da última atualização
_lastupdate_by  : Nome do usuário que alterou o form por último
_state          : 0=pendente, 1=Atribuído, 2=Finalizado e 3=Aprovado
_assigned_to    : No estado Atribuído, indica o nome do usuário 

```


### Modo OffLine

Quando o usuário entra no modo offline, é feito uma cópia de todas as páginas do servidor para o celular. 
Além das páginas, todos os forms atribuídos para o usuário serão copiados.
No modo offline o usuário pode editar os formularios que estão atribuídos para sí. 

Quando ele voltar ao modo online, as alterações dos formulários serão enviadas para o servidor.

## EPM (OPCA UA)

![ua](https://cloud.githubusercontent.com/assets/26389485/24060043/373b5e06-0b30-11e7-9029-ff3ec91bc257.png)
