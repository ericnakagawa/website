* * *

id: docs_cli_add guide: docs_cli layout: guide description: docs_cli_add_description additional_reading_tags: ["dependencies"]

* * *

{% include vars.html %}

<p class="lead">Instala um pacote e outros pacotes dos quais o primeiro depende.</p>

### Adicionar dependências [](#toc-adding-dependencies){#toc-adding-dependencies.toc}

Quando você quiser usar outro pacote, primeiro é necessário adicioná-lo às suas dependências. Isso significa executar `yarn add [package-name]` para instalá-lo no seu projeto.

Isso também vai atualizar o seu `package.json` e seu `yarn.lock` para que outros desenvolvedores trabalhando no projeto também tenham as mesmas dependências que você quando executarem `yarn` ou `yarn install`.

A maioria dos pacotes serão instalados do [registro npm](https://www.npmjs.com/) e são referenciados simplesmente pelo nome do pacote. Por exemplo, `yarn add react` instalará o pacote [`react`](https://www.npmjs.com/package/react) do registro npm.

Você pode especificar a versão usando uma das alternativas:

  1. `yarn add nome-do-pacote` instala a "última" versão do pacote.
  2. `yarn add nome-do-pacote@1.2.3` instala a versão específica do pacote do registro npm.
  3. `yarn add nome-do-pacote@versão` instala uma ["versão"]({{url_base}}/docs/cli/tag) específica. (Por exemplo, `beta`, `seguinte`, ou `recente`).

No geral, um pacote é simplesmente uma pasta com código e um arquivo `package.json` que descreve o conteúdo da pasta. Você pode referir ao pacote de várias maneiras diferentes:

Você também pode especificar pacotes de fontes diferentes:

  1. `yarn add nome-do-pacote` instala o pacote do [registro npm](https://www.npmjs.com/) a não ser que você tenha definido outro no seu `package.json`.
  2. `yarn add caminho:/de/uma/pasta/local` instala um pacote que está no seu sistema de arquivos locais. Isso é útil para testar outros pacotes que sejam seu e que não foram publicados ao registro.
  3. `yarn add caminho:/de/um/tarball.tgz` instala um pacote de um "gzipped tarball" que pode ser usado para compartilhar um pacotes antes de publicá-lo.
  4. `yarn add <url remota git>` instala um pacote de um repositório git remoto.
  5. `yarn add <url remota git>#<commit/versão>` instala um pacote de um repositório git remoto numa versão específica de um commit ou versão.
  6. `yarn add https://meu-projeto.org/pacote.tgz` instala um pacote de um "gzipped tarball" remoto.

### Ressalvas [](#toc-caveats){#toc-caveats.toc}

Se você já usou um gerenciador de pacotes como o npm anteriormente, você deve estar procurando por como adicionar uma dependência global.

Na grande maioria dos pacotes é considerado uma prática ruim ter dependências globais porque elas são implícitas. É bem melhor adicionar todas as suas dependências localmente para que elas sejam explícitas e todas outras pessoas usando seu projeto também terão as mesmas dependências que você.

Se você estiver usando uma ferramente de Linha de Comando (CLI) que tenha um `bin` você pode acessar estes arquivos na pasta `./node_modules/.bin`. Você também pode usar o comando [`global`]({{url_base}}/docs/cli/global):

```sh
yarn global add <pacote...>
```

### Comandos [](#toc-commands){#toc-commands.toc}

##### `yarn add <pacote...>` [](#toc-yarn-add){#toc-yarn-add.toc}

Isso instala um ou mais pacotes nas suas [`dependências`]({{url_base}}/docs/dependency-types#toc-dependencies).

##### `yarn add <pacote...> [--dev/-D]` [](#toc-yarn-add-dev-d){#toc-yarn-add-dev-d.toc}

Usar `--dev` ou `-D` vai instalar um ou mais pacotes nas suas [`devDependencies`]({{url_base}}/docs/dependency-types#toc-dev-dependencies). (Dependências de desenvolvimento)

##### `yarn add <pacote...> [--peer/-P]` [](#toc-yarn-add-peer-p){#toc-yarn-add-peer-p.toc}

Usar `--peer` ou `-P` vai instalar um ou mais pacotes nas suas [`peerDependencies`]({{url_base}}/docs/dependency-types#toc-peer-dependencies). (Dependências "parceiras")

##### `yarn add <pacote...> [--optional,-O]` [](#toc-yarn-add-optional-o){#toc-yarn-add-optional-o.toc}

Usar `--optional` ou `-O` instalará um ou mais pacotes nas suas [`optionalDependencies`]({{url_base}}/docs/dependency-types#toc-optional-dependencies). (Dependências opcionais)

##### `yarn add <pacote...> [--exact/-E]` [](#toc-yarn-add-exact-e){#toc-yarn-add-exact-e.toc}

Usar `--exact` ou `-E` instala o pacote na versão exata. O padrão é usar o lançamento mais recente com a mesma versão "maior". Por exemplo, `yarn add foo@1.2.3` aceitaria a versão `1.9.1`, porém `yarn add foo@1.2.3 --exact` só aceitaria a versão `1.2.3`.

##### `yarn add <pacote...> [--tilde/-T]` [](#toc-yarn-add-tilde-t){#toc-yarn-add-tilde-t.toc}

Usar `--tilde` ou `-T` instala a lançamento mais recente do pacote que tenha a mesma versão "menor". O padrão é usar o lançamento mais recente com a mesma versão "maior". Por exemplo, `yarn add foo@1.2.3 --tilde` aceitaria `1.2.9` mas não `1.3.0`.