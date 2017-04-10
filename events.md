[Índice](README.md#manual-elipse-mobile)

________________________________________

# Eventos

Os eventos do elipse mobile permitem que o usário defina uma condição para enviar um e-mail ou executar um script no servidor.

Os eventos podem ser usados, por exemplo, como alarmes ou para agendamento da criação de formulários.

## Condição
No campo condição o usário entra com uma expressão na qual ele acessa o valor dos tags através de "ValueOf".

Exemplos de condições:
```
	ValueOf("demo:TagInternal1") == 5
	ValueOf("demo:TagInternal2") != 3
	ValueOf("demo:TagInternal3") >= 50
```

*Obs: Os operadores lógicos possíveis são os mesmos utilizados em javascript.*

________________________________________

## Email

Quando a condição entrar no estado verdadeiro um e-mail será enviado. Coloque os usuários/grupos do sistema separados por ponto e virgula.

Para enviar um e-mal é preciso também fazer a configuração do servidor SMTP [configuração do servidor de email](config_app.md#servidor-de-e-mails).

[Voltar para o topo](events.md)

________________________________________

## Script

Quando a condição entrar no estado verdadeiro um script do usário será executado.
Para mais informações, consulte o capítulo [Referência de Scritps.](scripts.md)

[Voltar para o topo](events.md)
