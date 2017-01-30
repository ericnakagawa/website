Yarn is [voorgeïnstalleerd op AppVeyor](https://www.appveyor.com/updates/2016/11/01/). Je hoeft verder niks te doen om Yarn te gebruiken in je build.

Om je builds sneller te maken, kun je Yarn's cache map cachen door dit toe te voegen aan je `appveyor.yml` bestand:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```