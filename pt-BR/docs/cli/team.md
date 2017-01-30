* * *

id: docs_cli_cache guide: docs_cli layout: guide

* * *

<p class="lead">Manter os membros da equipe</p>

##### `yarn team` [](#toc-yarn-team){#toc-yarn-team.toc}

Gerenciar equipes em organizações e alterar associações de equipe.

### Comandos [](#toc-commands){#toc-commands.toc}

##### `yarn team create <scope:team>` [](#toc-yarn-team-create){#toc-yarn-team-create.toc}

Cria uma nova equipe.

##### `yarn team destroy <scope:team>` [](#toc-yarn-team-destroy){#toc-yarn-team-destroy.toc}

Destrói uma equipe existente.

##### `yarn team add <scope:team> <user>` [](#toc-yarn-team-add){#toc-yarn-team-add.toc}

Adiciona um usuário a um grupo existente.

##### `yarn team rm <scope:team> <user>` [](#toc-yarn-team-rm){#toc-yarn-team-rm.toc}

Remove um usuário de uma equipe que ele pertence.

##### `yarn team ls <scope>|<scope:team>` [](#toc-yarn-team-ls){#toc-yarn-team-ls.toc}

Se executado em um nome de organização, retornará uma lista de equipes existentes sob essa organização. Se executado em uma equipe, em vez dele retornará uma lista de todos os usuários pertencentes a essa equipe.

### Detalhes [](#toc-details){#toc-details.toc}

equipe do Yarn sempre operam diretamente sobre o registro atual, configurável por linha de comando usando `..--registry = <url de registro>`.

Para criar equipes e gerenciar membros de equipe, você *deve ser um administrador de equipe* sob a organização. Listar equipes e membros da equipe pode ser feito por qualquer membro das organizações.

Criação de organização e gerenciamento de administradores de equipes e membros da organização é pelo website do npm, não pelo CLI.

Para usar equipes para gerenciar permissões em pacotes que pertencem a sua organização, use o comando de acesso do yarn para conceder ou revogar as permissões apropriadas.