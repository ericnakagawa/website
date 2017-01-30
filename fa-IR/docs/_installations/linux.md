### لینوکس دبیان/اوبونتو

در توزیع دبیان یا اوبونتو لینوکس، شما می‌توانید Yarn را از طریق مخزن دبیان آن نصب کنید. قبل از آن نیاز است پیکربندی زیر را انجام دهید:

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

بر روی اوبونتو ۱۴.۰۴ و دبیان پایدار، شما همچنین نیاز به نصب یک نسخه نسبتاً به‌روز [نود‌ جی‌اس](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) را دارید. (این مورد در دبیان نسخه آزمایشی و اوبونتو ۱۶.۰۴ نیاز نیست، لذا که این موارد به صورت پیش‌فرض با نود جی‌اس مناسبی ارائه می‌شوند)

سپس به سادگی می‌توانید:

```sh
sudo apt-get update && sudo apt-get install yarn
```

### لینوکس / فدورا / RHEL

در لینوکس فدورا و RHEL می‌توانید Yarn را از طریق مخزن RPM آن نصب کنید.

```sh
sudo wget https://dl.yarnpkg.com/rpm/yarn.repo -O /etc/yum.repos.d/yarn.repo
```

اگر در حال حاضر نود جی‌اس بر روی سیستم شما نصب نیست، شما همچنین باید [ مخزن NodeSource](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora) آن را پیکربندی کنید:

```sh
curl --silent --location https://rpm.nodesource.com/setup_6.x | bash -
```

سپس به سادگی می‌توانید:

```sh
sudo yum install yarn
```

### Arch لینوکس

بر روی توزیع آرچ لینوکس می‌توانید Yarn را از طریق **AUR** نصب کنید.

اگه از [دستورهای کمکی AUR](https://wiki.archlinux.org/index.php/AUR_helpers) مثل yaourt استفاده می‌کنید به سادگی می‌تونید دستور زیر را اجرا کنید تا Yarn نصب شود:

```sh
yaourt -S yarn
```

### Solus

اگر از Solus استفاده می‌کنید، می‌توانید Yarn را از طریق مخزن Solus نصب کنید.

```sh
sudo eopkg install yarn
```

### اضافه کردن Yarn به Path

{% include_relative _installations/unix_path_setup.md %}