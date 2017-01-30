* * *

id: docs_cli_upgrade guide: docs_cli layout: guide additional_reading_tags: ["cli-add", "cli-tag", "dependencies-versions"]

* * *

{% include vars.html %}

<p class="lead">Meningkatkan paket yang sudah diinstal ke versi yang terbaru, berdasarkan jarak versi yang ditentukan.</p>

##### `yarn upgrade` [](#toc-yarn-upgrade){#toc-yarn-upgrade.toc}

Perintah ini akan meningkatkan semua paket yang sudah diinstal ke versi yang terbaru berdasarkan jarak versi yang ditentukan di `package.json`. File `yarn.lock` akan diperbarui juga.

```sh
yarn upgrade
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 867 new dependencies.
    [...]
    ├─ jest-cli@16.0.1
    │  ├─ yargs-parser@3.2.0
    │  └─ yargs@5.0.0
    ├─ jest-diff@16.0.0
    │  └─ diff@3.0.1
    [...]
    └─ yargs@4.8.1
    ✨  Done in 20.79s.
    

##### `yarn upgrade [package]` [](#toc-yarn-upgrade-package){#toc-yarn-upgrade-package.toc}

Perintah ini akan meningkatkan paket yang ditentukan ke versi yang terbaru. Versi yang terbaru adalah versi yang di tandai `latest` (ada kemungkinan perintah ini akan meningkatkan versi utama paket tersebut).

```sh
yarn upgrade d3-scale
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ d3-scale@1.0.3
    ✨  Done in 6.10s.
    

This will update your `package.json` to look like this:

```diff
-  "d3-scale": "^0.9.3",
+  "d3-scale": "^1.0.3",
```

##### `yarn upgrade [package@version]` [](#toc-yarn-upgrade-package-version){#toc-yarn-upgrade-package-version.toc}

This will upgrade (or downgrade) an installed package to the specified version. You can use any [SemVer]({{url_base}}/docs/dependency-versions#toc-semantic-versioning) version number or range.

```sh
yarn upgrade d3-scale@1.0.2
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ d3-scale@1.0.2
    ✨  Done in 6.43s.
    

This will update your `package.json` to look like this:

```diff
-  "d3-scale": "^1.0.3",
+  "d3-scale": "^1.0.2",
```

##### `yarn upgrade [package@tag]` [](#toc-yarn-upgrade-package-tag){#toc-yarn-upgrade-package-tag.toc}

This will upgrade a package to the version identified by `tag`. [Tag]({{url_base}}/docs/cli/tag#toc-what-are-tags) names are chosen by project maintainers, typically you use this command to install an experimental or long term support release of an actively developed package. The tag you choose will be the version that appears in your `package.json` file.

```sh
yarn upgrade react@next
```

    yarn upgrade v0.16.0
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ react@15.4.0-rc.4
    ✨  Done in 3.73s.
    

This will update your `package.json` to look like:

```diff
-  "react": "^15.3.2",
+  "react": "next",
```

Similarly, using the `latest` tag will result in an updated `package.json` that looks like:

```diff
-  "react": "^15.3.2",
+  "react": "latest",
```

##### `yarn upgrade [package] --ignore-engines` [](#toc-yarn-upgrade-package-ignore-engines){#toc-yarn-upgrade-package-ignore-engines.toc}

This upgrades a single named package to the version specified by the `latest` tag ignoring engines check.

```sh
yarn upgrade d3-scale --ignore-engines
```

    yarn upgrade vx.x.x
    [1/4] 
    [2/4] 
    [3/4] 
    [4/4] 
    success Saved lockfile.
    success Saved 1 new dependency
    └─ d3-scale@1.0.3
    ✨  Done in 6.10s.
    

This will update your `package.json` to look like this:

```diff
-  "d3-scale": "^0.9.3",
+  "d3-scale": "^1.0.3",
```