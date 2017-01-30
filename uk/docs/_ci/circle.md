У [CircleCI](https://circleci.com/) ви можете додати це до Вашого `circle.yml`, щоб встановити Yarn як частину Вашої побудови:

```yml
dependencies:
  pre:
    # Install Yarn
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

> Дайте CircleCI знати, чи Ви хочете щоб Yarn був [встановленим по завмовчуванню](https://discuss.circleci.com/t/preinstall-yarn/7353).