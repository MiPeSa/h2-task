# h2 Tehtävä

## A)

Micro-editorin asennettu versio.

![Add file: Micro version](micro-version.png)

## B)

Syötin komentokehotteeseen 

        $ sudo lshw -short -sanitize.
        
komento johti "sudo: lshw: command not found".
     
Asensin lshw:n 
     
        $ sudo lshw apt-get -y install lshw
     
Suoritin aikaisemman komennon asennuksen jälkeen uudelleen, joilloin komentokehotteeseen tuli seuraava lista.

![Add file: sudo lshw -short -sanitize command](lshw-command.png)

Komento lshw eli (List hardware), raportoi minulle listan järjestelmän eri laitteistokomponenteista. Listan informaatio on jaoteltu taulukkoon, jossa informaatio on jaoteltu rivittäin 4 otsikon alle, jotka ovat HardWare path/Device/Class/Description. Taulukon tiedoista löytyy esimerkiksi tietoja virtuaalikoneen sekä läppärini muistista, läppärini prosessorista sekä sen nopeudesta, koneen emolevystä, virtuaalikoneen laiteohjelmistosta, jne. Ilman "-short" ja "-sanitize" komentoa lshw listasi laitteistokomponenttien tiedot paljon laajemmin, sisältäen myös arkaluonteisia tietoja komponenteista. Ilmeisesti "-short" järjestää raportin käytännölliseen taulukkoon ja "-sanitize" jättää pois arkaluonteisen datan.

## c) 

Etsin verkosta erilaisia mielenkiintoisia komentoriviohjelmia. Valitsin seuraavat ohjelmat:

### Wikit

Wikit komentoriviohjelmalla pystyy hakemaan wikipediasta tietoja Linuxin komentokehotteessa. Wikit:n asennusta, sekä toimimista varten piti asentaa myös nodejs sekä npm. Asensin ne, jonka jälkeen asensin Wikit:n.

        $ sudo apt-get -y install nodejs npm
        $ sudo apt-get -y install wikit

Hakeminen komentokehotteessa tapahtuu lisäämällä wikit alkuun, jonka jälkeen laitetaan hakusana, esimerkiksi näin:
        $ wikit Linux

![Add file: Wikit](wikit.png)

### CMatrix

CMatrix komentoriviohjelma vaikutti hauskalta, joten päätin testata sitä. Asensin sen komennolla:
        $ sudo apt-get -y install cmatrix
Asennuksen jälkeen katsoin mitä CMatrixilla voi tehdä syöttämällä komennon 
        $ cmatrix -help
Komentokehotteeseen avautui lista toiminnoista.

![Add file: CMatrix](cmatrix-list.png)

Päätin kokeilla "cmatrix -r" eli rainbow mode. Alla ruutukaappaus, komentokehotteesta komennon jälkeen. Komento avasi "The Matrix" animaation.

!Add file: CMatrix list](cmatrix.png)

### Figlet
        $ sudo apt-get -y install figlet

Kolmantena ohjelmana asensin Figlet:n. Figlet on komentoriviohjelma, joka muuttaa käyttäjän syöttämät tiedot ASCII-bannereiksi. 

Figlet toimii komentokehotteessa esimerkiksi syöttämällä komennon:

        $ figlet "Hello World"

![Add file: Figlet](figlet.png)

## D)

Verkkosivulla https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited.(Karvinen Tero, 2020-02-03) kappaleessa "Important directories" on esiteltynä tärkeitä kansioita.

### /

/ eli root(juurihakemisto) on koko tiedostojärjestelmän ylin osa. Root sisältää tiedostojärjestelmän kaikki hakemistot. / (root) hakemisto sisältää esimerkiksi /usr kansion, joka sisältää käyttäjiin liittyvät ohjelmat.

![Add file: usr](usr-directories.png)

## /home/

/home/ kansio sisältää kaikkien käyttäjien kotihakemistot. Virtuaalikoneessani on vain yksi eli oma käyttäjäni, hakemisto vie minut oman käyttäjäni kotihakemistoon.

![Add file: home](home-directory.png)

## /home/miikkas

/home/miikkas on käyttäjäni kotihakemisto. Tämä hakemisto on ainoa paikka, jossa nimenomaan käyttäjälläni "miikkas" voi tallentaa tietoja pysyvästi.
Hakemistosta löytyy esimerkiksi käyttäjäni tiedostot(Documents).

![Add file: home user](home-user-directory.png)

## /etc/

/etc/ kansio sisältää kaikki järjestelmän asetukset. Asetukset ovat luettavissa tekstitiedostoina. /etc/ löytyy root hakemiston alta, sillä sen edessä on vain / eli root hakemiston merkki. Avasin esimerkiksi /etc/ hakemistosta "os-release" tiedoston.

![Add file: etc](etc-os-release.png)

## /media/

/media/ sisältää poistettavissa olevat mediat. /media kansiossa oli vain oman käyttäjäni kansio, joka oli tyhjä, mutta media kansiossa voisi olla esimerkiksi usb muistitikun mediat.

![Add file: media](media.png)

## /var/log/

/var/log/ hakemistosta löytyvät koko järjestelmän lokit. Avasin esimerkiksi lokeista boot lokin syöttämällä komennon " $ sudo cat boot.log". Lokista näkee mitä bootin aikana on tapahtunut. 

![Add file: boot log](boot-log.png)

## History

Tässä historiaa komentokehotteessa suorittamistani komennoista

![Add file: history 1](history-1.png)
![Add file: history 2](history-2.png)

## E)

grep komento etsii annetusta tiedostosta rivejä, jotka sisältävät osuman annetuihin hakusanoihin tai merkkeihin. 

Esimerkkejä:

Ensimmäisessä esimerkissä etsin grep komennon avulla /etc/passwd tiedostoa käyttäjälleni "miikkas"

Komento:
        $ grep miikkas /etc/passwd

![Add file: grem esimerkki 1](esim-grep-1.png)

Tässä etsin grep komennolla /etc/ hakemistosta kaikista tiedostoista merkkijonoa "192.168.1.50"
Komento:
        $ sudo grep -r "192.168.1.50" /etc/
        
![Add file: grem esimerkki 2](esim-grep-2.png)

## Lähteet

Karvinen Tero, 2020-02-03, Luettavissa(https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited).
