{{i18n.install_nightly_intro}}

Güncel bir yapı kurmanın en kolay yolu shell üzerindendir:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

Ubuntu/Debian için güncel yapılardan oluşan bir veri havuzu da mevcuttur. Bunu kullanılır hale getirmek için, bu komutu kullanın:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

Windows'da, [Windows Installer](https://nightly.yarnpkg.com/latest.msi) kullanılabilir.