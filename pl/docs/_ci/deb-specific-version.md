Zaleca się, aby zablokować określoną wersję Yarn, tak aby wszystkie wersje używały tej samej wersji Yarn, a Ty możesz przetestować nowe wersje Yarn przed zmienieniem jej z tą starszą. Można to zrobić przez dodanie numeru wersji do komendy `apt-get install`:

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1