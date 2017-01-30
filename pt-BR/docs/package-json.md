* * *

id: docs_configuration_index guide: docs_configuration layout: guide

* * *

{% include vars.html %}

## Fundamentos [](#toc-essentials){#toc-essentials.toc}

Os dois campos mais importantes no seu `package.json` são o `name` e `version`, sem eles seu pacote não será instalável. Os campos `name` e `version` são usados juntos para criar uma id exclusiva.

### `name` [](#toc-name){#toc-name.toc}

```json
{
  "name": "my-awesome-package"
}
```

Este é o nome do seu pacote. Ele é usado em URLs, como um argumento na linha de comando e como o nome do diretório dentro da pasta `node_modules`.

```sh
yarn add [name]
```

    node_modules/[name]
    

    https://registry.npmjs.org/[name]/-/[name]-[version].tgz
    

**Regras**

- Deve ser menor ou igual a 214 caracteres (incluindo o `@scope /` para pacotes com escopo).
- Não deve iniciar com um ponto (`.`) ou um sublinhado (`_`).
- Não deve ter uma letras maiúsculas no nome.
- Deve usar apenas caracteres de URL-seguro.

**Dicas**

- Não use o mesmo nome de um modulo fundamental para o Node.js
- Não coloque `js` ou `node` no nome.
- Mantenha os nomes curtos e descritivos. Você quer que as pessoas entendam o que é pelo nome, mas o nome também será usado em chamadas `require()`.
- Certifique-se de que não é algo no [registro](https://www.npmjs.com/) com o mesmo nome.

### `version` [](#toc-version){#toc-version.toc}

```json
{
  "version": "1.0.0"
}
```

A versão atual do seu pacote.

## Informações [](#toc-info){#toc-info.toc}

### `description` [](#toc-description){#toc-description.toc}

```json
{
  "description": "My short description of my awesome package"
}
```

A descrição é apenas uma frase que ajuda as pessoas a entenderem o propósito do pacote. Ela também pode ser usada na procura de pacotes em um gerenciador de pacotes.

### `keywords` [](#toc-keywords){#toc-keywords.toc}

```json
{
  "keywords": ["short", "relevant", "keywords", "for", "searching"]
}
```

Palavras-chave são palavras que são úteis ao procurar por pacotes em um Gerenciador de pacotes.

### `license` [](#toc-license){#toc-license.toc}

```json
{
  "license": "MIT",
  "license": "(MIT or GPL-3.0)",
  "license": "SEE LICENSE IN LICENSE_FILENAME.txt",
  "license": "UNLICENSED"
}
```

Todos os pacotes devem especificar uma licença para que os usuários saibam como eles são autorizados a usá-lo, e todas as restrições que você está colocando nele.

Você é encorajado a usar uma licença de código aberto ([OSI-aproved](https://opensource.org/licenses/alphabetical)), a menos que você tenha um motivo específico. Se você construiu seu pacote como parte do seu trabalho, é provavelmente melhor verificar com sua empresa antes de decidir sobre uma licença.

**Deve ser um dos seguintes:**

- Um [identificador de licença SPDX](https://spdx.org/licenses/) válido se você estiver usando uma licença padrão.
- Uma [expressão de 2.0 de sintaxe de expressão de licença SPDX](https://www.npmjs.com/package/spdx) valida se você estiver usando múltiplas licenças padrão.
- Uma sequência de caracteres de `Ver licença em < filename >` que aponta para um `< filename >` na raíz do seu pacote, se você estiver usando uma licença não-padrão.
- Uma sequência `não licenciado`, se você não quer conceder a outros o direito de usar um pacote privado ou não-publicado sob quaisquer condições.

## Links [](#toc-links){#toc-links.toc}

Vários links para documentação, lugares para problemas e onde mora seu código de pacote.

### `homepage` [](#toc-homepage){#toc-homepage.toc}

```json
{
  "homepage": "https://your-package.org"
}
```

A homepage é a URL para a página inicial ou a documentação do seu pacote.

### `bugs` [](#toc-bugs){#toc-bugs.toc}

```json
{
  "bugs": "https://github.com/user/repo/issues"
}
```

A URL para o rastreador de problemas do seu projeto. Isso também pode ser algo como um endereço de e-mail. Oferece aos usuários uma maneira de descobrir para onde enviar questões sobre o pacote.

### `repository` [](#toc-repository){#toc-repository.toc}

```json
{
  "repository": { "type": "git", "url": "https://github.com/user/repo.git" },
  "repository": "github:user/repo",
  "repository": "gitlab:user/repo",
  "repository": "bitbucket:user/repo",
  "repository": "gist:a1b2c3d4e5f"
}
```

O repositório é o local onde está o código para o pacote.

## Mantedores [](#toc-maintainers){#toc-maintainers.toc}

Os mantendores do seu projeto.

### `author` [](#toc-author){#toc-author.toc}

```json
{
  "author": { "name": "Your Name", "email": "you@example.com", "url": "http://your-website.com" },
  "author": "Your Name <you@example.com> (http://your-website.com)"
}
```

Informações sobre o autor do pacote. O autor é uma pessoa.

### `contributors` [](#toc-contributors){#toc-contributors.toc}

```json
{
  "contributors": [
    { "name": "Your Friend", "email": "friend@example.com", "url": "http://friends-website.com" }
    { "name": "Other Friend", "email": "other@example.com", "url": "http://other-website.com" }
  ],
  "contributors": [
    "Your Friend <friend@example.com> (http://friends-website.com)",
    "Other Friend <other@example.com> (http://other-website.com)"
  ]
}
```

Aqueles que contribuíram para o seu pacote. Contribuintes são um conjunto de pessoas.

## Arquivos [](#toc-files){#toc-files.toc}

Você pode especificar arquivos que serão incluídos no seu projeto, juntamente com o ponto de entrada principal para o seu projeto.

### `files` [](#toc-files){#toc-files.toc}

```json
{
  "files": [
    "filename.js",
    "directory/",
    "glob/*.{js,json}"
  ]
}
```

Estes são arquivos que são incluídos em seu projeto. Você pode especificar arquivos individuais, pastas inteiras ou usar curingas para incluir arquivos que atendam a determinados critérios.

### `main` [](#toc-main){#toc-main.toc}

```json
{
  "main": "filename.js"
}
```

Este é o ponto de entrada principal para a funcionalidade para o seu projeto.

### `bin` [](#toc-bin){#toc-bin.toc}

```json
{
  "bin": "bin.js",
  "bin": {
    "command-name": "bin/command-name.js",
    "other-command": "bin/other-command"
  }
}
```

Arquivos executáveis incluídos com seu projeto que será instalado.

### `man` [](#toc-man){#toc-man.toc}

```json
{
  "man": "./man/doc.1",
  "man": ["./man/doc.1", "./man/doc.2"]
}
```

Se você tem páginas associadas com seu projeto, adicione-as aqui.

### `directories` [](#toc-directories){#toc-directories.toc}

```json
{
  "directories": {
    "lib": "path/to/lib/",
    "bin": "path/to/bin/",
    "man": "path/to/man/",
    "doc": "path/to/doc/",
    "example": "path/to/example/"
  }
}
```

Ao instalar o pacote, você pode especificar localizações exatas para colocar arquivos binários, páginas de manual, documentação, exemplos, etc.

## Tarefas [](#toc-tasks){#toc-tasks.toc}

Seu pacote pode incluir scripts executáveis ou outras configurações.

### `scripts` [](#toc-scripts){#toc-scripts.toc}

```json
{
  "scripts": {
    "build-project": "node build-project.js"
  }
}
```

Scripts são uma ótima maneira de automatizar tarefas relacionadas ao seu pacote, tais como processos de compilação simples ou ferramentas de desenvolvimento. Usando o campo de `"scripts"`, você pode definir vários scripts para ser executado como `yarn run < script >`. Por exemplo, o script de `compilação-projeto` acima pode ser chamado com `yarn run build-project` e irá executar o `node build-project`.

Certos nomes de script são especiais. Se definido, o script `preinstall` é chamado pelo Yarn antes que o pacote seja instalado. Por razões de compatibilidade, scripts chamado `install` `postinstall` e `prepublish` serão todos chamados depois que seu pacote acabou de instalar.

O script`state` é o padrão `node server.js`.

### `config` [](#toc-config){#toc-config.toc}

```json
{
  "config": {
    "port": "8080"
  }
}
```

Opções de configuração ou parâmetros utilizados em seus scripts.

## Dependências [](#toc-dependencies){#toc-dependencies.toc}

Seu pacote muito provavelmente vai depender de outros pacotes. Você pode especificar as dependências no seu arquivo `package.json`.

### `dependencies` [](#toc-dependencies){#toc-dependencies.toc}

```json
{
  "dependencies": {
    "package-1": "^3.1.4"
  }
}
```

Estas são as dependências que são necessárias tanto no desenvolvimento quanto na produção do pacote.

> Você pode especificar uma versão exata, uma versão mínima (por exemplo, `> =`) ou um intervalo de versões (por exemplo, `> =... <`).

### `devDependecies` [](#toc-devdependencies){#toc-devdependencies.toc}

```json
{
  "devDependencies": {
    "package-2": "^0.4.2"
  }
}
```

Estes são os pacotes que são somente necessários quando no desenvolvimento do pacote, mas não será instalado na produção.

### `peerDependencies` [](#toc-peerdependencies){#toc-peerdependencies.toc}

```json
{
  "peerDependencies": {
    "package-3": "^2.7.18"
  }
}
```

Dependências de mesmo nível permitem a compatibilidade do estado do seuepacote com versões de outros pacotes.

### `optionalDependencies` [](#toc-optionaldependencies){#toc-optionaldependencies.toc}

```json
{
  "optionalDependencies": {
    "package-5": "^1.6.1"
  }
}
```

Dependências opcionais podem ser usadas com seu pacote, mas não são necessárias. Se um pacote opcional não é encontrado, a instalação continua.

### `bundledDependencies` [](#toc-bundleddependencies){#toc-bundleddependencies.toc}

```json
{
  "bundledDependencies": [
    "package-4"
  ]
}
```

Dependências de pacotes são uma matriz de nomes de pacote que irão ser empacotados juntos na publicação do pacote.

### `flat` [](#toc-flat){#toc-flat.toc}

```json
{
  "flat": true
}
```

Se seu pacote permite apenas uma versão de uma determinada dependência e você gostaria de impor o mesmo comportamento de [`yarn install --flat`]({{url_base}}/docs/cli/install#toc-yarn-install-flat) na linha de comando, defina isto como `true`.

Observe que se seu `package.json` contém `"flat": true` e outros pacotes dependem de sua (por exemplo, você está construindo uma biblioteca em vez de um aplicativo), esses outros pacotes também precisarão de `"flat": true` em seus `package.json` ou que sejam instalado com `yarn install --flat` na linha de comando.

## Sistema [](#toc-system){#toc-system.toc}

Você pode fornecer informações de nível de sistema associado com seu pacote, tais como compatibilidade de sistema operacional, etc.

### `engines` [](#toc-engines){#toc-engines.toc}

```json
{
  "engines": {
    "node": ">=4.4.7 <7.0.0",
    "zlib": "^1.2.8",
    "yarn": "^0.14.0"
  }
}
```

Os engine especificam as versões de clientes que devem ser usadas com o seu pacote. Isto verifica contra `process.versions`, bem como a versão atual yarn.

### `os` [](#toc-os){#toc-os.toc}

```json
{
  "os": ["darwin", "linux"],
  "os": ["!win32"]
}
```

This specifies operating system compatibility for your package. It checks against `process.platform`.

### `cpu` [](#toc-cpu){#toc-cpu.toc}

```json
{
  "cpu": ["x64", "ia32"],
  "cpu": ["!arm", "!mips"]
}
```

Use this to specify your package will only run on certain CPU architectures. This checks against `process.arch`.

## Publicando [](#toc-publishing){#toc-publishing.toc}

### `private` [](#toc-private){#toc-private.toc}

```json
{
  "private": true
}
```

Se você não quiser que seu pacote seja publicado em um gerenciador de pacote, defina isso como `true`.

### `publishConfig` [](#toc-publishconfig){#toc-publishconfig.toc}

```json
{
  "publishConfig": {
    ...
  }
}
```

Esses valores de configuração vão ser usados na publicação do seu pacote. Você pode identificar seu pacote, por exemplo.