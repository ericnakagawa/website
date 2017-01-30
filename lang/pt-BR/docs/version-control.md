* * *

id: docs_version_control guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock"]

* * *

Para que pessoas possam desenvolver, ou usar, seu pacote com sucesso, você precisa garantir que todos os arquivos necessários sejam verificados no seu sistema de controle fonte.

### Arquivos necessários [](#toc-required-files){#toc-required-files.toc}

Os seguintes arquivos devem ser verificados no controle de fonte para que alguém seja capaz de gerenciar seu pacote:

- `package.json`: Tem todas as dependências atuais do seu pacote.
- `yarn.lock`: Armazena as versões exatas de cada dependência do seu pacote.
- O código fonte que fornece a funcionalidade do seu pacote.

> Confira o [Pacote de exemplo do Yarn](https://github.com/yarnpkg/example-yarn-package) para os requisitos mínimos necessários para um pacote Yarn.