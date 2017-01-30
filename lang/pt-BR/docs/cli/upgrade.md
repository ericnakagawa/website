* * *

id: docs_cli_upgrade guide: docs_cli layout: guide additional_reading_tags: ["cli-add", "cli-tag", "dependencies-versions"]

* * *

{% include vars.html %}

<p class="lead">Atualiza pacotes para sua versão mais recente baseado no intervalo especificado.</p>

##### `yarn upgrade` [](#toc-yarn-upgrade){#toc-yarn-upgrade.toc}

Este comando atualiza todas as dependências para suas versões mais recentes, baseado no intervalo de versões especificado no arquivo `package.json`. O arquivo `yarn.lock` também será recriado.

```sh
yarn upgrade
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 867 new dependencies.
    [...]
    ├─ jest-cli@16.0.1
    │  ├─ yargs-parser@3.2.0
    │  └─ yargs@5.0.0
    ├─ jest-diff@16.0.0
    │  └─ diff@3.0.1
    [...]
    └─ yargs@4.8.1
    ✨  Done in 20.79s.
    

##### `yarn upgrade [package]` [](#toc-yarn-upgrade-package){#toc-yarn-upgrade-package.toc}

Este comando atualiza um único pacote para a versão especificada pela `última` tag (potencialmente atualizando o pacote através de versões maiores).

```sh
yarn upgrade d3-scale
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ d3-scale@1.0.3
    ✨  Done in 6.10s.
    

Isto vai atualizar seu `package.json` para se parecer com isso:

```diff
-  "d3-scale": "^0.9.3",
+  "d3-scale": "^1.0.3",
```

##### `yarn upgrade [package@version]` [](#toc-yarn-upgrade-package-version){#toc-yarn-upgrade-package-version.toc}

Isto vai atualizar (ou desatualizar) um pacote instalado para uma versão específica. Você pode usar qualquer número de versão semântica - [SemVer]({{url_base}}/docs/dependency-versions#toc-semantic-versioning) - ou intervalo de versão.

```sh
yarn upgrade d3-scale@1.0.2
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ d3-scale@1.0.2
    ✨  Done in 6.43s.
    

Isto vai atualizar seu `package.json` para se parecer com isso:

```diff
-  "d3-scale": "^1.0.3",
+  "d3-scale": "^1.0.2",
```

##### `yarn upgrade [package@tag]` [](#toc-yarn-upgrade-package-tag){#toc-yarn-upgrade-package-tag.toc}

Isto vai atualizar um pacote para a versão identificada pela `tag`. Nomes de [tag]({{url_base}}/docs/cli/tag#toc-what-are-tags) são escolhidos pelos mantenedores do projeto, e você usa este comando para instalar uma versão experimental ou de longo tempo de suporte de um pacote desenvolvido. A tag que você escolhe irá ser a versão que aparece no seu arquivo `package.json`.

```sh
yarn upgrade react@next
```

    yarn upgrade v0.16.0
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ react@15.4.0-rc.4
    ✨  Done in 3.73s.
    

Isto vai atualizar seu `package.json` para parecer com isso:

```diff
-  "react": "^15.3.2",
+  "react": "next",
```

Da mesma forma, usando a tag `latest` vai resultar em uma atualização no seu `package.json` que vai ficar assim:

```diff
-  "react": "^15.3.2",
+  "react": "latest",
```

##### `yarn upgrade [package] --ignore-engines` [](#toc-yarn-upgrade-package-ignore-engines){#toc-yarn-upgrade-package-ignore-engines.toc}

Isto atualiza um simples pacote nomeado para a versão especificada pela `última` tag, ignorando verificações de sistema.

```sh
yarn upgrade d3-scale --ignore-engines
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ d3-scale@1.0.3
    ✨  Done in 6.10s.
    

Isto vai atualizar seu `package.json` para se parecer com isso:

```diff
-  "d3-scale": "^0.9.3",
+  "d3-scale": "^1.0.3",
```