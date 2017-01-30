[Semaphore](https://semaphoreci.com/) предоставляет предустановленный Yarn для всех поддерживаемых версий Node.js. От пользователя не требуется никаких дополнительных действий.

Для того, чтобы удостовериться, что Ваша локальная версия Yarn совпадает с установленной на Semaphore, добавьте следущие строки в ваши команды установки в "Настройках Проекта":

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package - это инструмент для кеширования APT установок для Semaphore
# Опционально, Вы можете указать желаемую версию Yarn
install-package yarn=<version>
```