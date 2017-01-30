* * *

id: docs_cli_init guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Interactively creates or updates a package.json file.</p>

##### `yarn init` [](#toc-yarn-init){#toc-yarn-init.toc}

This command walks you through an interactive session to create a `package.json` file. Some defaults such as the license and initial version are found in yarn's `init-*` config settings.

Here's an example of running the command inside of a directory named `testdir`:

```sh
$ yarn init
```

```sh
question name (testdir): benim-harika-paketim
question version (1.0.0): 
question description: Bulabileceğiniz en iyi paket.
question entry point (index.js): 
question git repository: https://github.com/yarnpkg/example-yarn-package
question author: Yarn Contributor
question license (MIT): 
success Saved package.json
✨  Done in 87.70s.
```

This results in the following `package.json`:

```json
{
  "name": "benim-harika-paketim",
  "version": "1.0.0",
  "description": "Bulabileceğiniz en iyi paket.",
  "main": "index.js",
  "repository": {
    "url": "https://github.com/yarnpkg/example-yarn-package",
    "type": "git"
  },
  "author": "Yarn Contributor",
  "license": "MIT"
}
```

If you already have an existing `package.json` file, then it will use the file's entries as defaults.

The following existing `package.json`:

```json
{
  "name": "var-olan-paketim",
  "version": "0.1",
  "description": "Buradayım, öyleyse varım.",
  "repository": {
    "url": "https://github.com/yarnpkg/example-yarn-package",
    "type": "git"
  },
  "license": "BSD-2-Clause"
}
```

Results in the following defaults during the interactive session:

```sh
$ yarn init
```

```sh
question name (var-olan-paketim): 
question version (0.1): 
question description (Buradayım, öyleyse varım.):
question entry point (index.js): 
question git repository (https://github.com/yarnpkg/example-yarn-package): 
question author: Yarn Contributor
question license (BSD-2-Clause): 
success Saved package.json
✨  Done in 121.53s.
```

##### `yarn init` için varsayılan değerleri ayarlama [](#toc-setting-defaults-for-yarn-init){#toc-setting-defaults-for-yarn-init.toc}

The following [config]({{url_base}}/docs/cli/config) variables can be used to customize the defaults for `yarn init`:

- `init-author-name`
- `init-author-email`
- `init-author-url`
- `init-version`
- `init-license`

##### `yarn init --yes/-y` [](#toc-yarn-init-yes-y){#toc-yarn-init-yes-y.toc}

This command skips the interactive session mentioned above and generates a `package.json` based on your defaults. Some defaults may be modified changing `init-*` config settings like mentioned above. For example, given a fresh install of Yarn and inside a `yarn-example` directory:

```sh
$ yarn init --yes
```

    warning The yes flag has been set. This will automatically answer yes to all questions which may have security implications.
    success Saved package.json
    ✨  Done in 0.09s.
    

Which produces the following `package.json`:

```json
{
  "name": "yarn-example",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT"
}
```