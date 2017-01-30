[Semaphore](https://semaphoreci.com/) ma Yarn wstępnie zainstalowany dla wszystkich obsługiwanych wersji Node.js, i żadne działanie użytkownika nie jest wymagane do pracy dla pamięci podręcznej Yarn.

Aby zapewnić, że lokalna wersja Yarn pasuje na Semaphore, należy dodać wiersze poniżej do Twoich poleceń ustawień, w ustawieniach projektu.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```