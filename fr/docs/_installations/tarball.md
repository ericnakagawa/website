#### Installation Script

Une des façons les plus faciles d’installer Yarn sur macOS et les environnements Unix génériques est via notre script shell. Vous pouvez installer Yarn en exécutant le code suivant dans votre terminal :

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

Le processus d’installation inclut la vérification d’une signature GPG. [Voir la source sur GitHub](https://github.com/yarnpkg/website/blob/master/install.sh)

Vous pouvez également spécifier une version en exécutant le code suivant dans votre terminal :

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash -s -- --version [version]
```

Voir [les versions](https://github.com/yarnpkg/yarn/releases) possibles.

#### Installation manuelle via une archive tar

Vous pouvez installer Yarn en [téléchargeant une archive tar]({{site.baseurl}}/latest.tar.gz) et extraire n’importe où.

```sh
cd /opt
wget https://yarnpkg.com/latest.tar.gz
tar zvxf latest.tar.gz
# Yarn is now in /opt/yarn-[version]/
```