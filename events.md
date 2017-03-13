#Eventos

Os eventos do Elipse Mobile possibilitam enviar emails e gerenciar scripts que rodam no servidor para que ações sejam tomadas pelo próprio servidor quando as condições dos eventos forem satisfeitas.
Em ambos os eventos, é necessário configurar a condição em que o mesmo ocorra. Para montar uma condição, utiliza-se a função ValueOf e a mesma permite a utilização de operadores lógicos, tais como == (comparação), != (diferente de), >= (maior ou igual), < (menor), entre outros. 

Exemplos:
```
	=ValueOf("demo:TagInternal1") == 5
	=ValueOf("demo:TagInternal2") != 3
	=ValueOf("demo:TagInternal3") >= 50
```

*Obs: Os operadores lógicos e matemáticos possíveis são os mesmos utilizados em javascript.*

##Email:

Antes de configurar os eventos de envio de email, é necessário configurar o Servidor de emails, que é o servidor SMTP que gerenciará os emails enviados pelos eventos.
Primeiramente, acesse a aba **Configurações** e abra o **Servidor de e-mails**.

Configure o servidor SMTP conforme o servidor utilizado para envio de emails.
No exemplo abaixo, está a configuração utilizada no SMTP do Gmail.

![smtp_gmail](https://cloud.githubusercontent.com/assets/26389485/23870246/99d9a56a-0804-11e7-8396-f8da5003b032.png)

Permite configurar um evento que envia email para um usuário ou grupo de usuários quando a condição seja verdadeira.
Obs: Para que o email seja enviado com sucesso, é necessário configurar sevidor de e-mails na janela de Configurações.

##Script:

Permite que o servidor execute uma ou mais instruções ao validar a condição desejada.
	Após configurada a condição, já é possível escrever o script que será executado. Os comandos possíveis e os parâmetros são:

* [WriteTag](###WriteTag)
* [WriteTagEx](###WriteTagEx)

###WriteTag 
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

###WriteTagEx 
Escrita com timestamp e qualidade.

```
WriteTagEx( tagName, value , timestamp, quality, 
function (er) 
{});
```




