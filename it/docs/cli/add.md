* * *

id: docs_cli_add guide: docs_cli layout: guide description: docs_cli_add_description additional_reading_tags: ["dependencies"]

* * *

{% include vars.html %}

<p class="lead">Installa un pacchetto e tutte le sue dipendenze.</p>

### Aggiungere dipendenze [](#toc-adding-dependencies){#toc-adding-dependencies.toc}

Quando vuoi utilizzare un nuovo pacchetto, la prima cosa da fare è aggiungerlo alle dipendenze del progetto. Per farlo basta eseguire il comando `yarn add [package-name]` e questo sarà installato.

Inoltre verranno aggiornati i file `package.json` e `yarn.lock` affichè altri developer che lavorano al progetto riceveranno le stesse identiche dipendenze quando eseguono i comandi `yarn` oppure `yarn install`.

La maggior parte dei pacchetti sarà installata dal [registry npm](https://www.npmjs.com/) e saranno riferiti semplicemente attraverso il loro nome. Per esempio, `yarn add react` installerà il pacchetto [`react`](https://www.npmjs.com/package/react) dal registry di npm.

Puoi specificare la versione in uno dei seguenti modi:

  1. `yarn add package-name` installa l'ultima versione del pacchetto.
  2. `yarn add package-name@1.2.3` installa una versione specifica.
  3. `yarn add package-name@tag` installa un ["tag"]({{url_base}}/docs/cli/tag) specifico (esempio: `beta`, `next`, oppure `latest`).

In generale un pacchetto è semplicemente una cartella con dentro del codice e un file `package.json` che descrive il contenuto. Puoi fare riferimento a un pacchetto in una serie di modi diversi:

Puoi anche specificare pacchetti che provengono da fonti differenti:

  1. `yarn add package-name` installa un pacchetto dal [registry npm](https://www.npmjs.com/) a meno che non ne venga specificato uno diverso nel file `package.json`.
  2. `yarn add file:/path/to/local/folder` installa una pacchetto presente nel tuo file system locale. Utile per testare altri pacchetti che non sono ancora stati pubblicati nel registry.
  3. `yarn add file:/path/to/local/tarball.tgz` installa una pacchetto da un tarball compresso con gzip, che può essere utilizzato per condividere un pacchetto prima della pubblicazione.
  4. `yarn add <git remote url>` installa un pacchetto da un repository git remoto.
  5. `yarn add <git remote url>#<commit/tag>` installa un pacchetto da un repository git remoto ad un commit o tag specifico.
  6. `yarn add https://my-project.org/package.tgz` installa un pacchetto da un tarball (compresso con gzip) remoto.

### Avvertenze [](#toc-caveats){#toc-caveats.toc}

Se hai già utilizzato un gestore di pacchetti come npm, potresti chiederti come si installano dipendenze a livello globale.

Per la maggior parte dei pacchetti avere dipendenze globali è considerata una cattiva pratica, poiché queste rimangono implicite. È molto meglio installare le dipendenze a livello locale e renderle così esplicite, assicurando lo setto set di dipendenze a chiunque lavori sul progetto.

Se ti serve utilizzare un tool CLI che fornisce un `bin` eseguibile, puoi accederci nella cartella `./node_modules/.bin` locale al progetto. Altrimenti puoi utilizzare il comando [`global`]({{url_base}}/docs/cli/global):

```sh
yarn global add <package...>
```

### Comandi [](#toc-commands){#toc-commands.toc}

##### `yarn add <package...>` [](#toc-yarn-add){#toc-yarn-add.toc}

Installa uno o più pacchetti nelle [`dependencies`]({{url_base}}/docs/dependency-types#toc-dependencies).

##### `yarn add <package...> [--dev/-D]` [](#toc-yarn-add-dev-d){#toc-yarn-add-dev-d.toc}

`--dev` o `-D` installa uno o più pacchetti nelle [`devDependencies`]({{url_base}}/docs/dependency-types#toc-dev-dependencies) (dipendenze di sviluppo).

##### `yarn add <package...> [--peer/-P]` [](#toc-yarn-add-peer-p){#toc-yarn-add-peer-p.toc}

`--peer` o `-P` installa uno o più pacchetti nelle [`peerDependencies`]({{url_base}}/docs/dependency-types#toc-peer-dependencies) (dipendenze "alla pari").

##### `yarn add <package...> [--optional,-O]` [](#toc-yarn-add-optional-o){#toc-yarn-add-optional-o.toc}

`--optional` o `-O` installa uno o più pacchetti nelle [`optionalDependencies`]({{url_base}}/docs/dependency-types#toc-optional-dependencies) (dipendenze opzionali).

##### `yarn add <package...> [--exact/-E]` [](#toc-yarn-add-exact-e){#toc-yarn-add-exact-e.toc}

`--exact` o `-E` installa i pacchetti nelle versioni esatte. Di default installa la release più recente con la stessa versione major. Per esempio, `yarn add foo@1.2.3` accetta la versione `1.9.1`, ma `yarn add foo@1.2.3 --exact` accetta solo la `1.2.3`.

##### `yarn add <package...> [--tilde/-T]` [](#toc-yarn-add-tilde-t){#toc-yarn-add-tilde-t.toc}

`--tilde` o `-T` installa la versione più recente dei pacchetti con la stessa versione minor. Di default installa la versione versione più recente con la stessa versione major. Per esempio, `yarn add foo@1.2.3 --tilde` accetta `1.2.9` ma non `1.3.0`.