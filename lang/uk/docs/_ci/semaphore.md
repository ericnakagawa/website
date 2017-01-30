В [Semaphore](https://semaphoreci.com/), Yarn встановлений за замовченням для всіх версій Node.js, що підтримуються сервісом. Отже кеш Yarn доступний без додаткових налаштувань.

Для того щоб переконатись, що ваша локальна версія Yarn співпадає з встановленою на Semaphore, додайте рядки зазначені нижче до ваших команд налаштування в Налаштуваннях проекту.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```