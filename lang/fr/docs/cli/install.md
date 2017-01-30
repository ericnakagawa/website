* * *

id: docs_cli_install guide: docs_cli layout: guide

* * *

{% include vars.html %}

`yarn install` est utilisé pour installer toutes les dépendances d’un projet. C’est le plus couramment utilisé lorsque vous venez juste d'extraire le code d’un projet, ou lorsqu’un autre développeur du projet a ajouté une nouvelle dépendance que vous devez installer.

Si vous êtes habitué à l’utilisation de npm vous vous attendez peut-être a utiliser `--save` ou `--save-dev`. Celles-ci ont été remplacées par `yarn add` et `yarn add --dev` ou <0>yarn add -D</0>. Pour plus d’informations, consultez [la documentation de `yarn add`]({{url_base}}/docs/cli/add).

Exécutant `yarn` avec aucune commande exécutera `yarn install`, en passant par tous les indicateurs fournis.

##### `yarn install` [](#toc-yarn-install){#toc-yarn-install.toc}

Installer toutes les dépendances figurant au sein du `package.json` dans le dossier `node_modules` local.

##### `yarn install --flat` [](#toc-yarn-install-flat){#toc-yarn-install-flat.toc}

Permettre seulement une seule version d’un paquet. Dans la première exécution cela vous invite à choisir une version unique pour chaque paquet duquel plusieurs plages de version sont requises. Celles-ci s’ajouteront à votre `package.json` sous un champ nommé `resolutions`.

```json
"resolutions": {
  "package-a": "2.0.0",
  "package-b": "5.0.0",
  "package-c": "1.5.2"
}
```

##### `yarn install --force` [](#toc-yarn-install-force){#toc-yarn-install-force.toc}

Cela ré-extrait tous les paquets, même ceux qui ont été précédemment installés.

##### `yarn install --har` [](#toc-yarn-install-har){#toc-yarn-install-har.toc}

Produit des [Archives HTTP](https://en.wikipedia.org/wiki/.har) de toutes les demandes de réseau effectuées lors de l’installation. Les fichiers HAR sont couramment utilisées pour enquêter sur les performances du réseau et peuvent être analysées avec des outils tels que [Google HAR Analyzer](https://toolbox.googleapps.com/apps/har_analyzer/) ou [HAR Viewer](http://www.softwareishard.com/blog/har-viewer/).

##### `yarn install --no-lockfile` [](#toc-yarn-install-no-lockfile){#toc-yarn-install-no-lockfile.toc}

Ne pas lire ou générer un fichier de verrouillage `yarn.lock`.

##### `yarn install --production` [](#toc-yarn-install-production){#toc-yarn-install-production.toc}

À l’aide du champ `--production`, ou lorsque la variable d’environnement `NODE_ENV` est fixée a `production`, Yarn n’installera aucun paquet répertorié dans `devDependencies`.

> **Remarque :** `--prod` est également un alias de `--production`.

##### `yarn install --pure-lockfile` [](#toc-yarn-install-pure-lockfile){#toc-yarn-install-pure-lockfile.toc}

Ne pas générer un nouveau fichier de verrouillage `yarn.lock`.