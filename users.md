# Usuários

Dentro da página de usuários, é possível gerenciar todos os usuários da aplicação. Podendo 

## Criação de usuários

### Mobile

  O usuário Mobile é o usuário que é gerenciado pelo Elipse Mobile Server. Ao adicionar um usuário deste tipo, o usuário será exclusivamente do Elipse Mobile.

### LDAP

  O usuário LDAP é aquele que é gerenciado pelo servidor LDAP, servidor este que deve ser previamente configurado na aba **[Configurações](config.md#autenticação-externa-de-usuários)**.

### Grupo

  Ao adicionarmos um grupo, podemos adicionar políticas de segurança nos mesmos para que os usuários deste grupo.
  
![dispositivo](https://cloud.githubusercontent.com/assets/26389485/23913395/a668de50-08c1-11e7-81fc-b273cd815a9d.png)

| Propriedade    | Função  |
| -------------   | ------------- |
| Nome do usuário    | Nome utilizado no ato do login |
| Nome completo    | Nome completo do usuário |
| Email    | Email do usuário |
| Grupos  | Grupo(s) ao qual o usuário pertence |
| Senha  | Senha a ser cadastrada par o usuário |
| Repetir senha  | Senha a ser cadastrada par o usuário |
| Administrador  | Propriedade que determia se o usuário é Administrador do sistema|
| Acesso de escrita  | Propriedade que determina se o sitema permite ou não ao usuário escrever valores |
| Dispositivo único  | Quando a opção Dispositivo único é marcada na criação do usuário, significa que ele só poderá acessar o Elipse Mobile através de um mesmo aparelho de celular. O primeiro login deste usuário vai determinar o dispositivo que ele poderá usar. Caso seja feito login no browser ou outro celular vai aparecer o seguinte erro: "This device is not registed for this user." |

