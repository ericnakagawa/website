* * *

id: docs_cli_unlink guide: docs_cli layout: guide

* * *

<p class="lead">Desvincular um link simbólico criado para um pacote.</p>

Para remover um pacote criado como link simbólico usando [`yarn link`](./link), você pode utilizar o comando `yarn unlink`.

##### `yarn unlink` [](#toc-yarn-unlink){#toc-yarn-unlink.toc}

Execute `yarn unlink` no diretório que foi usado anteriormente para criar o link.

##### ` yarn unlink [package]`[](#toc-yarn-unlink-package){#toc-yarn-unlink-package.toc}

Para desvincular um pacote que teve o link simbólico criado durante o desenvolvimento do seu projeto, apenas execute `yarn unlink [package]`. Você vai precisar executar `yarn` ou `yarn install` para reinstalar o pacote que foi linkado.

Exemplo da documentação do [`yarn link`](./link): Assumindo que você tem dois diretórios `react` e `react-relay` que estão localizados próximos um do outro, com `react` linkado dentro do projeto `react-relay`:

```sh
$ cd react
$ yarn unlink
yarn link vx.x.x
success Unregistered "react".
```

```sh
$ cd ../react-relay
$ yarn unlink react
yarn link vx.x.x
success Unregistered "react".
```

Veja também:

- [`yarn link`](./link): link simbólico para desenvolvimento local.