# h2 Tehtävä


    x) Lue ja tiivistä (Muutama ranskalainen viiva riittää. Tässä alakohdassa ei tarvitse tehdä testejä tietokoneella)
        Karvinen 2020: Command line basics revisited (nämä komennot ja hakemistot kannattaa myös opiskella ulkoa ja harjoitella automaatiotasolle)
    a) Micro. Asenna micro-editori
    b) Rauta. Listaa testaamasi koneen rauta (‘sudo lshw -short -sanitize’). Asenna lshw tarvittaessa. Selitä ja analysoi listaus.
    c) Apt. Asenna kolme itsellesi uutta komentoriviohjelmaa. Kokeile kutakin ohjelmaa sen pääasiallisessa käyttötarkoituksessa. Ota ruutukaappaus. Kaikki terminaaliohjelmat kelpaavat, TUI (text user interface) ja CLI (command line interface). Osaatko tehdä apt-get komennon, joka asentaa nämä kolme ohjelmaa kerralla?
    d) FHS. Esittele kansiot, jotka on listattu "Command Line Basics Revisited" kappaleessa "Important directories". Näytä kuvaava esimerkki kunkin tärkeän kansion sisältämästä tiedostosta tai kansiosta. Jos kyseessä on tiedosto, näytä siitä kuvaava esimerkkirivi. Työskentele komentokehotteessa ja näytä komennot, joilla etsit esimerkit.
    e) The Friendly M. Näytä 2-3 kuvaavaa esimerkkiä grep-komennon käytöstä. Ohjeita löytyy 'man grep' ja tietysti verkosta.

- a) Micro-editorin asennettu versio.

![Add file: Micro version](micro-version.png)

- b) Syötin komentokehotteeseen 

        $ sudo lshw -short -sanitize.
        
     komento johti "sudo: lshw: command not found".
     
     Asensin lshw:n 
     
        $ sudo lshw apt-get -y install lshw
     
     Suoritin aikaisemman komennon asennuksen jälkeen uudelleen, joilloin komentokehotteeseen tuli seuraava lista.

![Add file: sudo lshw -short -sanitize command](lshw-command.png)

Komento lshw eli (List hardware), raportoi minulle listan järjestelmän eri laitteistokomponenteista. Listan informaatio on jaoteltu taulukkoon, jossa informaatio on jaoteltu rivittäin 4 otsikon alle, jotka ovat HardWare path/Device/Class/Description. Taulukon tiedoista löytyy esimerkiksi tietoja virtuaalikoneen sekä läppärini muistista, läppärini prosessorista sekä sen nopeudesta, koneen emolevystä, virtuaalikoneen laiteohjelmistosta, jne. Ilman "-short" ja "-sanitize" komentoa lshw listasi laitteistokomponenttien tiedot paljon laajemmin, sisältäen myös arkaluonteisia tietoja komponenteista. Ilmeisesti "-short" järjestää raportin käytännölliseen taulukkoon ja "-sanitize" jättää pois arkaluonteisen datan.

- c) Etsin verkosta erilaisia mielenkiintoisia komentoriviohjelmia. Valitsin seuraavat ohjelmat:

## Wikit

Wikit komentoriviohjelmalla pystyy hakemaan wikipediasta tietoja Linuxin komentokehotteessa. Wikit:n asennusta, sekä toimimista varten piti asentaa myös nodejs sekä npm. Asensin ne, jonka jälkeen asensin Wikit:n.

        $ sudo apt-get -y install nodejs npm
        $ sudo apt-get -y install wikit

Hakeminen komentokehotteessa tapahtuu lisäämällä wikit alkuun, jonka jälkeen laitetaan hakusana, esimerkiksi näin:
        $ wikit Linux
lisää tähän kuva

## CMatrix

CMatrix komentoriviohjelma vaikutti hauskalta, joten päätin testata sitä. Asensin sen komennolla:
        $ sudo apt-get -y install cmatrix
Asennuksen jälkeen katsoin mitä CMatrixilla voi tehdä syöttämällä komennon 
        $ cmatrix -help
Komentokehotteeseen avautui lista toiminnoista.

lisää tähän kuva

Päätin kokeilla "cmatrix -r" eli rainbow mode.

lisää kuva

## Figlet
        $ sudo apt-get -y install figlet

Kolmantena ohjelmana asensin Figlet:n. Figlet on komentoriviohjelma, joka muuttaa käyttäjän syöttämät tiedot ASCII-bannereiksi. 

Figlet toimii komentokehotteessa esimerkiksi syöttämällä komennon:

        $ figlet "Hello World"
lisää kuva
