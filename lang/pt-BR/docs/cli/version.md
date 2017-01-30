* * *

id: docs_cli_version guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Atualiza a versão do pacote.</p>

### Atualizando versões [](#toc-updating-versions){#toc-updating-versions.toc}

Usando o comando `yarn version`, você pode atualizar a versão de seu pacote via linha de comando.

Por exemplo, iniciando com este `package.json`:

```js
{
  "name": "exemplo-de-pacote-com-yarn",
  "version": "1.0.1",
  "description": "Um exemplo de um pacote para mostrar como o Yarn funciona"
}
```

Quando nós executamos o comando `yarn version`:

```sh
yarn version
```

    info Current version: 1.0.1
    question New version: 1.0.2
    info New version: 1.0.2
    ✨  Done in 9.42s.
    

Nós teremos a seguinte atualização no nosso `package.json`:

```json
{
  "name": "exemplo-de-pacote-com-yarn",
  "version": "1.0.2",
  "description": "Um exemplo de um pacote para mostrar como o Yarn funciona"
}
```

> **Nota:** A nova versão que você entrar deve ser uma versão semântica - [SemVer]({{url_base}}/docs/dependency-versions#toc-semantic-versioning) válida.

#### Tags do Git [](#toc-git-tags){#toc-git-tags.toc}

Se você executar `yarn version` dentro de um repositório do Git, uma [Tag do Git](https://git-scm.com/book/en/v2/Git-Basics-Tagging) será criada por padrão, seguindo o formato `v0.0.0`.

Você pode personalizar a tag do git que será criada, ou desabilitar esse comportamento usando o comando `yarn config set`.

Para mudar o prefixo da tag do git, você ode usar `version-tag-prefix`:

```sh
yarn config set version-tag-prefix "v"
```

Ou você pode mudar a mensagem do git usando `version-git-message` onde `%s` está a string de versão:

```sh
yarn config set version-git-message "v%s"
```

Você pode também habilitar ou desabilitar a assinatura de tags do git, usando `version-git-sign`:

```sh
yarn config set version-git-sign false
```

Você pode ainda habilitar ou desabilitar o comportamento de tagueamento do git inteiramente usando `version-git-tag`:

```sh
yarn config set version-git-tag true
```

### Comandos [](#toc-commands){#toc-commands.toc}

##### `yarn version` [](#toc-yarn-version){#toc-yarn-version.toc}

Cria uma nova versão usando uma sessão interativa onde você entrar com um valor para uma nova versão.

##### `yarn version --new-version <version>` [](#toc-yarn-version-new-version){#toc-yarn-version-new-version.toc}

Cria uma nova versão especificada por `<version>`.

##### `yarn version --no-git-tag-version` [](#toc-yarn-version-no-git-tag-version){#toc-yarn-version-no-git-tag-version.toc}

Cria uma nova versão sem criar uma tag do git.