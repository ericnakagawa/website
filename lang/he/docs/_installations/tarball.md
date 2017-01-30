#### סקריפט התקנה

אחת מהדרכים הפשוטות ביותר להתקין את Yarn על macOS או על מערכת מבוססת יוניקס היא דרך סקריפט ההתקנה שלנו. תוכל להתקין את Yarn על המערכת שלך על ידי הרצה של הקוד הבא בטרמינל שלך:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

תהליך ההתקנה מוודא חתימת GPG, [הקוד נמצא ב-GitHub.](https://github.com/yarnpkg/website/blob/master/install.sh)

תוכל גם לספק גרסה מסויימת על ידי הרצת הקוד הבא בטרמינל:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

מוזמן להסתכל על [הגרסאות שיצאו](https://github.com/yarnpkg/yarn/releases) כדי לקרוא על הגרסאות השונות.

#### התקנה ידנית דרך tarball

תוכל להתקין את Yarn באמצעות [הורדה של tarball]({{site.baseurl}}/latest.tar.gz), ואז לחלץ אותו למקום כלשהו.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn is now in /opt/yarn-[version]/
```