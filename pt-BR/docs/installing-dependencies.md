* * *

text for Translation id: docs_installing_dependencies guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock", "cli-install"]

* * *

Se você acabou de fazer check-out de um pacote de [controle de versão](./version-control), ie precisará instalar suas dependências.

> Se você está [adicionando as dependências](./managing-dependencies#toc-adding-a-dependency) em o seu projeto, então essas dependências são instaladas automaticamente durante esse processo.

### Instalando Dependências [](#toc-installing-dependencies){#toc-installing-dependencies.toc}

[`yarn install`](./cli/install) é usado para instalar todas as dependências num projeto. As dependências são recuperadas do arquivo `package.json` do seu projeto, e armazenadas no arquivo `yarn.lock`.

Quando desenvolvendo um pacote, instalar dependências é mais comum após:

  1. Você acabou de fazer check-out do código para um projeto que cria um pacote.
  2. Outro desenvolvedor no projeto adicionou uma nova dependência que você precisa para pegar.

### Opções de instalação [](#toc-installing-options){#toc-installing-options.toc}

Há muitas opções para instalar as dependências, incluindo:

  1. Instalar todas as dependências: `yarn` ou `yarn instalar`
  2. Instalar somente um versão do pacote: `yarn install --flat`
  3. Forçar o re-download de todos os pacote: `yarn install --force`
  4. Instalar apenas as dependências de produção: `yarn install --production`

Veja [a lista completa](./cli/install) de bandeiras que você pode passar para `yarn install`.