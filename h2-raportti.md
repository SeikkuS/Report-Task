h2 komentaja Pingviini

1. Aloitin lataamalla micron laittamalla terminaaliin: 

       $ curl https://getmic.ro | bash

2. Tämän jälkeen koitin katsoa raudan, mutta minulla ei ollut lshw asennettuna, joten ensin latasin sen.

       $ sudo apt-get install lshw
       $ sudo lshw -short -sanitize
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213909443-a8d0ead2-b005-4713-a4e2-1f7240b875de.png)
 
 3. Tässä listaus tietokoneeni osista. Pystytään selkeästi erottamaan tärkeimmät asiat, esim. mikä prosessori on käytössä ja paljonko muistia on käytössä. 

4. Päätin testiksi ladata kolme eri komentoriviohjelmaa samanaikaisesti (figlet, cmatrix, fortune). Alla komento, jolla helposti asensin kaikki 3, sekä kuva fortunen ja figletin demonstraatiosta.

       $ sudo apt install cmatrix fortune figlet
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213910111-12dc374f-09e6-427f-bc89-1676d76c285e.png)

5. Kävin läpi ja listasin sisällöt "Command line basics revisited"-sivun "important directories"-olevissa hakemistoista.

       cd / 
       ls -l
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213910298-63d7c22f-72b3-47e2-82e4-8e10323ca04d.png)
       
       cd /home/
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213910362-b54fa03e-298e-4900-9d93-106029127664.png)
 
       cd /home/seikku 
       tai
       cd ~
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213910425-5a164334-3ce1-4ea2-b3b8-ce610154aa2c.png)
 
      cd /etc/
      ls -a
      
 ![kuva](https://user-images.githubusercontent.com/105205141/213910571-d3c34ce5-6e95-431d-a631-b95e8c18e27d.png)
 
       cd /media/
       ls -l
       cd seikku
       ls -l
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213910615-1d950b76-be67-4d53-b60c-9681b7c36df0.png)
 
       
       cd /var/log/
       ls -a
       
 ![kuva](https://user-images.githubusercontent.com/105205141/213910671-b6a2306f-8203-401f-9fdc-4744eecd2730.png)
 
 6. Kokeilin grep komentoja /var/log/ hakemiston log-tiedostoihin, ja sain vastaukseksi "permission denied", kokeilin sitten toisesta hakemistosta: 

        cd /etc/
        ls 
        grep "10" passwd
        
 ![kuva](https://user-images.githubusercontent.com/105205141/213910829-f98be599-657c-4df1-9026-abfe414b721d.png)
 
 tässä komennossa etsitään tiedoston sisältä kaikki rivit, joissa on "10".
 
       grep -c "0" timezone
       
 tässä komennosssa lasketaan kuinka monta kertaa numero 0 esiintyy timezone -tiedostossa.
 
 ![kuva](https://user-images.githubusercontent.com/105205141/213927765-7076c140-1139-4e2d-99d7-8398464eb426.png)
 
       
       grep -l "0" *
       
  tässä komennossa listataan kaikki kyseisen hakemiston tiedostot, jotka sisältävät "0". 
  
  ![kuva](https://user-images.githubusercontent.com/105205141/213927996-587601b6-9ed3-4f43-8df4-8cf502ce2ce9.png)






