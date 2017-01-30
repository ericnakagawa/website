* * *

id: docs_cli_publish guide: docs_cli layout: guide

* * *

<p class="lead">Menerbitkan sebuah paket ke registri npm.</p>

Setelah paket diterbitkan, anda tidak diperkenankan untuk mengubah versi terkait, maka berhati-hatilah sebelum menerbitkan paket anda.

##### `yarn publish` [](#toc-yarn-publish){#toc-yarn-publish.toc}

Publishes the package defined by the `package.json` in the current directory.

##### `yarn publish [berkas]` [](#toc-yarn-publish-tarball){#toc-yarn-publish-tarball.toc}

Menerbitkan paket yang didefinisikan oleh sebuah berkas gzip `.tgz`.

##### `yarn publish [folder]` [](#toc-yarn-publish-folder){#toc-yarn-publish-folder.toc}

Publishes the package contained in the specified folder. `<folder>/package.json` should specify the package details.

##### `yarn publish --tag <tag>` [](#toc-yarn-publish-tag){#toc-yarn-publish-tag.toc}

Provided a tag to `yarn publish` lets you publish packages with a specific tag. For example, if you do a `yarn publish --tag beta`, and your package is named `blorp`, then someone else can install that package with `yarn add blorp@beta`.

##### `yarn publish --access <public|restricted>` [](#toc-yarn-publish-access){#toc-yarn-publish-access.toc}

The `--access` flag controls whether the npm registry publishes this package as a public package, or restricted.