It is recommended that you lock in a specific version of Yarn, so that all your builds use the same version of Yarn, and you can test new Yarn releases before switching over. Je kunt dit doen door het versienummer toe te voegen aan de `apt-get install` commando:

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1