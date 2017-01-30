* * *

id: docs_cli_clean guide: docs_cli layout: guide

* * *

<p class="lead">Nettoie et supprime les fichiers inutiles de dépendances du package.</p>

##### `yarn clean` [](#toc-yarn-clean){#toc-yarn-clean.toc}

La commande `clean` libère de l’espace en supprimant les fichiers inutiles et les dossiers de dépendances. Il réduit le nombre de fichiers dans le dossier de votre projet `node_modules` ceci est utile dans un environnement où les paquets sont archivés dans le contrôle de version directement.

Une fois que vous exécutez `yarn clean`, Yarn va créer un fichier `.yarnclean` qui doit être ajouté au contrôle de version. Le nettoyage se fait alors automatiquement dans le cadre du `yarn install` (ou simplement `yarn`) et `yarn add`.

*Remarque : Cette commande est considérée utile pour les utilisation avancées seulement. Il est déconseillé d’utiliser cette commande uniquement si vous rencontrez des problèmes avec la quantité de fichiers qui sont installés dans le cadre de `node_modules`. Elle utilise une heuristique pour identifier les fichiers qui peuvent ne pas être nécessaires d’un paquet distribué et n'est pas parfaitement toujours sans conséquences inattendues.*