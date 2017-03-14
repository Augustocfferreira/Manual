# Eventos

Os eventos do Elipse Mobile possibilitam enviar emails e gerenciar ações para que decisões sejam tomadas pelo próprio servidor quando as condições dos eventos forem satisfeitas.
Tanto para os emails como para os Scripts, é necessário configurar a condição para que o evento ocorra. Para montar esta condição, utiliza-se a função ValueOf, pois a mesma permite a utilização de operadores lógicos, tais como == (comparação), != (diferente de), >= (maior ou igual), < (menor), entre outros. 

Exemplos:
```
	=ValueOf("demo:TagInternal1") == 5
	=ValueOf("demo:TagInternal2") != 3
	=ValueOf("demo:TagInternal3") >= 50
```

*Obs: Os operadores lógicos possíveis são os mesmos utilizados em javascript.*

## Email:

Após isto, já é possível configurar um evento de envio de emails. O mesmo permite enviar um ou mais emails para um usuário ou grupo de usuários quando a do evento condição ser verdadeira.

## Script:

Permite que o servidor execute uma ou mais instruções ao validar a condição desejada.
	Após configurada a condição, já é possível escrever o script que será executado. Os comandos possíveis e os parâmetros são:

* [WriteTag](###WriteTag)
* [WriteTagEx](###WriteTagEx)

### WriteTag 
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

### WriteTagEx 
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
