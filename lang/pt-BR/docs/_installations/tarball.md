#### Script de instalação

Uma das maneiras mais fáceis de instalar Yarn no macOS ou ambientes genéricos de Unix é através do nosso script shell. Você pode instalar Yarn executando o seguinte código no seu terminal:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

O processo de instalação inclui a verificação da assinatura GPG. [Veja a fonte no GitHub](https://github.com/yarnpkg/website/blob/master/install.sh)

Você também pode especificar a versão executando o seguinte código no seu terminal:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

Veja [os lançamentos](https://github.com/yarnpkg/yarn/releases) para versões possíveis.

#### Instalação manual através de tarball

Você pode instalar Yarn [baixando a tarball]({{site.baseurl}}/latest.tar.gz) e extraindo em qualquer lugar.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn is now in /opt/yarn-[version]/
```