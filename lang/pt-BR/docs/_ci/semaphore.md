O [Semaphore](https://semaphoreci.com/) tem o Yarn pré-instalado para todas as versões suportadas do Node.js, e nenhuma interação do usuário é necessária para que o cache do Yarn funcione.

Para garantir que sua versão local do Yarn corresponda à no Semaphore, adicione as linhas abaixo ao seus comandos de configuração, em Configurações do Projeto.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package is a tool for caching APT installations in Semaphore
# defining a package version is optional
install-package yarn=<version>
```