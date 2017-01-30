* * *

id: docs_cli_login guide: docs_cli layout: guide

* * *

{% include vars.html %}

<p class="lead">Grava o nome de usuário e e-mail do registro.</p>

##### `yarn login` [](#toc-yarn-login){#toc-yarn-login.toc}

Quando este comando é executado é pedido para você digitar o seu nome de usuário e e-mail do [registro npm](https://www.npmjs.com/). Ele **não** perguntará a sua senha. Mais tarde quando você executar um comando que precise de autenticação como [`yarn publish`]({{url_base}}/docs/cli/publish), você precisará digitar sua senha para continuar.

```sh
yarn login
```

```sh
yarn login vx.x.x
question npm username: meu-nome-de-usuario
question npm email: meu-usuario@exemplo.com.br
✨  Done in 6.03s.
```

Use [`yarn logout`]({{url_base}}/docs/cli/logout) para deletar nome de usuário e e-mail.