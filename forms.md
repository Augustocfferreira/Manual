# Elipse Mobile Forms

##Introdução
O Elipse Mobile forms permite a criação de formulários para serem preenchidos online ou offline.
Estes formulários podem ser usados como pequenos bancos de dados e também para fazer coletas em campo.


 * Visão geral
 * Agendamento
 * Eventos e integração
 

##Conceitos

Cada form do Elipse Mobile representa uma tabela.

Para criar um form vá em _Menu -> Conexões -> "+" -> Form_

![Tela mostrando menu]()

![Tela mostrando mais]()

Entre com o nome do formulário:

![Tela form]()

###Tipos de campos

###Fase de revisão 
[X] Incluir fase de revisão
Esta opção faz com que exista uma fase adicional no fluxo do formário.

###Permissões
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
 
##Fluxo de edição do Form

Ao ser criada 


##Agendamento de criação de forms

Condição -  ser sexta feira

```
(new Date(ValueOf("demo:_now"))).getDay() == 5
```
Note: Sunday is 0, Monday is 1, and so on.
http://www.w3schools.com/jsref/jsref_obj_date.asp

Script

```
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


##Script ao receber form

Quando uma resposta é criada/edita, um evento de script de é chamado no lado do servidor.

Este evento pode ser usado para :
 * Validar o form
 * Copiar dados para outros sistema (EPM/E3) via writetag
 * Enviar um e-mail de notificação sobre alteração do form
 
Exemplo:
```

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
Além dos campos definidos pelo usuário existe campos pré-definidos.
São eles

```
_id
_lastupdate_at
_lastupdate_by
_state
_assigned_to

```


