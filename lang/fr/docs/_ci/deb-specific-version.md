Il est recommandé de bloquer Yarn dans une version spécifique, afin que tous vos builds utilisent la même version de Yarn, et vous pouvez tester les nouvelles versions de Yarn avant d'en changer. Vous pouvez le faire en ajoutant le numéro de version lors de l’appel `apt-get install` :

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1