Yarn est pré-installé sur [Semaphore](https://semaphoreci.com/) pour toutes les versions supportées de Node.js, et aucune action n'est requise de la part de l'utilisateur pour que le cache de Yarn fonctionne.

Pour être sûr que votre version locale de Yarn corresponde à celle de Semaphore, ajoutez les lignes ci-dessous à vos commandes d'installation, dans Project Settings.

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb http://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
# install-package est un outil qui met en cache les installations de APT sur Semaphore
# Définir une version pour le paquet est optionnel
install-package yarn=<version>
```