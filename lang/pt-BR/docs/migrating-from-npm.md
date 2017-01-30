* * *

id: docs_migrating_from_npm guide: docs_migrating_from_npm layout: guide

* * *

Migrar do npm é um processo bem fácil para a maioria dos usuários. Yarn pode usar o mesmo formato de `package.json` que o npm, e se pode instalar qualquer projeto do registro npm.

Se você quer tentar Yarn em um projeto existente, execute:

```sh
yarn
```

Isso ira escrever na sua pasta `node_modules` usando o algoritmo de resolução do Yarn que é compatível com a [resolução de algoritmo do node.js](https://nodejs.org/api/modules.html#modules_all_together).

Se você receber um erro, por favor verifique se existe um problema existente no [Rastreador de problemas do yarn](https://github.com/yarnpkg/yarn/issues).

Quando você executar `yarn` ou `yarn add <pacote>`, o Yarn vai gear o arquivo `yarn.lock` na pasta raíz do seu pacote. Você não precisa ler ou compreender este arquivo - basta verificar no controle de fonte. Quando outras pessoas começam usando Yarn em vez de `npm`, o arquivo de `yarn.lock` irá garantir que começam precisamente as mesmas dependências que você tem.

Na maioria dos casos, só executar `yarn` ou `yarn add` pela primeira vez. Em alguns casos, as informações em um arquivo de `package.json` não são explícitas o suficiente para eliminar as dependências, e a forma determinista que Yarn escolhe dependências vai decidir o conflito de dependências. Isto é especialmente provável de acontecer em projetos maiores, onde às vezes `npm install` não funciona e desenvolvedores estão frequentemente removendo `node_modules` e reconstruindo do zero. Se isso acontecer, tente usar o `npm`para deixar a versão de dependências mais explícitas, antes de converter para yarn.

Outros desenvolvedores do projeto podem continuar usando `npm`, assim você não precisa ter todo mundo convertendo ao mesmo tempo. Os desenvolvedores usando o `Yann` terão exatamente a mesma configuração que uns aos outros, e os desenvolvedores usando `npm` podem obter configurações ligeiramente diferentes, que é o comportamento esperado do `npm`.

Mais tarde, se você decidir que o Yarn não é para você, pode voltar a usar o `npm` sem fazer nenhuma alteração específica. Você pode excluir seu antigo arquivo de `yarn.lock` se ninguém no projeto usa Yarn, mas não é necessário.

Se você estiver usando um arquivo `npm-shrinkwrap.json` agora, esteja ciente que você pode terminar com um conjunto diferente de dependências. Fio não suporta arquivos npm shrinkwrap já que eles não têm informação suficiente neles para algoritmo mais deterministico do Yarn. Se você estiver usando um arquivo shrinkwrap pode ser mais fácil converter todos os que trabalham no projeto usar Yarn ao mesmo tempo. Basta remover o arquivo existente do `npm-shrinkwrap.json` e de check-in no recém-criado arquivo `yarn.lock`.

### Comparação de comandos CLI [](#toc-cli-commands-comparison){#toc-cli-commands-comparison.toc}

| npm                                          | Yarn                                 |
| -------------------------------------------- | ------------------------------------ |
| `npm install`                                | `yarn install`                       |
| ***(N/A)***                                  | `yarn install --flat`                |
| ***(N/A)***                                  | `yarn install --har`                 |
| ***(N/A)***                                  | `yarn install --no-lockfile`         |
| ***(N/A)***                                  | `yarn install --pure-lockfile`       |
| `npm install [package]`                      | ***(N/A)***                          |
| `npm install --save [package]`               | `yarn add [package]`                 |
| `npm install --save-dev [package]`           | `yarn add [package] [--dev/-D]`      |
| ***(N/A)***                                  | `yarn add [package] [--peer/-P]`     |
| `npm install --save-optional [package]`      | `yarn add [package] [--optional/-O]` |
| `npm install --save-exact [package]`         | `yarn add [package] [--exact/-E]`    |
| ***(N/A)***                                  | `yarn add [package] [--tilde/-T]`    |
| `npm install --global [package]`             | `yarn global add [package]`          |
| `npm rebuild`                                | `yarn install --force`               |
| `npm uninstall [package]`                    | ***(N/A)***                          |
| `npm uninstall --save [package]`             | `yarn remove [package]`              |
| `npm uninstall --save-dev [package]`         | `yarn remove [package]`              |
| `npm uninstall --save-optional [package]`    | `yarn remove [package]`              |
| `npm cache clean`                            | `yarn cache clean`                   |
| `rm -rf node_modules && npm install` | `yarn upgrade`                       |