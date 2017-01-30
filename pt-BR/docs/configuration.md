* * *

id: docs_configuration_index guide: docs_configuration layout: guide

* * *

<!-- [TODO: Rewrite and accommodate for other configuration files] -->

## Configurando seus pacote [](#toc-configuring-your-package){#toc-configuring-your-package.toc}

Yarn procura por arquivos `package.json` para identificar cara pacote e configura o comportamento do yarn durante a execução no seu pacote.

Uma configuração exemple para o pacote `pet-kitten`, que é encontrada em `pet-kitten/package.json`:

    {
      "name": "pet-kitten",
      "version": "0.1.0",
      "main": "pet.js",
      "dependencies": {
        "hand": "1.0.0"
      }
    }
    

## Use `yarn.lock` para fixar suas dependências [](#toc-use-yarn-lock-to-pin-your-dependencies){#toc-use-yarn-lock-to-pin-your-dependencies.toc}

Yarn também usa o arquivo `yarn.lock` na raiz do seu projeto para fazer a resolução de dependências mais rápida e confiável. Você nunca precisará tocar nesse arquivo, yarn o possui e vai muda-lo no gerenciamento de dependências.

Para garantir que seu app funciona consistentemente, **você sempre deverá salvar o arquivo `yarn.lock` no seu repositório de código**