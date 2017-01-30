* * *

id: docs_cli_cache guide: docs_cli layout: guide

* * *

<p class="lead">Limpa e remove arquivos desnecessários das dependências do pacote.</p>

##### `yarn clean` [](#toc-yarn-clean){#toc-yarn-clean.toc}

O comando `clean` libera espaço removendo arquivos e pastas desnecessários das dependências. Isso reduz o número de arquivos na pasta `node_modules` do seu projeto, isso é útil em um ambiente onde pacotes são checados no controle de versão diretamente.

Quando você executa `yarn clean`, Yarn cria um arquivo `.yarnclean` que deve ser adicionado no controle de versão. Limpeza é feita automaticamente quando se executa `yarn install`(ou simplesmente `yarn`) e `yarn add`.

*Nota: Esse comando é considerado somente para casos avançados de uso. A menos que você esteja enfrentando problemas com a quantidade de arquivos que estão instalados na pasta `node_modules` não é recomendado o uso desse comando. Ele usa uma heurística para identificar arquivos que podem não ser necessários para a distribuição de um pacote e podem não ser inteiramente seguros.*