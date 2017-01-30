* * *

id: docs_cli_install guide: docs_cli layout: guide

* * *

{% include vars.html %}

`yarn install` este utilizat pentru a instala toate dependenţele unui proiect. Acesă comandă este cel mai frecvent utilizată atunci când tocmai ai descărcat codul pentru un proiect, sau când un alt programator la proiect a adăugat o dependenţă nouă pe care trebuie să o descarci.

Dacă ești obișnuit cu folosirea npm probabil te aștepți să folosești `--save` sau `--save-dev`. Acestea au fost înlocuite de `yarn add` şi `yarn add --dev`. Pentru mai multe informaţii, vezi [documentaţia pentru `yarn add`]({{url_base}}/docs/cli/add).

Executând `yarn` fără nici o comandă este echivalent cu a executa `yarn install`, cu parametri deja furnizați.

##### `yarn install` [](#toc-yarn-install){#toc-yarn-install.toc}

Instalează toate dependenţele enumerate în fișierul `package.json` în folderul local `node_modules`.

##### `yarn install --flat` [](#toc-yarn-install-flat){#toc-yarn-install-flat.toc}

Permite doar o versiune a unui pachet. La prima executare vei avea opțiunea să alegi o singură versiune pentru fiecare pachet care este dependență în multiple intervale de versiune. Aceste alegeri vor fi adăugate în fișierul `package.json` sub un câmp numit `resolutions`.

```json
"resolutions": {
  "package-a": "2.0.0",
  "package-b": "5.0.0",
  "package-c": "1.5.2"
}
```

##### `yarn install --force` [](#toc-yarn-install-force){#toc-yarn-install-force.toc}

Această comandă instalează toate dependențele, indiferent dacă unele dintre ele au fost instalate anterior.

##### `yarn install --har` [](#toc-yarn-install-har){#toc-yarn-install-har.toc}

Afișează o [arhivă HTTP](https://en.wikipedia.org/wiki/.har) formată din toate conexiunile de rețea efectuate în timpul instalării. Fişierele HAR sunt frecvent utilizate pentru a investiga performanţele reţelei, şi pot fi analizate cu aplicații precum [Google HAR Analyzer](https://toolbox.googleapps.com/apps/har_analyzer/) sau [HAR Viewer](http://www.softwareishard.com/blog/har-viewer/).

##### `yarn install --no-lockfile` [](#toc-yarn-install-no-lockfile){#toc-yarn-install-no-lockfile.toc}

Nu citi sau genera un lockfile `yarn.lock`.

##### `yarn install --production` [](#toc-yarn-install-production){#toc-yarn-install-production.toc}

Folosind parametrul `--production`, sau atunci când variabila de mediu `NODE_ENV` este `production`, Yarn nu va instala nici un pachet enumerat în `devDependencies`.

> **Notă:** `--prod` este de asemenea un alias pentru `--production`.

##### `yarn install --pure-lockfile` [](#toc-yarn-install-pure-lockfile){#toc-yarn-install-pure-lockfile.toc}

Nu genera un lockfile `yarn.lock`.