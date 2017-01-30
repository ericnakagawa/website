#### Script cài đặt

Một trong những cách dễ nhất để cài Yarn trên macOS và môi trường Unix nói chung là thông qua shell script. Bạn có thể cài Yarn bằng cách chạy đoạn code sau trong terminal:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

Quá trình cài đặt bao gồm xác nhận chữ ký GPG. [Xem mã nguồn trên GitHub](https://github.com/yarnpkg/website/blob/master/install.sh)

Bạn cũng có thể chỉ định một phiên bản bằng cách chạy đoạn code sau trong terminal của bạn:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

Xem [các bản phát hành](https://github.com/yarnpkg/yarn/releases) cho các phiên bản có thể.

#### Cài đặt thủ công qua tarball

Bạn có thể cài Yarn bằng cách [tải về một tập tarball]({{site.baseurl}}/latest.tar.gz) và giải nén nó ở bất cứ đâu.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn is now in /opt/yarn-[version]/
```