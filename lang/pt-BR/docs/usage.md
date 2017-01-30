* * *

id: docs_usage guide: docs_getting_started layout: guide additional_reading_tags: ["basics", "cli"]

* * *

{% include vars.html %}

Agora que você tem Yarn [instalado]({{url_base}}/docs/install), você pode começar a usa-lo. Veja alguns dos comandos mais comuns que você vai precisar.

**Começando um novo projeto**

```sh
yarn init
```

**Adicionando uma dependência**

```sh
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

**Atualizando uma dependência**

```sh
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

**Removendo uma dependência**

```sh
yarn remove [package]
```

**Instalando todas as dependências do projeto**

```sh
yarn
```

ou

```sh
yarn install
```