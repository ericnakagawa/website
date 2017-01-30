* * *

id: docs_cli_outdated guide: docs_cli layout: guide

* * *

<p class="lead">Confere dependências do pacote que estão desatualizadas.</p>

##### `yarn outdated` [](#toc-yarn-outdated){#toc-yarn-outdated.toc}

Lista as informações de versão para todos as dependências do pacote. Essa informação inclui a versão instalada atualmente, a versão desejada baseado no semver (Versão semântica), e a última versão disponível.

Por exemplo, suponha que o seu `package.json` tenha as seguintes dependências listadas:

```js
"dependencies": {
  "lodash": "4.15.0",
  "underscore": "~1.6.0"
}
```

A execução do comando deve exibir algo do tipo:

```sh
yarn outdated
```

    Package    Current Wanted Latest
    lodash     4.15.0  4.15.0 4.16.4
    underscore 1.6.0   1.6.0  1.8.3 
    ✨  Done in 0.72s.
    

##### `yarn outdated [package...]` [](#toc-yarn-outdated-package){#toc-yarn-outdated-package.toc}

Lista as informações de versão para um ou mais dependências de um pacote.

Para o arquivo `package.json` de exemplo mostrado anteriormente você deve ver o seguinte resultado ao conferir uma das dependências:

```sh
yarn outdated lodash
```

    Package Current Wanted Latest
    lodash  4.15.0  4.15.0 4.16.4
    ✨  Done in 1.04s.