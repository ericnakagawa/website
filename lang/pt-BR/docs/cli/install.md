* * *

id: docs_cli_install guide: docs_cli layout: guide

* * *

{% include vars.html %}

`yarn install` é usado para instalar todas dependências de um projeto. Este comando é normalmente usado quando você acabou de baixar o código de um projeto ou quando outro desenvolvedor no projeto adicionou uma dependência nova que você precisa baixar.

Se você está acostumado ao npm você pode estar esperando usar `--save` ou `--save-dev`. Estes comandos foram substituídos por `yarn add` e `yarn add --dev`. Para mais informações, veja [a documentação do `yarn add`]({{url_base}}/docs/cli/add).

Executar `yarn` com nenhum comando adicional irá executar `yarn install`, passando adiante qualquer "flag" definida.

##### `yarn install` [](#toc-yarn-install){#toc-yarn-install.toc}

Instala todas dependências listadas no `package.json` em sua pasta local `node_modules`.

##### `yarn install --flat` [](#toc-yarn-install-flat){#toc-yarn-install-flat.toc}

Só permite uma versão de um pacote. Na primeira execução este comando pede que você escolha a versão de cada pacote que é dependido em múltiplos "alcances" de versões. Isso será adicionado ao seu `package.json` em um campo `resolutions` (resoluções).

```json
"resolutions": {
  "pacote-a": "2.0.0",
  "pacote-b": "5.0.0",
  "pacote-c": "1.5.2"
}
```

##### `yarn install --force` [](#toc-yarn-install-force){#toc-yarn-install-force.toc}

Este comando baixa todos os pacotes de novo, mesmo aqueles que já estavam instalados.

##### `yarn install --har` [](#toc-yarn-install-har){#toc-yarn-install-har.toc}

Retorna um [arquivo HHTP](https://en.wikipedia.org/wiki/.har) com todos os pedidos feitos à rede durante a instalação. Arquivos HAR são usados para investigar performance da rede e podem ser analisados com ferramentas como [Google's HAR Analyzer](https://toolbox.googleapps.com/apps/har_analyzer/) ou [HAR Viewer](http://www.softwareishard.com/blog/har-viewer/).

##### `yarn install --no-lockfile` [](#toc-yarn-install-no-lockfile){#toc-yarn-install-no-lockfile.toc}

Não lê ou gera um arquivo de travamento `yarn.lock`.

##### `yarn install --production` [](#toc-yarn-install-production){#toc-yarn-install-production.toc}

Ao usar a "flag" `--production` ou quando a variável de ambiente `NODE_ENV` é definida como `production`, o yarn não instalará qualquer pacote listado nas `devDependencies` (Dependências de desenvolvimento).

> **Nota:** `--prod` é um "alias" (Abreviação para uso) de `--production`.

##### `yarn install --pure-lockfile` [](#toc-yarn-install-pure-lockfile){#toc-yarn-install-pure-lockfile.toc}

Não gera um arquivo de travamento `yarn.lock`.