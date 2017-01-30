{{i18n.install_nightly_intro}}

A maneira mais fácil de instalar compilações noturnas é através de nosso script de shell:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

Um repositório Ubuntu/Debian das compilações noturnas também estão disponíveis. Para ativa-lo, execute os seguintes comandos:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

No Windows, o [Instalador Windows](https://nightly.yarnpkg.com/latest.msi) pode ser usado.