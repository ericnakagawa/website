* * *

id: docs_cli_index guide: docs_cli layout: guide

* * *

{% include vars.html %}

O yarn fornece uma série de comandos de linha de comando para te ajudar com vários aspectos do seu pacote do yarn, incluindo instalação, administração, publicação, etc.

Enquanto todos os comandos estão disponíveis aqui, em ordem alfabética, alguns dos comandos mais populares são:

- [`yarn add`]({{url_base}}/docs/cli/add): adiciona um pacote para uso no seu pacote atual.
- [`yarn init`]({{url_base}}/docs/cli/init): inicializa o desenvolvimento de um pacote.
- [`yarn install`]({{url_base}}/docs/cli/install): instala todas dependências definidas no arquivo `package.json`.
- [`yarn publish`]({{url_base}}/docs/cli/publish): publica um pacote para um gerenciador de pacotes.
- [`yarn remove`]({{url_base}}/docs/cli/remove): remove um pacote que não está sendo usado do seu pacote atual.

## Comando padrão [](#toc-default-command){#toc-default-command.toc}

Executar `yarn` com nenhum comando adicional irá executar `yarn install`, passando adiante qualquer "flag" definida.

## Concorrência e `--mutex` [](#toc-concurrency-and-mutex){#toc-concurrency-and-mutex.toc}

Quando se executa múltiplas instâncias do yarn no mesmo servidor você pode se segurar que apenas uma instância é executada por vez (e evitar conflitos) usando a "flag" global `--mutex` seguido de `file` ou `network`.

Quando se usa `file` o yarn irá ler/escrever um arquivo "mutex" `.yarn-single-instance` no diretório de trabalho atual por padrão. Você também pode definir um nome de arquivo alternativo ou global.

```sh
--mutex file
--mutex file:/tmp/.yarn-mutex
```

Quando se usa `network` o yarn criará um servidor na porta `31997` por padrão. Você também pode definir uma porta alternativa.

```sh
--mutex network
--mutex network:30330
```