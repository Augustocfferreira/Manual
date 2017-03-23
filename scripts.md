[Índice](README.md#manual-elipse-mobile)

# Referência de Scripts

  Os Scripts são módulos de linguagem de programação nos quais se pode criar procedimentos associados a eventos específicos, permitindo uma maior flexibilidade no desenvolvimento de aplicações.

  Abaixo segue a lista de todas as funções disponíveis para a utilização no Elipse Mobile.
* [SendMail](#sendmail)
* [WriteForm](#writeform)
* [WriteTag](#writetag)
* [WriteTagEx](#writetagex)

## SendMail
  Envio de email.

```js
SendMail(users : string, subject : string, message : string, callback);
```
Parâmetros:
```
 users    : Lista dos usuários separados por ponto e virgula
 subject  : Assunto do e-mail
 message  : Conteúdo do e-mail
 callback : Função que vai receber o retorno assincrono da operação
```
Exemplo:
 
```js
SendMail("usuario1;usuario2", "Dia de preencher form", "message",
 function (er) 
 {});
```

[Voltar para o topo](scripts.md)
 
## WriteForm
  Escrita
 
 ```js
 WriteForm("form:", {campo: 1}, 
 function(er)
 {});
 ```
 Parâmetros:
```
 form     : <string> - Formulário que receberá o valor
 field    : <string> - Campo que receberá o valor
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
 Exemplo:
 ```js
 WriteForm("form:", {campo: 1}, 
 function(er)
 {});
 ```
 [Voltar para o topo](scripts.md)

## WriteTag 
Escrita somente do valor no tag.

```js
WriteTag( tagName, value , function (er) 
{});
```
Parâmetros:
```
 tagName  : <string> - Nome da conexão e nome do tag separados pelo caractere ":"
 value    : 
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
Exemplo:
```js
WriteTag( "demo:TagInternal3", 15,
function (er){});
```
Escrevendo no tag interno 3, o valor 15.

[Voltar para o topo](scripts.md)

## WriteTagEx 
Escrita com timestamp e qualidade.

```js
WriteTagEx( tagName, value , timestamp, quality, 
function (er) 
{});
```
Parâmetros:
```
 tagName  : <string> - Nome da conexão e nome do tag separados pelo caractere ":"
 value    : 
 timestamp: <datetime> - 
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
Exemplo:
```js
WriteTagEx("e3:Data.InternalTag1", 2, new Date().getTime(), 0,
function (er){ });
```
[Voltar para o topo](scripts.md)
