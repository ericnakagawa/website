* * *

id: docs_cli_index guide: docs_cli layout: guide

* * *

{% include vars.html %}

Yarn menyediakan banyak perintah command-line untuk membantu anda dalam berbagai aspek, termasuk instalasi, administrasi, dukugan penerbitan paket, dan lain lain.

While all of the available commands are provided here, in alphabetical order, some of the more popular commands are:

- [`yarn add`]({{url_base}}/docs/cli/add): adds a package to use in your current package.
- [`yarn init`]({{url_base}}/docs/cli/init): initializes the development of a package.
- [`yarn install`]({{url_base}}/docs/cli/install): installs all the dependencies defined in a `package.json` file.
- [`yarn publish`]({{url_base}}/docs/cli/publish): publishes a package to a package manager.
- [`yarn remove`]({{url_base}}/docs/cli/remove): removes an unused package from your current package.

## Default Command [](#toc-default-command){#toc-default-command.toc}

Running `yarn` with no command will run `yarn install`, passing through any provided flags.

## Concurrency and `--mutex` [](#toc-concurrency-and-mutex){#toc-concurrency-and-mutex.toc}

When running multiple instances of yarn as the same user on the same server, you can ensure only one instance runs at any given time (and avoid conflicts) by passing the global flag `--mutex` followed by `file` or `network`.

When using `file` Yarn will write/read a mutex file `.yarn-single-instance` in the current working directory by default. You can also specify an alternate or global filename.

```sh
--mutex file
--mutex file:/tmp/.yarn-mutex
```

When using `network` Yarn will create a server at port `31997` by default. You can also specify an alternate port.

```sh
--mutex network
--mutex network:30330
```