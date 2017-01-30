Sur [Codeship](https://codeship.com/), vous pouvez installer Yarn avec une étape de votre build en ajoutant ceci à vos *Setup Commands* dans les paramètres de votre projet :

```sh
npm install --global yarn
```

Si vous utilisez la [plateforme Docker](https://pages.codeship.com/docker) de Codeship , il est recommandé à la place d’installer Yarn via [notre paquet Debian/Ubuntu](https://yarnpkg.com/en/docs/install#linux).