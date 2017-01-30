* * *

id: docs_cli_ls guide: docs_cli layout: guide

* * *

<p class="lead">Liste de tous les paquets installés.</p>

##### `yarn list` [](#toc-yarn-ls){#toc-yarn-ls.toc}

```sh
yarn list
```

La commande de `yarn ls` imite le comportement de Unix attendu de l’inscription. Dans Yarn, la commande `list` répertorie toutes les dépendances pour le répertoire de travail actuel en référençant tous les fichiers de données de meta gestionnaire de package, qui comprend des dépendances du projet.

    yarn list vx.x.x
    ├─ package-1@1.3.3
    ├─ package-2@5.0.9
    │  └─ package-3@^2.1.0
    └─ package-3@2.7.0
    

##### `yarn list [--depth]` [](#toc-yarn-ls-depth){#toc-yarn-ls-depth.toc}

Par défaut, tous les paquets et leurs dépendances seront affichés. Pour limiter la profondeur des dépendances, vous pouvez ajouter l'option, `--depth`, ainsi que le niveau désiré pour la commande `list`.

    yarn list --depth=0
    

N’oubliez pas, les niveaux sont indexées sur zéro.