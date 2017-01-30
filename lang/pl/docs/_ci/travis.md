[Travis CI](https://travis-ci.org/) wykrywa użycie Yarna sprawdzając, czy `yarn.lock` znajduje się w głównym katalogu repozytorium. Jeśli istnieje, Travis CI zainstaluje `yarn`, jeśli to konieczne, oraz wykona `yarn` jako domyślne polecenie instalacji.

Jeśli Twój etap instalacji jest bardziej skomplikowany, musisz zainstalować Yarna samodzielnie, dopóki nie jest on preinstalowany w obrazach kompilacji.

Istnieje parę sposobów na instalację Yarna; jeden wymagający użycia `sudo`, drugi nie. Gdy używasz [środowiska opartego na kontenerze](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), użyj drugiego sposobu.

## Kompilacje z dostępnym `sudo`

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

## Kompilacje oparte na kontenerze

Kompilacje oparte na kontenerze nie posiadają uprawnień do komendy `sudo`, więc muszą korzystać z innego sposobu instalacji. Na przykład:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```