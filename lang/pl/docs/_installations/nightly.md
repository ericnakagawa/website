{{i18n.install_nightly_intro}}

Najprostszym sposobem instalacji nightly buildu jest wykonanie naszego skryptu shell:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

Repozytorium Ubuntu/Debiana nightly buildów jest również dostępne. Aby je aktywować wykonaj poniższe komendy:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

Na Windowsie można skorzystać z [Instalatora Windows](https://nightly.yarnpkg.com/latest.msi).