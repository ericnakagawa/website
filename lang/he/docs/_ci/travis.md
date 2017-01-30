[Travis CI](https://travis-ci.org/) מזהה האם קיים קובץ `yarn.lock` בתיקייה הראשית של הפרויקט שלך, וכך מחליט האם אתה משתמש ב-Yarn. אם הוא קיים, Travis CI יתקין את `yarn` אם דרוש, ויקרא ל`yarn` כברירת המחדל לפקודת ההתקנה.

אם ההתקנה שלך דורשת יותר, נדרש להתקין את Yarn בעצמך עד שהוא יותקן מראש על ה-build images.

יש כמה דרכים להתקין את Yarn; הראשונה עם `sudo`, השניה היא בלי. אם אתה משתמש ב[סביבה מבוססת קונטיינרים](https://docs.travis-ci.com/user/ci-environment/#Virtualization-environments), תשתמש באחרון.

## Builds עם `sudo`

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

## סביבות מבוססות קונטיינרים (מכולות)

סביבות מבוססות קונטריינרים לא בעלות הרשאות לפקודת `sudo`, לכן הן צריכות להשתמש בדרך אחרת כדי להתקין את Yarn. לדוגמה:

```yaml
sudo: false
before_install:
  - curl -o- -L https://yarnpkg.com/install.sh | bash
  - export PATH=$HOME/.yarn/bin:$PATH
```