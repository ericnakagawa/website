Yarn é [pré-instalado no AppVeyor](https://www.appveyor.com/updates/2016/11/01/), então você não precisa fazer nada extra para usá-lo como parte da sua build.

Para acelerar suas builds, você pode cachear a pasta de cache do Yarn adicionando isso ao seu `appveyor.yml`:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```