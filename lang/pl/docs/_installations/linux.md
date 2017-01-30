### Debian/Ubuntu Linux

Na Debianie lub Ubuntu można zainstalować Yarna za pośrednictwem naszego repozytorium pakietów Debiana. Najpierw trzeba będzie je skonfigurować:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key Dodaj - echo "deb https://dl.yarnpkg.com/debian/ stabilne głównej" | sudo tee /etc/apt/sources.list.d/yarn.list
```

Na Ubuntu 14.04 i stabilnej wersji Debiana (wydanie oficjalne) będziesz również potrzebował skonfigurować [repozytorium NodeSource](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) dzięki któremu uzyskasz aktualną wersję Node.js (wersja testowa Debiana i Ubuntu 16.04 posiadają wystarczająco aktualną wersję Node.js więc ten krok nie jest wymagany dla tych środowisk)

Następnie wpisujesz:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

Na CentOSie, Fedorze i RHELu możesz zainstalować Yarn za pomocą naszego repozytorium pakietów RPM.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

Jeżeli nie masz jeszcze zainstalowanego Node.js, powinieneś skonfigurować też [repozytorium NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora):

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

Następnie wpisujesz:

```sh
sudo yum install yarn
```

### Arch Linux

Na Arch Linuxie Yarn może zostać zainstalowany za pomocą **AUR**.

Jeżeli używasz [AUR Helpera](https://wiki.archlinux.org/index.php/AUR_helpers) takiego jak choćby yaourt możesz po prostu wpisać:

```sh
yaourt -S yarn
```

### Solus

Na Solusie możesz zainstalować Yarn poprzez jego repozytorium.

```sh
sudo eopkg install yarn
```

### Ustawienie ścieżki

{% include_relative _installations/unix_path_setup.md %}