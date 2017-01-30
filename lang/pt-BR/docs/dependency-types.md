* * *

text for Translation id: docs_dependency_types guide: docs_dependencies layout: guide

* * *

Dependências têm muitas finalidades diferentes. Algumas dependências são necessárias para construir seu projeto, outros são necessários ao executar seu programa. Assim, há diferentes tipos de dependências que você pode ter (e.g. `dependencies`, `devDependencies` e `peerDependencies`).

Seu arquivo `package.json` conterá todas essas dependências:

```json
{
  "name": "my-project",
  "dependencies": {
    "package-a": "^1.0.0"
  },
  "devDependencies": {
    "package-b": "^1.2.1"
  },
  "peerDependencies": {
    "package-c": "^2.5.4"
  },
  "optionalDependencies": {
    "package-d": "^3.1.0"
  }
}
```

A maioria das pessoas so tem `dependencies` e `devDependecies`, mas cada uma é importante entender.

##### `dependencies` [](#toc-dependencies){#toc-dependencies.toc}

Essas são suas dependências normais, ou as que você precisa quando executando seu código (e.g. React ou ImmutableJS).

##### `devDependecies` [](#toc-devdependencies){#toc-devdependencies.toc}

Estas são as dependências do seu desenvolvimento. Dependências que você precisa em algum momento do workflow de desenvolvimento, mas não quando executa seu código (por exemplo, Babel ou fluxo).

##### `peerDependencies` [](#toc-peerdependencies){#toc-peerdependencies.toc}

Dependências de mesmo nível são um tipo especial de dependência que só aparecem quando se publica seu próprio pacote.

Ter uma dependência do mesmo nível significa que seu pacote precisa de uma dependência que é dependência exata da pessoa que está instalando o pacote. Isso é útil para pacotes como `react` que precisa ter uma única cópia de `react-dom` que é também usado pela pessoa que instalá-lo.

##### `optionalDependencies` [](#toc-optionaldependencies){#toc-optionaldependencies.toc}

Dependências opcionais são apenas isso: opcional. Se a instalação delas falhar, Yarn ainda vai dizer que o processo de instalação foi bem sucedidos.

Isso é útil para as dependências que não necessariamente funcionarão em cada máquina e você tem um segundo plano case elas não seja instalado (por exemplo, Vigia).

##### `bundledDependencies` [](#toc-bundleddependencies){#toc-bundleddependencies.toc}

Array de nomes de pacotes que serão empacotados na publicação do pacote.

Dependências de pacote dever estar dentro do projeto. A funcionalidade é basicamente a mesma que as dependências normais. Elas também serão empacotadas quando `yarn pack` for executado.

Dependências normais geralmente são instaladas no registro npm. Dependências de pacote são úteis em case que dependências normais não são suficiente:

- Quando você quiser re-utilizar uma biblioteca de terceiros que não vem de registro npm ou que foi modificado.
- Quando quiser re-utilizar seus próprios projetos como módulos.
- Quando você deseja distribuir alguns arquivos com seu módulo.