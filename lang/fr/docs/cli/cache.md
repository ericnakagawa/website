* * *

id: docs_cli_cache guide: docs_cli layout: guide

* * *

##### `yarn cache ls` [](#toc-yarn-cache-ls){#toc-yarn-cache-ls.toc}

Yarn stocke chaque paquet dans un cache global dans votre répertoire utilisateur sur le système de fichiers. `yarn cache ls` affichera chaque paquet stockè en cache.

##### `yarn cache dir` [](#toc-yarn-cache-dir){#toc-yarn-cache-dir.toc}

En cours d’exécution `yarn cache dir` affichera le chemin d’accès où le cache global de Yarn est actuellement stocké.

##### `yarn cache clean` [](#toc-yarn-cache-clean){#toc-yarn-cache-clean.toc}

L’exécution de cette commande efface le cache local. Il sera restocké à nouveau la prochaine fois `yarn` ou `yarn install` est exécuté.

### Modifier le chemin d’accès du cache de Yarn [](#toc-change-the-cache-path-for-yarn){#toc-change-the-cache-path-for-yarn.toc}

Changez la valeur `cache-folder` pour configurer le répertoire de cache.

```sh
yarn config set cache-folder <path>
```

Vous pouvez également spécifier le répertoire de cache en spécifiant `--cache-dossier` :

```sh
yarn <command> --cache-folder <path>
```