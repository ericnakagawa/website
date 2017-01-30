[CircleCI](https://circleci.com/) üzerinde `circle.yml` dosyasına bunu ekleyerek yapınızın parçası olarak Yarn'ı yükleyebilirsiniz:

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

> CircleCI'de Yarn'ın [varsayılan olarak yüklü](https://discuss.circleci.com/t/preinstall-yarn/7353) olmasını istediğinizi belirtebilirsiniz.