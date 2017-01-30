É recomendado que você trave o Yarn em uma versão específica, assim todas as suas builds usarão a mesma versão do Yarn, e você poderá testar novas versões do Yarn antes de trocar. Você pode fazer isso adicionando o número da versão à chamada do `apt-get install`:

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1