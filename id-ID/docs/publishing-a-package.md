* * *

id: docs_publishing_a_package guide: docs_creating_a_package layout: guide

* * *

Untuk dapat membagikan paket anda dengan pengembang lain di seluruh dunia, anda perlu untuk menerbitkannya terlebih dahulu.

When you publish a package with Yarn it goes onto the [npm registry](https://www.npmjs.com/) which is used to distribute packages globally.

### Logging into npm [](#toc-logging-into-npm){#toc-logging-into-npm.toc}

If you haven't already, you'll first need to [create an npm account](https://www.npmjs.com/signup). Once you've done that you can setup your username and email in Yarn.

```sh
yarn login
```

This will prompt you for your username and email. However, it will not ask you for your password. Yarn does not hold onto your password or any sessions. When you go to publish or modify something on npm, you will need to enter your password then.

### Publishing your package [](#toc-publishing-your-package){#toc-publishing-your-package.toc}

Once you have written all the code in your package, tested it out and you are ready to publish you can kick things off:

```sh
yarn publish
```

First you will be asked to enter a new version to publish:

    [1/4] Bumping version...
    info Current version: 1.0.0
    question New version: _____
    

Next you will be asked to enter your npm password:

    [2/4] Logging in...
    info npm username: your-npm-username
    info npm username: you@example.com
    question npm password: ____________
    

Finally, Yarn will publish the package and revoke your session token.

    [3/4] Publishing...
    success Published.
    [4/4] Revoking token...
    success Revoked login token.
    ✨  Done in 10.53s.
    

Each time you want to publish a new version of your package you can follow this same flow.

### Accessing your package [](#toc-accessing-your-package){#toc-accessing-your-package.toc}

Your package should now be available at https://www.npmjs.com/package/my-new-project and you should be able to install it:

```sh
yarn add my-new-project
```

You can also see all the info in the npm registry:

```sh
yarn info my-new-project
```

```js
{ name: 'my-new-project',
  description: 'My New Project description.',
  'dist-tags': { latest: '1.0.0' },
  versions: [ '1.0.0' ],
  maintainers: [ { name: 'Your Name', email: 'you@example.com' } ],
  time:
  { modified: '{{ site.time | date_to_xmlschema }}',
    created: '{{ site.time | date_to_xmlschema }}',
    '1.0.0': '{{ site.time | date_to_xmlschema }}' },
  homepage: 'https://my-new-project-website.com/',
  keywords: [ 'cool', 'useful', 'stuff' ],
  repository:
   { url: 'https://example.com/your-username/my-new-project',
     type: 'git' },
  contributors:
   [ { name: 'Your Friend',
       email: 'their-email@example.com',
       url: 'http://their-website.com' },
     { name: 'Another Friend',
       email: 'another-email@example.com',
       url: 'https://another-website.org' } ],
  author: { name: 'Your Name', email: 'you@example.com' },
  bugs: { url: 'https://github.com/you/my-new-project/issues' },
  license: 'MIT',
  readmeFilename: 'README.md',
  version: '1.0.0',
  main: 'index.js',
  files: [ 'index.js', 'lib/*.js', 'bin/*.js' ],
  bin: { 'my-new-project-cli': 'bin/my-new-project-cli.js' },
  dist:
   { shasum: '908bc9a06fa4421e96ceda243c1ee1789b0dc763',
     tarball: 'https://registry.npmjs.org/my-new-project/-/my-new-project-1.0.0.tgz' },
  directories: {} }
```