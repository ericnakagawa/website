* * *

id: docs_cli_run guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Executa um script definido no pacote.</p>

Você pode definir [`scripts`]({{url_base}}/docs/package-json#toc-scripts) no seu arquivo [`package.json`]({{url_base}}/docs/package-json).

```json
{
  "name": "meu-pacote",
  "scripts": {
    "build": "babel src -d lib",
    "test": "jest"
  }
}
```

##### `yarn run [script] [-- <argumentos>]` [](#toc-yarn-run-script){#toc-yarn-run-script.toc}

Se voce definir um objeto `scripts` em seu pacote, esse comando irá executar o `[script]`. Por exemplo:

```sh
yarn run test
```

Executar esse comando irá executar o script chamado `"test"` em seu `package.json`.

Você pode passar argumentos adicionais para seu script usando `--`.

```sh
yarn run test -- -o --watch
```

Executar esse comando irá executar `jest -o --watch`.

`[script]` pode também ser qualquer executável instalado localmente dentro de ` node_modules/.bin/`.

##### `yarn run` [](#toc-yarn-run){#toc-yarn-run.toc}

Se você não especificar um script para o comando `yarn run`, o comando `run` irá listar todos os scripts disponíveis para um pacote.