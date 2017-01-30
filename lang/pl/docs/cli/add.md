* * *

id: docs_cli_add guide: docs_cli layout: guide description: docs_cli_add_description additional_reading_tags: ["dependencies"]

* * *

{% include vars.html %}

<p class="lead">Instaluje pakiet i wszystkie jego zależności.</p>

### Dodawanie zależności [](#toc-adding-dependencies){#toc-adding-dependencies.toc}

Gdy chcesz użyć nowego pakietu, musisz najpierw dodać go do zależności. W tym celu uruchom `yarn add [package-name]`, aby zainstalować go w Twoim projekcie.

Spowoduje to również zaktualizowanie `package.json` oraz `yarn.lock` tak, aby inni programiści pracujący nad projektem po uruchomieniu `yarn` lub `yarn install` otrzymali takie same zależności.

Większość pakietów zostanie zainstalowana z [rejestru npm](https://www.npmjs.com/) i będzie określana po prostu po ich nazwie. Na przykład, `yarn add react` zainstaluje pakiet [`react`](https://www.npmjs.com/package/react) z rejestru npm.

Możesz określić wersje przy użyciu poniższych komend:

  1. `yarn add package-name` instaluje najnowszą wersję pakietu.
  2. `yarn add package-name@1.2.3` instaluje określoną wersję pakietu z rejestru.
  3. `yarn add package-name@tag` instaluje określony ["tag"]({{url_base}}/docs/cli/tag) (np. `beta`, `next` lub `latest`).

Ogólnie rzecz biorąc, pakiet to po prostu folder zawierający kod oraz plik `package.json` opisujący zawartość. Możesz odwoływać się do pakietu na wiele różnych sposobów:

Możesz również określić pakiety pochodzące z różnych źródeł:

  1. `yarn add package-name` instaluje pakiet z [rejestru npm](https://www.npmjs.com/), chyba że określiłeś inny w pliku `package.json`.
  2. `yarn add file:/path/to/local/folder` instaluje pakiet z lokalnego systemu plików. Przydaje się do testowania innych pakietów, których jeszcze nie opublikowałeś w rejestrze.
  3. `yarn add file:/path/to/local/tarball.tgz` instaluje pakiet ze skompresowanego archiwum tar ("gzipped tarball"), który może być użyty do udostępnienia pakietu przed publikacją.
  4. `yarn add <git remote url>` instaluje pakiet ze zdalnego repozytorium gita.
  5. `yarn add <git remote url>#<commit/tag>` instaluje pakiet ze zdalnego repozytorium gita w określonej wersji commita lub tagu.
  6. `yarn add https://my-project.org/package.tgz` instaluje pakiet ze zdalnego, skompresowanego archiwum tar ("gzipped tarball").

### Caveats [](#toc-caveats){#toc-caveats.toc}

Jeśli używałeś już wcześniej menadżera pakietów takiego jak npm, być może chcesz się dowiedzieć jak zainstalować globalne zależności.

Dla zdecydowanej większości pakietów posiadanie globalnych zależności jest uważane za złą praktykę, ponieważ są one ukryte. Znacznie lepszym sposobem jest dodawanie wszystkich zależności lokalnie, dzięki czemu są one jawne oraz inne osoby używające Twojego projektu otrzymają takie same zależności.

Jeśli chcesz użyć narzędzia CLI zawierającego pliki wykonywalne `bin`, możesz z nich skorzystać w katalogu `./node_modules/.bin`. Możesz również użyć komendy [`global`]({{url_base}}/docs/cli/global):

```sh
yarn global add <package...>
```

### Commands [](#toc-commands){#toc-commands.toc}

##### `yarn add <package...>` [](#toc-yarn-add){#toc-yarn-add.toc}

Instaluje jeden lub więcej pakietów w Twoich zależnościach [`dependencies`]({{url_base}}/docs/dependency-types#toc-dependencies).

##### `yarn add <package...> [--dev/-D]` [](#toc-yarn-add-dev-d){#toc-yarn-add-dev-d.toc}

`--dev` lub `-D` instaluje jeden lub więcej pakietów w Twoich zależnościach [`devDependencies`]({{url_base}}/docs/dependency-types#toc-dev-dependencies).

##### `yarn add <package...> [--peer/-P]` [](#toc-yarn-add-peer-p){#toc-yarn-add-peer-p.toc}

`--peer` lub `-P` instaluje jeden lub więcej pakietów w Twoich zależnościach [`peerDependencies`]({{url_base}}/docs/dependency-types#toc-peer-dependencies).

##### `yarn add <package...> [--optional,-O]` [](#toc-yarn-add-optional-o){#toc-yarn-add-optional-o.toc}

`--optional` lub `-O` instaluje jeden lub więcej pakietów w Twoich zależnościach [`optionalDependencies`]({{url_base}}/docs/dependency-types#toc-optional-dependencies).

##### `yarn add <package...> [--exact/-E]` [](#toc-yarn-add-exact-e){#toc-yarn-add-exact-e.toc}

`--exact` lub `-E` instaluje pakiety w ich dokładnych wersjach. Domyślnie instalowane jest najnowsze wydanie z tą samą wersją "major". Na przykład, `yarn add foo@1.2.3` przyjmie wersję `1.9.1`, lecz `yarn add foo@1.2.3 --exact` przyjmie jedynie wersję `1.2.3`.

##### `yarn add <package...> [--tilde/-T]` [](#toc-yarn-add-tilde-t){#toc-yarn-add-tilde-t.toc}

Using `--tilde` or `-T` installs the most recent release of the packages that have the same minor version. The default is to use the most recent release with the same major version. For example, `yarn add foo@1.2.3 --tilde` would accept `1.2.9` but not `1.3.0`.