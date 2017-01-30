[Semaphore](https://semaphoreci.com/) heeft Yarn voorgeïnstalleerd voor alle ondersteunde versies van Node.js. Je hoeft niks te doen om de Yarn cache te laten werken.

Om verzekerd te zijn dat je lokaal dezelfde Yarn versie gebruikt als op Semaphore, voeg de volgende regels toe aan je setup commands, in Project Settings.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```