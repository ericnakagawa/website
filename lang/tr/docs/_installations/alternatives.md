### Alternatifler

Başka bir işletim sistemi kullanıyorsanız veya işletim sisteminiz için belirli diğer seçeneklerden biri sizin için çalışmazsa, alternatifler bir kaç seçenek vardır. Eğer Node.js yüklü değilse, onu [yüklemeniz](https://nodejs.org/) gerecektir.

Debian, Ubuntu ve CentOS gibi genel Linux dağıtımlarında Yarn'ı paketlerimizi kullanarak kurmanız tavsiye edilir.

{% include_relative _installations/tarball.md %}

#### Npm ile yüklemek

> **Not:** Npm aracılığıyla yükleme genellikle önerilmez. npm is non-determinstic, packages are not signed, and npm does not perform any integrity checks other than a basic SHA1 hash, which is a security risk when installing system-wide apps.
> 
> Bu nedenlerden dolayı işletim sisteminize uygun en iyi yükleme yöntemi aracılığıyla Yarn'ı yüklemenız önerilir.

Eğer [npm paket yöneticisi ](http://npmjs.org/) kurduysanız bunun üzerinden de Yarn'ı yükleyebilirsiniz. Eğer zaten [Node.js](https://nodejs.org/) yüklediyseniz npm de sisteminizde yüklüdür.

Npm yüklediğinizde kullanacağınız komut:

```sh
npm install --global yarn
```

### Yol Kurulurumu

#### Unix/Linux/macOS

{% include_relative _installations/unix_path_setup.md %}

#### Windows

{% include_relative _installations/windows_path_setup.md %}