* * *

id: docs_creating_a_project guide: docs_yarn_workflow layout: guide

* * *

Não importa se você tem um repositório/diretório existente de código, ou se você está começando um projeto completamente novo, adicionar Yarn funciona da mesma maneira sempre.

No seu terminal/console, no diretório que você deseja adicionar Yarn (que quase sempre deve ser a raiz do seu projeto), execute o seguinte comando:

```sh
yarn init
```

Isto abrirá um formulário interativo para a criação de um novo projeto do Yarn com as seguintes perguntas:

    name (your-project):
    version (1.0.0):
    description:
    entry point (index.js):
    git repository:
    author:
    license (MIT):
    

Você pode digitar as respostas para cada um dos campos ou só apertar enter/return para usar o padrão ou deixar em branco.

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

Quando você executa `yarn init`, ele só esta criando esse arquivo, nada acontece no fundo. Você pode editar esse arquivo o quando você quiser.

Seu `package.json` é usado para armazenar informações sobre seu projeto. Isso inclui o nome do seu projeto, os mantedores, onde está o código-fonte, mas o mais importante: o que as dependências necessitam para serem instaladas no projeto.