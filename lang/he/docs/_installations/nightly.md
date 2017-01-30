{{i18n.install_nightly_intro}}

הדרך הקלה ביותר להתקנה של גרסה לילית היא דרך הרצת קובץ הסקריפט שלנו:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

יש לנו גם מאגר חבילות Ubuntu/Debian לגרסה הלילית. כדי לאפשר אותו, הרץ את הפקודות הנ"ל:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

ב-Windows, ניתן להשתמש ב-[Windows Installer](https://nightly.yarnpkg.com/latest.msi).