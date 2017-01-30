[Semaphore](https://semaphoreci.com/) дође са инсталираним Yarn-ом за све подржане Node.js верзије. Такође, никаква подешавања нису потребна да би се користили Yarn-ови претходно преузети пакети ради бржег извршавања градње.

Да бисте се осигурали да Yarn који је инсталиран на вашем систему одговара ономе који је инсталиран на Semaphore платформи, додајте ове инсталационе команде у ваша подешавања за пројекат.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```