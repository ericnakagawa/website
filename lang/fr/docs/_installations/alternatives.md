### Alternatives

Si vous utilisez un autre OS ou une des autres options spécifiques à votre système d’exploitation ne fonctionne pas pour vous, il y a quelques solutions de rechange. Vous devrez [installer Node.js](https://nodejs.org/) si vous ne l’avez pas déjà installé.

Sur les distributions Linux communes telles que Debian, Ubuntu et CentOS, il est recommandé d’installer Yarn par l’intermédiaire de nos packages à la place.

{% include_relative _installations/tarball.md %}

#### Installer via npm

> **Remarque :** L'installation via npm n’est généralement pas recommandée. npm est non déterministe, les paquets ne sont pas signés et npm n’effectue pas de contrôles d’intégrité autre qu’un hachage SHA1 basique, ce qui représente un risque de sécurité lors de l’installation d'applications sur l'ensemble du système.
> 
> Pour ces raisons, il est fortement recommandé que vous installez Yarn par la méthode d’installation la mieux adaptée à votre système d’exploitation.

Vous pouvez également installer Yarn via le [gestionnaire de paquets npm](http://npmjs.org/), si vous l'avez déjà installé sur votre système. Si vous avez déjà [Node.js](https://nodejs.org/) installé alors npm sera déjà installé.

Une fois que vous avez npm installé, vous pouvez exécuter :

```sh
npm install --global yarn
```

### Configuration du chemin d’accès

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}