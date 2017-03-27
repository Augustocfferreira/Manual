[Índice](README.md#manual-elipse-mobile)

_________________________________________

# Notas de Versão

- [Versão 1.4](releasenotes.md#versão-14)
- [Versão 1.3](releasenotes.md#versão-13)
- [Versão 1.2](releasenotes.md#versão-12)
- [Versão 1.1](releasenotes.md#versão-11)

_________________________________________

## Versão 1.4
- Nova conexão de dados com [EPM via OPC-UA](connections.md#epm-opca-ua);
- Possibilidade de criar [grupos de usuários](users.md#grupo);
- [Conexão nativa com E3](connections.md#e3-nativo) atualizada;
- Eventos de [script no servidor](events.md#script);
- Novo tipo de conexão: [Forms](connections.md#form);
- Possibilidade de configuração de [permissões de usuários por tela](pages.md#páginas);
- Atualizações de segurança;
- Correções;

_________________________________________

## Versão 1.3

- Novo design: agora cada controle está com características individuais de acordo com seu tipo;
- Suporte a expressões nos campos: é possível escrever expressões que também suportam valores de tags em diversos campos de edição dos controles, tornando-os dinâmicos;
- Novo controle Commands: um controle que permite criar uma lista dinâmica de opções;
- Edição no cliente: é possível editar as aplicações através dos aplicativos dos dispositivos móveis.
- A conexão arduino remota, só está disponível no servidor online.

[Voltar para o topo](releasenotes.md)

_________________________________________

## Versão 1.2

Geral

- Leitura em blocos no client web. mais detalhes...
- Controles nos aplicativos cliente agora têm fundo preenchido
- Os clients também têm versão Francês e Chinês (Tradicional), além do Inglês e Português.
- A web ganhou versão traduzida que escolhe o idioma através das configurações do browser.
- Corrigido problema com HTTPs observado em testes de stress.
- Pequena alteração no licenciamento. Agora é possível criar/editar mais usuários do que número licenciado. Só não é possível fazer login.
- O servidor ganhou atualizações e otimizações para rodar na nuvem
- Corrigido: Campos do tipo read-only estavam podendo ser editados no configurador
- Alterado o formato do arquivo de dados e configuração que agora é json. A importação é automática.
- Adicionada proteção no server contra ataques do tipo cross-site request forgery. mais detalhes...
- Criada uma opção no servidor para desabilitar conexões SSL3 e permitir apenas conexões TLS.
- Corrigido problema para enviar e-mails para mais de um usuário.

Client Windows

- Corrigido problema de formatação quando decimals era negativo
- Corrigido problema que duplicava a string de useragent

Client Android

- Substituída a forma como era feito a conexão para corrigir problemas com certificados HTTPS
- Separados os menus Sobre e Configurações
- Alterado tela de login para ficar mais uniforme com outros clientes

[Voltar para o topo](releasenotes.md)

_________________________________________

## Versão 1.1

**Novidades:**

- Novo controle PageLink que permite que ele mostre um valor e também seja usado para navegação para outra tela. Geralmente este controle apresenta um resumo , uma totalização e a tela apresenta os detalhes.

- Criada opção para pedir opcionalmente uma confirmação de comando no pulser e toggle.

- Envio de e-mail baseada em uma condição. Agora é possível configurar uma condição baseada em um tag e quando a condição for verdadeira é enviado um e-mail para um ou mais usuários.

- Agora um utilitário da openssl é enviado junto da instalação para geração de certificados.

- Atualização da openssl para 1.0.1k de 8 Jan 2015

- Agora os administradores podem ser marcados como read-only.

**Bugs e correções**

- Melhorias de performance no server e clientes.

- Outros pequenos bugs corrigidos no editor.

- Corrido problema no login LDAP via HTTPs

[Voltar para o topo](releasenotes.md)
