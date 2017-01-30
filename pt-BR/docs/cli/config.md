* * *

identificação: docs_cli_config guia: layout de docs_cli: guia

* * *

<p class="lead">Gerencia os arquivos de configuração do Yarn</p>

##### `yarn config set <chave> <valor> [-g|--global]` [](#toc-yarn-config-set-g-global){#toc-yarn-config-set-g-global.toc}

Define a configuração `chave` para um certo `valor`.

Exemplo:

```sh
$ yarn config set init-license BSD-2-Clause
yarn config vx.x.x
success Set "init-license" to "BSD-2-Clause".
✨  Done in 0.05s.

```

##### `yarn config get <chave>` [](#toc-yarn-config-get){#toc-yarn-config-get.toc}

Exibe o valor de uma `chave` no `stdout`.

Exemplo:

```sh
$ yarn config get init-license
BSD-2-Clause
```

##### `yarn config delete <chave>` [](#toc-yarn-config-delete){#toc-yarn-config-delete.toc}

Deleta uma `chave` da configuração.

Exemplo:

```sh
Text for Translation
$ yarn config delete test-key
yarn config vx.x.x
success Deleted "test-key".
✨  Done in 0.06s.
```

##### `yarn config list` [](#toc-yarn-config-list){#toc-yarn-config-list.toc}

Mostra a configuração atual.

Exemplo:

```sh
$ yarn config list
yarn config vx.x.x
info yarn config
{ 'version-tag-prefix': 'v',
  'version-git-tag': true,
  'version-git-sign': false,
  'version-git-message': 'v%s',
  'init-version': '1.0.0',
  'init-license': 'MIT',
  'save-prefix': '^',
  'ignore-scripts': false,
  'ignore-optional': true,
  registry: 'https://registry.yarnpkg.com',
  'user-agent': 'yarn/0.15.0 npm/? node/v6.2.1 darwin x64' }
info npm config
{ registry: 'https://registry.npmjs.org/',
  '//localhost:4873/:_authToken': 'some-auth-token' }
✨  Done in 0.05s.

```