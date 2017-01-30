Yarn jest już[zainstalowny wczesśniej na AppVeyor](https://www.appveyor.com/updates/2016/11/01/), więc nie ma potrzeby wykonywania żadnych dodatkowych kroków w celu wykorzystania go jako część kompilacji.

Aby przyspieszyć kompilacje, można buforować Yarn w folderze pamięci podręcznej przez dodanie tego skryptu do Twojego `appveyor.yml`:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```