[Índice](README.md#manual-elipse-mobile)

_________________________________________

# Configurações do Servidor

   - [Usuário Administrador do Sistema](config_server.md#usuário-administrador-do-sistema)
   - [HTTPs](config_server.md#https)
   - [Portas](config_server.md#portas)
   - [Versionamento](config_server.md#versionamento)
   - [Configuração de Firewall](config_server.md#configuração-de-firewall)

Ao lado do relógio do Windows, é possível verificar o ícone do Elipse Mobile Server. Para fazer qualquer tipo de configuração no mesmo, basta clicar com o botão direito e abrir a opção *Settings...*.
  
![1](https://cloud.githubusercontent.com/assets/26389485/23995614/3276a3b0-0a29-11e7-9e7d-0d3166075d6d.png)
  
![server](https://cloud.githubusercontent.com/assets/26389485/24042783/44fc5bd2-0af2-11e7-8b96-3165577f0531.png)
  
  As seguintes configurações estarão disponíveis:

## Usuário Administrador do Sistema

![adm](https://cloud.githubusercontent.com/assets/26389485/24041422/252be97c-0aec-11e7-9257-e774905669c3.png)

  No item System Administrator, é possível ver o usuário administrador do sistema e, caso necessário, é possível alterar o nome e/ou a senha do mesmo clicando em *Change...*.

_________________________________________

## HTTPS

![https](https://cloud.githubusercontent.com/assets/26389485/24041733/7e885a18-0aed-11e7-9e13-7566b0588783.png)

  No ítem HTTPS, é possível habilitar as conexões seguras e importar a chave e o certificado de segurança da conexão.
  
  * [Como gerar um certificado de teste para HTTPs?](http://kb.elipse.com.br/pt-br/questions/5441)
  
  [Voltar para o topo](config_server.md)

_________________________________________

## Portas

![ports](https://cloud.githubusercontent.com/assets/26389485/24041423/253f83ba-0aec-11e7-89f1-16751c4e3b34.png)

  As portas utilizadas pelo Elipse Mobile Server podem ser configuradas manualmente no ítem Ports. Por padrão, a configuração HTTP estará em 80 e a HTTPs em 443. Podendo ser alterado para qualquer outra porta disponível no Windows.
  
  [Voltar para o topo](config_server.md)

_________________________________________

## Versionamento

![sobre](https://cloud.githubusercontent.com/assets/26389485/24041421/2511f3f0-0aec-11e7-841c-d968735f8f74.png)

  Na aba *About* da configuração do Elipse Mobile Sever, é possível ver a versão em que se encontra o mesmo.
  
  [Voltar para o topo](config_server.md)

_________________________________________

## Configuração de Firewall

A configuração do Firewall é necessária para conectar o celular ou outro computador no servidor Elipse Mobile Server.
A partir da versão 1.1 do Elipse Mobile Server está disponível a configuração automática do Firewall do Windows.
Para que a regra seja criada, basta abrir a janela de configuração do Elipse Mobile Server e confirmar as configurações.
Ao clicar em OK, será verificada se existe a regra criada para o Elipse Mobile, caso ela não existir é mostrada a seguinte mensagem:

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

[Voltar para o topo](config_server.md)
