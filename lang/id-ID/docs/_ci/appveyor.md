Yarn [telah terpasang di AppVeyor](https://www.appveyor.com/updates/2016/11/01/), sehingga Anda tidak perlu melakukan apapun untuk dapat menggunakan Yarn di build step anda.

Untuk mempercepat waktu build, anda dapat melakukan cache (tembolok) untuk paket yang telah diinstal Yarn dengan menambahkan perintah berikut kedalam file `appveyor.yml` proyek anda:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```