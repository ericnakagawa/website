* * *

id: docs_cli_info guide: docs_cli layout: guide

* * *

<p class="lead">Mostra informações sobre um pacote.</p>

##### `yarn info <pacote> [<campo>]` [](#toc-yarn-info){#toc-yarn-info.toc}

Este comando baixará informações sobre o pacote e a retorna em um formato de árvore. O pacote não precisa estar instalado localmente.

```sh
yarn info react
```

    yarn info vx.x.x
    { name: 'react',
      version: '15.4.0-rc.2',
      description: 'React is a JavaScript library for building user interfaces.',
      time: { modified: '2016-10-06T22:09:27.397Z', ... } ... }
    

O estilo padrão de resposta para este comando é uma serialização com uma aspa. Para emitir linhas válidas de JSON utilize a "flag" padrão `--json`:

```sh
yarn info react --json
```

    {"type":"inspect","data":{"name":"react","time":{...}}}
    {"type":"finished","data":417}
    

### Informações para uma versão específica [](#toc-information-for-a-specific-version){#toc-information-for-a-specific-version.toc}

Acrescente `@[version]` no argumento do pacote para mostrar informações específicas daquela versão:

```sh
yarn info react@15.3.0
```

    yarn info vx.x.x
    { name: 'react',
      version: '15.3.0',
      description: 'React is a JavaScript library for building user interfaces.',
      time: { modified: '2016-10-06T22:09:27.397Z', ... } ... }
    

### Selecionando campos específicos [](#toc-selecting-specific-fields){#toc-selecting-specific-fields.toc}

Se o argumento opcional de campo é passado então apenas este campo é retornado.

```sh
yarn info react description
```

    yarn info vx.x.x
    React is a JavaScript library for building user interfaces.
    

Se o campo especificado for um objeto a árvore dos filhos é retornada:

```sh
yarn info react time
```

    yarn info vx.x.x
    { modified: '2016-10-06T22:09:27.397Z',
      created: '2011-10-26T17:46:21.942Z', ... }
    
    yarn info react time --json
    {"type":"inspect","data":{"modified":"2016-10-06T22:09:27.397Z","created":...}}
    ...
    

### Pedindo o arquivo leia-me (readme) [](#toc-retrieving-the-readme-field){#toc-retrieving-the-readme-field.toc}

Note que, por padrão, `yarn info` não irá retornar o campo `leia-me` (já que ele é muito longo). Para pedir explicitamente por este campo, use o segundo argumento:

```sh
yarn info react readme
```

    yarn info vx.x.x
    ## react
    
    An npm package to get you immediate access to
    [React](https://facebook.github.io/react/).
    ...