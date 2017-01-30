### Windows

Il y a deux options pour l’installation de Yarn sous Windows.

#### Télécharger l'installateur

Cela vous donnera un fichier `.msi` qui vous guidera dans l’installation de Yarn sous Windows, lorsque vous l'exécuterez.

Si vous utilisez le programme d’installation, vous devrez d’abord installer [Node.js](https://nodejs.org/).<a class="btn btn-primary" href="/latest.msi">Télécharger l'installateur</a>#### Installer via Chocolatey

[Chocolatey](https://chocolatey.org/) est un gestionnaire de package pour Windows, vous pouvez installer Chocolatey en suivant [ces instructions](https://chocolatey.org/install).

Une fois que vous avez Chocolatey installé, vous pouvez installer yarn en exécutant le code suivant dans votre console :

```sh
choco install yarn
```

Cela garantit également que [Node.js](https://nodejs.org/) soit installé.

#### Note

Veuillez ajouter le répertoire de votre projet et le répertoire du cache de Yarn (%LocalAppData%\Yarn) dans la liste blanche de votre logiciel antivirus, sinon l'installation des packages seront significativement plus lents car chaque fichier sera analysé lorsqu'il est écrit sur le disque.