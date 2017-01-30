* * *

id: docs_cli_publish guide: docs_cli layout: guide

* * *

<p class="lead">Publie un paquet dans le registre npm.</p>

Une fois qu’un package est publié, vous ne pouvez plus jamais modifier cette version spécifique, alors faites attention avant du publier.

##### `yarn publish` [](#toc-yarn-publish){#toc-yarn-publish.toc}

Publie le package défini par le `package.json` dans le répertoire courant.

##### `yarn publish [tarball]` [](#toc-yarn-publish-tarball){#toc-yarn-publish-tarball.toc}

Publie le package défini par une archive tar gzippé `.tgz`.

##### `yarn publish [folder]` [](#toc-yarn-publish-folder){#toc-yarn-publish-folder.toc}

Publie le package contenu dans le dossier spécifié. `< dossier >/package.json` devrait préciser les détails du package.

##### `yarn publish --tag <tag>` [](#toc-yarn-publish-tag){#toc-yarn-publish-tag.toc}

Fourni une tag a `yarn publish` qui vous permet de publier des packages avec une tag spécifique. Par exemple, si vous éxécutez `yarn publish --tag beta`, et votre paquet est nommé `blorp`, quelqu'un d’autre peut installer ce paquet avec `yarn add blorp@beta`.

##### `yarn publish --access <public|restricted>` [](#toc-yarn-publish-access){#toc-yarn-publish-access.toc}

L'option `--access` contrôle si le registre de la npm publie ce paquet comme un paquet public ou privé.