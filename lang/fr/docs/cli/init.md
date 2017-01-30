* * *

id: docs_cli_init guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Interactivement créer ou mettre à jour un fichier package.json.</p>

##### `yarn init` [](#toc-yarn-init){#toc-yarn-init.toc}

Cette commande vous guide à travers une session interactive pour créer un fichier `package.json`. Des valeurs par défaut telles que la licence et la version initiale se trouvent dans les paramètres de configuration `init-*` de Yarn.

Voici un exemple d’exécution de la commande à l’intérieur d’un répertoire nommé `testdir` :

```sh
$ yarn init
```

```sh
question name (testdir): mon-paquet-genial
question version (1.0.0): 
question description: Le meilleur paquet possible.
question entry point (index.js): 
question git repository: https://github.com/yarnpkg/example-yarn-package
question author: Un contributeur de Yarn
question license (MIT): 
success Saved package.json
✨  Done in 87.70s.
```

Il en résulte le suivant `package.json` :

```json
Text for Translation
{
  "name": "mon-paquet-genial",
  "version": "1.0.0",
  "description": "Le meilleur paquet possible.",
  "main": "index.js",
  "repository": {
    "url": "https://github.com/yarnpkg/example-yarn-package",
    "type": "git"
  },
  "author": "Un contributeur de Yarn",
  "license": "MIT"
}
```

Si vous avez déjà un fichier `package.json` existant, il utilisera alors les entrées du fichier comme valeurs par défaut.

Le `package.json` ci-dessous:

```json
{
  "name": "my-existing-package",
  "version": "0.1",
  "description": "I exist therefore I am.",
  "repository": {
    "url": "https://github.com/yarnpkg/example-yarn-package",
    "type": "git"
  },
  "license": "BSD-2-Clause"
}
```

Résulte dans les valeurs par défaut suivantes au cours de la session interactive :

```sh
$ yarn init
```

```sh
question name (my-existing-package): 
question version (0.1): 
question description (I exist therefore I am.):
question entry point (index.js): 
question git repository (https://github.com/yarnpkg/example-yarn-package): 
question author: Yarn Contributor
question license (BSD-2-Clause): 
success Saved package.json
✨  Done in 121.53s.
```

##### Définition de valeurs par défaut pour `yarn init` [](#toc-setting-defaults-for-yarn-init){#toc-setting-defaults-for-yarn-init.toc}

Les variables de [config]({{url_base}}/docs/cli/config) suivantes peuvent servir à personnaliser les paramètres par défaut de `yarn init` :

- `init-author-name`
- `init-author-email`
- `init-author-url`
- `init-version`
- `init-license`

##### `yarn init --yes/-y` [](#toc-yarn-init-yes-y){#toc-yarn-init-yes-y.toc}

Cette commande contourne la session interactive mentionnée ci-dessus et génère un `package.json` basé sur vos valeurs par défaut. Certains paramètres par défaut peuvent être modifiées en changeant les paramètres config `init-*` comme mentionné ci-dessus. Par exemple, avec une nouvelle installation Yarn et à l’intérieur d’un répertoire nommé `yarn-exemple` :

```sh
$ yarn init --yes
```

    warning The yes flag has been set. This will automatically answer yes to all questions which may have security implications.
    success Saved package.json
    ✨  Done in 0.09s.
    

Qui produit le suivant `package.json` :

```json
{
  "name": "yarn-example",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT"
}
```