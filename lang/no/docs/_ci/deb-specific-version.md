Det anbefales at du låser en spesifikk versjon av Yarn, slik at alle bygg bruker den samme versjonen av Yarn. Da kan du teste nye utgivelser av Yarn før du bytter. You can do this by adding the version number to the `apt-get install` call:

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1