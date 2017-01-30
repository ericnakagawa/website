### Windows

There are two options for installing Yarn on Windows.

#### Загрузить установщик

This will give you a `.msi` file that when run will walk you through installing Yarn on Windows.

Если вы используете установщик, то для начала вам нужно установить [Node.js](https://nodejs.org/).<a class="btn btn-primary" href="/latest.msi">Download Installer</a>#### Install via Chocolatey

[Chocolatey](https://chocolatey.org/) is a package manager for Windows, you can install Chocolatey by following [these instructions](https://chocolatey.org/install).

После того как вы установите Chocolatey вы можете установить Yarn, введя в консоль команду:

```sh
choco install yarn
```

Также у вас должен быть установлен [Node.js](https://nodejs.org/).

#### Notice

Please whitelist your project folder and the Yarn cache directory (%LocalAppData%\Yarn) in your antivirus software, otherwise installing packages will be significantly slower as every single file will be scanned as it's written to disk.