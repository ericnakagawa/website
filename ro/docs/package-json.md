* * *

id: docs_configuration_package_json guide: docs_configuration layout: guide

* * *

{% include vars.html %}

## Essentials [](#toc-essentials){#toc-essentials.toc}

The two most important fields in your `package.json` are `name` and `version`, without them your package won't be able to install. The `name` and `version` fields are used together to create a unique id.

### `name` [](#toc-name){#toc-name.toc}

```json
{
  "name": "my-awesome-package"
}
```

This is the name of your package. It gets used in URLs, as an argument on the command line, and as the directory name inside `node_modules`.

```sh
yarn add [name]
```

    node_modules/[name]
    

    https://registry.npmjs.org/[name]/-/[name]-[version].tgz
    

**Reguli**

- Must be less than or equal to 214 characters (including the `@scope/` for scoped packages).
- Must not start with a dot (`.`) or an underscore (`_`).
- Must not have an uppercase letter in the name.
- Must use only URL-safe characters.

**Recomandări**

- Don't use the same name as a core Node.js module
- Don't put `js` or `node` in the name.
- Keep names short and descriptive. You want people to understand what it is from the name, but it will also be used in `require()` calls.
- Make sure that there isn't something in the [registry](https://www.npmjs.com/) with the same name.

### `version` [](#toc-version){#toc-version.toc}

```json
{
  "version": "1.0.0"
}
```

The current version of your package.

## Info [](#toc-info){#toc-info.toc}

### `description` [](#toc-description){#toc-description.toc}

```json
{
  "description": "Descrierea mea scurtă a pachetului meu minunat"
}
```

The description is just a string that helps people understand the purpose of the package. It can be used when searching for packages in a package manager as well.

### `keywords` [](#toc-keywords){#toc-keywords.toc}

```json
{
  "keywords": ["cuvinte cheie", "scurte", "și", "relevante", "pentru", "căutare"]
}
```

Keywords are an array of strings that are useful when searching for packages in a package manager.

### `license` [](#toc-license){#toc-license.toc}

```json
{
  "license": "MIT",
  "license": "(MIT or GPL-3.0)",
  "license": "VEZI LICENȚĂ ÎN LICENSE_FILENAME.txt",
  "license": "UNLICENSED"
}
```

All packages should specify a license so that users know how they are permitted to use it and any restrictions that you are placing on it.

You are encouraged to use an Open Source ([OSI-approved](https://opensource.org/licenses/alphabetical)) license unless you have a specific reason not to. If you built your package as part of your job it's likely best to check with your company before deciding on a license.

**Must be one of the following:**

- A valid [SPDX license identifier](https://spdx.org/licenses/) if you are using a standard license.
- A valid [SPDX license expression syntax 2.0 expression](https://www.npmjs.com/package/spdx) if you are using multiple standard licenses.
- A `SEE LICENSE IN <filename>` string that points to a `<filename>` in the top level of your package if you are using a non-standard license.
- A `UNLICENSED` string if you do not want to grant others the right to use a private or unpublished package under any terms.

## Link-uri [](#toc-links){#toc-links.toc}

Various links to documentation, places to file issues and where your package code actually lives.

### `homepage` [](#toc-homepage){#toc-homepage.toc}

```json
{
  "homepage": "https://pachetul-tau.org"
}
```

The homepage is the URL to the landing page or documentation for your package.

### `bugs` [](#toc-bugs){#toc-bugs.toc}

```json
{
  "bugs": "https://github.com/user/repo/issues"
}
```

The URL to your project's issue tracker. This can also be something like an email address as well. It provides users a way to find out where to send issues with your package.

### `repository` [](#toc-repository){#toc-repository.toc}

```json
{
  "repository": { "type": "git", "url": "https://github.com/user/repo.git" },
  "repository": "github:user/repo",
  "repository": "gitlab:user/repo",
  "repository": "bitbucket:user/repo",
  "repository": "gist:a1b2c3d4e5f"
}
```

The repository is the location where your the actual code for your package lives.

## Maintainers [](#toc-maintainers){#toc-maintainers.toc}

The maintainers of your project.

### `author` [](#toc-author){#toc-author.toc}

```json
{
  "author": { "name": "Numele Tău", "email": "tu@example.com", "url": "http://site-ul-tau.com" },
  "author": "Numele Tău <tu@example.com> (http://site-ul-tau.com)"
}
```

Package author information. An author is one person.

### `contributors` [](#toc-contributors){#toc-contributors.toc}

```json
{
  "contributors": [
    { "name": "Your Friend", "email": "friend@example.com", "url": "http://friends-website.com" }
    { "name": "Other Friend", "email": "other@example.com", "url": "http://other-website.com" }
  ],
  "contributors": [
    "Your Friend <friend@example.com> (http://friends-website.com)",
    "Other Friend <other@example.com> (http://other-website.com)"
  ]
}
```

Those that have contributed to your package. Contributors are an array of people.

## Fișiere [](#toc-files){#toc-files.toc}

You can specify files that will be included in your project, along with the main entry point for your project.

### `files` [](#toc-files){#toc-files.toc}

```json
{
  "files": [
    "filename.js",
    "directory/",
    "glob/*.{js,json}"
  ]
}
```

These are files that are included in your project. You can specify single files, whole directories or use wildcards to include files that meet a certain criteria.

### `main` [](#toc-main){#toc-main.toc}

```json
{
  "main": "filename.js"
}
```

This is the primary entry point for the functionality for your project.

### `bin` [](#toc-bin){#toc-bin.toc}

```json
{
  "bin": "bin.js",
  "bin": {
    "command-name": "bin/command-name.js",
    "other-command": "bin/other-command"
  }
}
```

Executable files included with your project that will be installed.

### `man` [](#toc-man){#toc-man.toc}

```json
{
  "man": "./man/doc.1",
  "man": ["./man/doc.1", "./man/doc.2"]
}
```

If you have man pages associated with your project, add them here.

### `directories` [](#toc-directories){#toc-directories.toc}

```json
{
  "directories": {
    "lib": "path/to/lib/",
    "bin": "path/to/bin/",
    "man": "path/to/man/",
    "doc": "path/to/doc/",
    "example": "path/to/example/"
  }
}
```

When installing your package, you can specify exact locations to put binary files, man pages, documentation, examples, etc.

## Tasks [](#toc-tasks){#toc-tasks.toc}

Your package can include runnable scripts or other configuration.

### `scripts` [](#toc-scripts){#toc-scripts.toc}

```json
{
  "scripts": {
    "build-project": "node build-project.js"
  }
}
```

Scripts are a great way of automating tasks related to your package, such as simple build processes or development tools. Using the `"scripts"` field, you can define various scripts to be run as `yarn run <script>`. For example, the `build-project` script above can be invoked with `yarn run build-project` and will run `node build-project.js`.

Certain script names are special. If defined, the `preinstall` script is called by yarn before your package is installed. For compatibility reasons, scripts called `install`, `postinstall`, and `prepublish` will all be called after your package has finished installing.

The `start` script value defaults to `node server.js`.

### `config` [](#toc-config){#toc-config.toc}

```json
{
  "config": {
    "port": "8080"
  }
}
```

Configuration options or parameters used in your scripts.

## Dependencies [](#toc-dependencies){#toc-dependencies.toc}

Your package will very likely depend on other packages. You can specify those dependencies in your `package.json` file.

### `dependencies` [](#toc-dependencies){#toc-dependencies.toc}

```json
{
  "dependencies": {
    "package-1": "^3.1.4"
  }
}
```

These are dependencies that are required in both development and production for your package.

> You can specify an exact version, a minimum version (e.g., `>=`) or a range of versions (e.g. `>= ... <`).

### `devDependencies` [](#toc-devdependencies){#toc-devdependencies.toc}

```json
{
  "devDependencies": {
    "package-2": "^0.4.2"
  }
}
```

These are packages that are only required when developing your package but will not be installed in production.

### `peerDependencies` [](#toc-peerdependencies){#toc-peerdependencies.toc}

```json
{
  "peerDependencies": {
    "package-3": "^2.7.18"
  }
}
```

Peer dependencies allow you to state compatibility of your package with versions of other packages.

### `optionalDependencies` [](#toc-optionaldependencies){#toc-optionaldependencies.toc}

```json
{
  "optionalDependencies": {
    "package-5": "^1.6.1"
  }
}
```

Optional dependencies can be used with your package, but are not required. If the optional package is not found, installation still continues.

### `bundledDependencies` [](#toc-bundleddependencies){#toc-bundleddependencies.toc}

```json
{
  "bundledDependencies": [
    "package-4"
  ]
}
```

Bundled dependencies are an array of package names that will be bundled together when publishing your package.

### `flat` [](#toc-flat){#toc-flat.toc}

```json
{
  "flat": true
}
```

If your package only allows one version of a given dependency, and you'd like to enforce the same behavior as [`yarn install --flat`]({{url_base}}/docs/cli/install#toc-yarn-install-flat) on the command line, set this to `true`.

Note that if your `package.json` contains `"flat": true` and other packages depend on yours (e.g. you are building a library rather than an application), those other packages will also need `"flat": true` in their `package.json` or be installed with `yarn install --flat` on the command line.

## System [](#toc-system){#toc-system.toc}

You can provide system-level information associated with your package, such as operating system compatibility, etc.

### `engines` [](#toc-engines){#toc-engines.toc}

```json
{
  "engines": {
    "node": ">=4.4.7 <7.0.0",
    "zlib": "^1.2.8",
    "yarn": "^0.14.0"
  }
}
```

The engines specify versions of clients that must be used with your package. This checks against `process.versions` as well as the current version of yarn.

### `os` [](#toc-os){#toc-os.toc}

```json
{
  "os": ["darwin", "linux"],
  "os": ["!win32"]
}
```

This specifies operating system compatibility for your package. It checks against `process.platform`.

### `cpu` [](#toc-cpu){#toc-cpu.toc}

```json
{
  "cpu": ["x64", "ia32"],
  "cpu": ["!arm", "!mips"]
}
```

Use this to specify your package will only run on certain CPU architectures. This checks against `process.arch`.

## Publishing [](#toc-publishing){#toc-publishing.toc}

### `private` [](#toc-private){#toc-private.toc}

```json
{
  "private": true
}
```

If you do not want your package published in a package manager, set this to `true`.

### `publishConfig` [](#toc-publishconfig){#toc-publishconfig.toc}

```json
{
  "publishConfig": {
    ...
  }
}
```

These configuration values will be used when publishing your package. You can tag your package, for example.