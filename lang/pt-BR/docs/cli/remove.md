* * *

id: docs_cli_remove guide: docs_cli layout: guide

* * *

##### `yarn remove <pacote...>` [](#toc-yarn-remove){#toc-yarn-remove.toc}

Executar `yarn remove foo` irá remover o pacote chamado `foo` de suas dependências diretas atualizando seus arquivos `package.json` e `yarn.lock` no processo.

Outros desenvolvedores trabalhando no projeto podem executar `yarn install` para sincronizar sua pasta `node_modules` com o conjunto atualizado de dependências.

Quando se remove um pacote, ele é removido de todos tipos de suas dependências: `dependencies`, `devDependencies`, etc.

> **Nota:**: `yarn remove` sempre atualizará o seu `package.json` e seu `yarn.lock`. Isso garante que desenvolvedores diferentes do mesmo projeto tenham sempre o mesmo conjunto de dependências. Não é possível desabilitar este comportamento.