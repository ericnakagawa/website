При использовании [Codeship](https://codeship.com/), вы можете установить Yarn как часть вашего процесса сборки путём добавления следующих строк в *Setup Commands* в настройках проекта:

```sh
npm install --global yarn
```

Если вы используете [Docker Platform](https://pages.codeship.com/docker), рекомендуется устанавливать Yarn через [наш Debian/Ubuntu пакет](https://yarnpkg.com/en/docs/install#linux).