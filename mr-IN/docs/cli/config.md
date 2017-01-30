* * *

id: docs_cli_config guide: docs_cli layout: guide

* * *

<p class="lead">Manages the yarn configuration files.</p>

##### `yarn config set <key> <value> [-g|--global]` [](#toc-yarn-config-set-g-global){#toc-yarn-config-set-g-global.toc}

Sets the config `key` to a certain `value`.

Example:

```sh
$ yarn config set init-license BSD-2-Clause
yarn config vx.x.x
success Set "init-license" to "BSD-2-Clause".
✨  Done in 0.05s.

```

##### `yarn config get <key>` [](#toc-yarn-config-get){#toc-yarn-config-get.toc}

Echoes the value for a given `key` to `stdout`.

Example:

```sh
$ yarn config get init-license
BSD-2-Clause
```

##### `yarn config delete <key>` [](#toc-yarn-config-delete){#toc-yarn-config-delete.toc}

Deletes a given `key` from the config.

Example:

```sh
$ yarn config delete test-key
yarn config vx.x.x
success Deleted "test-key".
✨  Done in 0.06s.
```

##### `yarn config list` [](#toc-yarn-config-list){#toc-yarn-config-list.toc}

Displays the current configuration.

Example:

```sh
$ yarn config list
yarn config vx.x.x
info yarn config
{ 'version-tag-prefix': 'v',
  'version-git-tag': true,
  'version-git-sign': false,
  'version-git-message': 'v%s',
  'init-version': '1.0.0',
  'init-license': 'MIT',
  'save-prefix': '^',
  'ignore-scripts': false,
  'ignore-optional': true,
  registry: 'https://registry.yarnpkg.com',
  'user-agent': 'yarn/0.15.0 npm/? node/v6.2.1 darwin x64' }
info npm config
{ registry: 'https://registry.npmjs.org/',
  '//localhost:4873/:_authToken': 'some-auth-token' }
✨  Done in 0.05s.

```