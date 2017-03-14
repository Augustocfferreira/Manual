# Configurações

Na aba de configurações do Elipse Mobile é possível configurar o servidor LDAP para autenticação externa de usuários e a configuração de um servidor de emails SMTP.

## Autenticação externa de usuários

LDAP (Lightweight Directory Access Protoco) é um protocolo independente de fabricante que permite compartilhar informações sobre sistemas, usuários etc.

O Elipse Mobile pode usar um servidor LDAP para fazer a autenticação de usuários.
Caso este parâmetro esteja em branco, o elipse mobile tentar encontrar o servidor LDAP padrão.

Para isso vá em Configurações e informe o nome do servidor LDAP. O Active Directory da microsoft é um exemplo de serviço que aceita este protocolo.

![7a1090776d_690x421](https://cloud.githubusercontent.com/assets/26389485/23913081/9a91761a-08c0-11e7-86a8-ba2203d4424d.png)


## Servidor de e-mails

  Para que seja possível fazer o envio de emails pelo Elipse Mobile, se faz necessário configurar o servidor de emails, que é o servidor SMTP que gerenciará os emails enviados.
  Configure o servidor SMTP conforme o servidor utilizado para envio de emails.
  No exemplo abaixo, está a configuração utilizada no SMTP do Gmail.

![smtp_gmail](https://cloud.githubusercontent.com/assets/26389485/23870246/99d9a56a-0804-11e7-8396-f8da5003b032.png)

  Após esta configuração, já é possível configurar eventos de envio de email. Para mais informações [clique aqui.](events.md#email)
