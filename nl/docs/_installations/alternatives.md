### Alternatieven

Er zijn een aantal alternatieven als je een ander OS gebruikt of een van de versies specifiek voor jouw OS niet werkt. Indien je dit nog niet hebt gedaan, zul je [Node.js moeten installeren](https://nodejs.org/).

Op reguliere Linux distributies zoals Debian, Ubuntu en CentOS wordt het aangeraden om Yarn te installeren via onze packages.

{% include_relative _installations/tarball.md %}

#### Installeer via npm

> **Let op:**: Installatie via npm wordt niet aangeraden. npm is non-determinstic, packages are not signed, and npm does not perform any integrity checks other than a basic SHA1 hash, which is a security risk when installing system-wide apps.
> 
> For these reasons, it is highly recommended that you install Yarn through the installation method best suited to your operating system.

You can also install Yarn through the [npm package manager](http://npmjs.org/) if you already have it installed. If you already have [Node.js](https://nodejs.org/) installed then you should already have npm.

Once you have npm installed you can run:

```sh
npm install --global yarn
```

### Path Setup

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}