Yarn è [ preinstallato su AppVeyor ](https://www.appveyor.com/updates/2016/11/01/), quindi non sarà necessario fare niente di extra per usarlo come parte delle tue build.

Per velocizzare le tue builds, puoi memorizzare in cache la cartella cache di Yarn aggiungendo questo al tuo `appveyor.yml`:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```