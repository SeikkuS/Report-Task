# Linux -virtuaalikoneen asennuksen raportti

Tein harjoituksen omalla tietokoneellani kotona 17.1. klo 17.00.

## VirtualBoxin asennus

Aloitin menemällä VirtualBoxin sivuille (https://www.virtualbox.org), siirryin downloads -osioon, josta latasin uusimman version (7.06) "windows hosts" painikkeesta. 
Asensin VirtualBoxin nettisivun tarjoamalla asennusohjelmalla.
Vaihdoin tiedostonsijaintia paikkaan, josta löydän hakemiston helpommin.
Muuten käytin asennusohjelman oletusasetuksia. 
Tämän jälkeen käynnistin sovelluksen ja painoin oikealta sinistä "New"-painiketta. 

## Debianin lataaminen ja asentaminen

Menin oppitunnilla näytetylle ohjesivulle (https://terokarvinen.com/2021/install-debian-on-virtualbox/), josta heti ensimmäisenä siirryin debianin sivuille (https://cdimage.debian.org/images/unofficial/non-free/images-including-firmware/current-live/amd64/iso-hybrid/). 
Sieltä minä latasin haluamani ISO version  (debian-live-11.6.0-amd64-xfce+nonfree.iso).
Ladattuani ISO:n siirsin sen toiseen hakemistoon helposti löydettävään paikkaan, jonka jälkeen VirtualBoxissa valitsin kyseisen tiedoston uudesta hakemistostaan.
Nimeksi annoin Debian-Linux ja päätin painaa "skip unattended" -painiketta toisella kurssilla mainitun ongelman takia (ilmeisesti joskus "skip unattended" antaa virheilmoituksia eikä onnistu asentamaan linuxia virtuaalikoneeseen oikein).
Tämän jälkeen annoin muistiksi tietokoneelle 6096 MB ja 2 suoritinydintä. 
Tallenustilaa virtuaalikoneelle annoin 60gb.
Painoin NEXT, jonka jälkeen tarkistin tiedot yhteenvedosta ja painoin "finish".
Asennuksen jälkeen suoritin uuden virtuaalikoneen valitsemalla sen virtualboxin valikossa ja painamalla oikeasta ylänurkasta löytyvää vihreätä nuolenmuotoista start-nappia.
Virtuaalikoneen käynnistyksessä se avasi Main Menu -valikon, josta valitsin ylimmän vaihtoehdon eli Debian GNU/Linux Live (kernel versio-amd64).
Asennuksen päätyttyä pääsin työpöydälle. Kokeilin että verkkoselain toimii, jonka jälkeen painoin Install Debian -painiketta työpöydältä. 
Asennusohjelma käynnistyi ja valitsin ensimmäiseksi sijaintini (Helsinki). 
Seuraavaksi valitsin näppäimistön kielen ja valitsin "Finnish" vasemmalta puolelta ja oikealta valitsin "Finnish(classic, no dead keys)".
Otin varmuuskopion oman tietokoneeni tiedoista pilveen ja painoin Partitions -osiosta Erase Disk ja boot loaderista Master Boot.
Tämän jälkeen loin käyttäjän, nimesin tietokoneen anonyymisti ja annoin salasanan. 
Tarkistin yhteenvedon ja painoin install.

## Päivitykset

Asennuksen päätytyyä sammutin virtuaalikoneen ja käynnistin uudelleen. Kirjauduin sisään antamillani tunnuksilla.
Avasin terminaalin tehtäväpalkin painikkeesta. kirjoitin:
    
    $ sudo apt-get update
    
tässä välissä syötin salasanan terminaaliin pyynnöstä.

    $ sudo apt-get -y dist-upgrade
    
Päätin myös seurata ohjeita ja asentaa palomuurin.

    $ sudo apt-get -y install ufw
    $ sudo ufw enable
    
Päätin myös korjata virtuaalikoneen resoluution painamalla virtualboxin ikkunan yläosasta "Devices" ja painamalla "Insert Guest Additions CD image..."
Työpöydälle latautui CD-tiedosto, avasin sen, oikealla hiiren painikkeella avasin valikon hakemistossa ja painoin "Open Terminal Here"
Terminaaliin kirjoitin: 

    $ cd /media/*/VBox*
    $ ls
    $ sudo bash VBoxLinuxAdditions.run
    
Tämän jälkeen reboottasin virtuaalikoneen ja kokeilin asioiden toimivuutta. Selain toimi, terminaali toimi, ja Bidirectional Clipboard toimi. (pystyin copy & pasteemaan omalta tietokoneelta virtuaalikoneelle).

## Lopputulos

Asennuksissa ei ilmennyt mitään ongelmia. En saanut virheilmoituksia ja debian on nyt asennettu kaikkine päivityksineen. 
