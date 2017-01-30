[Travis CI](https://travis-ci.org/) erkennt an der `yarn.lock` im Stammverzeichnis des Repositorys, dass Yarn benutzt wird. Wenn es verfügbar ist, installiert Travis CI `yarn` und führt `yarn` als voreingestellten Installationsbefehl aus.

Wenn Sie eine umfassendere Installationsphase benötigen, müssen Sie Yarn selbst installieren bis es in build images vorinstalliert ist.

Es gibt mehrere Wege, um Yarn zu installieren; entweder mit `sudo` oder ohne. Wenn Sie die [containerbasierte Umgebung](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments) verwenden, nehmen Sie den letzteren.

## Builds mit `sudo`

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

## containerbasierte Builds

Containerbasirte Builds haben keine `sudo`-Privilegien, also müssen sie auf andere Art und Weise installiert werden, beispielsweise so:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```