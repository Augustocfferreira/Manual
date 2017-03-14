# Referência de Scripts

* [WriteTag](##WriteTag)
* [WriteTagEx](##WriteTagEx)

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
