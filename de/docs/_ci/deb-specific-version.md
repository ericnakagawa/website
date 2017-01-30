Es wird empfohlen, dass sie eine konkrete Version von Yarn verwenden, damit alle ihre "Builds" die gleiche Version von Yarn verwenden. Dadurch können sie neue Yarn Funktionalitäten testen bevor sie zu einer neuen Version wechseln. Dies wird erreicht, indem sie die Versionsnummer dem `apt-get install` Befehl hinzufügen:

    sudo apt-get install -y -qq yarn={{site.latest_version}}-1