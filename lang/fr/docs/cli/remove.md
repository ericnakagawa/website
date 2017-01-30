* * *

id: docs_cli_remove guide: docs_cli layout: guide

* * *

##### `yarn remove <package...>` [](#toc-yarn-remove){#toc-yarn-remove.toc}

En exécutant `yarn remove foo`, cela supprimera le package appelé `foo` de vos dépendances directes, mettra à jour vos fichiers `package.json` et `yarn.lock` dans le processus.

D'autres développeurs travaillant sur le projet peuvent exécuter `yarn install` pour synchroniser leurs propres répertoires `node_modules` avec l’ensemble de dépendances actualisées.

Lorsque vous supprimez un package, il est supprimé de tous les types de dépendances : `dependencies`, `devDependencies`, etc.

> **Remarque** : `yarn remove` mettra toujours à jour vos fichiers `package.json` et `yarn.lock`, ce qui garantit aux différents développeurs sur un même projet d'obtenir le même ensemble de dépendance. Il n’est pas possible de désactiver ce comportement.