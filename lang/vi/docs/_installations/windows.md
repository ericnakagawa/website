### Windows

Có hai cách để cài đặt Yarn trên Windows.

#### Tải bộ cài đặt

Bạn sẽ cần tải về một tập tin `.msi`. Khi chạy, nó sẽ hướng dẫn bạn từng bước để cài đặt Yarn trên Windows.

Bạn cần phải cài [Node.js](https://nodejs.org/) trước khi sử dụng bộ cài đặt.<a class="btn btn-primary" href="/latest.msi">Tải bộ cài đặt</a>#### Cài đặt qua Chocolatey

[Chocolatey](https://chocolatey.org/) là trình quản lý gói phần mềm trên Windows, bạn có thể cài đặt Chocolatey theo [hướng dẫn này](https://chocolatey.org/install).

Khi đã cài đặt xong Chocolatey, bạn có thể cài yarn bằng cách chạy dòng lệnh sau:

```sh
choco install yarn
```

Với cách này bạn cũng cần chắc rằng mình đã cài [Node.js](https://nodejs.org/).

#### Chú ý

Vui lòng để thư mục dự án và thư mục cache của Yarn (%LocalAppData%\Yarn) vào danh sách trắng của phần mềm chống virus của bạn, nếu không việc cài đặt các gói sẽ chậm đi đáng kể vì mỗi tập tin sẽ bị quét khi nó được ghi vào đĩa.