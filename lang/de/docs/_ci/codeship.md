Auf [Codeship](https://codeship.com/) können Sie Yarn als Teil des Builds installieren, indem Sie Ihren *Setup Commands* in den Projekteinstellungen dies hinzufügen:

```sh
npm install --global yarn
```

Falls Sie Codeship's [Docker Platform](https://pages.codeship.com/docker) verwenden empfiehlt es sich Yarn stattdessen durch [unser Debian/Ubuntu-Paket](https://yarnpkg.com/en/docs/install#linux) zu installieren.