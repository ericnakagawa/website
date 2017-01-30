{{i18n.install_nightly_intro}}

Cara paling mudah untuk menginstal nightly build adalah melalui shell script:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

An Ubuntu/Debian repository of the nightly builds is also available. To enable it, run the following commands:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

Pada Windows, anda dapat menggunakan [Windows installer](https://nightly.yarnpkg.com/latest.msi).