* * *

id: docs_cli_add guide: docs_cli layout: guide description: docs_cli_add_description additional_reading_tags: ["dependencies"]

* * *

{% include vars.html %}

<p class="lead">Installe un package ainsi que tous les packages dont il dépend.</p>

### Ajout des dépendances [](#toc-adding-dependencies){#toc-adding-dependencies.toc}

Lorsque vous souhaitez utiliser un autre package, vous devez d’abord l'ajouter à vos dépendances. Cela se traduit par l'exécution de `yarn add [package-name]` pour l'installer dans votre projet.

Cela mettra également à jour votre `package.json` et votre `yarn.lock` afin que les autres développeurs qui travaillent sur le projet puissent avoir les mêmes dépendances que vous lorsqu’ils exécutent `yarn` ou `yarn install`.

La plupart des paquets seront installés dans le [registre npm](https://www.npmjs.com/) et dénommés simplement par leur nom de paquet. Par exemple, `yarn add react` installera le paquet de [`react`](https://www.npmjs.com/package/react) du registre npm.

Vous pouvez spécifier les versions en utilisant une des commandes ci-dessous:

  1. `yarn add package-name` installe la « dernière » version du paquet.
  2. `yarn add package-name@1.2.3` installe une version particulière d’un paquet du registre.
  3. `yarn add package-name@tag` installe un [« tag »]({{url_base}}/docs/cli/tag) spécifique (`beta`, `next` ou `latest`).

En général, un paquet est tout simplement un dossier avec code et un fichier `package.json` qui décrit le contenu. Vous pouvez faire référence à un paquet de différentes manières :

Vous pouvez également spécifier des paquets de différents endroits :

  1. `yarn add package-name` installe le paquet du [registre npm](https://www.npmjs.com/) à moins que vous ayez spécifié un autre dans votre `package.json`.
  2. `yarn add file:/path/to/local/folder` installe un paquet qui est sur votre système de fichiers local. Ceci est utile pour tester vos autres paquets qui n’ont pas été publiés au registre.
  3. `yarn add file:/path/to/local/tarball.tgz` installe un package d’une archive tar qui pourrait être utilisé pour partager un paquet avant de publier.
  4. `yarn add <git remote url>` installe un paquet d'un dépôt git.
  5. `yarn add <git remote url>#<commit/tag>` installe un paquet d'un dépôt git distant a une git commit ou git tag spécifique .
  6. `yarn add https://my-project.org/package.tgz` installe un paquet d’une archive tar gzippée distante.

### Mises en garde [](#toc-caveats){#toc-caveats.toc}

Si vous avez utilisé un gestionnaire de paquets comme npm précédemment, vous cherchez peut-être a savoir comment ajouter des dépendances globales.

Pour la grande majorité de paquets, il est considéré comme une mauvaise pratique d’avoir des dépendances globales parce qu’elles sont implicites. Il est préférable d’ajouter toutes vos dépendances localement afin qu’elles soient explicites et que n'importe qui d’autre qui utilise votre projet obtiennent le même ensemble de dépendances.

Si vous essayez d’utiliser un outil CLI qui a un `bin` vous pouvez accéder à ces derniers dans votre répertoire `./node_modules/.bin`. Vous pouvez également utiliser la commande [`global`]({{url_base}}/docs/cli/global) :

```sh
yarn global add <package...>
```

### Commandes [](#toc-commands){#toc-commands.toc}

##### `yarn add <package...>` [](#toc-yarn-add){#toc-yarn-add.toc}

Ceci installera un ou plusieurs packages dans vos [`dépendances`]({{url_base}}/docs/dependency-types#toc-dependencies).

##### `yarn add <package...> [--dev/-D]` [](#toc-yarn-add-dev-d){#toc-yarn-add-dev-d.toc}

L'utilisation de `--dev` ou `-D` installera un ou plusieurs paquets dans vos [`devDependencies`]({{url_base}}/docs/dependency-types#toc-dev-dependencies).

##### `yarn add <package...> [--peer/-P]` [](#toc-yarn-add-peer-p){#toc-yarn-add-peer-p.toc}

L'utilisation de `--peer` ou `-P` installera un ou plusieurs paquets dans vos [`peerDependencies`]({{url_base}}/docs/dependency-types#toc-peer-dependencies).

##### `yarn add <package...> [--optional,-O]` [](#toc-yarn-add-optional-o){#toc-yarn-add-optional-o.toc}

L'utilisation de `--optional` ou `-O` installera un ou plusieurs paquets dans vos [`optionalDependencies`]({{url_base}}/docs/dependency-types#toc-optional-dependencies).

##### `yarn add <package...> [--exact/-E]` [](#toc-yarn-add-exact-e){#toc-yarn-add-exact-e.toc}

L'utilisation de `--exact` ou `-E` installera un ou plusieurs paquets avec versions fixes. Par défaut la version la plus récente avec la même version majeure est installée. Par exemple, `yarn add foo@1.2.3` acceptera la version `1.9.1`, mais `yarn add foo@1.2.3 --exact` n'accepte que la version `1.2.3`.

##### `yarn add <package...> [--tilde/-T]` [](#toc-yarn-add-tilde-t){#toc-yarn-add-tilde-t.toc}

L'utilisation de `--tilde` ou `-T` installera la version la plus recente du paquet avec la meme version mineure. Par défaut la version la plus récente avec la même version majeure est installée. Par exemple, `yarn add foo@1.2.3 --tilde` acceptera `1.2.9` mais pas `1.3.0`.