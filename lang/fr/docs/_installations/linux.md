### Debian/Ubuntu Linux

Sur Debian ou Ubuntu Linux, vous pouvez installer Yarn par l’intermédiaire de notre dépôt de paquets Debian. Vous devrez tout d’abord configurer le référentiel :

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - echo « deb https://dl.yarnpkg.com/debian/ stable main » | sudo tee /etc/apt/sources.list.d/yarn.list
```

Sur Ubuntu 14.04 et Debian version stable, vous devez également configurer [le référentiel NodeSource](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) pour obtenir une version assez récente de Node.js (Debian Testing et Ubuntu 16.04 sont emballés avec une version suffisante de Node.js, cette étape n’est donc pas requise dans ces environnements)

Ensuite, vous pouvez tout simplement :

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

Sur CentOS, Fedora et RHEL, vous pouvez installer Yarn par l’intermédiaire de notre dépôt de paquets RPM.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

Si vous n’avez pas déjà Node.js installé, vous devez également configurer [le référentiel de NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora) :

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

Ensuite, vous pouvez tout simplement :

```sh
sudo yum install yarn
```

### Arch Linux

Sur Arch Linux Yarn peut être installé via **AUR**.

Si vous utilisez un [AUR Helper](https://wiki.archlinux.org/index.php/AUR_helpers) tels que yaourt, vous pouvez simplement exécuter :

```sh
yaourt -S yarn
```

### Solus

Sur Solus, vous pouvez installer yarn via le référentiel Solus.

```sh
sudo eopkg install yarn
```

### Configuration du chemin d’accès

{% include_relative _installations/unix_path_setup.md %}