* * *

id: docs_cli_global guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Installer les paquets globalement sur votre système d’exploitation.</p>

##### `yarn global` [](#toc-yarn-global){#toc-yarn-global.toc}

`yarn global` est un préfixe utilisé pour un certain nombre de commandes comme `add`, `bin`, `ls` et `remove`. Les commandes se comportent de la meme façon que leurs versions normales avec la difference qu'elles utililisent un annuaire global local pour stocker les paquets. La commande `global` rend les binaires disponibles à utiliser sur votre système d’exploitation.

Ceci est utile pour l'outillage de développeurs ne faisant pas partie d’un projet individuel, mais est plutôt utilisé pour les commandes locales. Un tel exemple est [create-react-app](https://github.com/facebookincubator/create-react-app) qui peut être installé globalement comme ceci :

```sh $ yarn global add create-react-app --prefix /usr/local

# la commande `create-react-app` est maintenant disponible globalement dans votre système d'exploitation :

$ which create-react-app $ /usr/local/bin/create-react-app $ create-react-app ````

En savoir plus sur les commandes qui peuvent être utilisés avec `yarn global` :

- [`yarn add`]({{url_base}}/docs/cli/add) : ajoute un package à utiliser dans votre paquet actuel. 
- [`yarn bin`]({{url_base}}/docs/cli/bin) : affiche l’emplacement du dossier bin de yarn.
- [`yarn ls`]({{url_base}}/docs/cli/ls) : affiche la liste de paquets installés.
- [`yarn remove`]({{url_base}}/docs/cli/remove) : supprime un paquet qui n’est plus utilisé dans votre paquet.
- [`yarn upgrade`]({{url_base}}/docs/cli/upgrade) : mises à jour des paquets à leur dernière version, basée sur la plage spécifiée.