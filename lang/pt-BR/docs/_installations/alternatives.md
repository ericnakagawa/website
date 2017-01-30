### Alternativas

Se você está usando outro Sistema Operacional ou uma das outras opções específicas para seu Sistema Operacional não funcionar para você, existem algumas alternativas. Você precisará [instalar Node.js](https://nodejs.org/) se você já não tem ele instalado.

Em distribuições Linux comuns como Debian, Ubuntu e CentOS, é recomendado instalar Yarn através dos nosso pacotes.

{% include_relative _installations/tarball.md %}

#### Instalar via npm

> **Nota:** instalação via npm é geralmente não recomendada. npm não é determinístico, pacotes não são assinados, e npm não realiza nenhuma checagem de integridade a não ser uma checagem de hash SHA1, o que é um risco de segurança quando estiver instalando apps globalmente.
> 
> Por essas razões, é recomendado que você instale Yarn através de métodos mais adequados para seu sistema operacional.

Você também pode instalar o Yarn através do [gerenciador de pacotes npm](http://npmjs.org/) se você já o tiver instalado. Se você já tem [Node.js](https://nodejs.org/) instalado então você já deve ter npm.

Assim que você tiver o npm instalado você pode executar:

```sh
npm install --global yarn
```

### Caminho de instalação

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}