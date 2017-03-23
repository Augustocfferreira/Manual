[Índice](README.md#manual-elipse-mobile)

# Eventos

Os eventos do Elipse Mobile possibilitam enviar emails e gerenciar ações para que decisões sejam tomadas pelo próprio servidor quando as condições dos eventos forem satisfeitas.

* Condição

Tanto para os emails como para os Scripts, é necessário configurar a condição para que o evento ocorra. Para montar esta condição, utiliza-se a função ValueOf, pois a mesma permite a utilização de operadores lógicos, tais como == (comparação), != (diferente de), >= (maior ou igual), < (menor), entre outros. 

Exemplos:
```
	=ValueOf("demo:TagInternal1") == 5
	=ValueOf("demo:TagInternal2") != 3
	=ValueOf("demo:TagInternal3") >= 50
```

*Obs: Os operadores lógicos possíveis são os mesmos utilizados em javascript.*

## Email

O mesmo permite enviar um ou mais emails para um usuário ou grupo de usuários quando a condição do evento ser satisfeita. Porém, primeiramente é necessário fazer a [configuração do servidor de email](config.md#servidor-de-e-mails), para depois ser possível configurar um evento de envio de emails. 

Após a configuração do servidor, basta configurar a condição de envio, selecionar para qual usuário será enviado (podendo selecionar um grupo para o envio coletivo)  e escrever o assunto e mensagem a ser enviada.

## Script

Permite que o servidor execute uma ou mais instruções ao validar a condição desejada.
	Após configurada a condição, já é possível escrever o script que será executado.

*Para mais informações, consulte o capítulo [Referência de Scritps.](scripts.md)*

[Voltar para o topo](events.md)
