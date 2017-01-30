{{i18n.install_nightly_intro}}

Cách dễ nhất để cài đặt bản nightly build là qua shell script:

```sh
wget https://yarnpkg.com/install.sh
chmod +x install.sh
./install.sh --nightly
```

Một Ubuntu/Debian repository của bản nightly build cũng sẵn có. Để kích hoạt nó, chạy những lệnh sau:

```sh
sudo apt-key adv --fetch-keys http://dl.yarnpkg.com/debian/pubkey.gpg
echo "deb http://nightly.yarnpkg.com/debian/ nightly main" | sudo tee /etc/apt/sources.list.d/yarn-nightly.list
sudo apt-get update && sudo apt-get install yarn
```

Trên Windows, [trình cài đặt cho Windows](https://nightly.yarnpkg.com/latest.msi) có thể được sử dụng.