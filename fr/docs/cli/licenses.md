* * *

id: docs_cli_licenses guide: docs_cli layout: guide

* * *

<p class="lead">Afficher la liste des licences pour les paquets installés.</p>

##### `yarn licenses ls` [](#toc-yarn-licenses-ls){#toc-yarn-licenses-ls.toc}

Exécutez cette commande affiche une liste, en ordre alphabétique, de tous les paquets qui ont été installés par `yarn` ou `yarn install` et vous donne la licence (et l’URL au code source) associée à chaque package.

```sh
yarn licenses ls
```

    yarn licenses v0.14.0
    ├─ abab@1.0.3
    │  ├─ License: ISC
    │  └─ URL: git+https://github.com/jsdom/abab.git
    ├─ abbrev@1.0.9
    │  ├─ License: ISC
    │  └─ URL: http://github.com/isaacs/abbrev-js
    ├─ acorn-globals@1.0.9
    │  ├─ License: MIT
    │  └─ URL: https://github.com/ForbesLindesay/acorn-globals.git
    ├─ acorn@2.7.0
    │  ├─ License: MIT
    │  └─ URL: https://github.com/ternjs/acorn.git
    ├─ align-text@0.1.4
    │  ├─ License: MIT
    │  └─ URL: git://github.com/jonschlinkert/align-text.git
    ├─ amdefine@1.0.0
    │  ├─ License: BSD-3-Clause AND MIT
    │  └─ URL: https://github.com/jrburke/amdefine.git
    ├─ ansi-escapes@1.4.0
    │  ├─ License: MIT
    │  └─ URL: https://github.com/sindresorhus/ansi-escapes.git
    ├─ ansi-regex@2.0.0
    │  ├─ License: MIT
    │  └─ URL: https://github.com/sindresorhus/ansi-regex.git
    ...
    

##### `yarn licenses generate-disclaimer` [](#toc-yarn-licenses-generate-disclaimer){#toc-yarn-licenses-generate-disclaimer.toc}

L’exécution de cette commande retourne une liste triée des licences de tous les paquets que vous avez installé à `stdout`.

```sh
<code>yarn licenses generate-disclaimer</code>
```
</code>

    The following software may be included in this product: package-1. This software contains the following license and notice below:
    
    [[LICENSE TEXT]]
    
    -----
    
    The following software may be included in this product: package-2. [[LICENSE TEXT]]