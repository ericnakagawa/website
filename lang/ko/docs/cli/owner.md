* * *

id: docs_cli_owner guide: docs_cli layout: guide

* * *

<p class="lead">Manage package owners.</p>

### What is a package owner? [](#toc-what-is-a-package-owner){#toc-what-is-a-package-owner.toc}

A package "owner" in the registry is a user that has access to make changes to a package. A single package can have as many owners as you want.

Owners have permission to do the following tasks:

  1. Publish new versions of the package
  2. Add or remove other owners of the package
  3. Change metadata for a package

### Caveats [](#toc-caveats){#toc-caveats.toc}

There aren't any other levels of access at this time. All users can either modify a package or they cannot. In the future, there may be more types of roles, but not at this time.

### Commands [](#toc-commands){#toc-commands.toc}

##### `yarn owner ls <package>` [](#toc-yarn-owner-ls){#toc-yarn-owner-ls.toc}

Lists all of the owners of a `<package>`.

##### `yarn owner add <user> <package>` [](#toc-yarn-owner-add){#toc-yarn-owner-add.toc}

Adds the `<user>` as an owner of the `<package>`. You must already be an owner of the `<package>` in order to run this command.

##### `yarn owner rm <user> <package>` [](#toc-yarn-owner-rm){#toc-yarn-owner-rm.toc}

Removes the `<user>` as an owner of the `<package>`. You must already be an owner of the `<package>` in order to run this command.