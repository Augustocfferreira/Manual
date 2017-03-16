# Configurações

Na aba de configurações do Elipse Mobile é possível configurar o servidor LDAP para autenticação externa de usuários e a configuração de um servidor de emails SMTP.

## Autenticação externa de usuários

LDAP (Lightweight Directory Access Protoco) é um protocolo independente de fabricante que permite compartilhar informações sobre sistemas, usuários etc.

O Elipse Mobile pode usar um servidor LDAP para fazer a autenticação de usuários.
Caso este parâmetro esteja em branco, o elipse mobile tentar encontrar o servidor LDAP padrão.

Para isso vá em Configurações e informe o nome do servidor LDAP. O Active Directory da microsoft é um exemplo de serviço que aceita este protocolo.

![7a1090776d_690x421](https://cloud.githubusercontent.com/assets/26389485/23913081/9a91761a-08c0-11e7-86a8-ba2203d4424d.png)

### Como funciona a autenticação

Como os aparelhos celulares podem estar em uma rede separada, e existe uma grande variedade de sistemas incluindo a página web, a autenticação é sempre feita pelo servidor e não pelo cliente.

Isso significa que usuário e senha são passados pela internet do cliente até o server e o server verifica se o usuário existe.

Por este motivo, esta autenticação só é feita quando o cliente está conversando com o server no modo seguro (https).

A configuração de usuários, fica dentro do aplicativo em questão, que por sua vez fica na pasta Projects de dentro do diretório do Elipse Mobile Server. Nas configurações de usuário externos não é salva e nunca é informada a senha LDAP.

Para usuários internos do elipse Mobile é salvo o SHA1 usuário senha.

Por questões de segurança, recomendamos que o usuário administrador geral do sistema tenha uma senha complexa, de um tamanho razoável com letras e números. Este usuário não é autenticado via LDAP mas vai usar a conexão segura que criptografa todas as informações.
Este usuário também vai ter acesso direto ao computador, e pode optar por evitar conexões via internet.


## Servidor de e-mails

  Para que seja possível fazer o envio de emails pelo Elipse Mobile, se faz necessário configurar o servidor de emails, que é o servidor SMTP que gerenciará os emails enviados.
  Configure o servidor SMTP conforme o servidor utilizado para envio de emails.
  No exemplo abaixo, está a configuração utilizada no SMTP do Gmail.

![smtp_gmail](https://cloud.githubusercontent.com/assets/26389485/23870246/99d9a56a-0804-11e7-8396-f8da5003b032.png)

  Após esta configuração, já é possível configurar eventos de envio de email. Para mais informações [clique aqui.](events.md#email)

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
