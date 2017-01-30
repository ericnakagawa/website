ב-[CircleCI](https://circleci.com/), תוכל להתקין את Yarn כחלק מתהליך הבנייה שלך על ידי הוספה של השורות הבאות לקובץ `circle.yml`:

```yml
dependencies:
  pre:
    # Install Yarn
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

> תודיע ל-CircleCI אם אתה רוצה ש-Yarn [יותקן בתצורת ברירת המחדל](https://discuss.circleci.com/t/preinstall-yarn/7353).