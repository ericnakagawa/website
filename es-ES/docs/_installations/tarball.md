#### Script de instalación

Una de las maneras mas faciles de instalar Yarn en macOS y entornos Unix genericos es via shell script. Puede instalar Yarn corriendo el siguiente codigo en su terminal:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

El proceso de instalacion incluye verificar una firma GPG. [Ver el codigo fuente en GitHub](https://github.com/yarnpkg/website/blob/master/install.sh)

You can also specify a version by running the following code in your terminal:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

Ver [los releases](https://github.com/yarnpkg/yarn/releases) para posibles versiones.

#### Instalacion manual via tarball

Puede instalar Yarn [descargando un tarball]({{site.baseurl}}/latest.tar.gz) y extrayendolo en cualquier lugar.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn se encuentra ahora en /opt/yarn-[version]/
```