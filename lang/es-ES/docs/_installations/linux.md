### Debian/Ubuntu Linux

En Debian o Ubuntu Linux, puedes instalar Yarn a través de nuestro repositorio Debian. Primero, usted necesitará configurar el repositorio:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

En Ubuntu 14.04 y Debian estable, también tendrás que configurar [el repositorio de NodeSource](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) para obtener una versión lo suficientemente nueva de Node.js (Debian Testing y 16.04 Ubuntu vienen empaquetados con una versión bastante nueva de Node.js, así que este paso no es necesario en estos ambientes)

Entonces puedes simplemente:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### CentOS / Fedora / RHEL

En CentOS, Fedora y RHEL, puedes instalar Yan a través de nuestro repositorio de paquetes RPM.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo - O /etc/yum.repos.d/yarn.repo
```

Si no tienes instalado Node.js, también debes configurar [el repositorio de NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora):

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

Entonces puedes simplemente:

```sh
sudo yum install yarn
```

### Arch Linux

En Arch Linux Yarn puede ser instalado a través de la **AUR**.

Si utilizas un [Ayudante de AUR](https://wiki.archlinux.org/index.php/AUR_helpers) como yaourt puedes simplemente ejecutar:

```sh
yaourt -S yarn
```

### Solus

El Solus, puede instalar Yarn mediante el repositorio Solus.

```sh
sudo eopkg install yarn
```

### Configuración de ruta

{% include_relative _installations/unix_path_setup.md %}