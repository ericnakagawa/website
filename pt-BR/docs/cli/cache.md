* * *

id: docs_cli_cache guide: docs_cli layout: guide

* * *

##### `yarn cache ls` [](#toc-yarn-cache-ls){#toc-yarn-cache-ls.toc}

O yarn arquiva todos pacotes num "cache" global em sua pasta de usuário no sistema de arquivos. `yarn cache ls` mostrará na tela todos os pacotes arquivados.

##### `yarn cache dir` [](#toc-yarn-cache-dir){#toc-yarn-cache-dir.toc}

Executar `yarn cache dir` mostrará na tela o caminho da pasta onde o "cache" global do yarn está arquivado.

##### `yarn cache clean` [](#toc-yarn-cache-clean){#toc-yarn-cache-clean.toc}

Executar este comando limpará o "cache" local. Este será populado novamente na próxima vez que o comando `yarn` ou `yarn install` for executado.

### Mudar a pasta de "cache" do yarn [](#toc-change-the-cache-path-for-yarn){#toc-change-the-cache-path-for-yarn.toc}

Defina o valor de configuração `cache-folder` (Pasta de "cache") para configurar a pasta de "cache".

```sh
yarn config set cache-folder <caminho>
```

Você pode especificar o diretório de cache com a "flag" `--cache-folder`:

```sh
yarn <comando> --cache-folder <caminho>
```