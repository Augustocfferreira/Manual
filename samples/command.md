[Índice](connections.md)

________________________________________

# Exemplo Command

Para a construção do controle *Temperature Control* na pasta *Monitoring* da aplicação Demo, iniciaremos adicionando um controle *Command* na tela.

![1-controle](https://cloud.githubusercontent.com/assets/26389485/24566287/4ed0ee32-162f-11e7-9116-131015fe2a34.png)

Após isto, configuraremos os tags de leitura e escrita. O tag de leitura é o tag monitorado pela sessão Zonas para mostrar para o usuário o valor corrente. Já o tag escrita, é o tag que receberá o valor selecionado nos Comandos.

![2 - leitura escrita](https://cloud.githubusercontent.com/assets/26389485/24566290/4edee29e-162f-11e7-997d-28a2211288e3.png)

[Voltar para o topo](command.md)

_______________________________________

## ZONAS

Com os tags configurados, é possível configurar as Zonas e os comandos.

Nas Zonas, temos que criar uma zona para qualquer valor possível do tag leitura.
Primeiramente, iremos configurar a zona *Cold*, que é responsável por informar que a temperatura está abaixo de 10 graus.

Logo, a propriedade Texto foi configurada como *Cold* e a condição para  mesma exibir, será **value < 10**.
Com esta condição, o texto só irá aparecer quando o valor do tag leitura for menor que 10.

![3 - cold](https://cloud.githubusercontent.com/assets/26389485/24566288/4ed5cfc4-162f-11e7-9626-9ad762961b6a.png)

Agora a condição que configuraremos é o *Hot*, que aparece quando o a temperatura está acima de 23 graus. Logo, o texto será configurado como *Hot* e a condição será **value > 23**.

![4 - hot](https://cloud.githubusercontent.com/assets/26389485/24566289/4eda9ab8-162f-11e7-8f29-98ccc2ab9e53.png)

Por fim, a última zona que será configurada, será o intervalo entre 10 e 23 graus. Logo, configuraremos o texto como *Cool* e a condição **value <= 23 && value >= 10**.

![5 - cool](https://cloud.githubusercontent.com/assets/26389485/24566284/4e7abf30-162f-11e7-840d-ee0f946c7e31.png)

[Voltar para o topo](command.md)

_______________________________________

## COMANDOS

Com a configuração das zonas feita, é possível configurar as ações possíveis em cada caso. Para isto, configuraremos os comandos *Exhaustion* para diminuir e *Warm* para aumentarmos a temperatura.

Na criação do comando *Exhaustion*, preencheremos o seu texto, a condição para exibir será quando a temperatura for maior que 23 graus, ou seja, **value > 23** e o valor para escrita será 1. Desta forma, quando acionarmos o comando, será escrito o valor 1 (true) no TagInternal7, que é responsável pela exaustão.

![6 - exhaustion](https://cloud.githubusercontent.com/assets/26389485/24566285/4e9d5bbc-162f-11e7-94de-d8f3e73cf251.png)

Já no comando *Warm*, o comportamento tem que ser o contrário, escrevendo 0 (false) no TagInternal7. Desta forma a exaustão será desligada.

![7 - warm](https://cloud.githubusercontent.com/assets/26389485/24566286/4ec13a78-162f-11e7-904c-93d0550a0966.png)

Feito isto, nosso objeto Command está pronto para monitorar o tag de leitura e pronto para fazer a escrita caso entre nas condições configuradas.

[Voltar para o topo](command.md)