* * *

id: docs_creating_a_package guide: docs_creating_a_package layout: guide

* * *

{% include vars.html %}

**package** é um diretório com código e o arquivo `package.json` que fornece informação para o Yarn sobre o seu pacote.

A maioria dos pacote usam algum tipo de sistema de controle de versão. O mais comum é git, mas o Yarn não liga qual você escolhe. Para este guia, nosso exemplo ira usar git.

> **Nota:** Se você quer seguir este guia, certifique-se de instalar [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) e [Yarn]({{url_base}}/docs/install).

### Criando seu primeiro pacote [](#toc-creating-your-first-package){#toc-creating-your-first-package.toc}

Para criar seu primeiro pacote, abra seu terminal/console de sistema e execute os seguintes comandos:

```sh
git init my-new-project
cd my-new-project
yarn init
```

Isso vai criar um novo repositório git, coloca-lo na pasta, e abrir um formulário interativo para criar um novo projeto yarn com as seguintes questões:

```sh
name (my-new-project):
version (1.0.0):
description:
entry point (index.js):
git repository:
author:
license (MIT):
```

Você pode digitar as respostas para cada um dos campos ou só apertar enter/return para usar o padrão ou deixar em branco.

> **Dica:** Se você quer usar os padrões para tudo, pode executar `yarn init --yes` e também ignorará todas as perguntas.

### `package.json` [](#toc-package-json){#toc-package-json.toc}

Agora você deve ter um `package.json` que parece com isso:

```json
{
  "name": "my-new-project",
  "version": "1.0.0",
  "description": "My New Project description.",
  "main": "index.js",
  "repository": {
    "url": "https://example.com/your-username/my-new-project",
    "type": "git"
  },
  "author": "Your Name <you@example.com>",
  "license": "MIT"
}
```

Os campos que você vê no `package.json` tem os seguintes significados:

- **name** é o identificador do seu pacote, se você vai publicá-lo no registro global, você precisa ter certeza que é único.
- **version** é a versão semver-compatible do seu pacote, para você publicar o pacote o quanto você quiser, mas eles devem ter novas versões.
- **description** é um campo opcional, max recomendado, que é usado por outros usuários do Yarn para o projeto ser procurado e entendido.
- **main** é usado para definir o ponto de entrada do seu código e é usado por programas como Node.js. Se não especificado, o padrão será `index.js`.
- **repository** é outro campo opcional mas recomendado para ajudar os usuários do seu pacote achar o código fonte para contribuir.
- **author** é o criador ou mantedor de um pacote. Segue o formato `"Seu Nome <voce@exemplo.com>(http://seu-website.com)"`
- **license** são os tempos legais de publicação do seu pacote e o qual é a permissão de uso do código do seu pacote.

Quando você executa `yarn init`, ele só esta criando esse arquivo, nada acontece no fundo. Você pode editar esse arquivo o quando você quiser.

#### Campos adicionais [](#toc-additional-fields){#toc-additional-fields.toc}

Vamos ver alguns campos adicionais do `package.json` que você pode querer adicionar.

```json
{
  "name": "my-new-project",
  "...": "...",
  "keywords": ["cool", "useful", "stuff"],
  "homepage": "https://my-new-project-website.com",
  "bugs": "https://github.com/you/my-new-project/issues",
  "contributors": [
    "Your Friend <their-email@example.com> (http://their-website.com)",
    "Another Friend <another-email@example.com> (https://another-website.org)"
  ],
  "files": [
    "index.js",
    "lib/*.js",
    "bin/*.js"
  ],
  "bin": {
    "my-new-project-cli": "bin/my-new-project-cli.js"
  }
}
```

- **keywords** é uma lista de termos que outros desenvolvedores podem procurar para achar seu pacote ou pacotes relacionados.
- **homepage** é uma url que aponta usuários para o seu website que os informa sobre o pacote com uma introdução, documentação e links para recursos adicionais.
- **bugs** é uma url que aponta os usuários do seu pacote case eles descubram um problema com seu pacote.
- **contributors** é uma lista de colaboradores do seu pacote. Se há outras pessoas envolvidas no projeto, elas podem ser especificadas aqui.
- **files** é uma lista de arquivos que devem ser incluídos no pacote quando publicado e instalado. Se não especificado, Yarn vai incluir todos os arquivos.
- **bin** é um mapeamento de comandos cli(binários) para o Yarn para o pacote quando instalá-do.

Para uma lista completa de todos os campos do `package.json` e mais detalhes sobre cada campo acima, por favor veja [`package.json` documentation]({{url_base}}/docs/package-json).

### Licenciamento e de código aberto [](#toc-licensing-and-open-source){#toc-licensing-and-open-source.toc}

Pacotes Yarn são geralmente incentivados a ser [open source](https://opensource.org/definition). no entanto, é importante notar que pacotes não são inerentemente aberto simplesmente publicando-os.

Para seu código ser abeto, ele precisa ter uma licença de código aberto. Há muitas licenças de código aberto para escolher, algumas das mais comuns são:

- [Licença MIT](http://choosealicense.com/licenses/mit/)
- [Licença Apache 2.0](http://choosealicense.com/licenses/apache-2.0/)
- [Licença Pública Geral GNU 3.0](http://choosealicense.com/licenses/gpl-3.0/)

Se você quer mais opções, você pode checar [uma lista mais completa aqui](http://choosealicense.com/licenses/).

Quando você escolhe uma licença de código aberto para seu pacote, certifique-se de adicionar o arquivo `LICENSE` na na pasta raiz do seu pacote com o texto da licença e atualize seu campo `license` no arquivo `package.json`.

> **Nota:** Se você não quer que seu projeto seja licenciado como um projeto de código aberto, você devera ser explícito sobre o licenciamento ou é sem licença.

### Compartilhamento de código [](#toc-code-sharing){#toc-code-sharing.toc}

Você provavelmente ira querer que os usuários do seu pacote sejam capazes de acessar o código fonte e terem maneiras de reportar problemas. Há alguns websites populares para hospedagem do seu código:

- [GitHub](https://github.com)
- [GitLab](https://about.gitlab.com/)
- [BitBucket](https://bitbucket.org/)

Esses sites permitem que usuários vejam seu código, reportem problemas e contribuam com o projeto. Quando você tiver seu código em algum lugar você deve adicionais os seguintes campos no seu arquivo `package.json`:

```json
{
  "homepage": "https://github.com/username/my-new-project",
  "bugs": "https://github.com/username/my-new-project/issues",
  "repository": {
    "url": "https://github.com/username/my-new-project",
    "type": "git"
  }
}
```

### Documentação [](#toc-documentation){#toc-documentation.toc}

Você deve, idealmente, escrever uma documentação antes de publicar seu pacote. O mínimo que você deve escrever é um arquivo `README.md` na pasta raíz do seu projetos que introduz seu pacote e documenta a API pública.

Boa documentação é definida por dar aos usuários todo conhecimento preciso para começar, e continuar, a usar seu projeto. Pense sobre as questões que alguém que não saiba nada sobre seu projeto possa ter. Descreva coisas com precisão e detalhamento, conforme o necessário, mas também tente deixa-lo breve e fácil de ler. **Projetos com documentação de alta qualidade são muito mais bem sucedidos.**

### Mantenha pacotes pequenos [](#toc-keep-packages-small){#toc-keep-packages-small.toc}

Enquanto criando pacotes Yarn, você é incentivado a deixa-los pequenos e simples. Quebre grandes pacotes e pacotes menos, se tiver sentido fazê-lo. Isso é altamente recomendado, já que Yarn é capaz de instalar centenas, ou ate milhares, de pacotes de forma muito eficiente.

Pacotes pequenos são um grande modelo de gerenciamento de pacotes. Isso conduz frequentemente a menores tamanhos de download, já que não há o empacotamento massivo de dependências e só se usa um pequeno pedaço do pacote.

Você deve considerar também o conteúdo do seu pacote. Certifique-se que você não esta distribuindo acidentalmente seus testes e outros arquivos que não são necessários para o uso do seu pacote (script de compilação, imagens, etc).

Também tenha cuidado de quais pacotes são dependidos, de preferência a pacotes pequeno, ao menos que você tenha uma boa razão para fazer o contrário. Certifique-se que não esta acidentalmente dependendo de algo massivo.