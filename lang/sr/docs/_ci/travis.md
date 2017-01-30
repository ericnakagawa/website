[Travis CI](https://travis-ci.org/) ће сам уочити да користите Yarn помоћу присуства `yarn.lock` датотеке у вашем пројекту. Уколико датотека постоји, Travis CI ће инсталирати и извршити `yarn` као подразумијевану команду за инсталирање.

Уколико ваш пројекат током инсталационе фазе захтјева више од тога, потребно је да самостално инсталирате Yarn.

Постоје два начина да инсталирате Yarn: један је помоћу `sudo`, а други без. Уколико користите [окружење које је засновано на контејнерима](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), инсталирајте Yarn без коришћења `sudo` команде.

## Градња помоћу `sudo` команде

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

## Окружења која су заснована на контејнерима

Окружења која су заснована на контејнерима немају `sudo` привилегије, па морају да се ослањају на друге начине инсталације. На примјер:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```