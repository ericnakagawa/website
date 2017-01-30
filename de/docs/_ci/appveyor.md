Yarn ist [auf AppVeyor vorinstalliert](https://www.appveyor.com/updates/2016/11/01/), Sie müssen also nichts weiter tun, um es in Ihrem Build zu nutzen.

Um Builds zu beschleunigen, können Sie den Yarn-Cache-Ordner cachen, indem Sie dies Ihrer `appveyor.yml` hinzufügen:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```