No [CircleCI](https://circleci.com/), você pode instalar o Yarn como parte da sua build adicionando isso ao seu arquivo `circle.yml`:

```yml
dependencies:
  pre:
    # Instala o Yarn
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

> Deixe o CircleCI saber se você quer que o Yarn seja [instalado por padrão](https://discuss.circleci.com/t/preinstall-yarn/7353).