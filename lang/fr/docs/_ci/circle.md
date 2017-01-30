Sur [CircleCI](https://circleci.com/), vous pouvez installer Yarn avec une étape de votre build en ajoutant ceci à votre fichier `circle.yml` :

```yml
dependencies:
  pre:
    # Installer Yarn
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

> Si vous voulez que Yarn soit installé par défaut sur CircleCI, [faites-le savoir](https://discuss.circleci.com/t/preinstall-yarn/7353).