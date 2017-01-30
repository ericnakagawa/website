[Travis CI](https://travis-ci.org/) розпізнає необохідність використання Yarn по наявності файлу `yarn.lock` в кореневому каталозі репозиторію. При його наявності, Travis CI встановить менеджер пакетів `yarn` та виконає команду `yarn` для встановлення залежностей проекту.

Також ви можете встановити Yarn самостійно, до того як він буде проінстальований автоматично.

Для цього є декілька варіантів — з використанням `sudo` та без. Для використання [container-based environment](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), скористатйтесь останнім.

## `sudo`-enabled builds

```yml
sudo: required
before_install: # if "install" is overridden
  # Repo for Yarn
  - sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
  - echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  - sudo apt-get update -qq
  - sudo apt-get install -y -qq yarn
cache:
  directories:
  - $HOME/.cache/yarn
```

{% include_relative _ci/deb-specific-version.md %}

## container-based builds

Збірки основані на контейнерах, не мають `sudo` привілей, тож мають використовувати інші засоби для встановлення. Наприклад:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```