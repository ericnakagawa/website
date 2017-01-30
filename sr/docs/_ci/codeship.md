На [Codeship](https://codeship.com/) Yarn можете инсталирати као дио ваше градње, ако у *Setup Commands* вашег пројекта додате:

```sh
npm install --global yarn
```

Умјесто тога, уколико користите Codeship [Docker платформу](https://pages.codeship.com/docker), препоручује се да Yarn инсталирате преко [нашег Debian/Ubuntu пакета](https://yarnpkg.com/en/docs/install#linux).