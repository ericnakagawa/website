* * *

id: docs_cli_cache guide: docs_cli layout: guide

* * *

##### `yarn cache ls` [](#toc-yarn-cache-ls){#toc-yarn-cache-ls.toc}

Yarn stores every package in a global cache in your user directory on the file system. `yarn cache ls` will print out every cached package.

##### `yarn cache dir` [](#toc-yarn-cache-dir){#toc-yarn-cache-dir.toc}

Running `yarn cache dir` will print out the path where yarn's global cache is currently stored.

##### `yarn cache clean` [](#toc-yarn-cache-clean){#toc-yarn-cache-clean.toc}

Running this command will clear the local cache. It will be populated again the next time `yarn` or `yarn install` is run.

### Change the cache path for yarn [](#toc-change-the-cache-path-for-yarn){#toc-change-the-cache-path-for-yarn.toc}

Set `cache-folder` config value to configure the cache directory.

```sh
yarn config set cache-folder <path>
```

You can also specify the cache directory by flag `--cache-folder`:

```sh
yarn <command> --cache-folder <path>
```