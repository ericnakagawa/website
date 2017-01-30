* * *

id: docs_cli_owner guide: docs_cli layout: guide

* * *

<p class="lead">Gerencia os donos de um pacote.</p>

### O que é um dono de pacote? [](#toc-what-is-a-package-owner){#toc-what-is-a-package-owner.toc}

Um "dono de pacote" no registro é um usuário que tem acesso para fazer alterações no pacote. Um único pacote pode ter quantos donos você quiser.

Os donos têm permissão para executar as seguintes tarefas:

  1. Publicar novas versões do pacote
  2. Adicionar ou remover outros donos do pacote
  3. Muda meta-dados do pacote

### Ressalvas [](#toc-caveats){#toc-caveats.toc}

Não há outros níveis de acesso no momento. Os usuários podem modificar o pacote ou não podem. No futuro pode haver mais tipos de funções, mas não há no momento.

### Comandos [](#toc-commands){#toc-commands.toc}

##### `yarn owner ls <pacote>` [](#toc-yarn-owner-ls){#toc-yarn-owner-ls.toc}

Lista todos os donos de um `<pacote>`.

##### `yarn owner add <usuário> <pacote>` [](#toc-yarn-owner-add){#toc-yarn-owner-add.toc}

Adiciona o `<usuário>` como dono de um `<pacote>`. Você deve ser um dos donos do `<pacote>` para poder executar este comando.

##### `yarn owner rm <usuário> <pacote>` [](#toc-yarn-owner-rm){#toc-yarn-owner-rm.toc}

Remove o `<usuário>` da lista de donos do `<pacote>`. Você deve ser um dos donos do `<pacote>` para executar este comando.