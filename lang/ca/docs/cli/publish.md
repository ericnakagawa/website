* * *

id: docs_cli_publish guide: docs_cli layout: guide

* * *

<p class="lead">Publishes a package to the npm registry.</p>

Once a package is published, you can never modify that specific version, so take care before publishing.

##### `yarn publish` [](#toc-yarn-publish){#toc-yarn-publish.toc}

Publishes the package defined by the `package.json` in the current directory.

##### `yarn publish [tarball]` [](#toc-yarn-publish-tarball){#toc-yarn-publish-tarball.toc}

Publishes the package defined by a `.tgz` gzipped tarball.

##### `yarn publish [folder]` [](#toc-yarn-publish-folder){#toc-yarn-publish-folder.toc}

Publishes the package contained in the specified folder. `<folder>/package.json` should specify the package details.

##### `yarn publish --tag <tag>` [](#toc-yarn-publish-tag){#toc-yarn-publish-tag.toc}

Provided a tag to `yarn publish` lets you publish packages with a specific tag. For example, if you do a `yarn publish --tag beta`, and your package is named `blorp`, then someone else can install that package with `yarn add blorp@beta`.

##### `yarn publish --access <public|restricted>` [](#toc-yarn-publish-access){#toc-yarn-publish-access.toc}

The `--access` flag controls whether the npm registry publishes this package as a public package, or restricted.