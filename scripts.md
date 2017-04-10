[Índice](README.md#manual-elipse-mobile)

_________________________________________

# Referência de Scripts

  Os Scripts são módulos de linguagem de programação nos quais se pode criar procedimentos associados a eventos específicos, permitindo uma maior flexibilidade no desenvolvimento de aplicações.

  Abaixo segue a lista de todas as funções disponíveis para a utilização no Elipse Mobile.
* [SendMail](#sendmail)
* [WriteForm](#writeform)
* [WriteTag](#writetag)
* [WriteTagEx](#writetagex)

_________________________________________

## SendMail
  Envio de email.

```js
SendMail(users , subject , message , callback);
```
Parâmetros:
```
 users    : <string> - Lista dos usuários separados por ponto e virgula
 subject  : <string> - Assunto do e-mail
 message  : <string> - Conteúdo do e-mail
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
Exemplo:
 
```js
SendMail("usuario1;usuario2",
         "Dia de preencher form", 
         "message",
         function (er)
         {
         }
        );
```

[Voltar para o topo](scripts.md)

_________________________________________
 
## WriteForm

  Escreve respostas em um formulário existente, ou cria o form se ele não existir.
  
 
 ```js
 WriteForm(formName, fields, callback);
 ```
 Parâmetros:
```
 formName  : <string> - Nome do formulário
 fields    : <string> - Lista de respostas a serem escritas
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
 Exemplo:
 ```js
WriteForm("form:", 
         {campo:  {value : 1 }}, 
         function(er)
         {
         });

 ```
 [Voltar para o topo](scripts.md)
 
_________________________________________

## WriteTag 
Escreve o valor em um tag.

```js
WriteTag( tagName, value , callback);
```
Parâmetros:
```
 tagName  : <string> - Nome da conexão e nome do tag separados pelo caractere ":"
 value    : <double|string|bool> - Valor que será escrito no tag
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
Exemplo:
```js
WriteTag( "demo:TagInternal3", 
          15,
          function (er)
          {
          }
        );
```
Escrevendo no tag demo:TagInternal3, o valor 15.

[Voltar para o topo](scripts.md)

_________________________________________

## WriteTagEx 
Escrita de tag com timestamp e qualidade.

```js
WriteTagEx( tagName, value , timestamp, quality, callback);
```
Parâmetros:
```
 tagName  : <string> - Nome da conexão e nome do tag separados pelo caractere ":"
 value    : <double> - Valor que será escrito no tag
 timestamp: <datetime> - Estampa de tempo utilizada na escrita do tag
 callback : <function (er)> - Função que vai receber o retorno assincrono da operação
```
Exemplo:
```js
WriteTagEx("e3:Data.InternalTag1", 2, new Date().getTime(), 0,
function (er){ });
```
[Voltar para o topo](scripts.md)
