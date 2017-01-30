* * *

id: docs_cli_outdated guide: docs_cli layout: guide

* * *

<p class="lead">Trouve les dépendances obsolètes du paquet.</p>

##### `yarn outdated` [](#toc-yarn-outdated){#toc-yarn-outdated.toc}

Répertorie les informations de version pour toutes les dépendances du paquet. Ces informations incluent la version actuellement installée, la version désirée basée sur semver et la dernière version disponible.

Par exemple, disons que `package.json` a les dépendances suivantes répertoriées :

```js
"dependencies": {
  "lodash": "4.15.0",
  "underscore": "~1.6.0"
}
```

La commande à exécuter doit ressembler à ceci :

```sh
yarn outdated
```

    Package    Current Wanted Latest
    lodash     4.15.0  4.15.0 4.16.4
    underscore 1.6.0   1.6.0  1.8.3 
    ✨  Done in 0.72s.
    

##### `yarn outdated [package...]` [](#toc-yarn-outdated-package){#toc-yarn-outdated-package.toc}

Répertorie les informations de version pour une ou plusieurs dépendances du package.

Pour l' exemple du `package.json` montré précédemment, vous devriez voir la sortie suivante lors de la vérification d'une des dépendances :

```sh
yarn outdated lodash
```

    Package Current Wanted Latest
    lodash  4.15.0  4.15.0 4.16.4
    ✨  Done in 1.04s.