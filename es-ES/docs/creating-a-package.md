* * *

id: doc_creando_un_paquete guide: doc_creando_un_paquete layout: guide

* * *

{% include vars.html %}

Un **paquete** es un directorio con código que contiene un archivo `package.json` que provee información a Yarn acerca del paquete.

La mayoría de los paquetes utiliza algún tipo de sistema de control de versiones. El más común es git pero con Yarn no importa cuál hayas seleccionado. Para esta guia, los ejemplos se harán en git.

> **Nota: ** Si quieres seguir esta guía. asegúrese de instalar primero [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) y [Yarn]({{url_base}}/docs/install).

### Creando tu primer paquete [](#toc-creating-your-first-package){#toc-creating-your-first-package.toc}

Para crear tu primer paquete, abra el terminal/consola del sistema y ejecute los siguientes comandos:

```sh
git init mi-proyecto
cd mi-proyecto
yarn init
```

Esto va a crear un nuevo repositorio git, entra en él y entonces se inicia un formulario interactivo para la creación de un nuevo proyecto Yarn con las siguientes preguntas:

```sh
name (mi-proyecto):
version (1.0.0):
description:
entry point (index.js):
git repository:
author:
license (MIT):
```

Puedes escribir respuestas para cada de estas preguntas o puedes simplemente dar enter para utilizar el valor por defecto o dejarlo en blanco.

> **Tip: ** Si quieres utilizar los valores predeterminados para todo también puedes utilizar el comando `yarn init --yes` y omitirá todas las preguntas.

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

Los campos que ves en el `package.json` tienen los siguientes significados:

- **name** es el identificador del paquete, si vas a publicarlo en un registro global asegúrate de que es un nombre único.
- **version** es la versionamiento semantico del paquete, puedes publicar un paquete tantas veces quieras pero usando versiones diferentes.
- **description** es un campo opcional pero recomendado que es usado por otros usuarios de Yarn para encontrar y entender tu proyecto.
- **main** es usado para definir el punto de entrada de tu código usado por programas como Node.js. Si no especificas ningún punto de entrada, por defecto será `index.js`.
- **repository** es un campo opcional pero recomendado que provee a los usuarios que usan el paquete de la ruta hacia el código fuente del paquete.
- **author** es el creador o responsable del paquete. Sigue el formato `"Your name <you@example.com> (http://your-website.com)"`
- **license** son los términos legales del paquete y define el uso permitido del código del mismo.

Cuando ejecutas `yarn init`, todo lo que esta haciendo es crear este archivo, en el fondo no pasa mas nada. Puedes editar este archivo tanto como quieras.

#### Campos adicionales [](#toc-additional-fields){#toc-additional-fields.toc}

Let's go through some additional `package.json` fields you might want to add.

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

- **keywords** is a list of terms that other developers can search for to find your package or related packages.
- **homepage** is a url to point users to a website that informs them on the package with an introduction, documentations, and links to additional resources.
- **bugs** is a url to point users of your package to if they discover an issue with your package.
- **contributors** is a list of contributors to the package. If there are other people involved in your project, you can specify them here.
- **files** is a list of files that should be included in your package when published and installed. If unspecified Yarn will include every file.
- **bin** is a mapping of cli commands (binaries) for Yarn to create for the package when installing it.

For a complete list of all the `package.json` fields and more details about each of the above fields please see the [`package.json` documentation]({{url_base}}/docs/package-json).

### Licensing and open source [](#toc-licensing-and-open-source){#toc-licensing-and-open-source.toc}

Yarn packages are generally encouraged to be [open source](https://opensource.org/definition), however it's important to note that they aren't inherently open source by simply publishing them.

In order for code to be open source it needs to have an open source license. There are many open source licenses to choose from, here are a couple of common ones:

- [MIT License](http://choosealicense.com/licenses/mit/)
- [Apache License 2.0](http://choosealicense.com/licenses/apache-2.0/)
- [GNU General Public License 3.0](http://choosealicense.com/licenses/gpl-3.0/)

If you want more options, you can get [a more complete list here](http://choosealicense.com/licenses/).

When you select an open source license for your package, be sure to add a `LICENSE` file in the root of your package with the license text and update your `package.json` `license` field.

> **Note**: If you do not want your project to be licensed as an open source project, you should be explicit about what the licensing is or if it is unlicensed.

### Code sharing [](#toc-code-sharing){#toc-code-sharing.toc}

You will likely want to allow users of your package to be able to access your source code and have a way to report issues. There are a couple of popular websites for hosting your code:

- [GitHub](https://github.com)
- [GitLab](https://about.gitlab.com/)
- [Bitbucket](https://bitbucket.org/)

These sites will allow your users to see your code, report issues, and contribute back. Once you have your code up somewhere you should add the following fields to your `package.json`:

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

### Documentation [](#toc-documentation){#toc-documentation.toc}

You should ideally write your documentation before you go publishing your package. At a minimum you should write a `README.md` file in the root of your project that introduces your package and documents the public API.

Good documentation is defined by giving users all the knowledge they'll need to get started with your project and continued use of it. Think about the questions someone who knows nothing about your project will have. Describe things accurately and as detailed as necessary, but also try to keep it brief and easy to read. **Projects with high quality documentation are far more successful.**

### Keep packages small [](#toc-keep-packages-small){#toc-keep-packages-small.toc}

When creating Yarn packages, you are encouraged to keep them small and simple. Break large packages into many small ones if it makes sense to do so. This is highly encouraged as Yarn is capable of installing hundreds or even thousands of packages very efficiently.

Many small packages are a great model of package management. Often this leads to smaller download sizes because you aren't bundling massive dependencies and only using a small piece of it.

You should also consider the contents of your package. Make sure you aren't accidentally distributing your tests or any other files that aren't necessary for using your package (build scripts, images, etc).

Also be careful of what packages you are depending on, prefer smaller dependencies unless you have a good reason not to. Be certain that you aren't accidentally depending on something massive.