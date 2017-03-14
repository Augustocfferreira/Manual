# Usuários

Dentro da página de usuários, é possível gerenciar todos os usuários da aplicação. Podendo 

## Criação de usuários

### Mobile

  O usuário Mobile é o usuário que é gerenciado pelo Elipse Mobile Server. Ao adicionar um usuário deste tipo, o usuário será exclusivamente do Elipse Mobile.

### LDAP

  O usuário LDAP é aquele que é gerenciado pelo servidor LDAP, servidor este que deve ser previamente configurado na aba **[Configurações](config.md#autenticação-externa-de-usuários)**.

### Grupo

  Ao adicionarmos um grupo, podemos adicionar políticas de segurança nos mesmos para que os usuários deste grupo.
  
### Dispositivo Único

Quando a opção unique device é marcada na criação do usuário, significa que ele só poderá acessar o Elipse Mobile através de um mesmo aparelho de celular.

O primeiro login deste usuário vai determinar o dispositivo que ele poderá usar.

![dispositivo](https://cloud.githubusercontent.com/assets/26389485/23913395/a668de50-08c1-11e7-81fc-b273cd815a9d.png)

Ele também não poderá usar o Elipse Mobile através de um web browser.

Caso seja feito login no browser ou outro celular vai aparecer o seguinte erro:
"This device is not registed for this user."
