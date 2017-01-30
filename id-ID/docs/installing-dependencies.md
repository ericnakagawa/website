* * *

id: docs_installing_dependencies guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock", "cli-install"]

* * *

Apabila anda baru saja mendapatkan paket dari [version control](./version-control), anda perlu untuk menginstal dependensinya.

> If you are [adding dependencies](./managing-dependencies#toc-adding-a-dependency) for your project, then those dependencies are automatically installed during that process.

### Installing Dependencies [](#toc-installing-dependencies){#toc-installing-dependencies.toc}

[`yarn install`](./cli/install) is used to install all dependencies for a project. The dependencies are retrieved from your project's `package.json` file, and stored in the `yarn.lock` file.

When developing a package, installing dependencies is most commonly done after:

  1. You have just checked out code for a project that is creating a package.
  2. Another developer on the project has added a new dependency that you need to pick up.

### Installing Options [](#toc-installing-options){#toc-installing-options.toc}

There are many options for installing dependencies, including:

  1. Installing all dependencies: `yarn` or `yarn install`
  2. Installing one and only one version of a package: `yarn install --flat`
  3. Forcing a re-download of all packages: `yarn install --force`
  4. Installing only production dependencies: `yarn install --production`

See [the full list](./cli/install) of flags you can pass to `yarn install`.