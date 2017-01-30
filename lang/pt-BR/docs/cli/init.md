* * *

id: docs_cli_init guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Cria ou atualiza um arquivo package.json interativamente.</p>

##### `yarn init` [](#toc-yarn-init){#toc-yarn-init.toc}

Este comando caminha com você por uma sessão interativa para criar um arquivo `package.json`. Algumas configurações padrões como a licença e a versão inciadas são achadas nas configurações `init-*` do yarn.

Aqui está um exemplo de quando se executa o comando dentro de uma pasta chamada `pastateste`:

```sh
$ yarn init
```

```sh
question name (testdir): meu-pacote-demais
question version (1.0.0): 
question description: O melhor pacote que você vai encontrar.
question entry point (index.js): 
question git repository: https://github.com/yarnpkg/example-yarn-package
question author: Contribuidor do Yarn
question license (MIT): 
success Saved package.json
✨  Done in 87.70s.
```

Isso resulta no seguinte `package.json`:

```json
{
  "name": "meu-pacote-demais",
  "version": "1.0.0",
  "description": "O melhor pacote que você vai encontrar.",
  "main": "index.js",
  "repository": {
    "url": "https://github.com/yarnpkg/example-yarn-package",
    "type": "git"
  },
  "author": "Contribuidor do Yarn",
  "license": "MIT"
}
```

Se você já tem um arquivo `package.json` existente, então ele usará os valores do arquivo como padrão.

O seguinte arquivo `package.json` existente:

```json
{
  "name": "meu-pacote-existente",
  "version": "0.1",
  "description": "Eu existo, logo, sou.",
  "repository": {
    "url": "https://github.com/yarnpkg/example-yarn-package",
    "type": "git"
  },
  "license": "BSD-2-Clause"
}
```

Resulta nos seguintes valores padrões na sessão interativa:

```sh
$ yarn init
```

```sh
question name (meu-pacote-existente): 
question version (0.1): 
question description (Eu existo, logo, sou.):
question entry point (index.js): 
question git repository (https://github.com/yarnpkg/example-yarn-package): 
question author: Contribuidor do Yarn
question license (BSD-2-Clause): 
success Saved package.json
✨  Done in 121.53s.
```

##### Definindo valores padrões para o `yarn init` [](#toc-setting-defaults-for-yarn-init){#toc-setting-defaults-for-yarn-init.toc}

As seguintes variáveis de [configuração]({{url_base}}/docs/cli/config) (config) podem ser usadas para personalizar os valores padrões do `yarn init`:

- `init-author-name (Nome do autor)`
- `init-author-email (E-mail do autor)`
- `init-author-url (URL do autor)`
- `init-version (Versão)`
- `init-license (Licença)`

##### `yarn init --yes/-y` [](#toc-yarn-init-yes-y){#toc-yarn-init-yes-y.toc}

Este comando pula a sessão interativa mencionada acima e gera um `package.json` baseado nos seus valores padrões. Alguns padrões podem ser modificados mudando as configurações `init-*` mencionadas acima. Por exemplo, dado uma instalação nova do yarn e dentro de uma pasta `yarn-exemplo`:

```sh
$ yarn init --yes
```

    warning The yes flag has been set. This will automatically answer yes to all questions which may have security implications.
    success Saved package.json
    ✨  Done in 0.09s.
    

O que produz o seguinte `package.json`:

```json
{
  "name": "yarn-example",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT"
}
```