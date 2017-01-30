Se recomienda que mantenga una version especifica de Yarn, para que todos sus builds usen la misma version de Yarn, y para que pueda probar nuevas versiones de Yarn antes de hacer el cambio. You can do this by adding the version number to the `apt-get install` call:

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1