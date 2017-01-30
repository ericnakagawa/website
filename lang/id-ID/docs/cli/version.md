* * *

id: docs_cli_version guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Memperbarui versi paket.</p>

### Updating versions [](#toc-updating-versions){#toc-updating-versions.toc}

Using the `yarn version` command you can update the version of your package via the command line.

For example, starting with this package.json `package.json`:

```js
{
  "name": "example-yarn-package",
  "version": "1.0.1",
  "description": "An example package to demonstrate Yarn"
}
```

When we run the `yarn version` command:

```sh
yarn version
```

    info Current version: 1.0.1
    question New version: 1.0.2
    info New version: 1.0.2
    ✨  Done in 9.42s.
    

We will get this updated `package.json`:

```json
{
  "name": "example-yarn-package",
  "version": "1.0.2",
  "description": "An example package to demonstrate Yarn"
}
```

> **Note:** The new version you enter must be a valid [SemVer]({{url_base}}/docs/dependency-versions#toc-semantic-versioning) version.

#### Git tags [](#toc-git-tags){#toc-git-tags.toc}

If you run `yarn version` within a Git repository a [Git tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging) will be created by default following the format `v0.0.0`.

You can customize the git tag that is created or disable this behavior by using `yarn config set`.

To change the prefix of the git tag you can use `version-tag-prefix`:

```sh
yarn config set version-tag-prefix "v"
```

Or you can change the git message using `version-git-message` where `%s` is the version string:

```sh
yarn config set version-git-message "v%s"
```

You can also turn signing git tags on or off using `version-git-sign`:

```sh
yarn config set version-git-sign false
```

You can even enabled or disable the git tagging behavior entirely by using `version-git-tag`:

```sh
yarn config set version-git-tag true
```

### Commands [](#toc-commands){#toc-commands.toc}

##### `yarn version` [](#toc-yarn-version){#toc-yarn-version.toc}

Create a new version using an interactive session to prompt you for a new version.

##### `yarn version --new-version <version>` [](#toc-yarn-version-new-version){#toc-yarn-version-new-version.toc}

Creates a new version specified by `<version>`.

##### `yarn version --no-git-tag-version` [](#toc-yarn-version-no-git-tag-version){#toc-yarn-version-no-git-tag-version.toc}

Creates a new version without creating a git tag.