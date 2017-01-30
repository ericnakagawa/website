* * *

id: docs_cli_test guide: docs_cli layout: guide

* * *

<p class="lead">Executa o script de testes definido pelo pacote.</p>

##### `yarn test` [](#toc-yarn-test){#toc-yarn-test.toc}

Se você definiu um object `scripts` no seu pacote, este comando vai rodar o script `test`.

Por exemplo, se você tem um bash script no seu pacote, `scripts/test`:

```sh
#!/bin/bash

echo "Olá Mundo!"
```

e o seguinte no seu `package.json`:

```json
{
  "name": "meu-pacote-de-homenagem",
  "version": "1.0.0",
  "description": "Este não é o melhor pacote do mundo, ele é apenas uma homenagem.",
  "main": "index.js",
  "author": "Contribuidor do Yarn",
  "license": "MIT",
  "scripts": {
    "test": "scripts/test"
  }
}
```

então executando `yarn test` deveria renderizar:

```sh
$ yarn test
yarn test v0.15.1
$ "./scripts/test"
Olá Mundo!
✨ Done in 0.17s.
```

##### `yarn run test` [](#toc-yarn-run-test){#toc-yarn-run-test.toc}

`yarn test` é só um atalho para `yarn run test`.