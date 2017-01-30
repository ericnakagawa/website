### Alternativas

Si esta usando otro SO o alguna de las otras opciones especificas para su SO no funciona, existen un par de alternativas. Necesita [instalar Node.js](https://nodejs.org/) si es que aun no lo tiene instalado.

En distribuciones comunes de Linux como Debian, Ubuntu y CentOS, se recomienda instalar Yarn con nuestros paquetes.

{% include_relative _installations/tarball.md %}

#### Instalar via npm

> **Nota:** Generalmente no se recomienda instalar via npm. npm is non-determinstic, packages are not signed, and npm does not perform any integrity checks other than a basic SHA1 hash, which is a security risk when installing system-wide apps.
> 
> For these reasons, it is highly recommended that you install Yarn through the installation method best suited to your operating system.

Tambien puede instalar Yarn a través del [gestor de paquetes npm](http://npmjs.org/) si es que ya lo tiene instalado. Si ya tienes [Node.js](https://nodejs.org/) instalado entonces ya tienes npm.

Una vez que tenga npm instalado puede correr:

```sh
npm install --global yarn
```

### Configuracion de ruta

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}