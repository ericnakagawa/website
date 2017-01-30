#### نصب از طریق shell script

یکی از ساده‌ترین راه‌ها برای نصب Yarn بر روی محیط‌های یونیکسی (از جمله لینوکس و macOS) استفاده از shell script ما می‌باشد. می‌توانید به سادگی Yarn را با اجرای کد زیر در ترمینال خود نصب کنید:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

روند نصب شامل تایید یک GPG signature می‌باشد. [سورس اسکریپت را در گیت‌هاب ببینید.](https://github.com/yarnpkg/website/blob/master/install.sh)

شما همچنین می‌توانید نسخه‌ی مورد نظر خود را با اجرای کد زیر در ترمینال مشخص کنید:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

امکان نصب [این نسخه‌ها](https://github.com/yarnpkg/yarn/releases) وجود دارد.

#### نصب دستی با استفاده از فایل فشرده tarball

همچنین می‌توانید Yarn را با [دانلود فایل فشرده ]({{site.baseurl}}/latest.tar.gz) و استخراج آن در هر مسیری نصب کنید.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn is now in /opt/yarn-[version]/
```