{{i18n.install_nightly_intro}}

La forma mas fácil de instalar un Nightly Build es mediante el siguiente script:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

Un repositorio para Ubuntu/Debian de Nightly Builds también está disponible. Para habilitarlo, corre los siguientes comandos:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

En Windows, puedes utilizar el [Instalador de Windows](https://nightly.yarnpkg.com/latest.msi).