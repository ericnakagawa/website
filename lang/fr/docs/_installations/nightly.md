{{i18n.install_nightly_intro}}

La façon la plus simple d’installer une "nightly build" est via notre script shell :

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

Il existe aussi un dépôt Ubuntu/Debian des nightly builds. Pour l’activer, exécutez les commandes suivantes :

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

Sous Windows, le [programme d’installation de Windows](https://nightly.yarnpkg.com/latest.msi) peut être utilisé.