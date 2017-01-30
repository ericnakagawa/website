[Travis CI](https://travis-ci.org/) détecte l’utilisation de Yarn par la présence de `yarn.lock` à la racine du dépôt. S’il est présent, Travis CI va installer `yarn` si nécessaire et exécuter `yarn` comme commande d’installation par défaut.

Si votre phase d’installation a besoin de plus de chose, il est nécessaire d’installer Yarn vous-même afin qu’il soit pré-installé sur les images de builds.

Il y a deux façons d’installer Yarn, l'une avec `sudo`, l’autre sans. Si vous utilisez [l’environnement basé sur le conteneur](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), utilisez le dernier.

## Builds activés par `sudo`

```yml
sudo: required
before_install: # si "install" est remplacé
  # Dépôt pour Yarn
  - sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
  - echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  - sudo apt-get update -qq
  - sudo apt-get install -y -qq yarn
cache:
  directories:
  - $HOME/.cache/yarn
```

{% include_relative _ci/deb-specific-version.md %}

## Builds basés sur un conteneur

Les builds basés sur le conteneur n’ont pas le droit à `sudo`, donc ils doivent s’appuyer sur d’autres moyens pour s’installer. Par exemple :

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```