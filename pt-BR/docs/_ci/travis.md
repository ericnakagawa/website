O [Travis CI](https://travis-ci.org/) detecta o uso do Yarn pela presença do `yarn.lock` na raíz do repositório. Se disponível, o Travis CI instalará o `yarn` se necessário, e executar `yarn` como o comando de instalação padrão.

Se sua fase de instalação exigir mais, é necessário instalar o Yarn você mesmo até que ele esteja pré-instalado nas imagens de build.

Há duas maneiras de instalar o Yarn; uma com `sudo`, e outra sem. Se você está usando um [ambiente baseado em container](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments) use o último.

## builds com `sudo` habilitado

```yml
sudo: required
before_install: # se "install" foi sobrescrito
  # Repositório para o Yarn
  - sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
  - echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  - sudo apt-get update -qq
  - sudo apt-get install -y -qq yarn
cache:
  directories:
  - $HOME/.cache/yarn
```

{% include_relative _ci/deb-specific-version.md %}

## builds baseadas em container

Builds baseadas em container não possuem o privilégio de `sudo`, então elas precisarão de outras maneiras para instalar. Por exemplo:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```