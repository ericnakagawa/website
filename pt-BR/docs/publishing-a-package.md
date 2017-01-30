* * *

id: docs_publishing_a_package guide: docs_creating_a_package layout: guide

* * *

Para compartilhar seu pacote com outros desenvolvedores ao redor do mundo através do Yarn, você primeiro precisará publicá-lo.

Quando você publica um pacote com Yarn, ele vai para [registro npm](https://www.npmjs.com/) que é usado para distribuir pacotes globalmente.

### Login em npm [](#toc-logging-into-npm){#toc-logging-into-npm.toc}

Se você não tiver, você primeiro precisará [criar uma conta do npm](https://www.npmjs.com/signup). Depois de feito isso, você pode configurar seu nome de usuário e e-mail no Yarn.

```sh
yarn login
```

Isso solicitará seu nome de usuário e e-mail. No entanto, ele não vai pedir você sua senha. Yarn não guarda sua senha ou qualquer sessões. Quando você vai publicar ou modificar algo na npm, você precisará digitar sua senha em seguida.

### Publicando um Pacote [](#toc-publishing-your-package){#toc-publishing-your-package.toc}

Uma vez que você tenha escrito todo o código em seu pacote, testei fora e você está pronto para publicar você pode começar:

```sh
yarn publish
```

Primeiro será pedido para introduzir uma nova versão para publicar:

    [1/4] Bumping version...
    info Current version: 1.0.0
    question New version: _____
    

Em seguida você será solicitado a digitar sua senha npm:

    [2/4] Logging in...
    info npm username: your-npm-username
    info npm username: you@example.com
    question npm password: ____________
    

Finalmente, o Yarn publicará o pacote e revogará o token de sessão.

    [3/4] Publishing...
    success Published.
    [4/4] Revoking token...
    success Revoked login token.
    ✨  Done in 10.53s.
    

Cada vez que você deseja publicar uma nova versão de seu pacote, você pode seguir este mesmo fluxo.

### Acessando seu pacote [](#toc-accessing-your-package){#toc-accessing-your-package.toc}

Seu pacote agora deve estar disponível em https://www.npmjs.com/package/my-new-project e você deve ser capaz de instalá-lo:

```sh
yarn add my-new-project
```

Você também pode ver toda a informação no registro do npm:

```sh
yarn info my-new-project
```

```js
{ name: 'my-new-project',
  description: 'My New Project description.',
  'dist-tags': { latest: '1.0.0' },
  versions: [ '1.0.0' ],
  maintainers: [ { name: 'Your Name', email: 'you@example.com' } ],
  time:
  { modified: '{{ site.time | date_to_xmlschema }}',
    created: '{{ site.time | date_to_xmlschema }}',
    '1.0.0': '{{ site.time | date_to_xmlschema }}' },
  homepage: 'https://my-new-project-website.com/',
  keywords: [ 'cool', 'useful', 'stuff' ],
  repository:
   { url: 'https://example.com/your-username/my-new-project',
     type: 'git' },
  contributors:
   [ { name: 'Your Friend',
       email: 'their-email@example.com',
       url: 'http://their-website.com' },
     { name: 'Another Friend',
       email: 'another-email@example.com',
       url: 'https://another-website.org' } ],
  author: { name: 'Your Name', email: 'you@example.com' },
  bugs: { url: 'https://github.com/you/my-new-project/issues' },
  license: 'MIT',
  readmeFilename: 'README.md',
  version: '1.0.0',
  main: 'index.js',
  files: [ 'index.js', 'lib/*.js', 'bin/*.js' ],
  bin: { 'my-new-project-cli': 'bin/my-new-project-cli.js' },
  dist:
   { shasum: '908bc9a06fa4421e96ceda243c1ee1789b0dc763',
     tarball: 'https://registry.npmjs.org/my-new-project/-/my-new-project-1.0.0.tgz' },
  directories: {} }
```