### Debian/Ubuntu Linux 

No Debian ou Ubuntu Linux, você pode instalar Yarn através do repositório de pacotes Debian. Você precisa configurara o repositório primeiro:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

No Ubunto 14.04 e Debian Stable, você também precisará configurar [o repositório NodeSource](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) para ter uma nove versão do Node.js (Debian Testing e Ubuntu 16.04 vem com uma versão suficiente do Node.js, esse passo não é necessário nesses ambientes)

Em seguida, você pode simplesmente executar:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

No CentOS, Fedora e RHEL, você pode instalar Yarn através do nosso repositório de pacotes RPM.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

Se você já não tem Node.js instalado, você precisará também configurar a o [repositório NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora):

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

Então, você pode simplesmente executar:

```sh
sum yum install yarn
```

### Arch Linux

No Arch Linux Yarn pode ser instalado através do **AUR**.

Se você usa um [AUR Helper](https://wiki.archlinux.org/index.php/AUR_helpers) como yaourt você pode executar:

```sh
yaourt -S yarn
```

### Solus

Na Solus, você pode instalar o Yarn através do repositório Solus.

```sh
sudo eopkg install yarn
```

### Caminho de instalação

{% include_relative _installations/unix_path_setup.md %}