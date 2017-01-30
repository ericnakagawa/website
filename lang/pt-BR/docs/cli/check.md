* * *

id: docs_cli_cache guide: docs_cli layout: guide

* * *

##### `yarn check` [](#toc-yarn-check){#toc-yarn-check.toc}

Verifica que as versões das dependências do arquivo `package.json` do projeto atual coincidem com aquelas do arquivo de travamento (lock file) do yarn.

##### `yarn check --integrity` [](#toc-yarn-check-integrity){#toc-yarn-check-integrity.toc}

Verifica que as versões e valores do hash de conteúdo de pacote no `package.json` do projeto correspondem ao do arquivo de travamento (lock file) do yarn. Isso ajuda a verificar que as dependências do pacote não foram alteradas.