* * *

id: docs_cli_info guide: docs_cli layout: guide

* * *

<p class="lead">Afficher des informations sur un paquet.</p>

##### `yarn info <package> [<field>]` [](#toc-yarn-info){#toc-yarn-info.toc}

Cette commande va chercher des informations sur un paquet et le retourner en forme d’arborescence. Le paquet ne doit pas nécessairement être installé localement.

```sh
yarn info react
```

    yarn info vx.x.x
    { name: 'react',
      version: '15.4.0-rc.2',
      description: 'React is a JavaScript library for building user interfaces.',
      time: { modified: '2016-10-06T22:09:27.397Z', ... } ... }
    

Le défaut de déclaration de style pour cette commande est une sérialisation entre guillemets simples. Pour émettre des lignes de JSON valide, utilisez l'option `--json`  :

```sh
yarn info react --json
```

    {"type":"inspect","data":{"name":"react","time":{...}}}
    {"type":"finished","data":417}
    

### Informations pour une version spécifique [](#toc-information-for-a-specific-version){#toc-information-for-a-specific-version.toc}

Ajouter `@[version]` à l’argument de paquet pour fournir des informations spécifiques à cette version:

```sh
yarn info react@15.3.0
```

    yarn info vx.x.x
    { name: 'react',
      version: '15.3.0',
      description: 'React is a JavaScript library for building user interfaces.',
      time: { modified: '2016-10-06T22:09:27.397Z', ... } ... }
    

### Sélection de champs spécifiques [](#toc-selecting-specific-fields){#toc-selecting-specific-fields.toc}

Si le champ facultatif argument est fourni, alors seulement cette partie de l’arborescence est renvoyée.

```sh
yarn info react description
```

    yarn info vx.x.x React is a JavaScript library for building user interfaces.
    

Si le champ spécifié est à son tour un objet imbriqué, l’arbre de l’enfant est renvoyé :

```sh
yarn info react time
```

    yarn info vx.x.x
    { modified: '2016-10-06T22:09:27.397Z',
      created: '2011-10-26T17:46:21.942Z', ... }
    
    yarn info react time --json
    {"type":"inspect","data":{"modified":"2016-10-06T22:09:27.397Z","created":...}}
    ...
    

### Récupérer le champ readme [](#toc-retrieving-the-readme-field){#toc-retrieving-the-readme-field.toc}

Notez que par défaut, `yarn info` ne retournera pas le champ `readme` (puisque il est souvent très long). Pour demander explicitement ce champ, utilisez le second argument :

```sh
yarn info react readme
```

    yarn info vx.x.x
    ## react
    
    An npm package to get you immediate access to
    [React](https://facebook.github.io/react/).
    ...