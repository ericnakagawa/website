* * *

id: docs_creating_a_package guide: docs_creating_a_package layout: guide

* * *

{% include vars.html %}

Un **package** est un répertoire avec du code et un fichier `package.json` qui fournit des informations à Yarn sur votre package.

La plupart des packages utilisent une sorte de système de contrôle de version. Le plus souvent, c'est git mais ça ne dérange pas Yarn si vous en choisissez un autre. Pour ce guide, nos exemples vont utiliser git.

> **Remarque :** Si vous souhaitez suivre ce guide, assurez-vous d'installer d'abord [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) et [Yarn]({{url_base}}/docs/install).

### Création de votre premier package [](#toc-creating-your-first-package){#toc-creating-your-first-package.toc}

Afin de créer votre premier package, ouvrez le terminal/la console de votre système et exécutez les commandes suivantes :

```sh
git init my-new-project
cd my-new-project
yarn init
```

Cela va créer un nouveau dépôt git, positionnez vous à l’intérieur et puis ouvrez un formulaire interactif pour la création d’un nouveau projet yarn avec les questions suivantes :

```sh
name (my-new-project):
version (1.0.0):
description:
entry point (index.js):
git repository:
author:
license (MIT):
```

Vous pouvez répondre à chacune d'entre elles, ou vous pouvez appuyez simplement sur entrée/retour pour utiliser la valeur par défaut ou la laisser vide.

> **Astuce :** Si vous souhaitez utiliser les valeurs par défaut pour tout, vous pouvez également exécuter `yarn init --yes` et il ignore toutes les questions.

### `package.json` [](#toc-package-json){#toc-package-json.toc}

Vous devriez maintenant avoir un `package.json` qui ressemble à ceci :

```json
{
  "name": "mon-nouveau-projet",
  "version": "1.0.0",
  "description": "La description de mon nouveau projet.",
  "main": "index.js",
  "repository": {
    "url": "https://exemple.com/votre-nomutilisateur/mon-nouveau-projet",
    "type": "git"
  },
  "author": "Votre Nom <toi@exemple.com>",
  "license": "MIT"
}
```

Les champs que vous voyez dans le `package.json` ont les significations suivantes :

- **name** correspond à l’identificateur de votre package, si vous souhaitez publier sur le registre global, vous devez vous assurer qu’il soit unique.
- **version** est la version compatible semver de votre package, vous pouvez publier un package autant de fois que vous voulez, mais ils doivent avoir de nouvelle version.
- **description** est un champ facultatif, mais recommandé pour les autres utilisateurs de Yarn pour le chercher et comprendre votre projet.
- **main** is used to define the entry point of your code used by programs like Node.js. If unspecified it will default to `index.js`.
- **repository** is another optional but recommended field that helps users of your package find the source code to contribute back.
- **author** is the creator or maintainer of a package. It follows the format `"Your Name <you@example.com> (http://your-website.com)"`
- **license** is the published legal terms of your package and what is the allowed usage of the code in your package.

When you run `yarn init`, all it is doing is creating this file, nothing happens in the background. You can feel free to edit this file as much as you want.

#### Additional fields [](#toc-additional-fields){#toc-additional-fields.toc}

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