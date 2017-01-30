При использовании [CircleCI](https://circleci.com/), вы можете установить Yarn как часть процесса сборки, добавив следующие строки в `circle.yml`:

```yml
dependencies:
  pre:
    # Устанавливаем Yarn
    - sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
    - echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
    - sudo apt-get update -qq
    - sudo apt-get install -y -qq yarn
  cache_directories:
    - ~/.cache/yarn
  override:
    - yarn install
```

{% include_relative _ci/deb-specific-version.md %}

> Если вы хотите [использовать Yarn по умолчанию](https://discuss.circleci.com/t/preinstall-yarn/7353), сообщите об этом CircleCI.