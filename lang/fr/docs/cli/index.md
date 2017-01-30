* * *

id: docs_cli_index guide: docs_cli layout: guide

* * *

{% include vars.html %}

Yarn fournit un ensemble riche de commandes pour vous aider avec les divers aspects de votre paquet, y compris l’installation, administration, publication, etc.

Même si toutes les commandes disponibles sont fournis ici, en ordre alphabétique, les commandes plus populaires sont :

- [`yarn add`]({{url_base}}/docs/cli/add) : ajoute un package à utiliser dans votre paquet actuel.
- [`yarn init`]({{url_base}}/docs/cli/init) : initialise le dévélopment d'un paquet.
- [`yarn install`]({{url_base}}/docs/cli/install) : installe toutes les dépendances définis dans un fichier `package.json`.
- [`yarn publish`]({{url_base}}/docs/cli/publish) : publie un paquet à un gestionnaire de paquets.
- [`yarn remove`]({{url_base}}/docs/cli/remove) : supprime un paquet qui n’est plus utilisé dans votre paquet.

## Commande par défaut [](#toc-default-command){#toc-default-command.toc}

Exécutant `yarn` avec aucune commande exécutera `yarn install`, en passant par tous les indicateurs fournis.

## Simultanéité et `--mutex` [](#toc-concurrency-and-mutex){#toc-concurrency-and-mutex.toc}

Lorsque vous exécutez plusieurs instances de yarn d'un même utilisateur sur le même serveur, vous pouvez faire en sorte qu’une instance s’exécute à un moment donné (et éviter les conflits) en transmettant l’indicateur global `--mutex` suivi de `fichier` ou de `réseau`.

Quand `file` est utilisé Yarn lira/écrira un fichier mutex `.yarn-single-instance` dans le répertoire de travail actif par défaut. Vous pouvez également spécifier un nom de fichier alternatif ou global.

```sh
--mutex file
--mutex file:/tmp/.yarn-mutex
```

Quand `network` est utilisé Yarn va créer un serveur au port `31997` par défaut. Vous pouvez également spécifier un autre port.

```sh
--mutex network
--mutex network:30330
```