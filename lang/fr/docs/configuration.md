* * *

id: docs_configuration_index guide: docs_configuration layout: guide

* * *

<!-- [TODO: Rewrite and accommodate for other configuration files] -->

## Configuration de votre package [](#toc-configuring-your-package){#toc-configuring-your-package.toc}

Yarn recherche les fichiers `package.json` pour identifier chaque package et configurer le comportement de yarn pendant l'exécution à l’intérieur de ce package.

Un exemple de configuration pour le package `pet-kitten`, qui se trouveraient dans `pet-kitten/package.json` :

    {
      "name": "pet-kitten",
      "version": "0.1.0",
      "main": "pet.js",
      "dependencies": {
        "hand": "1.0.0"
      }
    }
    

## Utiliser `yarn.lock` pour épingler vos dépendances [](#toc-use-yarn-lock-to-pin-your-dependencies){#toc-use-yarn-lock-to-pin-your-dependencies.toc}

Yarn utilise également un fichier `yarn.lock` à la racine de votre projet pour rendre la résolution des dépendances rapide et fiable. Vous ne devez jamais toucher ce fichier, yarn en est le propriétaire et il le changera lors de la gestion des dépendances.

Pour s’assurer que votre application fonctionne de manière cohérente, **vous devez toujours enregistrer le fichier `yarn.lock` dans le dépôt de votre code.**