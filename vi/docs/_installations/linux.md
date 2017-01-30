### Debian/Ubuntu Linux

Trên Debian hoặc Ubuntu Linux, bạn có thể cài Yarn thông qua Debian repository. Bạn sẽ cần phải cấu hình repository trước:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

Trên Ubuntu 14.04 và Debian Stable, bạn cũng sẽ cần cấu hình [NodeSource repository](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) để lấy bản mới nhất của Node.js (bản Debian thử nghiệm và Ubuntu 16.04 đi kèm với một phiên bản đầy đủ của Node.js, nên bước này không cần thiết trên những môi trường đó)

Sau đó bạn chỉ cần:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

Trên CentOS, Fedora và RHEL, bạn có thể cài Yarn thông qua RPM repository.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

Nếu bạn chưa cài Node.js, bạn nên cấu hình [NodeSource repository](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora):

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

Sau đó bạn chỉ cần:

```sh
sudo yum install yarn
```

### Arch Linux

Trên Arch Linux, Yarn có thể được cài đặt qua **AUR**.

Nếu bạn sử dụng một chương trình [AUR Helper](https://wiki.archlinux.org/index.php/AUR_helpers) như yaourt bạn chỉ cần chạy:

```sh
yaourt -S yarn
```

### Solus

Trên Solus, bạn có thể cài Yarn thông qua Solus repository.

```sh
sudo eopkg install yarn
```

### Thiết lập đường dẫn

{% include_relative _installations/unix_path_setup.md %}