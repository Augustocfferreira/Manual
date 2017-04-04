[Índice](README.md#manual-elipse-mobile)

________________________________________

# Eventos

Os eventos do Elipse Mobile possibilitam enviar emails e gerenciar ações para que decisões sejam tomadas pelo próprio servidor quando as condições dos eventos forem satisfeitas.

* Condição

Tanto para os emails como para os Scripts, é necessário configurar a condição para que o evento ocorra. Para montar esta condição, utiliza-se a função ValueOf, pois a mesma permite a utilização de operadores lógicos, tais como == (comparação), != (diferente de), >= (maior ou igual), < (menor), entre outros. 

Exemplos:
```
	ValueOf("demo:TagInternal1") == 5
	ValueOf("demo:TagInternal2") != 3
	ValueOf("demo:TagInternal3") >= 50
```

Existe também, a possibilidade de utilizar estas condições para condicionar outros campos, como Subtítulo, Cor e Imagem. Para isto, adicione o símbolo de igual "=" antes do ValueOf. Veja um exemplo:

'''
=ValueOf(demo:TagInternal1) < 15 ? "#0072B8" : "#117D10"
'''

![cor_var](https://cloud.githubusercontent.com/assets/26389485/24657913/79ff0bce-191e-11e7-8578-4212120a2587.png)

*Veja mais exemplos no [artigo](https://forum.elipse.com.br/t/expressoes-no-elipse-mobile/823).*

*Obs: Os operadores lógicos possíveis são os mesmos utilizados em javascript.*

________________________________________

## Email

O mesmo permite enviar um ou mais emails para um usuário ou grupo de usuários quando a condição do evento ser satisfeita. Porém, primeiramente é necessário fazer a [configuração do servidor de email](config_app.md#servidor-de-e-mails), para depois ser possível configurar um evento de envio de emails. 

Após a configuração do servidor, basta configurar a condição de envio, selecionar para qual usuário será enviado (podendo selecionar um grupo para o envio coletivo)  e preencher os campos de assunto e mensagem a ser enviada.

________________________________________

## Script

Permite que o servidor execute uma ou mais instruções ao validar a condição desejada.
	Após configurada a condição, já é possível escrever o script que será executado.

*Para mais informações, consulte o capítulo [Referência de Scritps.](scripts.md)*

[Voltar para o topo](events.md)
