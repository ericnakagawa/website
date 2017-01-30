* * *

id: docs_cli_licenses guide: docs_cli layout: guide

* * *

<p class="lead">Lista as licenças dos pacotes instalados.</p>

##### `yarn licenses ls` [](#toc-yarn-licenses-ls){#toc-yarn-licenses-ls.toc}

Este comando lista, em ordem alfabética, todos os pacotes que foram instalados por `yarn` ou `yarn install` e mostra a licença (e a URL do código-fonte) associados a cada página.

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

Este comando retorna uma lista de todas as licenças de todos pacotes que você instalou para o `stdout`.

```sh
yarn licenses generate-disclaimer
```

    The following software may be included in this product: pacote-1. This software contains the following license and notice below:
    
    [[LICENSE TEXT]]
    
    -----
    
    The following software may be included in this product: pacote-2. This software contains the following license and notice below:
    
    [[LICENSE TEXT]]