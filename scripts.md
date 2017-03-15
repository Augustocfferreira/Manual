# Referência de Scripts

  Os Scripts são módulos de linguagem de programação nos quais se pode criar procedimentos associados a eventos específicos, permitindo uma maior flexibilidade no desenvolvimento de aplicações.

  Abaixo segue a lista de todas as funções disponíveis para a utilização no Elipse Mobile.
* [SendMail](##SendMail)
* [WriteNode](##WriteNode)
* [WriteTag](##WriteTag)
* [WriteTagEx](##WriteTagEx)

## SendMail

```
SendMail("a",
 "Dia de preencher form",
 "message",
 function (er) 
 {
 });
 ```
 
 ## WriteNode
 
 ```
 WriteNode("form:", 
         {campo: 1}, 
         function(er){
         });
 ```
 

## WriteTag 
Escrita somente do valor no tag.

```
WriteTag( tagName, value , function (er) 
{});
```

Exemplo:
```
WriteTag( "demo:TagInternal3",
15,
function (er){});
```
Escrevendo no tag interno 3, o valor 15.

## WriteTagEx 
Escrita com timestamp e qualidade.

```
WriteTagEx( tagName, value , timestamp, quality, 
function (er) 
{});
```

Exemplo:
```
WriteTagEx("e3:Data.InternalTag1", 
2,
new Date().getTime(), 
0,
function (er){ });
```
