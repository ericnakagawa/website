[Travis CI](https://travis-ci.org/) controleert het gebruik van Yarn op basis van de aanwezigheid van een `yarn.lock` bestand in de repository root. Als het beschikbaar is, zal Travis CI `yarn` installeren wanneer nodig en `yarn` uitvoeren als de standaard installatie command.

If your install phase requires more, it is necessary to install Yarn yourself until it is pre-installed on build images.

There are a couple of ways to install Yarn; one with `sudo`, the other without. If you are using the [container-based environment](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments) use the latter.

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

Container-based builds do not have the `sudo` privilege, so they must rely on other means to install. For example:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```