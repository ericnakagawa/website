Bei [Semaphore](https://semaphoreci.com/) ist Yarn für alle unterstützten Node.js-Versionen vorinstalliert. Auch der Yarn Cache funktioniert ohne manuelle Anpassungen.

Um sicherzugehen, dass Ihre lokale Yarn Version mit der auf Semaphore übereinstimmt, fügen Sie die folgenden Zeilen unter Project Settings Ihren setup commands hinzu.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```