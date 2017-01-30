* * *

id: docs_cli_owner guide: docs_cli layout: guide

* * *

<p class="lead">Gérer les propriétaires de paquet.</p>

### Qu'est-ce qu'un propriétaire de paquet ? [](#toc-what-is-a-package-owner){#toc-what-is-a-package-owner.toc}

Un « propriétaire » de paquet dans le registre est un utilisateur qui peut modifier un package. Un seul paquet peut avoir autant de propriétaires que vous souhaitez.

Les propriétaires ont l’autorisation d’effectuer les tâches suivantes :

  1. Publier de nouvelles versions du paquet
  2. Ajouter ou supprimer d'autres propriétaires du paquet
  3. Modifier les métadonnées d’un paquet

### Mises en garde [](#toc-caveats){#toc-caveats.toc}

Il n’existe pas d’autres niveaux d’accès au temps d'écriture. Tous les utilisateurs peuvent soit modifier un package ou ils ne peuvent pas. Dans le futur, il pourrait y avoir plusieurs types de rôles, mais pas pour le moment.

### Commandes [](#toc-commands){#toc-commands.toc}

##### `yarn owner ls <package>` [](#toc-yarn-owner-ls){#toc-yarn-owner-ls.toc}

Affiche la liste de tous les propriétaires d’un `< paquet >`.

##### `yarn owner add <user> <package>` [](#toc-yarn-owner-add){#toc-yarn-owner-add.toc}

Ajoute `< user >` en tant que propriétaire du `< package >`. Vous devez être déjà propriétaire du `< package >` afin d’exécuter cette commande.

##### `yarn owner rm <user> <package>` [](#toc-yarn-owner-rm){#toc-yarn-owner-rm.toc}

Supprime `< user >` en tant que propriétaire du `< package >`. Vous devez être déjà propriétaire du `< package >` afin d’exécuter cette commande.