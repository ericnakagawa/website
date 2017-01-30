* * *

id: docs_creating_a_project guide: docs_yarn_workflow layout: guide

* * *

It doesn't matter if you have an existing repository/directory of code, or if you are starting a completely new project, adding Yarn works the same way every time.

In your terminal/console in the directory that you want to add Yarn (which should almost always be the root of your project), run the following command:

```sh
yarn init
```

This will open up an interactive form for creating a new yarn project with the following questions:

    name (your-project):
    version (1.0.0):
    description:
    entry point (index.js):
    git repository:
    author:
    license (MIT):
    

Puedes escribir respuestas para cada de estas preguntas o puedes simplemente dar enter para utilizar el valor por defecto o dejarlo en blanco.

### `package.json` [](#toc-package-json){#toc-package-json.toc}

Ahora, debes tener un `package.json` que luce similar a este:

```json
{
  "name": "mi-proyecto,
  "version": "1.0.0",
  "description": "Descripción de mi proyecto",
  "main": "index.js",
  "repository": {
    "url": "https://example.com/your-username/mi-proyecto",
    "type": "git"
  },
  "author": "Your Name <you@example.com>",
  "license": "MIT"
}
```

Cuando ejecutas `yarn init`, todo lo que esta haciendo es crear este archivo, en el fondo no pasa mas nada. Puedes editar este archivo tanto como quieras.

Your `package.json` is used to store info about your project. This includes the name of your project, the maintainers, where the source code lives, but most importantly what dependencies are needed to be installed for the project.