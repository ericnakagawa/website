Yarn به صورت پیش فرض بر روی AppVeyor نصب می‌باشد<0> و شما جهت استفاده از آن به عنوان بخشی از پروژه ساخت خود به انجا کار اضافی نیازی ندارید.</p> 

To speed up your builds, you can cache Yarn's cache folder by adding this to your `appveyor.yml`:

```yml
cache:
 - "%LOCALAPPDATA%\\Yarn"
```