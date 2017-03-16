# Configurações do Servidor

## Configurações de porta e Conexões seguras

N

## Configuração de Firewall

  A configuração do Firewall é necessária para conectar o celular ou outro computador no servidor Elipse Mobile Server.
  A partir da versão 1.1 do Elipse Mobile Server está disponível a configuração automática do Firewall do Windows.
  Para isto, clique com o botão direito do mouse no ícone do Elipse Mobile Server na área de notificações do Windows e selecione a opção Settings.
  
  ![1](https://cloud.githubusercontent.com/assets/26389485/23995614/3276a3b0-0a29-11e7-9e7d-0d3166075d6d.png)
  
  O Elipse Mobile Server utiliza uma porta para o protocolo HTTP e outra para o protocolo HTTPS.
O padrão da web é 80 para HTTP e 443 para HTTPS.

![2](https://cloud.githubusercontent.com/assets/26389485/23995618/33073ce0-0a29-11e7-8af1-d2ecba334448.png)

Ao clicar em OK será verificada se existe a regra criada para o Elipse Mobile, caso ela não existir é mostrada a seguinte mensagem:

![3](https://cloud.githubusercontent.com/assets/26389485/23995615/32b23448-0a29-11e7-94f1-4d9670701dde.png)

Clique em Yes para criar a regra.

![4](https://cloud.githubusercontent.com/assets/26389485/23995616/32e2c608-0a29-11e7-96e4-4d8afd92171f.png)

Pronto, a regra já está criada e contém as portas usadas pelo servidor.
Para visualizar o efeito desta configuração, abra o Firewall do Windows.

![5](https://cloud.githubusercontent.com/assets/26389485/23995619/33132cd0-0a29-11e7-8bd1-b98a9f3edab8.png)

Clique em Advanced Settings.

![6](https://cloud.githubusercontent.com/assets/26389485/23995617/32fa3d06-0a29-11e7-8f20-6052b0152cca.png)

Clique em Inbound Rules.

![7](https://cloud.githubusercontent.com/assets/26389485/23995620/333cae3e-0a29-11e7-9b00-84139df331f2.png)

Nesta lista aparece a regra Elipse Mobile Server que contém a configuração de portas.
