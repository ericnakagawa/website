* * *

id: docs_cli_link guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Gera uma ligação simbólica para uma pasta durante o desenvolvimento.</p>

No desenvolvimento um pacote pode ser ligado a outro projeto Isso é útil para testar novas funções ou para "debugar" um problema de um pacote que se manifesta em outro projeto.

Há dois comandos para facilitar esse tipo de linha de trabalho:

##### `yarn link` (no pacote que você quer fazer a ligação) [](#toc-yarn-link-in-package-you-want-to-link){#toc-yarn-link-in-package-you-want-to-link.toc}

Este comando é executado na pasta do pacote que você quer fazer a ligação. Por exemplo, se você está trabalhando no `react` e você quer usar sua versão local para "debugar" um problema no `react-relay`, simplesmente execute `yarn link` dentro do projeto `react`.

##### `yarn link [package...]`[](#toc-yarn-link-package){#toc-yarn-link-package.toc}

Use `yarn link [package]` para fazer a ligação de outro projeto que você gostaria de testar no seu projeto atual. Seguindo o exemplo acima, no projeto do `react-relay` você executaria `yarn link react` para usar sua versão local do `react` que você fez a ligação anteriormente.

Um exemplo completo, assumindo duas pastas `react` e `react-relay` próximas uma da outra:

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

Isso criará uma ligação simbólica chamada `react-relay/node_modules/react` que faz a ligação à sua cópia local do projeto `react`.

Para reverter este processo, simplesmente use `yarn unlink` ou `yarn unlink [package]`. Veja também:

- [`yarn unlink`]({{url_base}}/docs/cli/unlink): desfaça a ligação de um pacote ligado simbolicamente.