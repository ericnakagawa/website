Yarn est [pré-installé sur AppVeyor](https://www.appveyor.com/updates/2016/11/01/), donc vous n'avez rien à faire de plus pour l'utiliser dans vos builds.

Pour accélérer vos builds, vous pouvez mettre en cache le dossier de cache de Yarn, en ajoutant ceci à votre fichier `appveyor.yml` :

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```