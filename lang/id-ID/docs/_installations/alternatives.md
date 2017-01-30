### Alternatif

Jika anda menggunakan sistem operasi (OS) lain, atau salah satu dari opsi yang sesuai dengan OS anda tidak bisa anda gunakan, ada beberapa alternatif. Anda harus [menginstal Node.js](https://nodejs.org/) terlebih dahulu jika belum.

Pada distribusi Linux yang umum seperti Debian, Ubuntu dan CentOS, disarankan untuk menginstal yarn melalui package manager dari masing-masing sistem operasi tersebut.

{% include_relative _installations/tarball.md %}

#### Instalasi melalui npm

> **Catatan:** Instalasi melalui npm tidak direkomendasikan. npm tidak deterministik, package-packagenya tidak ditandai, dan npm tidak melakukan cek integritas apapun selain SHA1 hash dasar, yang merupakan resiko keamanan ketika melakukan instalasi aplikasi pada sistem yang besar.
> 
> Karena alasan-alasan tersebut, sangat disarankan untuk menginstal Yarn melalui metode instalasi yang sesuai dengan sistem operasi anda.

Anda juga dapat menginstal Yarn melalui [npm package manager](http://npmjs.org/) jika anda sudah menginstalnya sebelumnya. Jika anda sudah menginstal [Node.js](https://nodejs.org/) maka anda sudah mempunyai npm.

Setelah npm terinstal, anda dapat menjalankan:

```sh
npm install --global yarn
```

### Persiapan Path

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}