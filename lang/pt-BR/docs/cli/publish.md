* * *

id: docs_cli_publish guide: docs_cli layout: guide

* * *

<p class="lead">Publica um pacote para o registro npm.</p>

Quando um pacote é publicado você não pode alterar aquela versão em específico, então tome cuidado antes de publicar.

##### `yarn publish` [](#toc-yarn-publish){#toc-yarn-publish.toc}

Publica o pacote definido no `package.json` da pasta atual.

##### `yarn publish [tarball]` [](#toc-yarn-publish-tarball){#toc-yarn-publish-tarball.toc}

Publica o pacote definido por uma "gzipped tarball" `.tgz`.

##### `yarn publish [folder]` [](#toc-yarn-publish-folder){#toc-yarn-publish-folder.toc}

Publica o pacote contido numa pasta definida. O arquivo `<pasta>/package.json` deve especificar os detalhes do pacote.

##### `yarn publish --tag <versão>` [](#toc-yarn-publish-tag){#toc-yarn-publish-tag.toc}

Se definido uma versão para o `yarn publish` ele publicará o pacote na versão especificada. Por exemplo, se você executar `yarn publish --tag beta` e seu pacote é chamado `blorp`, então alguém pode instalar este pacote com o comando `yarn add blorp@beta`.

##### `yarn publish --access <public|restricted>` [](#toc-yarn-publish-access){#toc-yarn-publish-access.toc}

A "flag" `--access` controla se o registro npm publica este pacote como um pacote público ou restrito.