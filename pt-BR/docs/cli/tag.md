* * *

id: docs_cli_tag guide: docs_cli description: docs_cli_tag_description layout: guide

* * *

<p class="lead">Adicionar, remover ou listar tags em um pacote.</p>

### O que são tags? [](#toc-what-are-tags){#toc-what-are-tags.toc}

Tags de distribuição (ou dist-tags) são uma maneira de marcar versões publicadas do seu pacote com um rótulo. Usuários do seu pacote podem instala-lo usando esse rótulo, em vez to número de versão.

Por exemplo, se você tivesse um canal de liberação **stable** e um canal de liberação **canary**, poderia usar as tags como uma maneira de permitir que os usuários digitem:

```sh
yarn add your-package-name@stable
yarn add your-package-name@canary
```

Tags diferentes têm significados diferentes:

- `latest`: A versão atual do pacote
- `stable`: A última versão estável do pacote, normalmente o mesmo que o mais recente, a menos que tenha suporte a longo prazo (LTS)
- `beta`: Um lançamento antes de se tornar a mais recente e/ou estável, usado para compartilhar próximas mudanças antes de estarem prontas.
- `canary`: uma versão "noturna" ou pré-beta, se seu projeto é atualizado com frequência e dependido por muitas pessoas, você pode usar isto para compartilhar o código em estágios iniciais.
- `dev`: As vezes você quer testar uma revisão pelo registro enquanto continua trabalhando nas coisas, isso é útil pra isso.

Alguns projetos farão suas próprias Tags, como acharem adequado, ou no lugar de uma padrão. Como a `next` que é usado igual a `beta`.

Embora estes são amplamente considerados as tags "padrão", o único que tem algum significado real é `latest` que é usado para determinar qual versão instalar quando nenhuma versão é especificada.

### Ressalvas [](#toc-caveats){#toc-caveats.toc}

Você não pode usar tags que correspondem a números de versão do potencial desde que eles compartilham um espaço de nome:

```sh
yarn add your-package-name@<version>
yarn add your-package-name@<tag>
```

Qualquer tag que também pode ser usada como um intervalo válido semver será rejeitada. Por exemplo, você não pode ter uma tag chamada `v 2.3` porque em semver significa `> = 2.3.0 < 2.4.0`.

Em geral, evitar o uso de tags que se parecem com as versões, elas só confundem as pessoas, de qualquer maneira.

### Comandos [](#toc-commands){#toc-commands.toc}

##### `yarn tag add <package>@<version> <tag>` [](#toc-yarn-tag-add){#toc-yarn-tag-add.toc}

Adicione uma marca chamada `< tag >` para uma específica `< version>` de um `<package>`.

##### `yarn tag rm <package> <tag>` [](#toc-yarn-tag-rm){#toc-yarn-tag-rm.toc}

Remova uma tag chamada `<tag>` de um `<pacote>` que não está mais em uso.

> **Nota:** Você não precisa excluir uma tag antes de movê-la para outra versão do pacote. Melhor não fazer isso.

##### `yarn tag ls [<package>]` [](#toc-yarn-tag-ls){#toc-yarn-tag-ls.toc}

Liste todas as tags para um `<pacote>`. Se não especificado. `< pacote>` usará como padrão o pacote da pasta em que você está.