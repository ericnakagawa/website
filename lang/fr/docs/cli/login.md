* * *

id: docs_cli_login guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Enregistre les informations de connexions : nom d'utilisateur et adresse mail.</p>

##### `yarn login` [](#toc-yarn-login){#toc-yarn-login.toc}

L'éxecution de cette commande vous demanedra de renseigner votre nom d'utilisateur et adresse mail pour le [npm registry](https://www.npmjs.com/). Elle **ne** vous demandera pas votre mot de passe. Par la suite, lorsque vous exécuterez une commande nécessitant une authentification telle que [`yarn publish`]({{url_base}}/docs/cli/publish), vous pourrez saisir votre mot de passe.

```sh
yarn login
```

```sh
yarn login vx.x.x
question npm username: my-username
question npm email: my-username@example.com
✨  Done in 6.03s.
```

Vous pouvez supprimer le nom d'utilisateur et adresse mail enregistrés en utilisant la commande [`yarn logout`]({{url_base}}/docs/cli/logout).