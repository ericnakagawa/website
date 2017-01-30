* * *

id: docs_cli_global guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Instala pacotes globalmente no seu sistema de arquivos.</p>

##### `yarn global` [](#toc-yarn-global){#toc-yarn-global.toc}

`yarn global` é um prefixo usado para vários comandos como `add`, `bin`, `ls` e `remove`. Eles têm o mesmo comportamento que suas versões normais exceto que usam um diretório global para salvar os pacotes. O comando `global` torna arquivos executáveis (binários) disponíveis para uso pelo seu sistema operacional.

Isso é útil para ferramentas de desenvolvimento que não são partes de nenhum projeto específico mas que são usados para comandos locais. Um dos exemplos deste tipo é o [create-react-app](https://github.com/facebookincubator/create-react-app) que pode ser instalado globalmente assim:

```sh $ yarn global add create-react-app --prefix /usr/local

# o comando `create-react-app` agora está disponível globalmente:

$ which create-react-app $ /usr/local/bin/create-react-app $ create-react-app ````

Leia mais sobre os comandos que podem ser usados em conjunto com o `yarn global`:

- [`yarn add`]({{url_base}}/docs/cli/add): adiciona um pacote para usar no seu pacote atual. 
- [`yarn bin`]({{url_base}}/docs/cli/bin): mostra a localização da pasta bin do yarn.
- [`yarn ls`]({{url_base}}/docs/cli/ls): lista os pacotes instalados.
- [`yarn remove`]({{url_base}}/docs/cli/remove): remove um pacote que não será mais usado no seu pacote atual.
- [`yarn upgrade`]({{url_base}}/docs/cli/upgrade): atualiza os pacotes para a última versão baseado no "alcance" especificado.