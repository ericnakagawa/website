[Travis CI](https://travis-ci.org/) определяет использование Yarn с помощью проверки наличия файла `yarn.lock` в директории проекта. Если файл был найден, Travis CI установит `yarn` и будет использовать его по умолчанию.

Если Ваша фаза установки требует дополнительных действий, следует установить Yarn самостоятельно перед тем, как он будет установлен автоматически.

Существует два пути, как Вы можете установить Yarn: один с использованием `sudo`, другой без. Если вы используете [среду разработки на основе контейнера](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), **не используйте** sudo.

## Сборки с использованием `sudo`

```yml
sudo: required
before_install: # if "install" is overridden
  # Добавляем Yarn репозиторий
  - sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
  - echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  - sudo apt-get update -qq
  - sudo apt-get install -y -qq yarn
cache:
  directories:
  - $HOME/.cache/yarn
```

{% include_relative _ci/deb-specific-version.md %}

## Сборки с использованием контейнеров

У сборок, использующих контейнеры, отсутствуют права на выполнение команд с использованием `sudo`, поэтому придётся использовать методы установки, не использующие данную команду. Например:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```