### Debian/Ubuntu Linux

במערכות לינוקס מבוססות Debian או Ubuntu, תוכל להתקין את Yarn דרך מאגר חבילות ה-Debian שלנו. בשלב הראשון תצטרך להגדיר את המאגר:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

ב-Ubuntu 14.04 וב-Debian Stale, תצטרך להגדיר את [המאגר של NodeSource](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) כדי לקבל גרסה מספיק חדשה של Node.js (לעומת Debian Testing ו-Ubuntu 16.04 שמגיעות עם גרסה חדשה מספיק של Node.js, ולכן השלב הזה לא הכרחי עבורן)

ואז תוכל פשוט להריץ:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

במערכות מבוססות CentOS, Fedora ו-RHEL, תוכל להתקין את Yarn דרך מאגר חבילות ה-RPM שלנו.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

אם אין לך עדיין Node.js מותקן, תצטרך להגדיר קודם את [מאגר החבילות של NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora):

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

ואז תוכל פשוט להריץ:

```sh
sudo yum install yarn
```

### Arch Linux

במערכות מבוססות Arch Linux, ניתן להתקין את Yarn דרך ה-**AUR**.

אם אתה משתמש ב[AUR Helper](https://wiki.archlinux.org/index.php/AUR_helpers) כמו yaourt, תוכל פשוט להריץ:

```sh
yaourt -S yarn
```

### Solus

ב-Solus, תוכל להתקין את Yarn דרך המאגר של Solus.

```sh
sudo eopkg install yarn
```

### התקנה לנתיב

{% include_relative _installations/unix_path_setup.md %}