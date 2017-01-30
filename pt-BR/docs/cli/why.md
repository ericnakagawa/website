* * *

id: docs_cli_why guide: docs_cli layout: guide

* * *

<p class="lead">Mostra informações sobre por que um pacote está instalado.</p>

##### `yarn add <query>` [](#toc-yarn-why){#toc-yarn-why.toc}

Este comando irá identificar por um pacote instalado, detalhando quais outros pacotes dependem dele, por exemplo, ou se foi explicitamente marcado como uma dependência no manifesto `package.json`.

```sh
$ yarn why jest

yarn why vx.x.x
[1/4] 
[2/4] 
[3/4] 
[4/4] 
info Has been hoisted to "jest"
info This module exists because it's specified in "devDependencies".
info Disk size without dependencies: "1.29kB"
info Disk size with unique dependencies: "101.31kB"
info Disk size with transitive dependencies: "20.35MB"
info Amount of shared dependencies: 125
```

### Argumento de consulta [](#toc-query-argument){#toc-query-argument.toc}

O argumento de consulta obrigatório para `yarn why` pode ser qualquer uma das opções abaixo:

* um nome de pacote (como no exemplo acima)
* um diretório de um pacote; exemplo: `yarn why node_modules/once`
* um arquivo dentro de um diretório de um pacote; exemplo: `yarn why node_modules/once/once.js`

O caminho do arquivo também pode ser absoluto.