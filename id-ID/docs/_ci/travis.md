[Travis CI](https://travis-ci.org/) mendeteksi penggunaan Yarn dengan adanya `yarn.lock` pada root repository. Jika tersedia, Travis CI akan menginstall `yarn` jika diperlukan, dan mengeksekusi `yarn` sebagai perintah instalasi default.

Jika anda membutuhkan fase instalasi yang lebih spesifik, disarankan untuk melakukan instalasi Yarn secara mandiri hingga Yarn tersedia di build images yang anda pakai.

Ada beberapa cara untuk menginstal Yarn; dengan atau tanpa `sudo`. Apabila anda menggunakan [container-based environment](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), gunakan pilihan kedua.

## build menggunakan `sudo`

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

Container-based builds tidak memiliki kemampuan untuk melakukan `sudo`, sehingga harus menggunakan cara lain untuk menginstal:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```