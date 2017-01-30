ל-[Semaphore](https://semaphoreci.com/) יש את Yarn מותקן מראש בכל גרסאות ה-Node שלו, ולכן לא צריך להגדיר דבר בשביל לגרום למטמון של Yarn לעבוד.

כדי לוודא שגרסת ה-Yarn שלך תואמת לגרסה ב-Semaphore, תוסיף את השורותה באות בתהליך ההתקנה שנמצא בהגדרות הפרויקט.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```