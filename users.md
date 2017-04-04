[Índice](README.md#manual-elipse-mobile)

______________________________________________

# Usuários

Dentro da página de usuários, é possível gerenciar os usuários da aplicação. Os mesmos podem ser do tipo [Mobile](users.md#mobile-autenticação-interna), com autenticação interna, ou [LDAP](users.html#ldap-autenticação-externa), com autenticação externa. Para a organização e configuração de permissões, pode-se utilizar os [Grupos](users.md#grupo).

__________________________________________________

## Usuário Administrador do Sistema

Usuário este que é configurado no primeiro acesso ao sistema, o mesmo permite criar, parar/rodar e apagar as aplicações do sistema. Para mais informações, [clique aqui](applications.md).

Para alterar o usuário ou a senha do administrador do sistema, veja o capítulo [Configuração do Servidor](config_server.md#usuário-administrador-do-sistema).

__________________________________________________

## Criação de usuários

  - [Mobile](users.md#mobile-autenticação-interna)
  - [LDAP](users.md#ldap-autenticação-externa)
  - [Grupo](users.md#grupo)
  
__________________________________________________

### Mobile (Autenticação Interna)

![mobile_user](https://cloud.githubusercontent.com/assets/26389485/24060966/4d7be038-0b34-11e7-96a5-a4feecfb36ff.png)

O usuário Mobile é o usuário que é autenticado pelo Elipse Mobile Server.
  
![dispositivo](https://cloud.githubusercontent.com/assets/26389485/23913395/a668de50-08c1-11e7-81fc-b273cd815a9d.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome do usuário    | Nome utilizado no ato do login |
| Nome completo    | Nome completo do usuário |
| Email    | Email do usuário |
| Grupos  | Grupo(s) ao qual o usuário pertence |
| Senha  | Senha a ser cadastrada par o usuário |
| Repetir senha  | Senha a ser cadastrada par o usuário |

[Voltar para o topo](users.md)

__________________________________________________

### LDAP (Autenticação Externa)

![ldap_user](https://cloud.githubusercontent.com/assets/26389485/24060967/4d8f3fa2-0b34-11e7-8707-601f228da09b.png)

O usuário LDAP é um usário autenticado por um servidor externo de acordo com o protocolo LDAP.

Para configurar o servidor LDAP externo, vá no menu **[Configurações](config_app.md#autenticação-externa-de-usuários)**.

Utilitário para windows - Active Directory Explorer v1.44
https://technet.microsoft.com/en-us/sysinternals/adexplorer.aspx

[Voltar para o topo](users.md)

__________________________________________________

### Grupo

![group](https://cloud.githubusercontent.com/assets/26389485/24060964/4d59dd8a-0b34-11e7-9072-d463a1269367.png)

O objeto grupo define permissões que são herdadas por todos os usuários que pertencencem a este grupo.

[Voltar para o topo](users.md)

__________________________________________________

## Permissões

| Propriedade    | Função  |
| -------------   | ------------- |
| Administrador  | O usuário administrador é aquele que pode alterar o aplicativo, criar telas etc|
| Acesso de escrita  | Se o usário não é administrador, ele pode ter um acesso somente leitura de tags ou leitura e escrita se esta opção estiver marcada|
| Dispositivo único  | Quando a opção Dispositivo único é marcada na criação do usuário, significa que ele só poderá acessar o Elipse Mobile através de um mesmo aparelho de celular. O primeiro login deste usuário vai determinar o dispositivo que ele poderá usar. Caso seja feito login no browser ou outro celular vai aparecer o seguinte erro: "This device is not registed for this user."|

[Voltar para o topo](users.md)

__________________________________________________

## Permissões herdadas
Quando um usário pertence a um grupo, as características positivas são herdadas para o usuário pertencente aquele grupo.

[Voltar para o topo](users.md)
