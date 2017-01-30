### Windows

Existem duas opções para instalar Yarn no Windows.

#### Baixe o instalador

Isso vai te dar o arquivo `.msi` que quando executado ira instalar Yarn no Windows.

Se você usar o instalador primeiro você precisará do [Node.js](https://nodejs.org/).<a class="btn btn-primary" href="/latest.msi">Baixe o Instalador</a>#### Instalar através do Chocolatey

[Chocolatey](https://chocolatey.org/) é um gerenciador de pacotes para Windows, você pode instalar Chocolatey seguindo [Essas instruções](https://chocolatey.org/install).

Quando você tiver Chocolatey instalado, você pode instalar o Yarn executando o seguinte código no console:

```sh
choco install yarn
```

Isso também garantirá que você tem [Node.js](https://nodejs.org/) instalado.

#### Aviso

Por favor, ative permissões na sua pasta de projeto e na pasta de cache do Yarn(%LocalAppData%\Yarn) em seu software de antivirus, caso contrário instalar pacotes será significativamente mais lento porque todo arquivo será escaneado quando escrito no disco.