# Elipse Mobile Forms

##Introdução
O Elipse Mobile forms permite a criação de formulários para serem preenchidos online ou offline.
Estes formulários podem ser usados como pequenos bancos de dados e também para fazer coletas em campo.

 * Visão geral
 * Agendamento
 * Eventos e integração
 

##Conceitos

Um formulário ou form é representa uma folha com respostas.
No servidor Mobile se encontra a definição do modelo de form e o armazenamento de respostam preenchidas.
Um formulário também pode ser visto como uma tabela de um banco de dados aonde cada linha representa um formulário e cada coluna a pergunta.

No mobile as repostas possuem campos pré-definidos e um estado que controla o fluxo da edição.
Ao ser criado o form nasce com o estado pendente, que significa que ele deve ser preenchido por alguém.

Cada definição de form possui a definição de usuários administradores ou apenas usuários.
Os administradores são aqueles que podem criar novas entradas no banco (criar um form novo)  e usuário são aqueles que somentem podem preencher o form, mas não podem deletar ou criar uma formulário novo.

Quando o form é criado e está pendente, qualquer usuário (grupo) do formulário pode atribuir a tarefa de preencher o formulário para si.
Sendo assim o form entra no estado "Atribuído para alguém". Neste estado outros usuários não poderão editar este form. Isso evita que ele seja preenchido por mais de uma pessoa ao mesmo tempo.

O modelo de preenchimento offline também se baseia neste conceito de atribuição.
Quando um usuário decide ir offline para fazer uma coleta todos os formuários que estão atribuídos para ele são armazenados no dipositivo móvel.

Depois de preenchido o formulario é enviado automaticamente para o servidor (se online) ou fica armazenado até que a operação "Conectar" seja utilizada. Ao conectar, todos os formários editados offline serão enviados para o servidor.

Depois da fase de edição existe a fase de finalização. Mesmo quando as repostas são enviadas para o servidor não significa que ele esteja pronto. Assim, a áltima etapa da edição consiste em marcar o form como "finalizado".

Existe uma opção para o formulário que é "Revisão". Quando esta opção estiver marcada existe uma etapa extra após a finalizaçào. Esta etapa pode ser feita apenas pelos administrador do fom  e correspende a aprovação da coleta de dados.



Cada form do Elipse Mobile representa uma tabela.

Para criar um form vá em _Menu -> Conexões -> "+" -> Form_

![Tela mostrando menu]()

![Tela mostrando mais]()

Entre com o nome do formulário:

![Tela form]()

###Tipos de campos

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

Ao ser criado o form se encontra o estado 0=pendente.
Qualquer usuário do form pode atribuir um registro para si com a finalidade de editá-lo. 
Estado 1=Atribuído.
Ao concluir, o usuário passa o form para o estado 2=Finalizado.
Ele também pode desistir de preencher o form e ele volta para o estado 0=pendente.

Se o form estiver com a opção "ëtapa de revisão" então após a finalização um administrador do form precisa aprovar. Desta forma o form passa para o estado 3=Aprovado.



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


##Modo OffLine

Quando o usuário entra no modo offline, é feito uma cópia de todas as páginas dos servidor para o celular. 
Além das páginas, todos os forms atribuídos para o usuário serão copiados.
No modo offline o usuário pode editar os formularios que estão atribuídos para sí. 

Quando ele voltar ao modo online, as alterações dos formulários serão enviadas para o servidor.


##Sqlite browser

http://sqlitebrowser.org/
