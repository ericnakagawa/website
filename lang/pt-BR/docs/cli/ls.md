* * *

id: docs_cli_ls guide: docs_cli layout: guide

* * *

<p class="lead">Lista os pacotes instalados.</p>

##### `yarn list` [](#toc-yarn-ls){#toc-yarn-ls.toc}

```sh
yarn list
```

O comando `yarn list` imita o comportamento esperado para a listagem do Unix. No yarn, o comando `list` lista todas as dependências na pasta de trabalho atual ao referenciar todos os meta-dados dos arquivos do gerenciador de pacotes, o que inclui as dependências do projeto.

    yarn list vx.x.x
    ├─ package-1@1.3.3
    ├─ package-2@5.0.9
    │  └─ package-3@^2.1.0
    └─ package-3@2.7.0
    

##### `yarn list [--depth]` [](#toc-yarn-ls-depth){#toc-yarn-ls-depth.toc}

Por padrão todos pacotes e suas dependências serão exibidos. Para restringir a profundidade das dependências você pode adicionar uma "flag", `--depth`, junto da profundidade desejada para o comando `list`.

    yarn list --depth=0
    

Lembre-se de que os níveis de profundidade começam no zero.