#### Script instalasi

Salah satu cara tercepat untuk menginstal Yarn di macOS dan generic Unix environments adalah melalui shell script. Anda dapat menginstal Yarn dengan menjalankan code berikut pada terminal anda:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

Proses instalasi mencakup verifikasi tanda tangan GPG. [Lihat sumber pada GitHub](https://github.com/yarnpkg/website/blob/master/install.sh)

Anda juga dapat menentukan versi dengan menjalankan code berikut pada terminal:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

Lihat [rilis](https://github.com/yarnpkg/yarn/releases) untuk versi yang tersedia.

#### Instalasi manual melalui berkas

Anda dapat menginstal Yarn dengan [mengunduh tarball]({{site.baseurl}}/latest.tar.gz) dan mengekstraknya.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn is now in /opt/yarn-[version]/
```