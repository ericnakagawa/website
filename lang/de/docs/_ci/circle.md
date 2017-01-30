In [CircleCI](https://circleci.com/) können Sie Yarn als Teil des Builds installieren, indem Sie dies Ihrer `circle.yml`-Datei hinzufügen:

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

> Lassen Sie CircleCI wissen, dass Sie Yarn [standardmäßig installiert](https://discuss.circleci.com/t/preinstall-yarn/7353) haben möchten.