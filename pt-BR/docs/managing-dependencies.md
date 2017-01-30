* * *

id: docs_managing_dependencies guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock", "cli-add", "cli-upgrade", "cli-remove"]

* * *

{% include vars.html %}

Quando você deseja adicionar, atualizar ou remover dependências há alguns comandos diferente que você precisa saber.

Cada comando irá automaticamente atualizar seus arquivos [`package.json`]({{url_base}}/docs/package-json) e [`yarn.lock`]({{url_base}}/docs/yarn-lock).

### Adicionando uma dependência [](#toc-adding-a-dependency){#toc-adding-a-dependency.toc}

Se você quiser usar outro pacote, primeiro você precisa adicioná-lo como uma dependência. Para isso você deve executar:

```sh
yarn add [package]
```

Isto adicionará automaticamente o `[package]` de suas dependências em seu `package.json`. Ele também irá atualizar seu `yarn.lock` para refletir a alteração.

```diff
  {
    "name": "my-package",
    "dependencies": {
+     "package-1": "^1.0.0"
    }
  }
```

Você também pode adicionar outros [tipos de dependências]({{url_base}}/docs/dependency-types) usando bandeiras:

- `yarn add --dev` para adicionar em `devDependencies`
- `yarn add --peer` para adicionar em `peerDependencies`
- `yarn add --optional` para adicionar em `optionalDependencies`

Você pode especificar qual versão de um pacote que você deseja instalar especificando uma [versão de dependência]({{url_base}}/docs/dependency-versions) ou uma [etiqueta]({{url_base}}/docs/cli/tag).

```sh
yarn add [package]@[version]
yarn add [package]@[tag]
```

`[version]` ou `[tag]` é o que será adicionado ao seu `package.json` e então removido na instalação de dependências.

Por exemplo:

```sh
yarn add package-1@1.2.3
yarn add package-2@^1.0.0
yarn add package-3@beta
```

```json
{
  "dependencies": {
    "package-1": "1.2.3",
    "package-2": "^1.0.0",
    "package-3": "beta"
  }
}
```

### Atualizando uma dependência [](#toc-upgrading-a-dependency){#toc-upgrading-a-dependency.toc}

```sh
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

Isto irá atualizar o seus arquivos `package.json` e `yarn.lock`.

```diff
  {
    "name": "my-package",
    "dependencies": {
-     "package-1": "^1.0.0"
+     "package-1": "^2.0.0"
    }
  }
```

### Removendo uma dependência [](#toc-removing-a-dependency){#toc-removing-a-dependency.toc}

```sh
yarn remove [package]
```

Isto irá atualizar o seus arquivos `package.json` e `yarn.lock`.