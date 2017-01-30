* * *

id: docs_managing_dependencies guide: docs_yarn_workflow layout: guide additional_reading_tags: ["dependencies", "package-json", "yarn-lock", "cli-add", "cli-upgrade", "cli-remove"]

* * *

{% include vars.html %}

When you want to add, upgrade, or remove dependencies there are a couple of different commands you need to know.

Each command will automatically update your [`package.json`]({{url_base}}/docs/package-json) and [`yarn.lock`]({{url_base}}/docs/yarn-lock) files.

### Bir bağımlılık ekleme [](#toc-adding-a-dependency){#toc-adding-a-dependency.toc}

If you want to use another package, you first need to add it as a dependency. In order to do that you should run:

```sh
yarn add [paket]
```

This will automatically add the `[package]` to your dependencies in your `package.json`. It will also update your `yarn.lock` to reflect the change.

```diff
  {
    "name": "my-package",
    "dependencies": {
+     "paket": "^1.0.0"
    }
  }
```

You can also add other [types of dependencies]({{url_base}}/docs/dependency-types) using flags:

- `yarn add --dev` to add to `devDependencies`
- `yarn add --peer` to add to `peerDependencies`
- `yarn add --optional` to add to `optionalDependencies`

You can specify which version of a package you want to install by specifying either a [dependency version]({{url_base}}/docs/dependency-versions) or a [tag]({{url_base}}/docs/cli/tag).

```sh
yarn add [package]@[version]
yarn add [package]@[tag]
```

The `[version]` or `[tag]` will be what gets added to your `package.json` and then resolved against when installing the dependency.

For example:

```sh
yarn add package-1@1.2.3
yarn add package-2@^1.0.0
yarn add package-3@beta
```

```json
{
  "dependencies": {
    "package-1": "1.2.3",
    "package-2": "^1.0.0",
    "package-3": "beta"
  }
}
```

### Bir bağımlılık güncelleme [](#toc-upgrading-a-dependency){#toc-upgrading-a-dependency.toc}

```sh
yarn upgrade [paket]
yarn upgrade [paket]@[versiyon]
yarn upgrade [paket]@[etiket]
```

This will upgrade your `package.json` and your `yarn.lock` file.

```diff
  {
    "name": "my-package",
    "dependencies": {
-     "package-1": "^1.0.0"
+     "package-1": "^2.0.0"
    }
  }
```

### Bir bağımlılık silme [](#toc-removing-a-dependency){#toc-removing-a-dependency.toc}

```sh
yarn remove [paket]
```

This will update your `package.json` and your `yarn.lock` file.