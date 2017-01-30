Yarn [AppVeyor üzerinde önceden yüklenmiştir](https://www.appveyor.com/updates/2016/11/01/), bu yüzden yapınızın parçası olarak kullanmak için ekstra bir şey yapmanıza gerek yok.

Yapılarınızı hızlandırmak için Yarn'ın önbellek klasörünü alttaki komutu `appveyor.yml`'a ekleyerek önbelleğe alabilirsiniz:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```