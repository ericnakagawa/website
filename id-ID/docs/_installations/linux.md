### Debian/Ubuntu Linux

Pada Debian atau Ubuntu, anda dapat menginstal Yarn melalui repositori package Debian. Pertama, anda perlu mengkonfigurasi repositorinya:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

Pada Ubuntu 14.04 dan Debian Stable, anda juga perlu mengkonfigurasi [repositori NodeSource](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) untuk mendapatkan versi Node.js yang memadai (Debian Testing dan Ubuntu 16.04 sudah dikemas dengan versi Node.js yang memadai, sehingga langkah ini tidak dibutuhkan untuk environment tersebut)

Kemudian anda dapat menjalankan:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

Pada CentOS, Fedora dan RHEL, anda dapat menginstal Yarn melalui repositori RPM package.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

Jika anda belum menginstal Node.js, anda juga harus mengkonfigurasi [repositori NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora):

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

Kemudian anda dapat menjalankan:

```sh
sudo yum install yarn
```

### Arch Linux

Pada Arch Linux, yarn dapat diinstal melalui **AUR**.

Jika anda menggunakan [AUR Helper](https://wiki.archlinux.org/index.php/AUR_helpers) seperti yaourt anda dapat menjalankan:

```sh
yaourt -S yarn
```

### Solus

Pada Solus, anda dapat menginstal yarn melalui repositori Solus.

```sh
sudo eopkg install yarn
```

### Persiapan Path

{% include_relative _installations/unix_path_setup.md %}