[Semaphore](https://semaphoreci.com/) sudah mendukung Yarn untuk semua versi Node.js, anda tidak perlu melakukan konfigurasi tambahan untuk dapat menggunakannya.

Untuk memastikan bahwa versi Yarn anda cocok dengan yang ada di Semaphore, tambahkan baris berikut ke perintah konfigurasi Anda di pengaturan proyek.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```