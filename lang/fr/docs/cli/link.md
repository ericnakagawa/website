* * *

id: docs_cli_link guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Créez un lien symbolique a un dossier de paquet en cours du développement.</p>

Pour le développement, un paquet peut être lié dans un autre projet. Ceci est souvent utile pour tester les nouvelles fonctionnalités, ou lorsque vous essayez de débugger un problème dans un paquet qui se manifeste dans un autre projet.

Il y a deux commandes pour faciliter ce flux de travail :

##### `yarn link` (dans le paquet que vous souhaitez lier) [](#toc-yarn-link-in-package-you-want-to-link){#toc-yarn-link-in-package-you-want-to-link.toc}

Cette commande est exécutée dans le dossier du paquet que vous souhaitez link-er. Par exemple, si vous travaillez sur `react` et souhaitez utiliser votre version locale pour debugger un problème dans `react-relay`, il suffit de lancer `yarn link` à l’intérieur du projet `react`.

##### `yarn link [package...]`[](#toc-yarn-link-package){#toc-yarn-link-package.toc}

`yarn link [package]` permet de link-er un autre paquet que vous souhaitez tester dans votre projet actuel. Pour reprendre l’exemple ci-dessus, dans le projet `react-relay`, vous exécuteriez `yarn link react` pour utiliser votre version locale de `react` que vous avez déjà connecté.

Un exemple complet, en supposant que les deux projet dossiers `react` et `react-relay` à côté l'un de l’autre :

```sh
$ cd react
$ yarn link
yarn link vx.x.x
success Registered "react".
info You can now run `yarn link "react"` in the projects where you want to use this module and it will be used instead.
```

```sh
$ cd ../react-relay
$ yarn link react
yarn link vx.x.x
success Registered "react".
```

Cela créera un lien symbolique nommé `react-relay/node_modules/react` qui link à votre copie locale du projet `react`.

Pour inverser ce processus, il suffit d’utiliser `yarn unlink` ou `yarn unlink [package]`. Voir aussi :

- [`yarn unlink`]({{url_base}}/docs/cli/unlink): unlink ou délier un paquet lié `package`.