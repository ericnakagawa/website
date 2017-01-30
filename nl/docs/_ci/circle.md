Op [CircleCI](https://circleci.com/) kun je Yarn installeren door dit toe te voegen aan je `circle.yml` bestand:

```yml
dependencies:
 pre:
  # Installeer Yarn
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

> Laat CircleCI weten of je wilt dat Yarn [standaard geïnstalleerd wordt](https://discuss.circleci.com/t/preinstall-yarn/7353).